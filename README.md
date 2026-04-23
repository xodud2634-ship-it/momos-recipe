# MOMOS Recipe Manager

모모스 베이커리 레시피 & 배합 관리 시스템 — 직원 전용

---

## Netlify 배포 방법

1. netlify.com 회원가입
2. Add new site → Deploy manually
3. 이 폴더 드래그 앤 드롭 → 자동 배포
4. Site settings → Access control → Password protection → 비밀번호 설정

---

## Firebase 보안 규칙 (필수)

Firebase Console → Firestore Database → 규칙 탭에서 교체 후 게시:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}

---

## 비밀번호 변경

index.html 에서: const PW = 'momos2024';

---

## 기능
- 비밀번호 로그인 (직원 전용)
- 모바일/웹 모두 지원
- Firebase 동기화 (모든 기기 공유)
- Cloudinary 사진 저장 (모든 기기 공유)
- 배합 계산기 + 원가 계산
- 재료 추가/삭제 (삭제 확인)
- 카테고리 추가/수정/삭제
- 제품 카테고리 변경
- 공정 단계 관리
- 메모 / 즐겨찾기
- 인쇄 / 복사
