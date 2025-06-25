%*
try {
  const response = await fetch(`https://ja.wikipedia.org/api/rest_v1/page/summary/${tp.file.title}`);
  if (!response.ok) throw new Error("記事が見つかりません");
  const data = await response.json();
  %>
  > **Wikipedia概要**: <% data.extract %>
<%* } catch (error) { -%>
  > **エラー**: Wikipediaの記事を取得できませんでした。
<%* } -%>