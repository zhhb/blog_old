---
layout: post
title:  "Change blog to Jekyll!"
date:   2015-05-15 10:49:48
categories: hello Jekyll
---
最近终于有点空闲的时间了，好久没写的blog也基本荒废了，思索着hexo的各种不好用，果断的换成了Jekyll

恰好，经过长期在公司里推node.js，有好几个同事开始对node.js产生了兴趣，也正好在github-page上分享一些node.js方面的知识😄

{% highlight javascript %}
// 优秀的人总有共通点😄
var ability = {
    'learning ability'        :'excellent', //学习能力就不说了，时代步伐这么快，
                                            //不学点新东西未来估计就淹死了
    'cognitive ability'       :'excellent', //大家都说认知能力是智商高的表现
    'independent thinking'    :'excellent', //不是有句话叫做 "我思故我在" 嘛
    'problem dealing'         :'excellent', //搞定问题才能愉快的一起玩耍
    'cooperation capabilities':'excellent', //合作就是要让别人和自己都舒服😌
    'management'              :'good'       //管好自己容易，管好别人难～
}

//Don't Mind my poor English, please.
var myself = Object.create(ability,{
    'Profession'      : {
        writable    : true,
        configurable: true,
        enumerable  : true,
        value       : 'Web develop engineer' 
                      //虽然公司给的Title是高级前端，但我还是喜欢Web开发工程师
    },
    'Character'       : {
        writable    : false,
        configurable: false,
        enumerable  : true,
        value       : ['foresight','gentle','mensao'] 
                      //I'm farsighted gentleman！En,it's mensao.
    },
    'Master Techniques': {
        writable    : true, //新知识还是要学的
        configurable: true, //学了还是要常常更新才对
        enumerable  : true, //学了还是要和别人分享的
        value       : {
            'JavaScript':'excellent',
            'Node.js'   :'excellent',
            'JS libs'   :'very good',
            'HTML'      :'excellent',
            'CSS'       :'excellent',
            'brower'    :'good',
            'Java'      :'very good', //我能说我以前是Java developer吗
            'Nginx'     :'good',      //话说这个还是通过大学玩路由器了解的，真的不骗你
            'Tomcat'    :'ok',
            'Jetty'     :'ok',
            'Git'       :'very good', //代码管理全靠它了
            'Subversion':'good',      //什么？你还在用它 😱
            'Bash'      :'good',      //这个大家都知道
            'Mysql'     :'good',
            'Mongodb'   :'ok',        //公司不用啊，都生疏了
            'Oracle DB' :'ok',        //已经成为回忆了
            'SQL Server':'ok'         //用它的一般都是土豪
        }    
    }
});
console.table(myself);
{% endhighlight %}

<!-- Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help -->
