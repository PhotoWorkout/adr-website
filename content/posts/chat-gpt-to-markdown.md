---
title: "Chrome Hack to Save Chat GPT converstion as Markdown"
date: 2023-03-30T22:49:10+05:30
tags: 
- note to self
---
I was having a conversation with Chat GPT and wanted to save it as a markdown file. I found a way to do it using Chrome DevTools.
Here is the script I used to save the conversation as a markdown file.

## Chrome Script

```javascript
function h(html) {
  return html
    .replace(/<p>/g, '\n\n')
    .replace(/<\/p>/g, '')
    .replace(/<b>/g, '**')
    .replace(/<\/b>/g, '**')
    .replace(/<i>/g, '_')
    .replace(/<\/i>/g, '_')
    .replace(/<code[^>]*>/g, (match) => {
      const lm = match.match(/class="[^"]*language-([^"]*)"/);
      return lm ? '\n```' + lm[1] + '\n' : '```';
    })
    .replace(/<\/code[^>]*>/g, '```')
    .replace(/<[^>]*>/g, '')
    .replace(/Copy code/g, '')
    .replace(
      /This content may violate our content policy. If you believe this to be in error, please submit your feedback — your input will aid our research in this area./g,
      ''
    )
    .trim();
}

(function () {
  const e = document.querySelectorAll('.text-base');
  let t = '';

  for (const s of e) {
    if (s.querySelector('.whitespace-pre-wrap')) {
      t += `**${
        s.querySelector('img') ? 'You' : 'ChatGPT'
      }**: ${h(s.querySelector('.whitespace-pre-wrap').innerHTML)}\n\n`;
    }
  }

  const o = document.createElement('a');
  o.download = 'Conversation with ChatGPT.md';
  o.href = URL.createObjectURL(new Blob([t]));
  o.style.display = 'none';
  document.body.appendChild(o);
  o.click();
})();
```
To use it, open the conversation in Chrome and open the DevTools. Go to the Console tab and paste the script. **Hit enter** and the markdown file will be downloaded.

This script extracts the conversation with ChatGPT and creates a downloadable markdown file. The h function is used to format the content by replacing HTML tags with corresponding markdown syntax.

**Note**: This script is not perfect and may not work for all conversations. It is just a hack to save the conversation as a markdown file.

## Get a markdown table from Chat GPT

If you want to get tables in markdown language, you have to tell Chat GPT that you want the table in markdown format (and in a code box).

E.g. **Prompt**: "Make the table of the GDP growth rate of 2020, use markdown language and put it in a code box."

**ChatGPT**: Here's a simple markdown table for the GDP growth rate of 2020. You can copy and paste this into a markdown editor.

```markdown
| **Country**    | **GDP Growth Rate (2020)** |
|----------------|---------------------------|
| United States  | -3.5%                     |
| China          | 2.3%                      |
| Japan          | -4.8%                     |
| Germany        | -4.9%                     |
| United Kingdom | -9.9%                     |
| India          | -7.7%                     |
| France         | -8.2%                     |
| Brazil         | -4.1%                     |
| Italy          | -8.9%                     |
| Canada         | -5.4%                     |
```

Simply copy and paste the markdown table provided by ChatGPT from the code box, and it will be displayed as a table in the markdown format, appearing like this:

| **Country**    | **GDP Growth Rate (2020)** |
|----------------|---------------------------|
| United States  | -3.5%                     |
| China          | 2.3%                      |
| Japan          | -4.8%                     |
| Germany        | -4.9%                     |
| United Kingdom | -9.9%                     |
| India          | -7.7%                     |
| France         | -8.2%                     |
| Brazil         | -4.1%                     |
| Italy          | -8.9%                     |
| Canada         | -5.4%                     |



Credit: [Rosa Amanita, Source: Reddit](https://www.reddit.com/r/ChatGPT/comments/zm237o/save_your_chatgpt_conversation_as_a_markdown_file/)
