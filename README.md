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

## LaTeX の場合

ドライバオプション `dviout` を付けて scdviout-pgf パッケージを読み込む。
これにより、PGF のドライバが pgfsys-scdviout に指定される。

    \usepackage[dviout]{scdviout-pgf}

## plain TeX の場合

マクロ `\pgfsysdriver` を次のように定義する。

    \def\pgfsysdriver{pgfsys-scdviout.def}


更新履歴
--------

  * Version 0.8  ‹2017/08/08›
      - 最初の公開版。

--------------------
Takayuki YATO (aka. "ZR")  
https://github.com/zr-tex8r
