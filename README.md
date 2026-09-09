# 260515_ex01

## PDF 기반 보충 정리

`103-*` Git 자료는 같은 내용이 있는 이전 실습 폴더보다 이 폴더를 기준으로 정리했다.

- 로컬 저장소에서는 `git init` 후 파일의 변경 상태를 `git status`로 확인하고, `git add`와 `git commit`으로 변경을 기록한다.
- 원격 저장소는 `git remote add origin <URL>`로 연결한다. 첫 전송은 `git push -u origin main`으로 upstream을 지정하면 이후 `git push`만으로 전송할 수 있다.
- `git pull`은 fetch와 merge를 함께 수행한다. 원격 변경을 먼저 살펴보고 싶을 때는 `git fetch`를 사용한다.
- 협업 중 `--force`는 다른 사람의 커밋을 덮어쓸 위험이 있으므로 피하고, 꼭 필요한 상황이라면 원격 상태를 확인하는 `--force-with-lease`를 고려한다.

## TIL

- `add`는 저장이 아니라 **다음 커밋에 포함할 변경을 선택하는 단계**다.
- 원격 저장소를 연결하기 전에는 현재 브랜치와 원격 URL을 각각 `git branch`, `git remote -v`로 확인한다.
