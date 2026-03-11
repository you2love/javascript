# 后端开发者 JavaScript 学习指南

## 一、思维转变

### 1. 单线程异步模型
后端熟悉的可能是多线程/多进程模型，但 JS 是**单线程事件驱动**：

```javascript
// 阻塞思维（后端常见）
result = db.query(sql);  // 线程阻塞等待
process(result);

// 异步思维（JS）
db.query(sql, (err, result) => {  // 不阻塞，回调处理
    process(result);
});

// 现代写法：async/await（类似同步代码）
const result = await db.query(sql);
process(result);
```

### 2. 原型链 vs 类
```javascript
// 后端熟悉的类
class User {
    constructor(name) {
        this.name = name;
    }
}

// JS 本质是原型链
// User.prototype 是所有实例共享的原型
```

### 3. 弱类型 vs 强类型
```javascript
// 动态类型，运行时才检查
let x = 1;
x = "string";  // 合法

// TypeScript 解决这个问题
let x: number = 1;
x = "string";  // 编译错误
```

## 二、核心概念速通

### 1. 闭包（Closure）
函数记住并访问其词法作用域的能力：

```javascript
function createCounter() {
    let count = 0;  // 私有变量
    return {
        increment: () => ++count,
        getCount: () => count
    };
}
// 类似后端的闭包/闭包对象
```

### 2. this 绑定
```javascript
// 箭头函数：this 词法绑定
const obj = {
    value: 42,
    getValue: () => this.value  // undefined，this 指向外层
};

// 普通函数：this 动态绑定
const obj2 = {
    value: 42,
    getValue() { return this.value; }  // 42
};
```

### 3. 解构与展开
```javascript
// 解构（类似后端的 destructuring）
const { name, age } = user;
const [first, ...rest] = array;

// 展开（spread）
const merged = { ...obj1, ...obj2 };
const newArray = [...arr1, ...arr2];
```

### 4. 数组高阶函数
```javascript
// 函数式编程风格
users
    .filter(u => u.active)
    .map(u => u.name)
    .reduce((acc, name) => acc + name, '');
```

## 三、异步编程演进

```javascript
// 1. 回调地狱（避免）
getData((a) => {
    getMoreData(a, (b) => {
        getEvenMoreData(b, (c) => {
            // ...
        });
    });
});

// 2. Promise（链式调用）
getData()
    .then(a => getMoreData(a))
    .then(b => getEvenMoreData(b));

// 3. async/await（推荐，类似同步代码）
try {
    const a = await getData();
    const b = await getMoreData(a);
    const c = await getEvenMoreData(b);
} catch (e) {
    // 错误处理
}

// 4. Promise.all（并发）
const [users, posts] = await Promise.all([
    fetchUsers(),
    fetchPosts()
]);
```

## 四、Node.js 后端开发要点

### 1. 模块系统
```javascript
// ES Module（推荐）
import express from 'express';
export const handler = (req, res) => {};

// CommonJS（旧）
const express = require('express');
module.exports.handler = (req, res) => {};
```

### 2. Event Loop
```
   ┌───────────────────────────┐
┌─>│           timers          │
│  └─────────────┬─────────────┘
│  ┌─────────────┴─────────────┐
│  │     pending callbacks     │
│  └─────────────┬─────────────┘
│  ┌─────────────┴─────────────┐
│  │       poll (I/O)          │
│  └─────────────┬─────────────┘
│  ┌─────────────┴─────────────┐
│  │           check           │
│  └─────────────┬─────────────┘
└──│      close callbacks      │
   └───────────────────────────┘
```

### 3. Stream 流处理
```javascript
// 类似后端的流式处理
readStream
    .pipe(transformStream)
    .pipe(writeStream);
```

## 五、TypeScript 必备

```typescript
// 1. 接口定义
interface User {
    id: number;
    name: string;
    email?: string;  // 可选
}

// 2. 泛型
function identity<T>(arg: T): T {
    return arg;
}

// 3. 类型守卫
function isString(value: unknown): value is string {
    return typeof value === 'string';
}

// 4. 工具类型
type PartialUser = Partial<User>;
type ReadOnlyUser = Readonly<User>;
type UserId = Pick<User, 'id'>;
```

## 六、学习路径建议

| 阶段 | 内容 | 时间 |
|------|------|------|
| 1 | 语法基础（变量、函数、数据类型） | 1-2 天 |
| 2 | 异步编程（Promise、async/await） | 2-3 天 |
| 3 | Node.js 基础 + Express | 3-5 天 |
| 4 | TypeScript 入门 | 2-3 天 |
| 5 | 实战项目 | 1-2 周 |

## 七、常见坑

```javascript
// 1. 变量提升
console.log(x);  // undefined，不是报错
var x = 1;

// 2. 相等比较
[] == []  // false（引用比较）
[] === [] // false
'' == 0   // true（类型转换）

// 3. 默认参数
function f(a = []) {}  // 每次调用新数组，安全

// 4. 事件循环顺序
console.log('1');
setTimeout(() => console.log('2'), 0);
Promise.resolve().then(() => console.log('3'));
console.log('4');
// 输出：1, 4, 3, 2（微任务优先）
```

## 八、推荐资源

1. **MDN Web Docs** - 官方文档
2. **JavaScript 高级程序设计（第 4 版）** - 经典书籍
3. **You Don't Know JS** - 深入理解 JS
4. **Node.js 设计模式** - 后端开发参考
