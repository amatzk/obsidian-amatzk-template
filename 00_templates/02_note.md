---
tags:
  - note
---
> [!IMPORTANT]
> このテンプレート[[02_note]]の内容（見出しNote）はサンプルです。
> ご自分にとって使いやすいように編集してください。

## note
<%*
const year = tp.date.now("YYYY");
const fileName = tp.file.title;
await tp.file.move(`02_notes/${year}/${fileName}`);
%>
