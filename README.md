scdviout-pgf
============

LaTeX： PGF/TikZ を dviout に対応させる（ただし画期的）

### 改めて注意

画期的です。([参考])

[参考]: http://d.hatena.ne.jp/zrbabbler/20170808/1502160499

### 前提環境

  * フォーマット： LaTeX／plain TeX
  * エンジン： DVI 出力のエンジン
  * DVIウェア： dviout
  * 依存パッケージ：
      - pgf

### インストール

  - `*.sty`、`*.def` → $TEXMF/tex/latex/scdviout-pgf

### ライセンス

本パッケージは MIT ライセンスの下で配布される。


使用法
------

pgf または tikz を読み込む前に以下の記述を行う。

## LaTeX の場合

ドライバオプション `dviout` を付けて scdviout-pgf パッケージを読み込む。
これにより、PGF のドライバが pgfsys-scdviout に指定される。

※ `dviout` の指定が無い場合はこのパッケージは実質的に何もしない。

    \usepackage[dviout]{scdviout-pgf}

その他のオプションは「図の本質とは何か」を指定するのに用いる：

  * `snowman`： ゆきだるま。
  * `duck`： アヒル。
  * `phantom`： 無（あまり素敵でない）。

※既定では本質は`snowman`である（単に互換性のため）。これを不便に感じる人
のため、v0.82 で新たに“dcdviout-pgf”というパッケージを用意した。これは、
既定で本質が`duck`であることを除いて“scdviout-pgf”と同じ機能をもつ。

## plain TeX の場合

マクロ `\pgfsysdriver` を次のように定義する。

    \def\pgfsysdriver{pgfsys-scdviout.def}

既定では本質は`snowman`になる。マクロ `\scpgfsysessence` を定義することで
本質の値を設定できる。

    \def\scpgfsysessence{duck}

## ちなみに

本質をもっと別のもの（例えばスシ）にしたい場合は、`\scpgfsyssushicanvas`
というマクロで適切な描画がされるように定義すればよい。これにより、標準の
`snowman`や`duck`と同様に`sushi`を指定できるようになる。

※描画命令の書き方については、標準の `\scpgfsyssnowmancanvas` 等を参考に
してほしい。


更新履歴
--------

  * Version 0.82 ‹2017/08/28›
      - アヒルに対応した。
  * Version 0.8  ‹2017/08/08›
      - 最初の公開版。

--------------------
Takayuki YATO (aka. "ZR")  
https://github.com/zr-tex8r
