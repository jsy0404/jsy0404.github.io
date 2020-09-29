---
title: Git-Flow Usage
layout: posts
permalink: /categories/
author_profile: true
---



## Git-flow 사용법(Linux)

---
### Git-flow 초기 설정

#### Git-flow 설치

```shell
sudo apt install git-flow
```





### Git-flow 시작
---
#### 새로운 프로젝트 시작 시

  ```shell
  git init
  git flow init
  ```



#### 기존 repository 연동

  ```shell
  git clone 'link'
  git flow init
  ```





### Git-flow 사용법
---
#### Git-flow 전략
- 6개의 branch 존재
	- **`master`**: 최종 release 버전
	- **`develop`**: 다음 release를 위해 개발중인 단계
	- `feature`: 특정 기능 개발 단위. `develop`에서 파생
  - `release`: `develop`을 `master`로 merge하기 전 점검하는 단계. `develop`에서 파생
  - `hotfix`: `master`에 merge된 이후 버그가 발생했을 때, 긴급 버그 fix를 위한 branch. `master`에서 파생
  - `support`: 버전 호환성 문제를 처리하기 위한 branch. `feature`, `release`, `hotfix`같은 supporting branch 중 하나로 기타 기능을 담당.
- `master`와 `develop`은 항상 상주
- 이미지



#### Git-flow 커맨드

- `git flow 'branch' start <branch name>`과 같이 시작
  - ex) `git flow feature start login`, `git flow hotfix start hotfix-0.0.1`
- `git flow 'branch' finish <branch name>`과 같이 종료
  - ex)`git flow feature finish login`, `git flow hotfix finish hotfix-0.0.1`
  - 종료 시 자동으로 branch `delete` 및 `merge`
