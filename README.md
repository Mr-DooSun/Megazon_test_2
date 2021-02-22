# Megazon test 2

### 환경세팅하기
```
npm install
```
아래링크로 이동하여 Megazon test 1 에 server.ts파일을 실행 합니다. 
>
(빌드로 만들어진 server.js를 실행시켜도 무관함)
>
https://github.com/Mr-DooSun/Megazone_test

### 실행하기
```
npm run serve
```
### 결과 확인
http://localhost:8080/

---
>
## APK 빌드하기
>
### CapacitorJS 설치
```
npm install @capacitor/core @capacitor/cli
```
```
npx cap init
```

### capacitor.config.json 파일에 webDir 데이터 변환
```
webDir : "wwww"
```
에서
```
webDir : "dist"
```
으로 변환해줍니다

### 프로젝트 빌드
```
npm run build
```
### 안드로이드
```
npx cap add android
```
### 안드로이드 실행
```
npx cap open android
```