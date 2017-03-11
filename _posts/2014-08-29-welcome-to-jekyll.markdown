---
layout: post
title:  "Welcome to Jekyll!"
date:   2014-08-29 14:34:25
categories: jekyll update
tags: featured
image: /assets/images/2014-08-29-welcome-to-jekyll/desktop.JPG
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve --watch`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

{% highlight js %}

<footer class="site-footer">
 <a class="subscribe" href="{{ "/feed.xml" | prepend: site.baseurl }}"> <span class="tooltip"> <i class="fa fa-rss"></i> Subscribe!</span></a>
  <div class="inner">a
   <section class="copyright">All content copyright <a href="mailto:{{ site.email}}">{{ site.name }}</a> &copy; {{ site.time | date: '%Y' }} &bull; All rights reserved.</section>
   <section class="poweredby">Made with <a href="http://jekyllrb.com"> Jekyll</a></section>
  </div>
</footer>
{% endhighlight %}


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help





서비스 스케줄러는 클러스터 내의 컴퓨팅 리소스를 관리하고 사용자 애플리케이션을 어느 호스트에서 서비스할지 결정하는 시스템 소프트웨어입니다. 컨테이너 스케줄러로는 [kubernetes](https://kubernetes.io/)나 [docker swarm](https://www.docker.com/products/docker-swarm)등이 있으며, 하둡 스케줄러로는 [YARN](https://hadoop.apache.org/docs/current/hadoop-yarn/hadoop-yarn-site/YARN.html)이 많이 사용됩니다.

이 글에서는 이러한 스케줄러 중 하나인 [nomad](https://www.nomadproject.io/)를 소개합니다. [nomad](https://www.nomadproject.io/)는 [vagrant](https://www.vagrantup.com/), [consul](https://www.consul.io/), [packer](https://www.packer.io/)등의 시스템 소프트웨어로 유명한 [hashicorp](https://www.hashicorp.com/)사의 오픈소스 소프트웨어로, 자사의 [consul](https://www.consul.io/)과 [vault](https://www.vaultproject.io/)를 각각 service discovery와 secure storage에 사용합니다. hashicorp사는 자사의 웹페이지에서 nomad를 통해 5000개 호스트에 100만 개 컨테이너를 5분 만에 배포한 사례를 소개하고 있습니다.([Nomad Million Container Challenge](https://www.hashicorp.com/c1m.html))

