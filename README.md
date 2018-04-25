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

## concepts
* Resources 
* Transformer

### Resources 
* Resources are objects that represent data
* Two types of resource exist:
  * League\Fractal\Resource\Item - A singular resource, probably one entry in a data store
  * League\Fractal\Resource\Collection - A collection of resources
### Transformer
* an object or callback that will know how to output the data

#### why not callbacks for transformers(using Classes for Transformers)
* limited use
* data will need to be transformed multiple times and in multiple locations
* so creating classes to do this work can save code duplication
#### how to create a Transformer class?
* extend League\Fractal\TransformerAbstract
* contain at the very least a method with the name transform().
#### how to use the Transformer?
* Once the Transformer class is defined, it can be passed as an instance in the resource constructor.
```
$resource = new Fractal\Resource\Item($book, new BookTransformer);
$resource = new Fractal\Resource\Collection($books, new BookTransformer);
```
