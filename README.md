# REMNANT 사이트 — GitHub Pages 설치 방법

## 1. Firebase 프로젝트 만들기 (무료)
1. https://console.firebase.google.com 에서 프로젝트 생성
2. **Build > Firestore Database** → 데이터베이스 만들기 (프로덕션 모드, 가까운 지역)
3. **Build > Authentication > 시작하기** → 로그인 방법에서 **익명**과 **이메일/비밀번호** 둘 다 사용 설정
4. Authentication > 사용자 탭에서 **사용자 추가**: 관리자 이메일 + 비밀번호 입력 → 만들어진 사용자의 **UID** 복사
5. 프로젝트 설정(톱니바퀴) > 내 앱 > **웹 앱(</>)** 추가 → 나오는 `firebaseConfig` 값 복사

## 2. 파일 수정
- `index.html` 위쪽의 `FIREBASE_CONFIG`에 복사한 값을 붙여넣고, `ADMIN_EMAIL`에 관리자 이메일 입력
- `firestore.rules`의 `관리자UID`를 복사한 UID로 바꾼 뒤, Firestore > 규칙 탭에 붙여넣고 **게시**

## 3. GitHub에 올리기
1. 새 저장소(repository) 만들기 → `index.html` 업로드
2. Settings > Pages > Branch를 `main` / `(root)`로 설정 → 저장
3. 잠시 후 `https://아이디.github.io/저장소이름/` 으로 접속
4. Firebase > Authentication > 설정 > **승인된 도메인**에 `아이디.github.io` 추가

## 사용법
- 페이지 맨 아래 **🔒 관리자**를 눌러 비밀번호를 입력하면 관리자로 로그인돼요. 관리자만 삭제할 수 있어요.
- 주소 끝에 `#songs`, `#word`, `#pray`를 붙이면 해당 사이트가 바로 열려요.

## Claude 안에서 쓰던 버전과 다른 점
- **사진 자동 읽기(AI)는 빠졌어요.** 사진은 원본 그대로 첨부되고, 가사·코드는 직접 입력해요.
- 여러 장 한번에 올리기: 파일 이름이 같은 곡끼리(곡명-1.jpg, 곡명-2.jpg) 묶여요. 제목은 파일 이름이에요.
- 사진은 Firestore에 저장돼요(무료 한도 안에서 사용). 사용량이 많아지면 Firebase 사용량을 확인하세요.
- 삭제 권한은 규칙으로 서버에서 막혀요. 수정 권한(올린 사람·관리자)은 화면에서만 확인해요.
