---
title: バナーと注意
slug: MDN/Writing_guidelines/Page_structures/Banners_and_notices
tags:
  - MDN メタ
  - ガイド
  - 構造
translation_of: MDN/Writing_guidelines/Page_structures/Banners_and_notices
original_slug: MDN/Structures/Banners_and_notices
---
{{MDNSidebar}}

時には、記事に特別な注意を加える必要があります。
これは、そのページが非推奨の技術や、本番コードで使うべきでない他の資料を扱っている場合に起こるかもしれません。
この記事では、最も一般的なそのようなケースと、何をすべきかを説明します。

## 注意ボックスの追加方法

ほとんどの場合、ページコンテンツに適切なバナーを注入するマクロ呼び出しを追加し、ページのタグリストにタグを追加することで、これらの注意を適用します。

これを行うには、記事の一番上にマクロ呼び出しを挿入し、リストに新しいタグを追加します。
それが終わったら、プルリクエストを発行し、変更をレビューしてもらい、マージしてもらいます。
それ以降、ページには適切なバナーが表示され、最新の記事を探すときにページタグを参照するマクロは、更新したページが非推奨であること、またはそのようなことを知ることができるようになります。

> **Note:** 編集についてもっと知るには、[content リポジトリーの README](https://github.com/mdn/content) を見てください。

時には、項目リストやテーブルの中の一つの項目に、廃止 (obsolete) や非推奨 (deprecated) などのフラグを立てたいことがあります。
以下の各マクロには、そのための特別バージョンがあります。マクロ名の最後にある "\_header" を "\_inline"に変えてください。

## 非推奨のコンテンツ

非推奨のコンテンツとは、陳腐化しつつある技術やアイデアを扱ったコンテンツです。
もはや推奨されず、比較的近い将来にブラウザーから削除されることが予想されます。
非推奨コンテンツとしてページをマークするには、 [`deprecated_header`](https://github.com/mdn/yari/blob/main/kumascript/macros/Deprecated_Header.ejs) マクロを使用してください。
廃止されたコンテンツと同様に、その技術が Gecko 固有のものであれば、非推奨とされた Gecko のバージョンを引数として指定できます。

また、そのページには "Deprecated" というタグを追加してください。

## 標準外のコンテンツ

標準外のコンテンツとは、まだウェブ標準に含まれていないコンテンツのことです。これには、たとえ複数のブラウザーで実装されていたとしても、仕様書の草稿として提案されていない技術も含まれます。
これらのページでは [`non-standard_header`](https://github.com/mdn/yari/blob/main/kumascript/macros/Non-standard_Header.ejs) マクロを使用し、ページに "Non-standard" というタグを付ける必要があります。