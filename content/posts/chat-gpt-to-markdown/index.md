---
title: "Chrome Hack to Save Chat GPT conversation as Markdown"
date: 2023-03-30T22:49:10+05:30
lastmod: 2023-04-13T11:58:58+05:30
tags: 
- note to self
featured_image: markedown-for-chat-gpt.jpg
summary: "I was having a conversation with Chat GPT and wanted to save it as a markdown file. I found a way to do it using Chrome DevTools. Here is the script I used to save the conversation as a markdown file."
resources:
  - name: "featured-image"
    src: "markdown-for-chat-gpt.jpg"
---
I was having a conversation with Chat GPT and wanted to save it as a markdown file.
I found a way to do it using Chrome DevTools.
Here is the script I used to save the conversation as a markdown file.

## Chrome Script

```javascript
function formatMarkdown(html) {
  return html
    .replace(/<h1>/g, '# ')
    .replace(/<\/h1>/g, '\n')
    .replace(/<h2>/g, '## ')
    .replace(/<\/h2>/g, '\n')
    .replace(/<h3>/g, '### ')
    .replace(/<\/h3>/g, '\n')
    .replace(/<h4>/g, '#### ')
    .replace(/<\/h4>/g, '\n')
    .replace(/<h5>/g, '##### ')
    .replace(/<\/h5>/g, '\n')
    .replace(/<h6>/g, '###### ')
    .replace(/<\/h6>/g, '\n')
    .replace(/<p>/g, '')
    .replace(/<\/p>/g, '\n\n')
    .replace(/<b>/g, '**')
    .replace(/<\/b>/g, '**')
    .replace(/<strong>/g, '**')
    .replace(/<\/strong>/g, '**')
    .replace(/<i>/g, '_')
    .replace(/<\/i>/g, '_')
    .replace(/<em>/g, '_')
    .replace(/<\/em>/g, '_')
    .replace(/<ul>/g, '')
    .replace(/<\/ul>/g, '\n')
    .replace(/<ol>/g, '')
    .replace(/<\/ol>/g, '\n')
    .replace(/<li>/g, '- ')
    .replace(/<\/li>/g, '\n')
    .replace(/<code[^>]*>/g, '```\n')
    .replace(/<\/code[^>]*>/g, '```\n')
    .replace(/<table>/g, '\n')
    .replace(/<\/table>/g, '\n')
    .replace(/<tr>/g, '')
    .replace(/<\/tr>/g, ' | \n')
    .replace(/<td>/g, ' | ')
    .replace(/<\/td>/g, '')
    .replace(/<th>/g, ' | ')
    .replace(/<\/th>/g, '')
    .replace(/<thead>/g, '')
    .replace(/<\/thead>/g, '')
    .replace(/<tbody>/g, '')
    .replace(/<\/tbody>/g, '')
    .replace(/<[^>]*>/g, '')
    .trim();
}

(function () {
  const e = document.querySelectorAll('.text-base');
  let t = '';
  for (const s of e) {
    if (s.querySelector('.whitespace-pre-wrap')) {
      t += `**${
        s.querySelector('img') ? 'You' : 'ChatGPT'
      }**: ${formatMarkdown(s.querySelector('.whitespace-pre-wrap').innerHTML)}\n\n`;
    }
  }

  const o = document.createElement('a');
  o.download = 'Conversation_with_ChatGPT.md';
  o.href = URL.createObjectURL(new Blob([t]));
  o.style.display = 'none';
  document.body.appendChild(o);
  o.click();
})();
```
To use it, open the conversation in Chrome and open the DevTools. Go to the Console tab and paste the script. **Hit enter** and the markdown file will be downloaded.

This script extracts the conversation with ChatGPT, creates, and downloads a markdown file. The h function is used to format the content by replacing HTML tags with corresponding markdown syntax.

**Note**: This script is not perfect and may not work for all conversations. It is just a hack to save the conversation as a markdown file.

## Get a markdown table from Chat GPT (by prompt)

While the sciprt above works for tables, if you just want to get tables in markdown language, you could to tell Chat GPT that you want the table in markdown format (and in a code box).

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



Credit: I modified this code by [Rosa Amanita, Source: Reddit](https://www.reddit.com/r/ChatGPT/comments/zm237o/save_your_chatgpt_conversation_as_a_markdown_file/)