# From

From操作符是`RxJs`中最常使用的创建操作符之一，其可以从一个`数组`,`类数组`,`对象数组`,`Promise`和`可迭代对象`
等创建一个`Observable`。(From操作符还可以从一个字符串创建一个Observable，其把字符串当作一个由字符组成的数组)。

其签名如下：

```
from<T>(input: ObservableInput<T>, scheduler?: SchedulerLike): Observable<T>
```

示例1:

```ts
import {from} from 'rxjs';

const array = [10, 20, 30];
const result = from(array);

result.subscribe(x => console.log(x));

// Logs:
// 10
// 20
// 30
```

示例2:

```ts
import {from} from 'rxjs';

const promise = Promise.resolve("success");

const result = from(promise);

result.subscribe(x => console.log(x));

// Logs:
// success
```

示例3:

```ts
import {from} from 'rxjs';

const reject = Promise.reject("Error");
const result = from(reject);

result.subscribe({
    error(err) {
        console.log(err);
    }
})

// Logs:
// Error
```

通过上面的代码，我们可以知道，在从`数组`,`类数组`中生成Observable的时候，会触发`next`方法，而如果是从一个`Promise`
对象中转换，如果`Promise`成功`resolve`后，其触发`next`方法，但如果`reject`后，会导致`error`方法。
