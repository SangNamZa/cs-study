# Git & Github

## Git

Git은 버전 관리 시스템(VCS, Version Control System)이다.

### Git의 탄생이유

흔히 회사나 학교에서 문서에 대해 버전관리할 때 문서 제목에 버전을 달아서 관리한다.
* 현대문학의_이해_발표자료.pptx
* 현대문학의_이해_발표자료_중간.pptx
* 현대문학의_이해_발표자료_중간2.pptx
* 현대문학의_이해_발표자료_중간3.pptx
* 현대문학의_이해_발표자료_최종.pptx
* 현대문학의_이해_발표자료_최종2.pptx
* 현대문학의_이해_발표자료_진짜최종.pptx
* 현대문학의_이해_발표자료_진짜진짜최종.pptx

이와 같은 방식은 매우 불편하며, 파일 전체를 복사하기 때문에 메모리 측면에서도 좋지 않다. 그래서 탄생한 것이 버전 관리 시스템이다.
Git 이전에도 이것저것 많았지만 현재는 git이 가장 유명하다.(git말고 다른 것 써본 적이 없다.)

### Git의 장단점

#### 장점
* 파일이 수정된 부분을 추적해준다.
  * ![image](https://user-images.githubusercontent.com/38755868/186334986-0cb05f59-8ef7-41a4-9362-67a18f77151e.png)
* 버전 관리를 매우 편리하게 제공해준다.
  * master : 원본
  * feature : 기능 개발용 브랜치
  * bugfix : 버그 수정용 브랜치
  * release : 배포용 브랜치
* 변경된 부분에 대한 정보만 저장하기 때문에 메모리를 아낄 수 있다.
* Merge(코드 합치기)할 때 충돌을 잘 해결해준다.

#### 단점
* 자체 난이도가 높다.


## Github

Github는 git에서 작업한 내용을 호스팅(저장 & 관리)해주는 웹서비스다. 비슷한 걸로 Gitlab, Bitbucket 등이 있다.

### Github의 장단점

#### 장점
* Git에서 작업한 내용을 대신 관리해주기 때문에 이중 삼중화 되어 있는 Github의 서버가 전부 폭파되지 않는 이상 작업한 코드를 유실할 일이 없다.
* 협업에 용의하다.
  * Git으로 각자 PC에서 작업
  * Github로 push
  * Github에서 pull request 만들어서 팀원들 확인 받고 merge
* 각종 플러그인, 기능이 존재한다.
  * master 브랜치에 merge되면 소스를 서버에 자동배포(CI/CD, Continuous Integration and Continuous Delivery(Deployment))

#### 단점
* 개인정보, 암호키 등 공개되면 안되는 파일, 내용을 잘못 업로드할 시 전세계에 공개된다.
  * 실제 해킹 사례도 많다.

## 실습

1. git clone
2. 내용 추가 및 수정
3. git add
4. git commit
5. git push
6. pull request 날리기
7. approve 되면 merge 하기
