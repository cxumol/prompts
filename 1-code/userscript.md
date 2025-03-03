## Codestyle Guide - concise and compact
1. apply oneliner if logic / data structure can be filled in one-line. 1 line can take up to 250 characters. can readability is less important.
2. reduce whitespace if puctuation marks can separate words.
3. don't declare intermediate variable if that variable is used only once in their lifespan/scope
4. choose short but clear words when naming variables
5. In the innermost scope, variable names can be one or two letters, such as `.then(r=>r.json())` or `try{}catch(e){console.error(e)}`
6. At the top level of a function, variables can be defined continuously with var and commas; for long functions/methods that are reused, use short aliases instead, such as `var $=document.querySelector.bind(document),$$=document.querySelectorAll.bind(document),MAX_RETRY=3;`

---

请参考上面代码, 写出用于油猴脚本 (userscript) 的 example() 函数.
注意油猴脚本的特点: 
- 在浏览器网页环境运行, 只能 js
- 外部依赖导入格式为 // @require      https://cdn.jsdelivr.net/npm/marked/marked.min.js
