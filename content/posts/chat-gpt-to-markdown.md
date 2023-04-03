---
title: "Chrome Hack to Save Chat GPT converstion as Markdown"
date: 2023-03-30T22:49:10+05:30
tags: 
- note to self
---
I was having a conversation with Chat GPT and wanted to save it as a markdown file. I found a way to do it using Chrome DevTools.
Here is the script I used to save the conversation as a markdown file.

```javascript
function h(html) { return html.replace(/<p>/g, '\n\n').replace(/<\/p>/g, '').replace(/<b>/g, '**').replace(/<\/b>/g, '**').replace(/<i>/g, '_').replace(/<\/i>/g, '_').replace(/<code[^>]*>/g, (match) => { const lm = match.match(/class="[^"]*language-([^"]*)"/); return lm ? '\n```' + lm[1] + '\n' : '```'; }).replace(/<\/code[^>]*>/g, '```').replace(/<[^>]*>/g, '').replace(/Copy code/g, '').replace(/This content may violate our content policy. If you believe this to be in error, please submit your feedback — your input will aid our research in this area./g, '').trim(); } (()=>{ const e=document.querySelectorAll(".text-base");let t="";for(const s of e)s.querySelector(".whitespace-pre-wrap")&&(t+=`**${s.querySelector('img')?'You':'ChatGPT'}**: ${h(s.querySelector(".whitespace-pre-wrap").innerHTML)}\n\n`);const o=document.createElement("a");o.download="Conversation with ChatGPT.md",o.href=URL.createObjectURL(new Blob([t])),o.style.display="none",document.body.appendChild(o),o.click()})();
```
The script is a bit messy, but it works. I will clean it up later. To use it, open the conversation in Chrome and open the DevTools. Go to the Console tab and paste the script. Hit enter and the markdown file will be downloaded.