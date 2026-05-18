RE:제로 전시회 Firebase 공용 방명록용 세트

구성
- index.html: Firebase 공용 방명록/답글/작성중 표시 버전
- images/: 전시 사진 폴더

사용법
1. Firebase Console에서 프로젝트를 만듭니다.
2. Firestore Database를 만듭니다.
3. Firebase 웹 앱을 추가하고 firebaseConfig를 복사합니다.
4. index.html을 메모장으로 열고 const firebaseConfig = {...} 부분의 PASTE_YOUR... 값을 전부 교체합니다.
5. Firestore Rules에 아래 규칙을 넣고 Publish합니다.

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /re_zero_public_guestbook_v3/{document} {
      allow read, write: if true;
    }
  }
}

6. GitHub Pages 저장소에는 이 폴더 안의 내용물(index.html, images 폴더, README 등)을 루트에 업로드합니다.
   바깥 폴더 자체를 올리지 말고, 폴더 안 내용물을 올리세요.

주의
- firebaseConfig를 넣기 전에는 공용 방명록이 아니라 각자 기기 저장/local fallback처럼 동작할 수 있습니다.
- Rules를 열지 않으면 친구들이 글을 못 쓸 수 있습니다.
- 공개 Rules는 친구끼리 노는 전시회용입니다. 링크를 아는 사람은 누구나 쓸 수 있습니다.
