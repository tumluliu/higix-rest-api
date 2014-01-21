# Affilicated resources

## jobs

`jobs/4321`
`jobs/4321/tasks`
`jobs/4321/tasks/0`

_sample URL:_
`http://api.higix.org/jobs/4321`

## catalogs

* methods

  POST, DELETE, PUT, GET

## tags

* methods

  POST, DELETE, PUT, GET

## users

* methods
  
  POST, DELETE, PUT, GET

## authorities (relations between roles and apps)

* methods

  POST, DELETE, PUT, GET

## roles

* methods

  POST, DELETE, PUT, GET

## tasks (小工具), may be renamed to ...

It is a critical and confusing issue that how to elegantly define jobs (前台的基本提交单元，即hpgc任务), tasks (后台的基本执行单元，即hpc作业), tools, programs, algorithms, plugins and tasks (交互式小工具)?

简单的说，最终用户在higix上执行某种分析计算的过程是向系统提交一个个的计算任务，也就是job，这些jobs都是由一个或多个tasks组成的，其中每个task会对应一个服务器上已经存在的一个可执行程序program，这个程序以串行或者并行的方式实现了某种地理计算算法algorithm。plugin是higis系统在图形化用户界面上将program呈现给用户的一种形式，所以如果从API的角度看，它应该是可有可无的。而小工具，也就是后面乱入的那个task，也和plugin属于同一层次，应该在设计上和plugin统一考虑。

* methods: POST

## symbols

* methods

  POST, DELETE, GET

## tmpfiles

* methods

  POST
