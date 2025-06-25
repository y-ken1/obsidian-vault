<%*
/**
新規Note作成

- 作成するNoteのタイプををユーザ選択（買い物、TODO、メモ、開発）
- タイトルをユーザ入力
- 選択したNoteのタイプ仁応じてフォルダや内容を変更してNoteを作成する
*/


// フォルダ選択
const [MEMO, DEV, SHOPPING, TODO] = ["MEMO", "DEV", "SHOPPING", "TODO"];

const folderMap = {
  "買い物": {type: SHOPPING, dir:"310-Shopping"},
  "TODO": {type: TODO, dir:"320-Todo"},
  "メモ": {type: MEMO, dir:"100-Memo"},
  "開発": {type: DEV, dir:"200-Develop"},  
};

const selectedCategory = await tp.system.suggester(Object.keys(folderMap), Object.keys(folderMap));

if (!selectedCategory) {
  tR = "カテゴリの選択がキャンセルされました。テンプレートを中止します。";
  return;
}

const targetFolder = folderMap[selectedCategory].dir;

// タイトル
const userTitle = await tp.system.prompt("title");
if (!userTitle) {  
  return;
}


const today = tp.date.now("YYYY_MM_DD_HHmmss");
const timestamp = tp.date.now("YYYY-MM-DD HH:mm:ss");
const fileName = `${today}_${userTitle}.md`;
await tp.file.move(`${targetFolder}/${fileName}`);

const type = folderMap[selectedCategory].type;
const tag = (type===MEMO) ? "未分類" : "";
let output = `---
aliases:
  - 
tags: 
  - ${tag}
created:
  - ${timestamp}
---

# ${userTitle}

ここからメモを書く
`;

if (type === SHOPPING) {
  output = `- [ ] ${userTitle}`;
} else if(type === TODO) {
  const now = tp.date.now();
  const due = tp.date.now("YYYY-MM-DD", "+3d");
output = `- [ ] ${userTitle} 🛫 ${now} 📅 ${due}

## メモ

`;
}

tR = output;
%>