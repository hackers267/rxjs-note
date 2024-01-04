# 常用操作

# 一个Observabe根据另一个Observable生成

在有时候，我们会遇到，当点击一个按钮后，记数器重新记数，或者是当我们在搜索的时候，当我们使用新的关键字搜索后，分页重新从1开始这样的场景，这个时候，使用 *rxjs* 的 *switchMap* 操作符可以为我们解决问题。如下：

```javascript
import { switchMap,formEvent, interval, map } from "rxjs";

const btn = document.getElementById('id');
const click$ = formEvent(btn, "click").pipe((x,y)=>({x,y}));
const interval$ = interval(1000);

click$.pipe(
  switchMap(({x,y})=>{
    return interval$.pipe(
      map((i)=>{
        return {
          i,
          x,
          y
        }
      })
    )
  })
).subscrbe(console.log)

```

类似的应用场景可以根据上面的代码进行修改。
