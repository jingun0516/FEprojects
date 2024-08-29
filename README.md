# 메인 화면
![image](https://github.com/user-attachments/assets/22d32e66-16ba-4dc0-a80e-4b0d83f81dad)

# 개발 환경 및 배포 URL
  IDE
    IntelliJ
  배포 환경
    github pages
  
  URL: https://jingun0516.github.io/FEProjects/

# 프로젝트 개요
고양이 '호두' 의 사진을 다운받을 수 있고, 구독한 이후에 계속하여 '호두'의 사진을 받을 수 있는 사이트

# 주요 기능
- 고양이 '호두' 사진 다운로드
- '호두' 소개 섹션
- 이미지 갤러리
- 위치 지도 표시
- 이메일 구독 기능 및 유효성 검사
- 스크롤 탑 버튼
  
# 프로젝트 구조

- 📂 **images**           
  - 사용될 이미지 저장
- 📂 **js**
  - 📜 **main.js**        
    - 웹 페이지에서 사용되는 JavaScript 파일들이 저장
  - 📜 **secretKey.js**   
    - GoogleMap key 저장 (GitHub에 노출되지 않도록 주의)
- 📂 **style**
  - 📜 **style.css**      
    - 웹페이지의 스타일 정의
- 📜 **FEProjects.iml**
- 📜 **index.html**        
- 📜 **README.md**         
  - 웹 페이지의 메인 구조와 내용을 정의
- 📜 **reset.css**         
  - 브라우저 기본 스타일을 초기화 (폰트 설정)


# 요구사항 명세
    1. 피그마를 참고하여 페이지 구현을 합니다.
    2. 모바일 화면도 고려하여 페이지 구현을 합니다.
    3. 스크롤시 헤더가 고정되게 합니다. (단, 처음에는 고정된 상태가 아닙니다.)
    4. 스크롤 탑 버튼을 구현합니다. 
        1. 스크롤 탑 버튼은 스크롤시 나타납니다.
        2. 스크롤 탑 버튼은 푸터 아래로 내려가지 않습니다.
        3. 스크롤 탑 버튼을 누르면 스크롤이 최상단으로 올라갑니다. (단, 부드럽게 올라가야 합니다.)
    5. 구독하기 모달창
        1. 이메일을 입력하고 `Subscribe` 버튼을 클릭하면 모달창이 나타납니다.
        2. 이메일 유효성 검사를 진행해야 합니다. (값이 들어가지 않거나 이메일 형식이 유효하지 않으면 alert 창으로 경고 문구가 떠야합니다.)
        3. 이메일이 잘 입력되었다면 모달창이 뜹니다. 이때 모달창의 `OK! I love HODU` 버튼을 클릭하면 form이 제출되고 모달창이 닫힙니다.
  

# 요구사항 구현 방법
    1, 2. margin, padding, display: flex 등을 사용하여 요소 배치 
    3. position: sticky 사용
    4.  1. window.scrollY를 이용하여 window.scrollY > 0 일시 스크롤의 opacity를 1로 조정, 0일 시 0으로 조정
        2. 푸터 위에 position: fixed로 배치하여 푸터 아래로 내려가지 않도록 설정
        3. 자바스크립트로 스크롤 클릭 시 이벤트를 바인딩
    window.scrollTo({ top: 0, behavior: 'smooth' });
    5.  1. 이메일 유효성 검사를 통과한다면 모달창을 display: flex;로 설정하여 렌더링 (기본값 none)
        2. 이메일 표현 정규식 (/^[^\s@]+@[^\s@]+\.[^\s@]+$/) 을 통해 input값이 비어있다면 입력되지 않았음을, 패턴과 일치하지 않다면 유효하지 않음을 alert 창으로 나타냄
        3. 이메일 유효성 검사를 통과한다면 모달창을 display: flex;로 설정하여 렌더링 (기본값 none)
           모달창은 position: fixed를 통해 뷰포트의 정중앙에 나타나도록 설정
           현재 연결된 서버가 없기 때문에 콘솔창에서 제출한 데이터를 확인하도록 설정


# 요구사항 외의 추가 구현
  1. 다운로드 클릭 시 다운로드를 할 것인지 confirm 창 출력 후에 다운로드 실행
  2. 아이콘 클릭 시 각 아이콘에 맞는 홈페이지로 이동
  3. 아이콘 마우스 휠로 클릭 시에 새 창에서 이동


# 시행착오
- 먼저, 요구사항을 잘못 이해해서 데스크탑 화면과, 모바일 화면을 따로 하나씩 구현했었다.
- 또한 배치를 처음 할 때 모든 요소를 absolute로 피그마에 나와 있는 top/left로 때려박았는데,
- 렌더링은 문제 없이 되지만 시맨틱적인 부분이나 반응형 디자인, 성능, 유지보수성 등 많은 문제가 있음을 알게 되었고 수정했다.
- 또한 변수명을 btn-header 와 같은 케밥 표기법 (요소-내용) 식으로 설정했었는데, 
- 강사님의 설명에 따라 내용-요소로 수정하였고 자바스크립트에서는 카멜 표기법으로 수정했다.


# 느낀점
- HTML, CSS, JavaScript 에 대한 지식이라고는 개강 전 제공되는 강의를 잠깐 들은 게 전부였는데,
- 2주라는 짧은 기간 동안 프론트엔드 기초에 대해 많은 걸 배운 것 같다.
- 직접 구현하다보니 강사님들께서 실무에서 자주 쓰인다고 강조해주신 부분들이 크게 와닿았다.
- 위와 같은 시행착오들을 겪었기에 유사한 작업을 다시 하게 된다면 두 번, 세 번 반복해서 작업하는 일 없이 해낼 수 있을 것 같다.
- 또한, Figma 를 처음 접해보고 README.md 작성을 해보면서 조금이나마 사용법을 알게 되었고, 숙지할 필요성을 느꼈다.



