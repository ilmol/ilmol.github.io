---
layout: post
comments: true
title:  "Jekyll markdown 업데이트"
date:   2016-05-11 11:13:00 +0900
categories: etc, product
description: 오랜만에 Github Pages 서비스 업데이트를 하며 markdown 업데이트 단행.  
thumbnail: 2016jekyll3.png
crosspost_to_medium: true
---


오랜만에 와보니 [jekyll 의 업데이트와](https://github.com/blog/2100-github-pages-now-faster-and-simpler-with-jekyll-3-0) 와 그에따른 몇가지 수정을 요하는 부분들이 있었다. 이번 jekyll 3.0 업데이트의 큰 부분은 더이상 kramdown 외의 마크다운 엔진을 지원하지 않는다는 것이었고 redcarpet 엔진을 쓰고 있는나는 사실 몇초간 맨붕이 오긴 했었다.

각 포스트들에 첨부한 footnote 기능이나 코드블락을 잘 표현해주는 것이 맘에 들어서 선택한 엔진인지라 이거 혹시 이 기능들이 지원 안되는 건가 한탄을 하고 있었지만 jekyll3.0 업데이트 문서를 보니 다행히 redcarpet 과 rdiscount 의 기능들을 모두 사용 가능한듯 하다.

>If you are currently using Rdiscount or Redcarpet we've enabled kramdown's GitHub-flavored Markdown support by default, meaning kramdown should have all the features of the two deprecated Markdown engines, so the transition should be as simple as updating the Markdown setting to kramdown in your site's configuration (or removing it entirely) over the course of the next three months.

간단히 _config.yml 수정으로 엔진을 갈아 타는 것이지만 그 잠시간의 맨붕의 몇초를 생각하면 역시나 서비스 사용을 문제없이 오래하려면 기본틀 안에서 놀아야 한다는 걸 다시한번 상기하게 된다.

완벽한 마이그래이션은 아닐것이고 아마 인용문구 등의 사용이나 code 블락의 표현에서 어딘가에는 충돌이 있긴 할듯 하다.

Jekyll 3.0
-----

말 나온김에 제킬3.0을 살짝 살펴보면 markdown 지원을 kramdown 으로 제한하는 것 외에도 Textile 마크업 사용 또한 지원하지 않으며 relative permalinks 또한 지원하지 않는다.  

외에도 로컬서버에서 빌드하는 속도나 프리뷰 속도 개선및 liquid profiler 라 말한 속도가 표기된 테이블 출력등이 소개됬다.

>The changes introduced today promise to make GitHub Pages a faster, more intuitive experience for new and power users alike.

더욱 빠르고 직관적인 Pages 서비스를 위해서라는 슬로건 아래 불필요한 리소스 안잡아 먹고 서비스를 꾸준히 유지해 줄 수 있다면 해달라는거 뭘 못할까.

워드프레스에서 이사한지 1년이 넘었지만 서버, 보안, 가격 신경 안쓰고 무료로 즐기는 서비스일 뿐만이 아니라 아주 강력한 customization 에 아주 만족하고 있다.



