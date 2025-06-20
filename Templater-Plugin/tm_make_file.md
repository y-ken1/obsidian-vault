<%*
const userTitle = await tp.system.prompt("title");
const today = tp.date.now("YYYY_MM_DD_HHmmss");
const timestamp = tp.date.now("YYYY-MM-DD HH:mm:ss");
const fileName = `${today}_${userTitle}`;
await tp.file.rename(fileName);

const output = `---
aliases:
  - 
tags: 
  - 
created:
  - ${timestamp}
---

# ${userTitle}

ここからメモを書く
`;

tR = output;
%>