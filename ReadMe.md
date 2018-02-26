# このソフトウェアについて

# 開発環境

* [Raspberry Pi](https://ja.wikipedia.org/wiki/Raspberry_Pi) 3 Model B
    * [Raspbian](https://www.raspberrypi.org/downloads/raspbian/) GNU/Linux 8.0 (jessie)
        * [pyenv](http://ytyaru.hatenablog.com/entry/2019/01/06/000000)
            * Python 3.6.4

# 形式

構造化テキストの形式。

形式|説明|既存|用途
----|----|----|----
list|1要素1改行で表す| |データ配列、順序
tree|1階層をインデントか`.`で表す|xml, json, yaml|包含関係
table|ヘッダ行以降すべてデータ行|dsv(csv, tsv)|定型属性をもったデータの網羅

なお、ネットワーク構造は`@Root.Node.Leaf`, `@[*.txt]`などの参照で行う。

# メタ文字

## tree

メタ文字|意味
--------|----
`.`|階層の区切文字（1行記法）
`\n`|階層の区切文字（複数行記法）
` `,`\t`|空白文字(TAB, SPACE)
`"`, `'`|文字列リテラル
`#`|コメント
`$`|エイリアス（別名定義名）。参照時は`$name`,`${name}`,`${root.sub}`など。
`@`|参照（他キー、外部ファイル）`@root.sub`等
`@""`, `@''`|メタ文字が含んでいてもリテラルとして解釈する。例えば`\n`は改行コードにせずそのままの2文字とする。
`@[]`|外部ファイル参照。またはHTTPリクエストURL。
`@[data:]`|DataUri。BASE64などから画像などデータ作成する

# ライセンス

このソフトウェアはCC0ライセンスである。

[![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")](http://creativecommons.org/publicdomain/zero/1.0/deed.ja)

