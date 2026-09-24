# js基础实战2-排错题-题目

==请说出以下代码都错在哪里，以及书写正确的代码==

## JS代码书写位置

```html
<script src="./02.js">
    alert('弹框出现')
</script>
```

分析错误：
   <!-- script标签一旦设置的src属性，则里面代码不运行   -->
正确写法：
<script>
    alert('弹框出现')
</script>


```js

```





## 输出语句

```js
prompt(请输入您的姓名)
```

分析错误：
    <!-- 请输入您的姓名 是字符内容，需要有引号包裹，否则会被当成变量 -->
正确写法：
   <script>
      prompt('请输入您的姓名')
    </script>
```js

```





## 变量01

```js
let age = 18
let age = 19
```

分析错误：
    <!-- let 不允许重复声明同一个变量多次 -->
正确写法：
   <script>
      // 使用let 不允许重复声明同一个变量多次
      let age = 18
      //   let age = 19
      let ageNew = 19
    </script>




## 变量02

```js
console.log(age)
let age = 18
```

分析错误：
      <!-- // let 不能在声明变量之前先使用变量 -->
正确写法：
    <script>
      let age1 = 18
      console.log(age1)
    </script>
```js

```







## 字符串01

```js
let username = 张三
```

分析错误：
      <!-- // 张三 是字符串，需要使用引号包裹 -->
正确写法：
    <script>
    let username = '张三'
    </script>

```js

```







## 字符串02

```js
let uname = '张三"
```

分析错误：
      <!-- // 引号不能这样混搭  引号是成对出现的 -->
正确写法：
    <script>
      let uname1 = '张三'
      let uname2 = '张三'
      let uname3 = `张三`
    </script>
```js

```







## 数组

```js
// 需求：取出 星期六 

let arr = ['星期一', '星期二', '星期三', '星期四', '星期五', '星期六', '星期日']
console.log(arr[6])
```

分析错误：
      <!-- //   数组的下标是从0开始的，所以星期六的对应下标是5 -->
正确写法：
    <script>
      let arr4 = ['星期一','星期二','星期三','星期四','星期五','星期六', '星期日',]
      console.log(arr[5])
    </script>



```js

```









## 自增

```js
// 让num自身增加1

let num = 10

num + 1
```

分析错误：
      <!-- //   num + 1自增后的结果需要重新赋值修改num。  以上缺少对num的重新赋值 -->
正确写法：
  <script>
      let num5 = 10
      num5 = num5 + 1
    </script>


```js

```









## switch分支

```js
let num = prompt('请输入一个数字')

switch (num) {
    case 1:
        alert('用户您输入的是数字1')
    case 2:
        alert('用户您输入的是数字2')
    case 3:
        alert('用户您输入的是数字3')
    default:
        alert('用户您输入的是非1、2、3的数字')
}
```

分析错误：
  <!-- // 1. switch语句中缺少 break，会有穿透问题
      // 2. switch是进行全等比较，num变量存的是字符串类型数据，和case的值1 2 进行比较，是不成立的。 -->
正确写法：
<script>
    let num6 = +prompt('请输入一个数字')
      switch (num6) {
        case 1:
          alert('用户您输入的是数字1')
          break
        case 2:
          alert('用户您输入的是数字2')
          break
        case 3:
          alert('用户您输入的是数字3')
          break
        default:
          alert('用户您输入的是非1、2、3的数字')
          break
      }
    </script>
```js

```







## while循环

```js
let num = 1
while (num <= 5) {
    document.write(`月薪过万不是梦<br/>`)
}
```

分析错误：
      <!-- // 1. 以上代码缺少 num变量的变化量 num++
      // 2. 会导致 num一直都是1
      // 3. while条件一直是满足的情况
      // 4. while是个死循环 -->
正确写法：
<script>
    let num = 1
    while (num <= 5) {
        document.write(`月薪过万不是梦<br/>`)
        num++
    }
</script>
```js

```









## for循环

```js
for (let i = 1; i <= 3;) {
    document.write(`月薪过万不是梦 <br/>`)
}
```

分析错误：
   <!-- //   for循环中缺少 i变量变化量  i++ -->
正确写法：
   <script>
      for (let i = 1; i <= 3; i++) {
        document.write(`月薪过万不是梦 <br/>`)
      }
    </script>
```js

```







## 遍历数组

```js
// 需求：取出数组中的每一项

let arr = ['马超', '赵云', '张飞', '关羽', '黄忠', '小黑', '小红']

for (let i = 1; i < arr.length; i++) {
    console.log(arr[i])
}
```

分析错误：
      <!-- //  数组的下标从0开始，所以for循环遍历数组，i需要从0开始 -->
正确写法：
 <script>
      let arr = ['马超', '赵云', '张飞', '关羽', '黄忠', '小黑', '小红']
      for (let i = 0; i < arr.length; i++) {
        console.log(arr[i])
      }
    </script>
```js

```







## 修改数组的项

```js
// 需求：将数组中的小白修改成 小灰灰
let arr = ['小黑', '小白', '小红']

arr = '小灰灰'
```

分析错误：
      <!-- // 原本arr10变量存数组，现在存字符串小灰灰
      // arr10 = '小灰灰'
      // 语法： 数组名[下标] = 新值 -->
正确写法：
    <script>
      let arr = ['小黑', '小白', '小红']
      arr[1] = '小灰灰'
    </script>
```js

```







## 操作数组

```js
// 需求：在数组arr的最后面添加 blue

let arr = ['red', 'green']

arr.push = 'blue'
```

分析错误：
      <!-- // 数组的push是个方法，需要加 小括号 来使用, 而不是赋值操作
      // arr.push('blue')
      // 语法：数组.push(数据1, 数据2, ...) -->
正确写法：
    <script>
      let arr = ['red', 'green']
      arr.push('blue')
    </script>
```js

```







## 对象

```js
// phone 手机对象

let phone = {
    size = 6.1
    play = function () {
        console.log('走起，吃鸡')
    }
}
```

分析错误：
      <!-- //  对象是有属性和方法组成，属性名和属性值，
      // 方法名和函数之间都是冒号隔开，并且属性和方法之间需要有逗号隔开 -->
正确写法：
    <script>
      let phone = {
        size: 6.1,
        play: function () {
          console.log('走起，吃鸡')
        },
      }
    </script>
```js

```







## 遍历对象

```js
let obj = {
    uname: '小明',
    age: 18,
    sex: '男',
    height: 200,
}

// 遍历obj对象，取出对象的属性名和属性值
for (let k in obj) {
    console.log(k)
    console.log(obj.k)
}
```

分析错误：
    <!-- // 在for...in 语法中，对象的属性值需要通过 中括号语法才能取出对象的属性值 -->
正确写法：
    <script>
      let obj = {
        uname: '小明',
        age: 18,
        sex: '男',
        height: 200,
      }
      for (let k in obj) {
        console.log(k)
        console.log(obj[k])
      }
    </script>
```js

```









