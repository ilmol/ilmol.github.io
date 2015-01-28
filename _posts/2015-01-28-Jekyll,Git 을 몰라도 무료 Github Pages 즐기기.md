---
layout: post
title:  "Jekyll,Git 을 몰라도 무료 Github Pages 즐기기"
date:   2015-01-28 021:14:11 +0900
categories: products
description: 웹사이트및 블로그를 무료로 사용할 수 있는 Github Pages 서비스를 git 이나 명령어를 모르더래도 사용하는 방법.
---
Github Pages 는 Github에서 제공하는 무료 웹사이트 서비스로써 자신의 프로젝트 소개나 회사를 소개하기에 편한 곳이지만 Jekyll 엔진으로 돌아가므로 간단한 블로깅이 가능하다.  다시말해서 무료로 회원들이 블로깅 서비스를 누릴 수 있다.  "[워드프레스에서 Jekyll로 마이그레이션](http://ilmol.com/2015/01/%EC%9B%8C%EB%93%9C%ED%94%84%EB%A0%88%EC%8A%A4%EC%97%90%EC%84%9C%20Jekyll%EB%A1%9C%20%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98.html)" 에서 소개했듯이 많은 장점을 갖고 있지만 git 을 배워야 하고 Jekyll을 깔아야 하는 번거로움과 어려움이 따른다.

이 글에 소개되는 Fork를 이용한 Pages 사용법은 진입장벽이 높을 수 있는 Pages 를 간단한 방법으로 온라인에서 즐길수 있도록 하는 방법이다.  이 방법이 어떤 앱이나 프레임워크등의 전혀 새로운 아이디어가 아님을 밝힌다.  
![깃헙과 자킬 minisize](/assets/img/blog/octojekyll.png)


이 글의 대상은 Github 조차도 모르는 상황의 유저이며 아무런 사전 지식 없이 무료로 블로깅을 시작하도록 돕는 목적으로 쓰여졌다.

이 과정을 마치면 얻게되는 결과물은 이러하다.

* 온라인 상에서 자신의 주소 (http://유저아이디.github.io) 로 블로깅이 가능하다.
* 모든 작업은 github.com 에서 이루어지므로 컴퓨터에 설치해야 할 것은 없다.
* github.com 에서 파일을 추가하고 수정할 수 있게된다.


워드프레스에서 Jekyll + Github 으로 마이그레이션을 진행한 이야기는 바로 [이전 글](http://ilmol.com/2015/01/%EC%9B%8C%EB%93%9C%ED%94%84%EB%A0%88%EC%8A%A4%EC%97%90%EC%84%9C%20Jekyll%EB%A1%9C%20%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98.html)을 참고하기 바란다.


### Github 가입
* [Github.com](http://github.com) 에서 Username 과 이메일, 암호를 적고 곧바로 가입을 한다.  
* 가입후 Github 플랜을 골라야 한다.  무료가 이미 선택되어 있으니 하단에 Finish sign up 을 눌러 가입을 마무리 한다.  본인 확인을 위한 이메일이 도착해 있을테니 가입시 기입한 이메일 주소의 메일함으로 가서 확인 바란다.  이메일의 본인확인 링크를 클릭하여 확인하지 않을 경우 서비스를 사용할 수 없다.
![github signup finished](/assets/img/blog/2015finishgit.png)


### Fork 하기
가입 후 알아야 할 용어는 repository 와 fork 이다.

  * repository 는 각 계정의 프로젝을 넣는 공간이라고 이해할 수 있다.  Repo 라고 줄여 부르기도 한다.  여러개의 repo 를 만들 수 있고 누구든지 공개된 repo 에 들어가서 볼수 있다.
  * Fork 는 복사/클론 이라고 이해하면 될듯 하다.  누군가의 repo 에 들어가서 Fork 버튼을 누르게 되면 내 repo 안에 복사되어 저장된다.
 
용어를 알았다면 [https://github.com/barryclark/jekyll-now](https://github.com/barryclark/jekyll-now) 를 Fork 하여 내 저장공간인 repo 로 그대로 복사해오자.  링크를 따라가면 오른쪽 상단에 fork 버튼이 보일것이다. 
![github fork](/assets/img/blog/2015fork.png)
 
몇초가 걸리긴 하지만 Fork가 끝나면 여러 파일이 들어있는 repo가 생겼을 것이다.  왼쪽 상단을 보면 유저이름 / jekyll-now 라고 되어 있을것이다. 


### Setting 수정 - Repo 이름 바꾸기
Repository 이름을 jekyll-now 에서 자신의 유저이름.github.io 로 바꾸어야 한다.  Github이 해당 repo가 블로그 사이트로 사용되는걸 인증하는 방법이다.

오른쪽 Settings 을 누른후 Repository name 란에  jekyll-now 대신 자신의 아이디.github.io 라고 수정한다. 
![Repo name change](/assets/img/blog/2015reponame.png)

Jekyll-now 에서 지금까지의 과정을 [gif](https://github.com/barryclark/jekyll-now/raw/master/images/step1.gif) 로 만들어 올렸다.


### Customize Settings

파일을 수정하는 간단한 방법은 해당 파일을 클릭 후 연필 모양의 Edit 버튼을 누르는 것이다.
![연필모양의 edit 버튼](/assets/img/blog/2015gitedit.png)

사이트의 기본틀을 가져왔으니 기본 설정파일인 _config.yml 을 수정하고 사이트가 정상적으로 작동하는지 확인한 후 다음 단계인 글을 써보겠다.

* _config.yml 파일을 클릭한 후 Edit 버튼을 누른다.
* 각각의 비어있는 공간을 채워준다. 
* 모든 정보를 기입할 필요는 없으나 적어도 name 과 url 은 수정해준다.
* url은 "http://자신의 아이디.github.io" 라고 표기한다.
* 수정을 마쳤다면 하단에 Commit changes 버튼을 눌러준다.  가능하다면 버튼 바로위의 빈칸에 무엇을 수정하였는지 설명을 넣어주자.  올바른 연습이 될 것이다.

모든 수정을 마쳤다면 새 브라우저를 열어 자신의 블로그 주소로 접속해 보자.  가장 처음으로 사이트를 띄우는 상황이니 30분까지도 걸릴 수 있다.  참고 기다려보자.  이메일확인을 했는지도 꼭 확인하자.


### 첨부된 글을 수정하며 문법 배우기
모든 블로그 글은 _posts 폴더안에 있어야 한다.  첫 글은 이미 폴더 안에 첨부되어있으니 그 글을 수정하며 글 작성에 필요한 부분을 살펴보겠다.

* _posts 안의 2014-3-3-Hello-World.md 를 수정한다.
* 수정을 누르면 몇가지 눈에 띄는 부분이 보일것이다.
	* --- 3개의 대쉬가 위 아래로 있으며 이전의 _config.yml 파일처럼 지정 이름이 있고 값이 지정되어 있다.  Front-matter 라고 부르는 부분이다.  모든 글의 상단에는 바로 이 Front-matter 가 첨부되어야 한다.  글의 제목, layout 파일이름, 날짜를 꼭 넣으며 categories 등도 적어 넣을 수 있다.
	* layout: post 는 _layouts 폴더의 post.html 을 지정하며
	* title: 은 글의 제목을 지칭한다.  글의 웹 주소를 지칭하지는 않는다.  글의 웹 주소는 파일 이름을 따라 지정된다.
	* 글 안을 보면 **!&#91;대체텍스트&#93;(/폴더/이미지 주소)** 형식의 부분이 보일 것이다.  이미지를 나타내는 부분인데 !표를 빼면 단순 링크를 나타낸다. &#91;링크이름&#93;(링크주소)
	* 이미지를 웹에서 repo에 첨부하여 사용하는 방법이 없다.[^1]  그나마 간단한 방법은 issue 를 사용하여 이미지를 사용하는 방법이다.  이는 맨 하단에서 설명하도록 하겠다.
	* 이러한 표기법은 markdown 이라고 부르는데 글 작성시에 markdown 형식으로 글을 작성해야 한다.  그다지 어려운 형식은 아니니 꼭 배우기 바란다.[^2] 간단히만 보면 
	* # 는 h1(글제목), ## 는 h2, > 는 blockquote(인용문구), * 는 list. **를 양쪽에 쓰면 strong(강조).
* 하단의 Commit changes 버튼을 누르고 수정이 적용 되었는지 확인해보자.


### 새로운 글을 써보기
수정한것과 마찬가지의 순서이다.
다시 _posts 폴더에 들어가서 branch: master 옆의 주소 끝 부분에 있는 + 를 눌러준다.  
![_post옆 + 버튼](/assets/img/blog/2015gitplus.png)

새 파일을 만드는 페이지가 나오면 제일 먼저 파일 이름을 먼저 정해준다. 년-월-일-글제목.md 로 정해주어야 한다.  
![_post옆 빈공간](/assets/img/blog/2015gitnameit.png)

그리고 내용란에 Front-matter 를 먼저 적어준다.

```
---
layout: post
title:  "Github Pages 에 올리는 첫 글"
date:   2015-01-28 17:30:00
---
```

그 후 적고 싶은 글을 적어본다.  그리고 하단의 Commit new file 을 클릭한다.  첫 글이 올라갔을테니 확인해 본다.


### 그 외
첫 글은 올렸지만 아직 수정해야 할 것들이 남았다.  

* 방문자가 잘못된 경로로 접속하거나 페이지 에러가 났을때에 출력되는 404.md 페이지
* 현 repo 소개를 나타내는 (파일리스트 밑의 긴 글) README.md
* 실제 소개페이지가 될 about.md 를 자신의 소개로 채워보자.  사이트에서 About 클릭시 출력되는 페이지 이다.

### 이미지를 첨부하여 보여주기
위에서 잠깐 언급했지만 직접 이미지를 자신의 repo 에 업로드 하여 사용 하는 방법은 자신의 컴퓨터에 git을 설치하여 직접 자신의 repo 와 연결하는 방법 뿐이다.  이는 정석이긴 하나 글의 목적과는 다르므로 그것을 우회하는 편법은 Issues 를 사용하는 방법이다.

* 오른쪽 메뉴의 Settings 를 누른 후 Issues 를 체크하여 사용 가능토록 한다. 
* 오른쪽 메뉴 상단에 Issues 메뉴가 생겼을 것이다.  클릭한 후 "New Issue" 를 선택한다.  
	![New Issue 버튼](/assets/img/blog/2015gitissue.png)
* 제목은 아무거나 적을수 있지만 기왕 하는거 이미지를 넣을 포스트 제목을 넣는다.
* 그리고 이미지를 드래그 하여 글 란에 드랍한다.
* Submit new issue 를 누른 후 이미지의 주소를 복사하여 글 안에 삽입한다.
	!&#91;대체텍스트&#93;(http://이미지주소.jpg)
	

### 웹에서 모든게 가능한 Github Pages
Github Pages 를 제대로 로컬 컴퓨터에 설치하여 사용하는 것은 하루 이틀정도의 배움의 시간이 들어가지만 위의 방법을 사용하면 아주 초보 사용자도 많은 지식이 없이도 1시간 안에 블로깅 서비스를 사용 할 수 있다.  깃헙 페이지 서비스가 나에게 맞는지 테스팅 해본다면 위의 방법을 추천해드리고 싶다.  언제든지 해당 repo 를 삭제하면 되고 서비스가 맘에 든다면 CNAME 파일을 수정하여 독립 도메인 사용도 몇분안에 가능하다.

이미 블로깅을 하고 계시는 분이라면 이전글 "[워드프레스에서 Jekyll로 마이그레이션](http://ilmol.com/2015/01/%EC%9B%8C%EB%93%9C%ED%94%84%EB%A0%88%EC%8A%A4%EC%97%90%EC%84%9C%20Jekyll%EB%A1%9C%20%EB%A7%88%EC%9D%B4%EA%B7%B8%EB%A0%88%EC%9D%B4%EC%85%98.html)" 글을 읽어보셔도 도움이 되실듯 하다.


![writtenby ilmol](/assets/img/system/signature.png)



[^1]: 기타 다른 사이트에 이미지를 올리고 링크하는 법도 있지만 issues 를 사용하는 방법이 가장 나은듯 싶다.  더 좋은 방법이 있다면 나눠주시기를 바란다.

[^2]: 참고할만한 글들. [kalkin7](http://blog.kalkin7.com/2014/02/10/lets-write-using-markdown/), [nolboo](http://nolboo.github.io/blog/2014/04/15/how-to-use-markdown/)