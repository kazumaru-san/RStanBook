# StanとRでベイズ統計モデリング サポートページ

## 概要
このリポジトリではデータファイル, Stanコード, 実行するRコード, 図を描くRコード, 画像ファイルを公開しています.

本書では基本的に以下の3つの番号を一致させています.

* モデル式X-Y
* Stanコード（`modelX-Y.stan`）
* 実行するRコード（`run-modelX-Y.R`）

この他に, 図を描くコード`figX-Y.R`があります. また各章のディレクトリの構成は以下になっています.

* `input`:データが格納されています.
* `model`:モデルファイル（Stanコード）が格納されています.
* `output`:作成した図が含まれています.
* `exercise`:練習問題の解答例です.

## 実行方法
各章のディレクトリに移動してから実行することを想定しています. 例えば4章の`run-model4-5.R`を実行する場合にはRを起動後に以下のようにします.

```r
setwd('RStanBook/chap04/')
source('run-model4-5.R')
```

練習問題の解答例を実行するには, さらに`exercise`ディレクトリに移動してから実行することを想定しています.

```r
setwd('RStanBook/chap04/exercise/')
source('ex1.R')
```

## StanやRStanのバージョンアップに伴う補足
RStan 2.32.3 (2023年10月リリース)ではStan 2.26.1という比較的安定しているバージョンを使っています（2023/12/23現在の最新のStanは2.33.0 (2023年9月リリース)）。

もし`rstan`パッケージが将来的に（3年後？5年後？）最新のStanを使用するときが来ましたら、本書にある配列の書き方を以下のように修正して読んでください。

| 修正前 | 修正後 |
|:------------|:------------|
| `real X[N];`| `array[N] real X;` |
| `int<lower=0> Y[N];` | `array[N] int<lower=0> Y;` |
| `vector[K] V[N];`  | `array[N] vector[K] V;` |

この記法以外に古くなる部分は当面の間ありません。「はじめに」に書いた通り、モデリングの内容自体は簡単に古くなるものではなく、現在でもStanを使った統計モデリングを習得するにはベストな書籍と思っています。

[古いバージョンからの差分はこちら](update.md)

## `cmdstanr`パッケージとの使い分け
`cmdstanr`パッケージは最新のStanのリリースからそこまで間をあけずにリリースされる傾向があるため、最新のStanの機能を使いたい人には`cmdstanr`パッケージがオススメです。個人的には`rstan`と`cmdstanr`の使用感に大きな差はありません。`cmdstanr`は発展途中であり、推定結果からMCMCサンプルを取り出すときは`rstan`のほうが少し手間が少なく入門者向きと思います。

## 正誤表
[こちら](errata.md)

## ソースコードの実行環境
| 主なソフトやパッケージ名 | 執筆時点 | サポートページ内の現状 |
|:-----------|:------------|:------------|
| OS | Windows 7 SP1 (64bit) | Windows 10 (64bit) |
| R | 3.3.1 | 4.3.2 |
| Rtools | Rtools34 | Rtools43 |
| rstan | 2.11.1 | 2.32.3 |
| ggplot | 2.1.0 | 3.4.4 |
| ggmcmc | 1.1 | 1.5.1.1 |
| GGally | 1.1.0 | 2.2.0 |
| patchwork | - | 1.1.3 |
| ellipse | 0.3.8 | 0.5.0 |
| hexbin | 1.27.1 | 1.28.3 |
| ggtern | 2.1.1 | 3.4.2 |
| ggrepel | 0.5 | 0.9.4 |
| mvtnorm | 1.0.5 | 1.2-4 |
| gtools | 3.5.0 | 3.9.5 |
| NipponMap | - | 0.2 |
