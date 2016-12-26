## RxJS 中文 （翻译中）

基于 JavaScript 的 ReactiveX 库。

本项目是对 [Reactive-Extensions/RxJS](http://reactivex.io/rxjs/) 的重写，在适当的时候会将其取代。
本项目的目的是追求更好的性能、更清晰的模块化、更方便的调用堆栈信息，同时，本项目精简了 API 数量，可能会造成对旧版本不完全兼容，但我们会最大限度地做到向后兼容。

### 安装 RxJS

你可以使用 npm 或者 CDN 来安装 RxJS

### 了解 RxJS

通过阅读本手册的相关章节来了解 __被观察者（Observables）__、__观察者（Observables）__ 和 __对象（Subject，注意不是 Object）__ 等概念

### RxJS 手册

如果你想对各个操作器有详细的了解，可以查看手册

### RxJS 示例

如果你想看看用 RxJS 写的实际的例子，可以看看我们提供的教程

----

### 快速查找操作器

如果你不知道该使用哪个操作器，那么下面这个小程序能帮你：

* 我已经有一个被观察者了……
    * 我想改变每一个被发出的值
    * 我想从发出的值中挑出一个的属性
    * 我想在不影响原有的值得情况下使用这些值
    * 我只想要其中一部分值
    * 我想删掉一些值
    * 我想在所有的值上面做一些计算
    * 我想对其元数据进行加工
    * 如果一段时间没有交互
        * 我想让它报错
        * 我想让它变成另一个被观察者
    * 我只希望它发出一个值
        * 你需要的操作器是 single
    * 我想知道它发出了多少个值
    * 我想在最开始插入一个值
    * 我想推迟它
    * 我想对值进行分组
    * 我想让每个值变成一个新的被观察者
    * 我想在不打断链式调用的前提下，对它进行一些操作
    * 我想分享订阅 
        * 通过一个常规对象
        * 通过一个行为对象
        * 通过一个重播对象
        * 通过一个异步对象
        * 使用一个自定义的对象
        * 让它表现得想一个缓存
            * 那么你需要的是 cache 
    * 当出现一个错误时
        * 我想创建一个新的被观察者
        * 我想重新订阅
    * 当它完成时
        * 我想重新订阅
        * 我想创建一个新的被观察者
    * 当它完成、出错或被取消订阅时，我想执行一个函数回调
        * 你需要 finally
    * 我想要改变行程（何时开始、何时结束等）
        * 改变的是订阅
        * 改变的是值
    * 我想将它与其他被观察者结合起来
        * 只从第一个发出值得被观察者那里获取值
            * 你需要 race
        * 我希望得到任意一个被观察者的值
            * 你需要 merge
        * 我想对值进行操作后，再发出值 
            * 每次发出值时，我要用到每个被观察者最后的值
                * 你需要 combineLatest
            * 只有在它发出值时，我才要用到每个被观察者最后的值
                * 你需要 withLatestFrom
            * 每个值只用一次
                * 你需要 zip
* 我已经有多个被观察者了，我想把他们组合成一个被观察者……
    * 我希望只从第一个发出值得被观察者那里获取值
        * 你需要 race
    * 当它们都结束时，我希望得到通知
        * 你需要 forkJoin
    * 我希望得到任意一个被观察者的值
        * 你需要 merge
    * 我想对值进行操作后，再发出值 
        * 每次发出值时，我要用到每个被观察者最后的值
            * 你需要 combineLatest
        * 每个值只用一次
            * 你需要 zip
    * 我想对它们按顺序进行订阅
        * 你需要 concat
* 我需要创建一个被观察者……
    * 一个新的被观察者
        * 通过自定义的逻辑来创建
            * 你需要 create
        * 通过一个状态机来创建
            * 你需要 generate
        * 用来抛出一个错误
            * 你需要 throw
        * 会结束，但是不发出任何值
            * 你需要 empty
        * 什么都不发出
            * 你需要 never
        * 从现有的事件中创建
            * 来自 DOM 或者 Node.js 等的事件
                * 你需要 fromEvent
            * 使用 API 来添加或删除事件处理函数
                * 你需要 fromEventPattern
        * 从 ES6 的 Promise 中创建
            * 你需要 fromPromise
        * 从一个 Promise 或者事件源或者一个数组中创建
            * 你需要 from
        * 它会迭代（iterates）
            * 遍历一个数组
                * 你需要 fromArray
            * 遍历一个数字区间
                * 你需要 range
            * 遍历你给定的参数
                * 你需要 of
        * 根据定时器来发出值
            * 每隔一段时间发出值
                * 你需要 interval
            * 一段时间后发出值
                * 你需要 timer
        * 当它被订阅时才按需创建
            * 你需要 defer
    * 将回调转化为被观察者
        * 普通回调风格的 API
            * 你需要 bindCallback
        * Node.js 回调风格的 API
            * 你需要 bindNodeCallback


<script>
var uls = document.querySelectorAll('ul')
var ul = uls[uls.length - 1]
console.log(ul)
</script>

----

提示：打开开发者工具你就能体验 RxJS 了。
