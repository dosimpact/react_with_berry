
## 설치  
```
# vite로 프로젝트 생성 
yarn create vite {project name} --template react-ts

# yarn 4.x 버전 사용
yarn set version berry

# 패캐지 설치
yarn
```


1. **`.pnp.cjs`, `.pnp.js`, `.pnp.loader.mjs`**: 이 파일들은 Yarn PnP 환경에서 의존성 경로를 설정하는 파일입니다. 다른 개발자들이 동일한 환경에서 프로젝트를 실행할 수 있도록 이 파일을 공유하는 경우도 있지만, 보통 이 파일들은 로컬 환경에 종속적이므로 `.gitignore`에 추가할 수 있습니다.
   
2. **`.yarn/cache/**`: 캐시된 패키지 파일들입니다. 각 로컬 환경에서 패키지가 캐시되므로 이 폴더는 Git에 올리지 않아도 됩니다.

3. **`.yarn/unplugged/**`: PnP에서 패키지를 로컬에서 "언플러그"한 버전이 저장되는 폴더입니다. 이것도 Git에 올리지 않습니다.

4. **`.yarn/build-state.yml`**: 빌드 상태 파일로, 로컬 환경에 종속적이므로 올리지 않아도 됩니다.

5. **`node_modules/`**: PnP 사용 시에도 일부 개발 도구들은 여전히 `node_modules` 폴더를 사용하기 때문에 존재할 수 있습니다. 이 폴더는 항상 `.gitignore`에 추가하는 것이 좋습니다.

6. **`.yarn/install-state.gz`**: 설치 상태 파일로 로컬 환경에서만 필요합니다.

일반적으로 `.yarnclean`, `.yarn-integrity`, `.yarnrc.yml` 같은 설정 파일은 Git에 포함되지만, 위에서 언급한 캐시 파일들과 빌드 관련 파일들은 제외하는 것이 좋습니다.

`.gitignore`에 아래와 같이 추가하면 됩니다:

```
.pnp.*
.yarn/cache/
.yarn/unplugged/
.yarn/build-state.yml
.yarn/install-state.gz
node_modules/
```



##  이슈: yarn berry 설치 후 모듈 찾기 불가능  

