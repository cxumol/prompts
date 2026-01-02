```
<CodeStyle>
While being human-readable, be concise and compact.
1. When there's only one line inside a JS bracket block, write it as oneliner; remove whitespace around symbols like "[{]}," as they are only meant for redundant readability.
2. Preferred ES6 features are those contibuting to compact codestyle: arrow function, template literals
3. Unfavored ES6 features are those against to compact codestyle: `const`: use `var` instead to avoid TDZ performance issue, unless inside for{}, if{}.
4. You may define help functions like `var trim=s=>s.trim(),low=s=>s.toLowerCase(),up=s=>s.toUpperCase(),rev=s=>[...s].reverse().join('');` for a small code size, if they may used for multiple times.
</CodeStyle>

Examples of help functions:
<code>
var oai=async(api,msg,t=0.6)=>await fetch(api.base+'/chat/completions',{method:'POST',headers:{Authorization:'Bearer '+api.key,'Content-Type':'application/json'},body:JSON.stringify({"stream":false,"model":api.model,"messages":msg,temperature:t})}).then(r=>r.text()).then(j=>{let a;try{a=JSON.parse(j).choices?.[0]?.message?.content.trim();}catch{throw("JSON.parse err from oai-api call\n"+j)} if(!a)throw(j); return a;});
var retry_oai=async(_cfg,_i,msg,t=0.6)=>{for(let i=0;i<3;i++) try{return await oai(asapi(_cfg,_i+i),msg,temperature:t);}catch(err){console.error(err,msg);await new Promise(r=>setTimeout(r, 300)); continue;} };
var asapi=(cfg,i=0)=>{return {'base':cfg.base,'model':cfg.model,'key':cfg.k[rand(cfg.k.length,i)]} };
var asmsg=(_sys,_txt)=>[{"role":"system","content":_sys},{"role":"user","content":_txt}];
var asmsgimg=(_sys,_txt,datauri)=>[{"role":"system","content":_sys},{"role":"user","content":[{"type":"text","text":_txt},{"type":"image_url","image_url":{"url":datauri}}]}];
var btwn=(s,b,e)=>{let i=s.indexOf(b),j=s.lastIndexOf(e);if(i<0||j<0||i>=j)throw new Error(`btwn:start/end missing\nb:${b}\ne:${e}`);return s.slice(i,j+e.length)};
var readBlob=b=> new Promise((resolve) => {var reader=new FileReader();reader.onloadend=()=>resolve(reader.result);reader.readAsDataURL(b);})
</code>

file structure example:
<code>
import {x,y} from "https://example.com/lib.js";
//CFG
var API_AI={base:"https://api.openai.com/v1",model:"gpt",k:['sk-123']};
var ALLOW_TG=[456123,456123];
//helpfunc
var trim=s=>s.trim(),low=s=>s.toLowerCase(),up=s=>s.toUpperCase(),rev=s=>[...s].reverse().join('');
//func
var paddleOcrApi=(datauri,lang='ch'){var api='https://example.hf.space/run/predict';...};
var whisperApi=(datauri){var api='https://example.hf.space/run/predict';...};
//callbacks
bot.on("message:voice", async (ctx) => {});
//webhook
const handleUpdate = webhookCallback(bot, "std/http", {onTimeout:"return",timeoutMilliseconds:30000});
serve(async(req)=>{if(req.method !== "POST")return new Response();
  try {return await handleUpdate(req);}catch(e){console.error(e);return new Response();} 
});
</code>

Demand:

```
