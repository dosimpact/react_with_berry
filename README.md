# Vite + React + TS + Yarn Berry  

## 설치  
```
# vite로 프로젝트 생성 
yarn create vite {project name} --template react-ts

# yarn 4.x 버전 사용
yarn set version berry

# 패캐지 설치
yarn
```

## Zero Install

- .gitignore 설정만 해주면 된다.  

```
If you're using Zero-Installs:

.yarn/*
!.yarn/cache
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions

If you're not using Zero-Installs:

.pnp.*
.yarn/*
!.yarn/patches
!.yarn/plugins
!.yarn/releases
!.yarn/sdks
!.yarn/versions

```
## 이슈: node_modules가 자꾸 생기는 이슈(vite)  

```
// vite.config.ts
{
  ...,
  cacheDir: './.vite' // 추가
}

// .gitignore
{
  # vite cache
  .vite // 추가
}
```

## 이슈: yarn berry 설치 후 모듈 찾기 불가능  

```js
1.VS Code에 SDK 설치
yarn dlx @yarnpkg/sdks vscode


2.Tyesciprt를 워크스페이스의 버전으로 변경하기. 
- Ctrl + Shift + P
- Select Typescript Version
- Use Workspace Version 클릭

```