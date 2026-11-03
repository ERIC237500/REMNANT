# REMNANT 사이트 — GitHub Pages 설치 방법

이 버전은 **관리자 없이 누구나 올리고, 수정하고, 삭제할 수 있어요.**

## 1. Firebase 프로젝트 만들기 (무료)
1. https://console.firebase.google.com 에서 프로젝트 생성
2. **Build > Firestore Database** → 데이터베이스 만들기 (프로덕션 모드, 가까운 지역)
3. **Build > Authentication > 시작하기** → 로그인 방법에서 **익명** 사용 설정
4. 프로젝트 설정(톱니바퀴) > 내 앱 > **웹 앱(</>)** 추가 → 나오는 `firebaseConfig` 값 복사

## 2. 파일 수정
- `index.html` 위쪽의 `FIREBASE_CONFIG`에 복사한 값을 붙여넣기
- `firestore.rules` 내용을 Firestore > 규칙 탭에 붙여넣고 **게시**

## 3. GitHub에 올리기
1. 새 저장소(repository) 만들기 → `index.html` 업로드
2. Settings > Pages > Branch를 `main` / `(root)`로 설정 → 저장
3. 잠시 후 `https://아이디.github.io/저장소이름/` 으로 접속
4. Firebase > Authentication > 설정 > **승인된 도메인**에 `아이디.github.io` 추가

## 사용법
- 주소 끝에 `#songs`, `#word`, `#pray`를 붙이면 해당 사이트가 바로 열려요.

## 주의할 점
- 링크를 아는 누구나 모든 글을 수정·삭제할 수 있어요. 잘못 지워도 되돌릴 수 없으니, 필요하면 Firebase 콘솔에서 주기적으로 데이터를 내보내(백업) 두세요.
- 사진 자동 읽기(AI)는 없어요. 사진은 원본으로 첨부되고, 가사·코드는 직접 입력해요.
- 여러 장 한번에 올리기: 파일 이름이 같은 곡끼리(곡명-1.jpg, 곡명-2.jpg) 한 곡으로 묶이고, 제목은 파일 이름이 돼요.
- 사진은 Firestore에 저장돼요. 무료 한도를 넘지 않는지 가끔 확인하세요.
