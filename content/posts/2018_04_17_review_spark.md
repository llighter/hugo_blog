---
title: "리뷰: 9가지 사례로 익히는 고급 스파크 분석"
date: 2018-04-17T00:21:05+09:00
draft: false
---

{{< figure src="/hugo_blog/images/Advanced_Analytics_with_Spark.jpg" width="400" link="http://www.hanbit.co.kr/store/books/look.php?p_code=B2901427500" target="_blank" >}}

이 책은 스파크를 실제 데이터셋을 기반으로 여러가지 사례를 분석하는 내용으로 이루어져 있다.
이 책을 접할 때 까지 스파크나 스칼라에 대해 공부해 본적이 없었다.
먼저, 불편한 점이 있었다면 초심자로서 처음 설치를 하고 세팅을 하는데에 시간이 많이 들었다. 물론 책의 제목에서 알 수 있듯이 **고급(Advanced)** 분석이기 때문에 기본적인 설정이나 사용능력은 갖추어야 한다는 측면에서 볼 때 이 책이 잘못한 점은 없다. 다만 사례를 분석하는 만큼 처음 설정에 시간은 많이 쏟지 않고 내용을 따라갈 수 있다면 스파크에 대해 더 친숙하게 다가갈 수 있을 것이라 생각한다. 
물론 나 같은 경우 [구글 클라우드 플랫폼][1]에 [Compute Engine][2]을 구축하여 예제를 실행하느라 시간이 더 걸린 측면이 있다.

{{< figure src="/hugo_blog/images/compute_engine.png" width="800" >}}

또한, REPL 환경에서 작업했기 때문에 작업을 했기 때문에 연습하면서 실행해 놓은 코드를 저장하지 못하는 점이 있었다. 이는 추후에 [Jupyter Notebook][3]을 설치하면 해결할 수 있을 것이라 생각한다.
{{< figure src="/hugo_blog/images/spark-sql.png" width="800" >}}

컴파일 된 코드를 사용할 때는 vi 환경이 불편했기 때문에 데스크탑에서 작업을 하고 [깃헙][4]을 통해 서버에서 내려받는 방식으로 사용했다.
{{< figure src="/hugo_blog/images/spark-git.png" width="800" >}}
{{< figure src="/hugo_blog/images/spark-load.png" width="800" >}}

물론 이러한 설치과정이나 설정하는 부분들이 이미 완료되어 있다면 이 책은 사례를 중심으로 빠르게 학습하는데에는 좋은 책이라고 생각한다.
책의 전체를 읽을 필요없이 9가지 주제로 이루어져 자신이 원하는 분야를 선택하고 학습할 수 있어서 빠르게 구현해보고 싶은 사람이라면 훌륭한 선택이 될 것이라 생각한다.

이 책은 스파크 자체에 대한 내용을 다루므로 전체 아키텍쳐에 한 부분을 다루는 것이라 할 수 있다.
만약, [ELK 스택][5]을 알고 있다면 하나의 아키텍쳐로 구성할 수도 있을 것 같다.

결론을 말하자면, 기존에 스파크에 대한 지식이 있고 설정이 완료된 상태라면 빠르게 구현해보고 테스트 하기 위한 휼륭한 교재라고 생각한다. 만약 분석 결과를 실제로 서비스 하고 싶다면 위에서 언급한 것과 같이 [ELK 스택][5]과 같은 오픈소스를 활용할 수 있어야 할 것이다.

[1]: https://cloud.google.com/?hl=ko
[2]: https://cloud.google.com/compute/?hl=ko
[3]: http://jupyter.org/
[4]: https://github.com/llighter/demo-spark-analytics
[5]: https://www.elastic.co/kr/elk-stack
