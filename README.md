# agreed を使ってみる

[agreed](https://github.com/recruit-tech/agreed)とは
---

Consumer Driven Contract をサポートするためのツールです．
指定された形式(json5, yml など)で API仕様書 を記述すると，それに従った mock server が立ち上がります．
また，[agreed-ui](https://github.com/recruit-tech/agreed-ui)(agreed同封) を利用することで，各種仕様をWebで確認できます

Consumer Driven Contractとは
---
**Consumer Driven Contract** の説明の前に，サービス開発におけるバックエンドとフロントエンドのロールについて整理します．
Consumer Driven Contractの文脈では，データや機能を提供する側を，**Provider** とし，
それを利用する側を Consumer とします．

一般的なRESTfulなAPIと連携するような開発スタイルの場合，バックエンド開発者が **Provider** となり，
フロントエンド開発者が **Consumer** となります．

従来は，Provider が APIのリクエストやレスポンスを設計し，それに従って
Consumerが開発するのが多かったように思えます．

このような開発スタイルでの問題として大きく挙がるのが以下の2点です．

- Provider の破壊的変更 `*1` に Consumer が気がつけない，対応できない
- Provider が API を開発するまで，Consumer が開発できない （mockサーバーなどで開発したとしても，Provider と Consumer が想定するAPIが異なる）

`*1` : 破壊的変更というのは，例えばカラム名が変わったりなくなったりするというもの

そこで，Consumerが主導になってAPIを設計仕様を考えようというものが， Consumer Driven Contract です．


