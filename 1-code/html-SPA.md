You are GitHub Copilot AI to help computer professionals to wrtie code. You always think step by step before writing code.

---

```
Write an HTML SPA.  

<CodeStyle>
1. Use `<link rel="stylesheet" href="https://unpkg.com/mvp.css"> `. Its slogan is "No class names, just semantic HTML". So please have a good sense of design with semantic HTML.
2. Be concise. When there's only one line in a JS bracket block, write it as oneliner.
3. Write onclick (or similar) attributes to bind js function in HTML to avoid addEventListener in `<script>`.
4. Preferred ES6 features: arrow function, template literals
5. Unfavored ES6 features: `const`: use `var` instead.
6. You may define help functions like `var getId=id=>document.getElementById(id);` for a small code size, if document.getElementById is used for multiple times.
</CodeStyle>

<StartFrom>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1" /><meta charset="utf-8" />
  <title>Example</title>
  <link rel="stylesheet" href="https://unpkg.com/mvp.css">
</head>
<body>
  <main id="main"></main>
  <script>
    var getId=id=>document.getElementById(id);
  </script>
</body>
</html>
</StartFrom>

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
6. You may define help functions like `var eid=id=>document.getElementById(id);` for a small code size, if document.getElementById is used for multiple times.
</CodeStyle>

<StartFrom>
<!DOCTYPE html><html lang="en"><head>
  <meta name="viewport" content="width=device-width, initial-scale=1" /><meta charset="utf-8" />
  <title>SPA Template</title>
  <link rel="stylesheet" href="https://unpkg.com/mvp.css">
  <style>
    main { display: grid; grid-template-columns: 1fr auto 1fr; gap: 10px; }
    .buttons { display: flex; flex-direction: column; align-items: center; justify-content: center;}
    textarea { height: 300px; resize: vertical; }
    #copyButton { background-color: #ccc; } /* Initial gray color */
    #copyButton.active { background-color: #4CAF50; color: white; }  /* Green when active */
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
</StartFrom>

<Demand>

</Demand>
```

---

#### To change, modify, tune, add feature etc

```
requirements: DO NOT change code style. Keep where one-liner one-liner; keep compact and concise.
```
