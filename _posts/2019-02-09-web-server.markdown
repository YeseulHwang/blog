---
layout: posts
title: "웹서버란 무엇인가? - 아파치(Apache)와 톰캣(Tomcat)의 차이는?"
excerpt: "Web server, Web Application Server, Web Container, Servlet Container, Apache httpd, Apache Tomcat, 웹 어플리케이션 서버, 웹 컨테이너, 소블릿 컨테이너"
date: 2019-02-08
permalink: /posts/
categories: 
  - computer
  - web
tags: 
  - Web server
  - Web Application Server
  - Web Container
  - apache httpd
  - apache tomcat
  - servlet
published: true
---
> **이 글에서 다루는 내용**
> [x] 이 글에서는 웹서버와 웹 어플리케이션 서버가 무엇인지
> [x] 아파치(Apache)와 톰캣(Tomcat)의 차이가 무엇인지

#웹 서버 vs 웹 어플리케이션 서버 vs 웹 컨테이너
웹서버(Web Server)와 웹 어플리케이션 서버(Web Application Server, WAS)는 둘다 웹사이트에서의 사용자의 컨텐츠를 요청을 처리한다는 공통의 목적이 있습니다.
그러나 웹서버와 웹 어플리케이션 서버에 대해 명확히 정의된 바가 없기 때문에[^1] 
필드에서 주로 사용되는 점을 정리해 보겠습니다.

웹서버는 HTML 페이지, 파일, 이미지, 비디오 등과 같은 정적인(static) 컨텐츠에 대한 요청에 응답하기 위하여 주로 사용됩니다.
클라이언트는 거의 브라우저나 모바일 앱이고 요청은 http형식을 따릅니다.
반면 WAS는 웹서버를 통하여 Java나 JSP (Java Server Pages)로 작성된 어플리케이션과 같은 동적인 (dynamic) 컨텐츠를 다루는 것이 어렵기 때문에 고안된 것이라고 할 수 있습니다.
WAS의 클라이언트는 어플리케이션이고 요청은 http형식을 따라도 되지만 WAS와 어플리케이션간의 커뮤니케이션이기 때문에 꼭 그럴 필요는 없습니다.
클라이언트는 어플리케이션이고 WAS안에 웹 서버나 또다른 WAS를 포함할 수 있습니다.  
대표적인 예로는 Oracle WebLogic이 있습니다.

제가 공부를 하는 과정에서 대부분의 글에서는 톰캣 Tomcat을 WAS로 분류하고 있었습니다. 
그러나 엄밀히 말하자면 톰캣은 웹 컨테이너 혹은 소블릿 컨테이너(Web Container, or more strictly Servlet Container) 입니다.[^2]
소블릿은 서버에서 실행되는 자바 프로그램을 의미하고 웹 컨테이너는 이러한 소블릿과 상호작용하는 웹 서버의 구성요소 입니다.
웹 컨테이너는 소블릿의 라이프사이클을 관리하고 URL을 특정 소블릿과 매핑합니다.[^3] (~~무슨말인지는 잘 모르겠당~~)
웹 컨테이너는 소블릿, JSP 등 서버-사이드 코드를 포함하는 파일에 대한 요청을 다루고 요청 및 응답 오브젝트를 생성하고 관리 하는 등의 역할을 합니다. (~~역시 무슨말인지 모르겠당~~)
결국, tomcat을 WAS로 혼동하는 이유는 웹 컨테이너가 웹서버의 구성요소이고 흔히 WAS에 이러한 웹서버가 포함되어있기 때문입니다.[^4]


#아파치 vs 톰캣
아파치는 아파치 http 서버 (Apache HTTP Server, httpd)의 줄임말로서 쓰이고 있습니다.
그러나 사실 아파치의 본래 의미는 아파치 소프트웨어 파운데이션(Apache Software Foundation, ASF)입니다. 
ASF에서는 현재 350개가 넘는 오픈소스 프로젝트를 진행하고 있는데 Apache Hadoop, Apache Spark 등 개발한 소프트웨어 앞에 아파치라는 이름을 붙여 명명하고 있습니다.
ASF에서 개발한 오픈소스 소프트웨어 중에서 가장 유명한 것이 바로 아파치 httpd이기 때문에
아스피린이나 에프킬라처럼 아파치는 개발한 기관명이지만 웹서버를 지칭하는 고유명사처럼 사용됩니다.
그런데 더욱 재미있는 것은 톰캣 역시 아파치 프로젝트중 하나이기 때문에 정식 명칭은 아파치 톰캣 (Apache Tomcat)이 된다는 것입니다.
정리해 보면 아파치 httpd와 아파치 톰캣 모두 아파치 프로젝트이지만 실무자들 사이에서 
간단하게 아파치와 톰캣으로 불린다는 것입니다.

앞에 정리한 바에 따르면 아파치 httpd는 웹서버이고 아파치 톰캣은 웹 컨테이너 입니다.
그러나 아파치 톰캣은 웹 서버와 결합하여 쓰이고 그 결합체가 WAS이므로 WAS라고 이야기해도 틀리지는 않을 것 같습니다.

*reference*
[^1]: https://www.nginx.com/resources/glossary/application-server-vs-web-server/
[^2]: https://en.wikipedia.org/wiki/Apache_Tomcat
[^3]: https://en.wikipedia.org/wiki/Web_container
[^4]: https://stackoverflow.com/questions/936197/what-is-the-difference-between-application-server-and-web-server
[^5]: http://www.differencebetween.net/technology/difference-between-apache-and-tomcat/