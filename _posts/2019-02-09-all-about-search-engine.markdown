---
layout: posts
title: "검색 엔진에 대하여"
excerpt: "search engine, "
date: 2019-02-08
permalink: /posts/
categories: 
  - computer
  - search engine
tags: 
  - search engine
published: false
---
> **이 글에서 다루는 내용**
> [x] 검색 엔진이란 무엇인지
> [x] 

#검색엔진이란 무엇인가

##검색엔진의 원리
검색엔진은 형태소 분석기, 색인 기능, 그리고 검색기능으로 이루어져 있다고 설명하고 있다.
https://needjarvis.tistory.com/167

1. 형태소 분석기
필요한 단어들은 패션 잡지, 신문에서 본문을 가져와 형태소 분석을 하여 저장해 놓는 방법을 활용
형태소 분석기는 엘라스틱서치에서 만든 노리(Nori)와 기존 많은 사람들이 사용하는 은전한닢 프로젝트(MeCab)
노리에 대한 설명은 https://www.elastic.co/kr/blog/nori-the-official-elasticsearch-plugin-for-korean-language-analysis
노리 설치 방법 https://www.elastic.co/guide/en/elasticsearch/plugins/current/analysis-nori.html
파이썬에서는 KoNLPy 라이브러리 있음
노리는 엘라스틱서치의 플러그 인인데 파이썬에서도 가능한지 모르겠음

2. 색인 기능
인덱스란?
엘라스틱 서치을 사용한다고 햇을때
GET 입력되어있는 조회하기
맨 처음에 하면 404 에러가 나옴
PUT을 활용하여 인덱스를 생성
인덱스 안에 도큐먼트를 만들때 POST사용
생성된 도큐먼트를 수정, 여러개 한꺼번에 입력할때 update, bulk옵션을 줄 수 있음
인덱스에서 매핑을 해야지 각 property가 어떤 형식인지(int, boolean, string, date, geo_point 등) 혼동없이 데이터를 이용가능

인프런 강의로 기본 개념 학습
https://www.inflearn.com/course/elk-스택-데이터-분석/엘라스틱서치-데이터-입력-조회-삭제-get-post-put-delete/

3. 검색 기능
앞의 색인 및 도큐먼트가 저장되어 있어야 검색을 할 준비를 마친 것입니다.
search 옵션을 사용하면 되는데 이때 requests body를 다양하게 변형하면서 다채로운 검색이 가능
참고 https://www.elastic.co/guide/en/elasticsearch/reference/current/search-request-body.html

###Apache Lucene 아파치 루씬
아파치 루씬은 정보검색 (Information Retrieval, IR) 무료 오픈소스 라이브러리입니다. 

아파치는 아파치 소프트웨어 파운데이션(Apache Software Foundation, ASF)를 줄여 부르는 말입니다. 
ASF에서는 현재 350개가 넘는 오픈소스 프로젝트를 진행하고 있는데 Apache HTTP Server, Apache Hadoop, Apache Spark 등 개발한 소프트웨어 앞에 아파치라는 이름을 붙여 명명하고 있습니다.
아파치 루씬도 이러한 프로젝트 중에 하나 입니다.
루씬 자체가 검색 엔진인 것이 아니라 하나의 강력한 라이브러리이기 때문에 루씬을 활용하여 검색엔진을 구축할 수 있습니다.
루씬을 활용한 대표적인 검색엔진이 Elasticsearch와 Solr입니다. 

참고 문헌 
https://www.apache.org/foundation/
#검색엔진의 종류

##검색엔진 순위
검색엔진 순위 ([최신버전 확인][https://db-engines.com/en/ranking/search+engine])
검색엔진 트렌드 [최신버전 확인][https://db-engines.com/en/ranking_trend/search+engine]
2019년 2월 기준으로 Elasticsearch, Splunk, Solr, MarkLogic,	Sphinx 순으로 1~5위를 기록했습니다. 
Elasticsearch는 2014년 이후 급성장하여 2016년 이후 안정적으로 1위를 유지하고 있는 반면 Solr는 1위 검색엔진이었지만 2016이후 하락하는 추세를 가진이후 현재 3위에 머무르고 있습니다. 
Splunk는 2018년에 처음으로 Solr를 추월하여 현재 2위입니다.

##오픈소스 검색엔진
가장 널리 사용되는 세가지 오픈 소스 비교
https://db-engines.com/en/system/Elasticsearch%3BSolr%3BSphinx

###Elasticsearch
데이터 처리 과정에 대해 정리
https://www.slideshare.net/kjmorc/ss-80803233
https://www.slideshare.net/xpressengine/xecon-phpfest2014elasticsearch

검색 기능 자체를 외주로 줄 수도 있음-- 찾아보면 많이 있을 것
  https://www.elastic.co/kr/solutions/site-search
구글 커스텀 서치 https://developers.google.com/custom-search/
Custom Search Site Restricted JSON API requests cost $5 per 1000 queries and there is no daily query limit. 
You may sign up for billing in the API Console.