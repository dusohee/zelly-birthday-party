# 🐹 Zelly 생파 프로젝트 노트

## 현재 구조

```
젤리생파/
├── zelly_party.html      ← ✅ v1 완성본 (정적, 바로 배포 가능)
├── three.min.js
├── images/               ← 햄스터 PNG 65장
│
├── realtime/             ← 🚧 v2 실시간 버전 (개발 예정)
│   ├── index.html        ← 스켈레톤 코드 (Firebase 연동 구조 잡혀있음)
│   ├── firebase-config.js← Firebase 설정 템플릿
│   └── three.min.js
│
└── NOTES.md              ← 이 파일
```

---

## v1 → v2 확장 계획

### 핵심 아이디어
누군가 URL에 접속하면 인스타 아이디를 입력하고,
본인의 햄스터가 3D 파티장에 실시간으로 뿅! 하고 등장.
모든 접속자 화면에 동시에 보임.

### 구현 단계
- [ ] Firebase 프로젝트 생성 (firebase-config.js 채우기)
- [ ] realtime/index.html 에 v1 씬 코드 붙여넣기
- [ ] addHamsterSprite() / removeHamsterSprite() 함수 구현
- [ ] 입장 애니메이션 (아래서 뿅! 올라오는 효과)
- [ ] 퇴장 처리 (탭 닫으면 자동 제거 - onDisconnect 이미 준비됨)
- [ ] 도메인 연결 (dusohee.com 또는 서브도메인)

### 나중에 추가하면 좋을 것들
- 입장할 때 이름 뱃지 달린 햄스터가 튀어나오는 연출
- 실시간 채팅 or 이모지 반응 (🎉 💕 🐹)
- 방명록 (파티 끝난 뒤에도 메시지 남기기)
- 생일 주인공(Zelly) 클릭하면 특별 효과

---

## 서비스 비교 (무료 한도)

| 서비스 | 동시접속 | 저장소 | 추천 이유 |
|--------|---------|--------|----------|
| **Firebase** ⭐ | 100명 | 1GB | 무료 넉넉, 한국 자료 많음 |
| Supabase | 제한없음 | 500MB | 오픈소스, SQL 친화적 |
| Pusher | 200명 | - | 실시간 특화, 메시지 20만/일 |

→ 생파 용도엔 Firebase 무료 플랜으로 충분. 신용카드 불필요.

---

## Firebase 시작하기

1. https://console.firebase.google.com
2. 새 프로젝트 → 프로젝트 이름: `zelly-party`
3. 빌드 → Realtime Database → 테스트 모드로 시작
4. 프로젝트 설정 → 웹 앱 추가 → 설정값 복사
5. `realtime/firebase-config.js` 에 붙여넣기
6. 완료!
