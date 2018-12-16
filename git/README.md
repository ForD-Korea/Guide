# GitHub 가이드라인

협업 과정에서 이런 말을 들어본다고 하자. 

> 아, 우선 issue로 달아주시구요, 제 레포에서 fork 떠서 원하는 부분 수정해 주시구요, PR 올려주세요. 

Issue는 무엇이고 레포는 무엇이고.. 그것을 관리하는 GitHub은 무엇일까 ? 



## GitHub 소개

GitHub(깃허브) : 분산 버전 관리 툴인 깃(Git)을 사용하는 프로젝트를 지원하는 웹 호스팅 서비스 <br/>
**오픈 소스 코드 저장소**이며 많은 오픈 소스들이 GitHub를 통해 관리되고 있다.

## Git 소개

깃(Git) : 분산 버전 관리 툴. <br/>

많은 팀 단위 개발 협업과정에서 **Git**이 많이 사용되고 있다. 

개발자가 두 명 이상이라면, 소스 코드를 ver0.1, ver0.1.1.. 이렇게 관리하는데에는 분명 한계가 있다. 



 

![이미지](./images/memo1.PNG)

![이미지](./images/memo2.PNG)

![이미지](./images/memo3.PNG)

![이미지](./images/memo4.PNG)

![이미지](./images/memo5.PNG)

![이미지](./images/memo6.PNG)

![이미지](./images/memo7.PNG)

> Comment : 이 그림의 의도도 좋고 전달하고자 하는 바도 명확해서 좋으나, 그대로 쓰기에는 구어체인 점도 그렇고 다시 만들어야 할 필요가 있습니다. 

만약, 이렇게 소스파일을 관리하며 **모든 개발자가 불편함을 느끼지 않았다면 정말 Git을 사용하지 않아도 괜찮다.** 



## Git을 사용하게 된다면? 

![이미지](./images/state.PNG)

파일 변경사항에 대해 **history** 를 위와 같이 확인할 수 있다. 



## GitHub 설치

[설치](https://git-scm.com/downloads)페이지에서 현재 컴퓨터의 운영체제에 맞는 Git을 받으면 된다. 

![install](./images/install.png)

  

## Git 사용해보기

주로 사용하게 될 명령어는 크게 4가지다.

1. git add <br/>
   : 변경 사항된 사항을 Stage라고 하는 공간에 올린다.

   > Stage : 어떤 파일을 공유할지 선별해서 임시로 올려두는 정류소 같은 곳. 

2. git commit <br/>
   : 코드의 변경 사항을 저장한다.

   > 실제 공유되는 원격 저장소에 저장 되기 전, 내 컴퓨터에서 변경사항을 저장한다.

3. git push <br/>
   : 로컬 저장소에 저장된 변경 내용을 깃허브 혹은 깃 서버로 전송한다.

   > 공유를 위해 원격 저장소로 저장한 내용을 보낸다. 이 작업이 완료되면 해당 파일의 변경사항을 모두와 공유할 수 있다. 

4. git pull <br/>
   : 깃허브 혹은 깃 서버에 있는 내용을 로컬 저장소로 이동한다.

   > 원격 저장소에 있는 파일의 변경사항을 내려 받을 수 있다. 

5. git checkout name <br/>
   : 브랜치를 이동한다.

   > 브랜치에 관한 내용은, [branch란 무엇인가](https://git-scm.com/book/ko/v2/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EB%B8%8C%EB%9E%9C%EC%B9%98%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80) 를 읽어보고 학습하는 것을 권장한다. 



### GitHub 계정 만들기

우선 GitHub 게정부터 만들자.

[GitHub](https://github.com)  링크로 들어가서 가입할 수 있다. 

GitHub 계정을 만들었으면, 저장소(Repository, 줄여서 Repo)를 만든다.

1. 이런 창이나

![이미지](./images/repo1.PNG)

1. 이런 창이 보이면 `NEW` 클릭

![이미지](./images/repo2.PNG)

1. Repository 이름을 입력하고  `Create repository` 버튼클릭 

![이미지](./images/repo3.PNG)
​    

1. 주소창 오른쪽의 `복사` 아이콘 클릭 

   > 이 작업이 끝나면, 내가 생성한 원격 저장소의 주소를 복사하는 작업이 완료된 것이다. 

![이미지](./images/repo4.PNG)

### GitHub 사용 해보기 (bash)

git bash 실행

> **window** 유저라면 git bash 실행   
> **Mac** 유저라면 terminal 실행

1. 폴더 생성 (Comment : 여기서 git_test 빈 폴더로 되어있는 사진 하나 더 필요할듯 합니다. )

   > 예시 Repo는 바탕화면에 생성하였으며, 원하는 곳에 생성할 수 있다.
   > 단, **빈 폴더** 여야 한다. 

2. 폴더로 이동

3. 명령어 입력 (git clone "복사한 URL")

   ```
   $ git clone https://github.com/KimHunJin/test.git
   ```

4. `git_test -> test` 폴더로 이동. 

   ![이미지](./images/make.PNG)

5. 텍스트 파일 생성 (test.txt : 테스트를 위한 임시 파일)  
   ![이미지](./images/make2.PNG)

6. 명령어 입력 

   > 1. git add <파일 이름> : <파일 이름> 에 해당하는 파일을 Stage에 올린다는 뜻.
   > 2. git add * : 변경사항이 있는(혹은 처음 생성한) 모든 파일을 Stage에 올린다는 뜻. 

7. 명령어 입력 (git commit -m "메시지")

   ![이미지](./images/commit.PNG)

8. 명령어 입력 git config --global user.name "GitHub 가입할 때 사용한 이름"

9. 명령어 입력 git config --global user.email "GitHub 가입할 때 사용한 이메일"

10. 명령어 입력 git push

    ![이미지](./images/push.PNG)

11. 확인

    ![이미지](./images/push2.PNG)
    ​    

## 소스트리 사용방법

소트트리는 Git 명령어 (pull, commit 등)을 잘 모르더라도 GUI	로 쉽게 깃을 사용할 수 있게 도와주는 IDE이다.

### 소스트리 설치하기 (맥, 윈도우 동일)

1. 소스트리 설치 : [링크](https://www.sourcetreeapp.com/)

2. 소스트리 및 빗버킷 가입 

   ![이미지](./images/sourcetree.PNG)

   Bitbucket 클라우드 클릭 <br/>
   소스트리 및 빗 버킷 가입하여 진행

3. 인증

   ![이미지](./images/sourcetree_auth.PNG)

4. 다음과 같은 화면이 나오면 기본적인 세팅 완료

   ![이미지](./images/sourcetree_main.PNG)

### 소스트리 사용하기

1. [깃허브 만들기](#깃허브-계정-만들기) 페이지에서 만들었던 Repository 가져오기
	
	다음 화면에서 새로만들기 - URL복제를 클릭한다.   
	클릭 후 앞서 만든 깃허브 레포지토리를 입력한다.
	
	![이미지](./images/sourcetree_origin.PNG)
	
	![이미지](./images/sourcetree_origin_copy.PNG)
	
	![이미지](./images/sourcetree_origin_copy_data.PNG)
	
2. 클론 하기

	클론에 성공하면 다음과 같이 화면에 레포지토리 리스트에 추가되고, 워크스페이스 창이 나타난다.
	
	![이미지](./images/sourcetree_workspace.PNG)
	
3. 테스트 파일 생성해보기

	클론에 성공했으면 복제한 폴더로 이동하여 텍스트 파일을 하나 만든다.
	
	![이미지](./images/source_tree_testfile.PNG)
	
4. 테스트 파일 커밋하기

	소스트리로 돌아가 생성한 테스트 파일이 다음과 같이 생성됐는지 확인한다.
	
	![이미지](./images/source_tree_add.PNG)
	
	확인이 됐으면 체크박스를 선택하고 커밋한다.

	![이미지](./images/sourcetree_commit.PNG)
	
	커밋 메시지를 작성하고 커밋 버튼을 누르면 다음과 같이 팝업이 생성된다. 확인을 누르도록 하자.
	
	![이미지](./images/sourcetree_commit_ok.PNG)
	
5. 히스토리 확인하기

	커밋을 성공적으로 완료 했으면 히스토리에 커밋 내용이 추가된 것을 볼 수 있다.
	
	![이미지](./images/source_tree_history.PNG)
	
6. 푸시 하기

	성공적으로 커밋을 완료 했으면 푸시(Push)를 클릭하여 원격저장소로 업로드한다.
	
	![이미지](./images/sourcetree_push.PNG)
	
	확인을 누르면 로그인 팝업이 나오며, 깃허브 계정 정보를 입력하면 된다. <br/>
	(**주의**; 빗버킷이나 소스트리의 계정정보가 아니다.)
	
	![이미지](./images/sourcetree_push_login.PNG)
	
7. 확인하기

	성공적으로 푸시를 완료 했으면 원격 저장소인 깃허브 저장소로 이동한다.
	
	다음과 같이 파일이 생성됐음을 볼 수 있다.
	
	![이미지](./images/sourcetree_push_ok.PNG)
	
8. 마무리

	클론을 통하여 다른 Repository 역시 가져올 수 있다. GitHub에 공개 된 모든 코드는 오픈소스이며, 라이센스만 잘 명시해 주면 사용하는 데 지장없다.
	
`Git / GitHub` 사용방법은 기본적으로 꼭 알아둬야 할 지식이다. 앞으로 자주 사용하게 될 테니 익숙해지고, 주기적으로 커밋을 하며 GitHub를 관리하는 좋은 습관을 들이기를 추천한다. 
	
> ( 잔디가 심어지는 것을 보면 내심 뿌듯하다 :D )
