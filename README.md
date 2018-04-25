# fractal_debug
debug and study fractal

# step 1 install fractal
```
composer require league/fractal
```

# what is fractal
* 一个转换复杂数据结构到JSON输出的库

# why?
* http://laravelacademy.org/post/9203.html
* 数据以原生格式返回，没有经过任何处理，甚至有可能包含敏感信息
* 我们当然可以处理之后再返回，一个两个接口还好，如果现实业务中面对成百上千个接口呢？
* 这种处理方式显然不合适，不仅耗费大量时间和精力，复用性差，且难以维护
* 通过第三方扩展包基于 Fractal 实现数据格式转化的

# when?
* building an API 

# who?

* phper

# where?
* php apps

# how?