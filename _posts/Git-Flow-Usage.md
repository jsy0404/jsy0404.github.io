---
title: Git-Flow Usage
layout: posts
permalink: /categories/
author_profile: true
---



# Git-flow(*Linux*)
## Git-flow 설치

```shell
sudo apt install git-flow
```



## Git-flow 사용법

### Gitflow 전략
- 6개의 branch 존재
	- **`master`**: Release(배포) 버전 관리를 위한 Branch. 오로지 배포 가능한 상태만을 관리.
	- **`develop`**: 다음 release를 위해 개발중인 단계
	- `feature`: 특정 기능 개발 단위. `develop`에서 파생
  - `release`: `develop`을 `master`로 merge하기 전 점검하는 단계. `develop`에서 파생
  - `hotfix`: `master`에 merge된 이후 버그가 발생했을 때, 긴급 버그 fix를 위한 branch. `master`에서 파생
  - `support`: 버전 호환성 문제를 처리하기 위한 branch. `feature`, `release`, `hotfix`같은 supporting branch 중 하나로 기타 기능을 담당.
- `master`와 `develop`은 항상 상주
- 이미지



### Git-flow 커맨드
#### Initialize


| git-flow        | git                                           |
| --------------- | --------------------------------------------- |
| `git flow init` | `git init`                                    |
|                 | `git commit --allow-empty -m "Initial commit` |
|                 | `git checkout -b develop master`              |



#### Connect to the remote repository


| git-flow | git                         |
| -------- | --------------------------- |
| *N/A*    | `git remote add origin url` |



#### Features


- **Create a feature branch**

  | gitflow                            | git                                         |
  | ---------------------------------- | ------------------------------------------- |
  | `git flow feature start MYFEATURE` | `git checkout -b feature/MYFEATURE develop` |

- **Share a feature branch**

  | gitflow                              | git                                 |
  | ------------------------------------ | ----------------------------------- |
  | `git flow feature publish MYFEATURE` | `git checkout feature/MYFEATURE`    |
  |                                      | `git push origin feature/MYFEATURE` |

- **Get latest for a feature branch**

  | gitflow                                  | git                                          |
  | ---------------------------------------- | -------------------------------------------- |
  | `git flow feature pull origin MYFEATURE` | `git checkout feature/MYFEATURE`             |
  |                                          | `git pull --rebase origin feature/MYFEATURE` |

- **Finalize a feature branch**

  | gitflow                             | git                                   |
  | ----------------------------------- | ------------------------------------- |
  | `git flow feature finish MYFEATURE` | `git checkout develop`                |
  |                                     | `git merge --no-ff feature/MYFEATURE` |
  |                                     | `git branch -d feature/MYFEATURE`     |

- **Push the merged feature branch**

  | gitflow | git                                               |
  | ------- | ------------------------------------------------- |
  | *N/A*   | `git push origin develop`                         |
  |         | `git push origin :feature/MYFEATURE`(*if pushed*) |



#### Release


- **Create a release branch**

  | gitflow                        | git                                     |
  | ------------------------------ | --------------------------------------- |
  | `git flow release start 1.2.0` | `git checkout -b release/1.2.0 develop` |

- **Share a release branch**

  | gitflow                          | git                             |
  | -------------------------------- | ------------------------------- |
  | `git flow release publish 1.2.0` | `git checkout release/1.2.0`    |
  |                                  | `git push origin release/1.2.0` |

- **Get latest for a release branch**

  | gitflow | git                                      |
  | ------- | ---------------------------------------- |
  | *N/A*   | `git checkout release/1.2.0`             |
  |         | `git pull --rebase origin release/1.2.0` |

- **Finalize a release branch**

  | gitflow                         | git                               |
  | ------------------------------- | --------------------------------- |
  | `git flow release finish 1.2.0` | `git checkout master`             |
  |                                 | `git merge --no-ff release/1.2.0` |
  |                                 | `git tag -a 1.2.0`                |
  |                                 | `git checkout develop`            |
  |                                 | `git merge --no-ff release/1.2.0` |
  |                                 | `git branch -d release/1.2.0`     |

- **Push the merged feature branch**

  | gitflow | git                                           |
  | ------- | --------------------------------------------- |
  | *N/A*   | `git push origin master`                      |
  |         | `git push origin develop`                     |
  |         | `git push origin --tags`                      |
  |         | `git push origin :release/1.2.0`(*if pushed*) |



#### Hotfixes


- **Create a hotfix branch**

  | gitflow                      | git                            |
  | ---------------------------- | ------------------------------ |
  | `git flow hotfix start 1.2.1 | `git checkout -b hotfix/1.2.1` |

- **Finalize a hotfix branch**

  | gitflow                        | git                              |
  | ------------------------------ | -------------------------------- |
  | `git flow hotfix finish 1.2.1` | `git checkout master`            |
  |                                | `git merge --no-ff hotfix/1.2.1` |
  |                                | `git tag -a 1.2.1`               |
  |                                | `git branch -d hotfix/1.2.1`     |
  |                                | `git checkout develop`           |
  |                                | `git merge --no-ff master`       |

- **Push the merged hotfix branch**

  | gitflow | git                                          |
  | ------- | -------------------------------------------- |
  | *N/A*   | `git push origin master`                     |
  |         | `git push origin develop`                    |
  |         | `git push origin --tags`                     |
  |         | `git push origin :hotfix/1.2.1`(*if pushed*) |



## Reference

[https://gist.github.com/JamesMGreene/cdd0ac49f90c987e45ac](https://gist.github.com/JamesMGreene/cdd0ac49f90c987e45ac)

