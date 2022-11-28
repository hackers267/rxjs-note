# 基础概念

`rxjs`的介绍之有有这么一个内容，
> Think of RxJs as Lodash for events.

也就是说，对于事件，使用了`rxjs`就可以像`lodash`一样思考了。在`rxjs`中，有几个重要的概念，其中包括:

- `Observable` 被观察者或者被订阅者
- `Obserser`(观察者或者订阅者)
- `Subscription` 订阅
- `Operators` 操作符
- `Subject`
- `Schedulers`

在这几个中，最基础的就应该是`Observable`，`Observser`和`Operators`了。在以后的内容的，我们不再翻译*Observable*和*Observer`。

## Observable

`Observable`是产生数据的地方，其产生的数据可以直接或间接的被`Observer`消费。`Observable`还可以通过`Operators`的*筛选*,
*合并*,*拆分*等转换为其它的`Observable`。

## Observer

`Observer`是消费数据的地方，一个`Observable`只有被`Observer`消费之后，其才有意义。

## Operators

`Operators`是RxJs中最复杂的一部分内容。其的复杂度在于其API的数量多，包括:

- 创建`Observable`
- 筛选`Observable`
- 合并`Observable`
- 拆分`Observable`

