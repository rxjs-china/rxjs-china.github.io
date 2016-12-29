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
        * 变成一个常量
            * 你需要 [mapTo](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-mapTo)
        * 计算出得出一个新的值
            * 你需要 [map](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-map)
    * 我想从每一个值中挑出一个的属性
        * 你需要 [pluck](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-pluck)
    * 我想在不影响原有的值得情况下使用这些值
        * 你需要 [do](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-do)
    * 我只想要其中一部分值
        * 用自定义的规则来过滤这些值
            * 你需要 [filter](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-filter)
        * 我想要最开始的一些值
            * 只要第一个值
                * 你需要 [first](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-first)
            * 不止一个值
                * 你需要 [take](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-take)
            * 自定义需要哪些值
                * 你需要 [takeWith](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-takeWhile)
        * 我想要第 N 个值
            * 你需要 [elementAt](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-elementAt)
        * 我想要末尾的一些值
            * 只最后一个值
                * 你需要 [last](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-last)
            * 自定义需要哪些值
                * 你需要 [takeLast](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-takeLast)
        * 直到另一个被观察者发出值或结束
            * 你需要 [takeUntil](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-takeUntil)
    * 我想忽略一些值
        * 忽略全部
            * 你需要 [ignoreElements](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-ignoreElements)
        * 忽略开头的值
            * 忽略 N 个
                * 你需要 [skip](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-skip)
            * 自定义忽略哪几个
                * 你需要 [skipWhile](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-skipWhile)
        * 直到另一个被观察者发出值
            * 你需要 [skipUntil](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-skipUntil)
        * 如果某个值重复出现就忽略
            * 值相等就算是重复
                * 重复的两个值必须连续出现
                    * 你需要 [distinctUntilChanged](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-distinctUntilChanged)
                * 重复的两个值不须连续出现
                    * 你需要 [distinct](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-distinct)
            * 值的某个属性相等就算是重复
                * 重复的两个值必须连续出现
                    * 你需要 [distinctUntilKeyChanged](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-distinctUntilKeyChanged)
                * 重复的两个值不须连续出现
                    * 你需要 [distinctKey](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-distinctKey)
        * 忽略出现得太频繁的值
            * 我只需要一个时间窗口内的第一个值
                * 时间窗口由另一个被观察者决定
                    * 你需要 [throttle](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-throttle)
                * 每隔一段时间就算一个时间窗口
                    * 你需要 [throttleTime](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-throttleTime)
            * 我只需要一个时间窗口内的最后一个值
                * 时间窗口由另一个被观察者决定
                    * 你需要 [audit](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-audit)
                * 每隔一段时间就算一个时间窗口
                    * 你需要 [auditTime](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-auditTime)
            * 在一段静默期后发出最后一个值
                * 静默期由另一个被观察者决定
                    * 你需要 [debounce](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-debounce)
                * 静默期由时间决定
                    * 你需要 [debounceTime](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-debounceTime)
    * 我想在所有的值上面做一些计算
        * 然后只发出一个值
            * 你需要 [reduce](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-reduce)
        * 然后对应地发出每一个计算后的值
            * 你需要 [scan](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-scan)
        * 然后对应地发出每一个计算后的值，这个值是一个嵌套的被观察者(a nested Observable)
            * 你需要 [mergeScan](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-mergeScan)
    * 我想对其元数据进行加工
        * 将 next, error, complete 这些事件都变成通知
            * 你需要 [materialize](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-materialize)
        * 我要知道每个值之间的时间间隔
            * 你需要 [timeInterval](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-timeInterval)
    * 如果一段时间没有发出值
        * 我想让它报错
            * 你需要 [timeout](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-timeout)
        * 我想订阅另一个被观察者
            * 你需要 [timeoutWith](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-timeoutWith)
    * 我只希望它发出一个值
        * 你需要 [single](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-single)
    * 我想知道它发出了多少个值
        * 你需要 [count](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-count)
    * 我想在最开始插入一个值
        * 你需要 [startWidth](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-startWith)
    * 我想推迟它
        * 我给定推迟时间
            * 你需要 [delay](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-delay)
        * 推迟时间由另一个被观察者决定
            * 你需要 [delayWhen](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-delayWhen)
    * 我想对值进行分组
        * 等它结束后再分组
            * 把所有值变成一个数组
                * 你需要 [toArray](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-toArray)
            * 把所有值变成一个 Promise 对象
                * 你需要 [toPromise](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-toPromise)
        * 每个值与前一个值算一组
            * 你需要 [pairwise](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-pairwise)
        * 用一个规则把所有值分成两组
            * 你需要 [partition](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-partition)
        * 每 N 个值分一组
            * 将这 N 个值作为一个数组发出
                * 你需要 [bufferCount](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-bufferCount)
            * 将这 N 个值作为一个被观察者发出
                * 你需要 [windowCount](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-windowCount)
        * 每隔一段时间分一组
            * 将每组值作为一个数组发出
                * 你需要 [bufferTime](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-bufferTime)
            * 将每组值作为一个被观察者发出
                * 你需要 [windowTime](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-windowTime)
        * 根据另一个被观察者的发出动作来分组
            * 将每组值作为一个数组发出
                * 你需要 [buffer](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-buffer)
            * 将每组值作为一个被观察者发出
                * 你需要 [window](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-window)
        * 根据一个按需生成的被观察者的发出动作来分组
            * 将每组值作为一个数组发出
                * 你需要 [bufferWhen](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-bufferWhen)
            * 将每组值作为一个被观察者发出
                * 你需要 [windowWhen](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-windowWhen)
        * 用另一个被观察者 A 来开始分组，再用另一个被观察者 B 来结束分组
            * 将每组值作为一个数组发出
                * 你需要 [bufferToggle](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-bufferToggle)
            * 将每组值作为一个被观察者发出
                * 你需要 [windowToggle](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-windowToggle)
        * 根据值分组
            * 你需要 [groupBy](http://reactivex.io/rxjs/class/es6/Observable.js~Observable.html#instance-method-groupBy)
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
