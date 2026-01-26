# JavaScript 学习网站 (2026版)

这是一个完整的 JavaScript 学习网站项目，采用2026年最新的 JavaScript 知识和技术实践，适合初学者和进阶开发者。

## 项目结构

```
js-tutorial/
├── index.html                      # 主页
├── css/
│   ├── style.css                   # 主样式文件
│   ├── tutorial.css                # 教程页面样式
│   └── examples.css                # 示例页面样式
├── js/
│   ├── main.js                     # 主页 JavaScript
│   ├── tutorial-1-intro.html       # 第1章: JavaScript 简介 (2026版)
│   ├── tutorial-2-variables.html    # 第2章: 变量和数据类型 (2026版)
│   ├── tutorial-3-functions.html   # 第3章: 函数
│   ├── tutorial-4-arrays-objects.html # 第4章: 数组和对象
│   ├── tutorial-5-conditions.html  # 第5章: 条件语句
│   ├── tutorial-6-loops.html       # 第6章: 循环语句
│   ├── advanced-1-dom.html         # 进阶: DOM 操作
│   ├── advanced-2-events.html      # 进阶: 事件处理
│   ├── advanced-3-es6.html         # 进阶: ES6+ 新特性 (2026完整版)
│   ├── advanced-4-async.html       # 进阶: 异步编程与 Promise
│   ├── advanced-5-typescript.html   # 进阶: TypeScript 基础
│   ├── advanced-6-libraries.html    # 进阶: 常用准标准库
│   ├── advanced-7-bestpractices.html # 进阶: 最佳实践
│   └── advanced-8-patterns.html    # 进阶: 设计模式和代码模式
└── examples/
    ├── calculator.html              # 计算器示例 (ES6类实现)
    ├── todo.html                    # 待办事项示例 (现代化实现)
    ├── clock.html                   # 时钟示例
    └── slideshow.html               # 图片轮播示例
```

## 功能特点

### 基础教程 (6章)
1. **JavaScript 简介 (2026版)** - JavaScript 的现代生态、全栈能力、AI 集成
2. **变量和数据类型 (2026版)** - const/let 最佳实践、解构、可选链、空值合并
3. **函数** - 箭头函数、参数、作用域、回调函数
4. **数组和对象** - 数据结构、Map/Set、解构和展开
5. **条件语句** - if-else、switch、逻辑运算符
6. **循环语句** - for、while、do-while、for...of、for...in

### 进阶教程 (8章)
1. **DOM 操作** - 操作页面元素
2. **事件处理** - 处理用户交互事件
3. **ES6+ 新特性 (2026版)** - 箭头函数、解构、模板字符串、类、私有字段、实用类型工具
4. **异步编程** - Promise、async/await、Promise 并发、AbortController
5. **TypeScript 基础** - 类型系统、泛型、实用类型
6. **常用准标准库** - Lodash、Day.js、Zod、Dexie、Nanoid等
7. **最佳实践** - 代码质量、性能优化、安全性、测试
8. **设计模式和代码模式** - 单例、工厂、观察者、策略、装饰器等

### 实战示例 (4个)
1. **计算器** - ES6 类实现，事件委托，键盘支持
2. **待办事项** - 完整 Todo List，localStorage 持久化，crypto.randomUUID()
3. **时钟显示** - 实时时钟，12/24小时制切换
4. **图片轮播** - 自动轮播效果，支持手动切换和暂停

## 技术特点

### 2026年最新特性
- **ES2022-2026 特性** - 私有字段、类静态块、Object.hasOwn、数组 at() 方法
- **现代异步模式** - Promise.allSettled、Promise.any、AbortController
- **类型安全** - JSDoc 类型提示，TypeScript 基础
- **模块化** - ES Modules
- **现代 API** - crypto.randomUUID()、structuredClone()

### 开发最佳实践
- 优先使用 `const`，必要时使用 `let`
- 避免使用 `var`
- 使用箭头函数
- 使用解构和展开运算符
- 使用可选链 `?.` 和空值合并 `??`
- 使用 async/await 处理异步
- 使用类进行面向对象编程
- 使用事件委托处理大量元素
- 数据持久化到 localStorage

### UI/UX
- 纯 HTML/CSS/JavaScript，无需构建工具
- 响应式设计，支持移动端
- 现代化的渐变色和动画效果
- 清晰的代码注释和示例
- 交互式学习体验

## 使用方法

1. 直接在浏览器中打开 `index.html`
2. 点击首页的教程卡片开始学习
3. 查看示例页面学习实际应用
4. 参考代码实现自己的项目

## 浏览器兼容性

- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## 学习建议

1. 按顺序学习基础教程，特别是更新后的第1、2章
2. 重点学习进阶教程中的 ES6+ 新特性和异步编程
3. 每学完一章，尝试自己编写代码
4. 查看示例页面，理解2026年的现代编程模式
5. 使用 crypto.randomUUID() 代替 Date.now()
6. 使用可选链 `?.` 和空值合并 `??`
7. 使用 const/let 代替 var
8. 使用 async/await 代替 Promise chains

## 2026年 JavaScript 生态

### 运行时
- Node.js (LTS)
- Deno
- Bun (超快 JavaScript 运行时)

### 框架
- React 19+
- Vue 3.5+
- Svelte 5+

### 工具
- Vite 6+
- TypeScript 5.7+
- npm / pnpm / bun (包管理器)

## 许可证

MIT License

## 更新日志

### 2026版更新
- ✨ 更新所有教程内容到2026年标准
- ✨ 添加 TypeScript 基础教程
- ✨ 添加 ES2022-2026 新特性
- ✨ 更新示例代码使用现代 JavaScript
- ✨ 使用 crypto.randomUUID() 生成 ID
- ✨ 使用 localStorage 数据持久化
- ✨ 使用事件委托处理事件
- ✨ 使用类进行组件化开发
- 🐛 修复示例中的安全漏洞（移除 eval）
- 🐛 修复示例中的 XSS 漏洞