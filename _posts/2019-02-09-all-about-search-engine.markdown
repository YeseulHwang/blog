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

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
