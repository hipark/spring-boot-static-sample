# Single Page Angularjs application with Spring Boot and Yeoman

## 필요 패키지 설치
### `node.js` & `npm` 설치
- node.js 설치
```
sudo apt-get update
sudo apt-get install nodejs
```
- node.js 업데이트가 필요하면
```
node.js update
sudo npm cache clean -f
sudo npm install -g n
sudo n stable
```
- npm 설치
```
sudo apt-get install npm
```
- npm 업데이트가 필요하면
```
npm update npm -g
```

### `yo`, `gulp` and `bower` 설치
```
npm install -g yo gulp bower
```

### `generator-gulp-angular` 설치
```
npm install -g generator-gulp-angular
```

## 프로젝트 설정
### 프로젝트 생성
- STS에서 시작.(간단히 web 의존성만 추가, Gradle build tool 선택)
```
New -> Spring Starter Project
```
는- 또는 Spring 프로젝트를 CLI에서 초기화해서 시작.
```
spring init --dependencies=web spring-boot-static-sample
```

### 생성된 프로젝트 폴더로 이동
```
cd ~/workspace/git-repository/spring-boot-static-sample
```
### `yo gulp-angular` 실행 후, 이어지는 옵션 선택(Angular.js version 등)
```
yo gulp-angular --app-path='src/main/resources/front\' --dist-path='src/main/resources/static\'
```
- 옵션 추가하여 기본 src, dist 경로를 변경한다.
  - 기본 src 경로를 사용하면 src/main, src/test 폴더와 함께 관리함에 있어 불편함이 발생할 수 있다.
  - gulp build를 하면서 src폴더 내의 html, css, js, scss 를 제외한 모든 파일을 dist폴더로 복사하는데 이 때, src/main, src/test 폴더 또한 복사가 되므로 프로젝트에 에러가 발생한다.
- gulp/conf.js 파일을 열어 변경된 경로를 확인할 수 있다.

## 프로젝트 실행

### gulp 실행하면 바로 확인 가능
```
gulp serve
```
### `gulp` 또는 `gulp build`
```
gulp build
```

### gulp build 후 STS에서 서버 실행 또는 명령어로 실행
```
./gradlew bootrun
```
### 서버 접속 (http://localhost:8080/#/)
