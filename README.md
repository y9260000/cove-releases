# Cove

<p align="center"><b>my little notch cove</b><br>맥 노치에 음악 · 가사 · 일정 · 알림까지</p>

## 다운로드

👉 **[최신 버전 받기 (Cove.dmg)](https://github.com/y9260000/cove-releases/releases/latest)**

요구사항: **macOS 14.4 이상, Apple Silicon**

## 설치

1. `Cove.dmg`를 열고 **Cove를 Applications 폴더로 드래그**
2. Cove를 실행하면 "확인되지 않은 개발자" 경고가 떠요 — 아직 애플 공증 서명이 없어서 그래요. 아래 한 가지 방법으로 열 수 있어요:
   - **시스템 설정 → 개인정보 보호 및 보안** 맨 아래 → **"그래도 열기"** 클릭
   - 또는 터미널에서: `xattr -cr /Applications/Cove.app`
3. 처음 실행하면 **캘린더 접근** 권한을 물어봐요 (일정 표시용, 선택)
4. 메뉴바의 노치 아이콘 → 설정에서 **로그인 시 자동 시작**을 켜두면 항상 상주해요

## 주요 기능

- 🎵 **지금 재생 중** — 유튜브 뮤직, Spotify, 사파리 등 모든 미디어를 노치에. 앨범아트 · 시크 슬라이더 · 앨범색 이퀄라이저
- 📝 **싱크 가사** — 노래방처럼 따라오는 가사 (LRCLIB), 노치 아래 플로팅 바
- 📅 **캘린더** — 다음 일정 표시 + 임박 알림 배너 (구글 캘린더는 맥 캘린더에 계정 연결로 연동)
- 🔊 **HUD** — 볼륨/밝기/에어팟 연결/충전을 다이나믹 아일랜드 스타일로
- 🤖 **Claude Code 알림** — 작업 완료 시 노치 배너 + 세션 잔량 표시
- 👀 **Cove 캐릭터** — 음악이 없을 땐 노치 옆에서 눈만 빼꼼 (CPU 따라 깜빡임)

### Claude Code 연동 (선택)

`~/.claude/settings.json`에 Stop 훅을 추가하면 Claude가 응답을 마칠 때마다 노치에 알림이 떠요:

```json
{
  "hooks": {
    "Stop": [{ "hooks": [{ "type": "command", "command": "/Applications/Cove.app/Contents/MacOS/Cove notify \"답변 완료\" 2>/dev/null || true", "timeout": 10 }] }]
  }
}
```

아무 스크립트에서나 쓸 수도 있어요: `/Applications/Cove.app/Contents/MacOS/Cove notify "빌드 끝!"`

---

문의/버그: [Issues](https://github.com/y9260000/cove-releases/issues)
