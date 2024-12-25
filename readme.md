# Qiita2Review 組版システムなどを使った Markdown による同人誌執筆方法

# 同人誌出力のための Markdown 記法

## Markdown 

基本的に Qiita 記法がベースとなります。
Qiita 記法は GitHub Markdown format  とある程度互換性があります。
https://docs.github.com/ja/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

# 標準 Markdown を書く上での Tips

コードブロック

```
````
any code
````
````

の上下に改行を入れてください。(暫定的な仕様)


# スクリプトのバグ

画像
```
![s-IMG_7135(1).jpg](https://example.com/hoge.jpg)
```
のような、カッコ付きのファイル名は避ける必要があります。

記号の使用
「♫」(U+266B)を使うと文字化けします。


# 標準 Markdown で規定されていないフォーマット

以下は、それから外れた項目を記していきます。

## 出典

脚注タグを使います。

[^n] を記事に埋め込み、対応した出典を [^n] : で記す。

例：

```

木材    0.53    41    1300    [^4]
・
・
・

[^4]: 強度データは直交異方性材料としての木材の弾性および強度 沢田稔 材料12巻 (1963) 121 号 よりアカマツデータから計算

```
こうすると、markdown 表示では [^n] ：を書いた場で表示、紙の場合は [^n] ：を書いたページの下部に表示となる。

## 記事に対するキーワードの付け方

冒頭に Qiita 形式で羅列します。

例：

```
---
title: 宇宙農場プラント「メタルネットバルーンプラント」に重力を発生させてみた。その１
tags: 宇宙開発 宇宙農場 無重力
author: reodon
slide: false
---
```

 tags: がキーワードになります


## 記事のライセンス表記

冒頭の記事ディスクリプションに記載。
```
---
title: 宇宙農場プラント「メタルネットバルーンプラント」に重力を発生させてみた。その１
tags: 宇宙開発 宇宙農場 無重力
author: reodon
slide: false
license: CC0
---
```

ライセンス種類はやむを得ない場合を除き、メジャーライセンスを使用。
なお宇宙農業関係はデフォルト CC0

- CC0
- CC BY
- CC BY-NC
- CC BY-SA
- CC BY-NC-SA
- GPL-2.0
- GPL-3.0
- LGPL-2.1
- LGPL-3.0
- AGPL-3.0
- BSD-3-Clause
- Apache-2.0
- MIT

 デュアルライセンスの場合は以下のように。

license: GPL-2.0 MIT

Copyright を出すのは以下。
```
---
title: 宇宙農場プラント「メタルネットバルーンプラント」に重力を発生させてみた。その１
tags: 宇宙開発 宇宙農場 無重力
author: reodon
slide: false
license: CC0
copyright: reserved
---
```

# リンク

紙に記すことを考慮して、URLを可視化して表記

☓

```
 [SSA・STMに関する調査検討－概要 （スペースポリシー委員会）](https://www.sjac.or.jp/pdf/publication/backnumber/202007/20200703.pdf)
```

○
```
SSA・STMに関する調査検討－概要 （スペースポリシー委員会）
 [https://www.sjac.or.jp/pdf/publication/backnumber/202007/20200703.pdf](https://www.sjac.or.jp/pdf/publication/backnumber/202007/20200703.pdf)
```

 もしくは

○
```
SSA・STMに関する調査検討－概要 （スペースポリシー委員会） https://www.sjac.or.jp/pdf/publication/backnumber/202007/20200703.pdf

```
### リンクURLに日本語が含まれる場合
UTF8にデコードする前提で日本語で表記するのが望ましいがリンクの正常性を確認のこと。
```
https://ja.wikipedia.org/wiki/%E3%82%B9%E3%83%9A%E3%83%BC%E3%82%B9%E3%83%87%E3%83%96%E3%83%AA
```
↓
```
https://ja.wikipedia.org/wiki/スペースデブリ
```

##  画像

ファイル形式は jpg または png
ライセンスクリアしたもののみ利用のこと

サイズ指定していない場合実寸表示、

相対指定が望ましい。
画像はそのままだと100%になり、はみ出る場合はページ横幅にあわせて縮小。紙媒体では大きすぎることが多い。縮小設定をしておく。
通常の画像は
```
![ファイル名](https://qiita-image-store.s3.amazonaws.com/0/......8d78.jpeg)
```

のようになってますが

```
[]( scale=0.5 )![ファイル名](https://qiita-image-store.s3.amazonaws.com/0/......8d78.jpeg)
```
のように頭に［］( scale=0.5 )をつけると、Qiitaでは100%,PDFにしたときには50%サイズになります。

横幅は1104pixel(確認中)。

## ページ制御
```
[](review://pagebreak)
```
## 見出し

```
# 
```
を章区切りとして使用
それより下のレベルは適宜使用
----
論文の書き方について
「論文の書き方 -➁アウトライン草案から要約版論文を書き起こす- – Systems Android Robotics」
 http://www.ams.eng.osaka-u.ac.jp/user/ishihara/?p=2680
「アブストラクトの書き方 -４つのステップを実例付きで- – Systems Android Robotics」
 http://www.ams.eng.osaka-u.ac.jp/user/ishihara/?p=626

