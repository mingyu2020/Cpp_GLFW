[Visual Studio 2022와 OpenGL GLFW 연동 과정]

1. GLFW 설치
- 사이트 = https://www.glfw.org/download.html
- 64-bit Windows binaries 클릭하여 다운로드 후 압축해제

2. 설치한 GLFW 파일 옮기기
- 새로운 프로젝트 생성 : C++ / 콘솔앱
- 솔루션 빌드 실행 및 완료 후, 솔루션 폴더를 열어 'include', 'lib' 이름의 폴더를 생성
- 1 에서 받았던 glfw-3.4.bin.WIN64 ▶ include ▶ GLFW 폴더를 솔루션 폴더의 'include'폴더에 복사
- glfw-3.4.bin.WIN64 ▶ lib-vc2022 폴더 안의 'glfw3.lib' 파일을 솔루션 폴더의 'lib' 폴더에 복사

3. Visual Studio 속성 설정
- 프로젝트 속성 페이지에 진입
- 구성(C)의 모드를 '모든 구성'으로 변경
- C/C++ ▶ 일반 ▶ 추가 포함 디렉터리에 $(SolutionDir)/include 를 입력 후 적용
- 링커 ▶ 일반 ▶ 추가 라이브러리 디렉터리에 $(SolutionDir)/lib 를 입력 후 적용
- 링커 ▶ 입력 ▶ 추가 종속성의 맨 앞에 glfw3.lib;opengl32.lib; 추가(glfw라이브러리, openGL라이브러리 사용)

[테스트 코드 입력]
- 상단 첨부코드 확인


[테스트 코드 결과]
