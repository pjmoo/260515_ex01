# 260515_ex01

<!-- workspace-readme-learning:start -->
## 파일과 연결한 학습 안내

아래 설명은 이 폴더의 실제 소스와 빌드 설정을 기준으로 정리했습니다. 기존 소개의 기능 설명은 연결된 파일과 함께 확인할 수 있습니다.

### 주요 파일과 역할

| 파일 | 역할과 읽을 내용 |
| --- | --- |
| [01.html](<01.html>) | 제목입니다 화면 |

### 실행과 설정 확인

- [01.html](<01.html>)에서 화면을 확인합니다. 모듈·Fetch·외부 API를 사용하는 페이지는 로컬 HTTP 서버에서 열어 요청 실패 여부를 확인합니다.

### 관련 PDF와 보충 설명

- [5/27 강의](<../260629_ex/새 폴더/5-27/README.md>): DOM 요소 선택과 생성·수정·삭제를 화면의 실제 이벤트 처리와 연결합니다.

이 링크는 구현을 이해하기 위한 관련 기초 자료입니다. 해당 강의가 이 저장소의 모든 기능이나 이후 버전의 API를 설명한다는 뜻은 아닙니다.

### 읽는 순서와 복습

- 화면 요소 선택 → 사용자 입력 → 상태 변경 → 렌더링 순서로 코드를 추적합니다. 없는 요소, 빈 입력, 반복 클릭에서 화면 상태가 의도대로 유지되는지 확인합니다.

<!-- workspace-readme-learning:end -->

## PDF 기반 보충 정리

`103-*` Git 자료는 같은 내용이 있는 이전 실습 폴더보다 이 폴더를 기준으로 정리했다.

- 로컬 저장소에서는 `git init` 후 파일의 변경 상태를 `git status`로 확인하고, `git add`와 `git commit`으로 변경을 기록한다.
- 원격 저장소는 `git remote add origin <URL>`로 연결한다. 첫 전송은 `git push -u origin main`으로 upstream을 지정하면 이후 `git push`만으로 전송할 수 있다.
- `git pull`은 fetch와 merge를 함께 수행한다. 원격 변경을 먼저 살펴보고 싶을 때는 `git fetch`를 사용한다.
- 협업 중 `--force`는 다른 사람의 커밋을 덮어쓸 위험이 있으므로 피하고, 꼭 필요한 상황이라면 원격 상태를 확인하는 `--force-with-lease`를 고려한다.

## TIL

- `add`는 저장이 아니라 **다음 커밋에 포함할 변경을 선택하는 단계**다.
- 원격 저장소를 연결하기 전에는 현재 브랜치와 원격 URL을 각각 `git branch`, `git remote -v`로 확인한다.

<!-- pdf-til-supplement:start -->
## TIL 부연 설명 — PDF와 연결하기

기존 실습 내용을 이해하기 위한 PDF 기반 부연 설명이다. 아래 예시는 개념을 설명하기 위한 것이며, 이 프로젝트에서 실행해 관찰한 결과와는 구분한다. 페이지 번호는 표지를 포함한 PDF 순서다.

함께 읽을 파일: [01.html](<01.html>)

### HTML 구조가 화면 변경으로 이어지는 과정

브라우저는 HTML을 읽어 DOM 객체 트리를 만든다. querySelector로 얻는 것은 HTML 문자열이 아니라 현재 문서 안의 요소 참조이며, 찾지 못하면 null이다. classList로 상태를 바꾸면 표현 방식은 CSS가 담당하고, textContent로 값을 넣으면 문자열을 HTML 태그로 해석하지 않는다.

**예시로 이해하기:** 카드 목록을 만든다고 가정하면 데이터 배열 → createElement로 요소 생성 → textContent로 제목 지정 → 부모에 append 순서로 생각할 수 있다. 사용자 입력을 그대로 innerHTML에 넣는 방식은 피한다. HTML·CSS 실습에서는 먼저 정적인 구조를 이해한 뒤 이 과정을 동적 화면의 확장으로 읽는다.

근거: 161-1 Document Object Model — [4쪽](<../260629_ex/새 폴더/5-27/161-1_Document_Object_Model.pdf#page=4>) · [6쪽](<../260629_ex/새 폴더/5-27/161-1_Document_Object_Model.pdf#page=6>) · [14쪽](<../260629_ex/새 폴더/5-27/161-1_Document_Object_Model.pdf#page=14>) · [18쪽](<../260629_ex/새 폴더/5-27/161-1_Document_Object_Model.pdf#page=18>)

<!-- pdf-til-supplement:end -->
