You are GitHub Copilot AI to help computer professionals to wrtie code. You always think step by step before writing code.

---

```html
Write an HTML SPA.  

<CodeStyle>
1. Use `<link rel="stylesheet" href="https://unpkg.com/mvp.css"> `. Its slogan is "No class names, just semantic HTML". So please have a good sense of design with semantic HTML.
2. Be concise. When there's only one line in a JS bracket block, write it as oneliner; remove whitespace around symbols like "[{]}," for a compact view.
3. Write onclick (or similar) attributes to bind js function in HTML to avoid addEventListener in `<script>`.
4. Preferred ES6 features: arrow function, template literals
5. Unfavored ES6 features: `const`: use `var` instead to avoid TDZ performance issue, unless inside for{}, if{}.
6. You may define help functions like `var $=id=>document.getElementById(id);` for a small code size, if document.getElementById is used for multiple times.
</CodeStyle>

<Example>
<!DOCTYPE html><html lang="en"><head>
  <meta name="viewport" content="width=device-width, initial-scale=1" /><meta charset="utf-8" />
  <title>HTML SPA General Template</title>
  <link rel="stylesheet" href="https://unpkg.com/mvp.css">
  <style>
    main { display: grid; grid-template-columns: 1fr auto 1fr; gap: 10px; }
    .buttons { display: flex; flex-direction: column; align-items: center; justify-content: center;}
    textarea { height: 300px; resize: vertical; }
  </style>
</head><body>
<main>
  <textarea id="inputArea" placeholder="Input"></textarea>
  <div class="buttons">
      <button id="goBtn" onclick="main(this)">Go</button>
      <button id="copyBtn" onclick="copyOutput()" disabled>Copy Output</button>
  </div>
  <textarea id="outputArea" placeholder="Output" readonly></textarea>
</main>
  <script>
    // utils
    var ebus={events:{},on(s,t){this.events[s]||(this.events[s]=[]),this.events[s].push(t)},emit(s,t){this.events[s]&&this.events[s].forEach(i=>i(t))},off(s,t){this.events[s]&&(this.events[s]=this.events[s].filter(i=>i!==t))}}; //ebus.on('dataLoaded', (data) => console.log('Data loaded:', data)); ebus.emit('dataLoaded',{k:'v'});
    var $=s=>document.querySelector(s),$$=s=>Array.from(document.querySelectorAll(s));
    var newElm=(tag, p)=>Object.assign(document.createElement(tag), p), css=(e, sty)=>Object.assign(e.style, sty);
    var on=(p,ev,sel,cb)=>{p.addEventListener(ev,e=>{if(e.target.closest(sel))cb(e,e.target.closest(sel))})}, onAll=(el, ev, cb)=>el.forEach(e => e.addEventListener(ev,cb));//for simple case, use <a onclick="" />
    var get=url=>fetch(url).then(r=>r.json()), post=(url,d)=>fetch(url,{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify(d)}).then(r=>r.json());
    var debounce=(f,d)=>{let t;return(...a)=>{clearTimeout(t);t=setTimeout(()=>f(...a),d)}}, throttle=(f,d)=>{let t=false;return(...a)=>{if(t)return;t=true;f(...a);setTimeout(()=>t=false,d)}}, store=(k,v)=>v===undefined?JSON.parse(localStorage.getItem(k)):localStorage.setItem(k,JSON.stringify(v));
    var log = console.log;

    var inputArea=$('inputArea'), outputArea=$('outputArea'), copyBtn=$('copyBtn');
    var copyOutput=()=> navigator.clipboard.writeText(outputArea.value);
    var dropHandler=ev=>{ ev.preventDefault(); inputArea.value = ev.dataTransfer.files[0].name; }
    var dragOverHandler=ev=>ev.preventDefault();
  </script>
</body></html>
</Example>

<Demand>

</Demand>
```

---

```html
Write an HTML SPA.  

<CodeStyle>
1. Use `<link rel="stylesheet" href="https://unpkg.com/mvp.css"> `. Its slogan is "No class names, just semantic HTML". So please have a good sense of design with semantic HTML.
2. Be concise. When there's only one line in a JS bracket block, write it as oneliner; remove whitespace around symbols like "[{]}," for a compact view.
3. Write onclick (or similar) attributes to bind js function in HTML to avoid addEventListener in `<script>`.
4. Preferred ES6 features: arrow function, template literals
5. Unfavored ES6 features: `const`: use `var` instead to avoid TDZ performance issue, unless inside for{}, if{}.
6. You may define help functions like `var $=id=>document.getElementById(id);` for a small code size, if document.getElementById is used for multiple times.
</CodeStyle>

<Template>
<!DOCTYPE html><html lang="en"><head>
  <meta name="viewport" content="width=device-width, initial-scale=1" /><meta charset="utf-8" />
  <title>HTML SPA General Template</title>
  <link rel="stylesheet" href="https://unpkg.com/mvp.css">
  <style>
    main { display: grid; grid-template-columns: 1fr auto 1fr; gap: 10px; }
    .buttons { display: flex; flex-direction: column; align-items: center; justify-content: center;}
    textarea { height: 300px; resize: vertical; }
  </style>
</head><body>
<main>
  <textarea id="inputArea" placeholder="Input"></textarea>
  <div class="buttons">
      <button id="goBtn" onclick="main(this)">Go</button>
      <button id="copyBtn" onclick="copyOutput()" disabled>Copy Output</button>
  </div>
  <textarea id="outputArea" placeholder="Output" readonly></textarea>
</main>
  <script>
    var $=id=>document.getElementById(id), $$=s=>document.querySelectorAll(s);
    var inputArea=$('inputArea'), outputArea=$('outputArea'), copyBtn=$('copyBtn');
    var copyOutput=()=> navigator.clipboard.writeText(outputArea.value);
    var dropHandler=ev=>{ ev.preventDefault(); inputArea.value = ev.dataTransfer.files[0].name; }
    var dragOverHandler=ev=>ev.preventDefault();
  </script>
</body></html>
</Template>

<Demand>

</Demand>
```

---

#### To change, modify, tune, add feature etc

```
requirements: DO NOT change code style. Keep where one-liner one-liner; keep compact and concise.
```
