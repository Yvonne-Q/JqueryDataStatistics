####根据jquery.dataStatistics,修改部分源码，使能动态设置最大值和最小值

1. 修改过的javascript，不直接调用run方法，把run方法return出去
```javascript
     /**
     * 执行，增加了2改参数
     * @param max 最大值
     * @param min 最小值
     */
    function run(max, min) {
        var difference = (max || options.max) - (min || options.min);//要执行动画的次数
    }
    
     // run();
        return run;
```
2. 调用方法:
```html
<script>
   const b = $('.dataStatistics').dataStatistics({min: 0, max: 0, len: 3});
    b(200,0); //第一个参数目标值，第二个参数原始值
    b(201,200);  // 再次调用
</script>
```