# POLLUX Update Server

**이 저장소는 POLLUX 애플리케이션의 자동 업데이트 메타데이터를 제공합니다.**

## 📦 사용 가능한 애플리케이션

| 애플리케이션 | 환경 | 엔드포인트 | 상태 |
|-------------|------|-----------|------|
| POLLUX MARKDOWN | **Production** | [`/pollux-markdown/latest.json`](https://pollux-choh.github.io/pollux-update/pollux-markdown/latest.json) | 🟢 |
| POLLUX MARKDOWN | **Beta (Staging)** | [`/pollux-markdown-staging/latest.json`](https://pollux-choh.github.io/pollux-update/pollux-markdown-staging/latest.json) | 🟢 |

## 🔄 자동 업데이트 흐름

```
pollux-markdown 리포지토리
    │
    ├─ staging 브랜치 → Beta 빌드 → pollux-markdown-staging/
    │
    └─ main 브랜치 → Production 빌드 → pollux-markdown/
```

## 📁 디렉토리 구조

```
pollux-update/
├── pollux-markdown/           # Production 릴리즈
│   ├── latest.json
│   └── releases/
│       └── {version}/
│           ├── *.deb
│           ├── *.exe
│           └── *.sig
│
├── pollux-markdown-staging/   # Beta 릴리즈 (테스터용)
│   ├── latest.json
│   └── releases/
│       └── {version}-beta/
│           ├── *.deb
│           ├── *.exe
│           └── *.sig
│
└── README.md
```

## 🛡️ 보안

- 모든 릴리즈 파일은 **Tauri Signer**로 서명됨
- `.sig` 파일에 서명 정보 포함
- 앱이 업데이트 전 서명 검증 수행

## 🔗 GitHub Pages

- **Base URL**: https://pollux-choh.github.io/pollux-update/
- 이 저장소는 GitHub Pages를 통해 정적 파일을 제공합니다
- 자동 업데이트는 Tauri의 `tauri-plugin-updater`를 사용합니다

---

> 💡 **일반 사용자는 이 페이지에 직접 접근할 필요가 없습니다.**  
> 애플리케이션이 자동으로 업데이트를 확인합니다.
