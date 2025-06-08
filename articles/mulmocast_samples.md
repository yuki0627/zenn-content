---
title: "MulmoCastサンプル集"
emoji: "💬"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["MulmoCast", "サンプル"]
published: true
---

## PDF生成

コマンド

```sh
mulmo pdf scripts/samples/attention.json
```

- [インプット JSON](https://github.com/receptron/mulmocast-cli/blob/main/scripts/samples/attention.json)
- [アウトプット PDF](https://github.com/yuki0627/zenn-content/blob/6a9b7dd9c9c1f7101825a0e02a6c80748b572f99/output/attention_is_all_you_need.pdf)


## テスト動画

```sh
mulmo movie scripts/test/test_media.json
```

- [インプット JSON](https://github.com/receptron/mulmocast-cli/blob/main/scripts/test/test_media.json)
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/test_media.mp4)


## 動画生成

:::message
OpenAIとGCPの設定が必要
:::


コマンド

```sh
mulmo movie scripts/snakajima/spacex_shorts.json
```

- [インプット JSON](https://github.com/receptron/mulmocast-cli/blob/main/scripts/snakajima/spacex_shorts.json)
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/spacex_shorts.mp4)

## 写真から動画生成

https://github.com/yuki0627/zenn-content/blob/main/scripts/foods/

```sh
mulmo movie food.json
```
- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/foods/food.json)
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/food.mp4)


## クリップボードから動画生成

クリップボードにコピーしたスクリプトを元に動画を生成します。「-c ja」で同時に日本語のテロップを作成しています。

コマンド

```sh
mulmo movie __clipboard -c ja
```

- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/script-sumple-f1.json) このスクリプトをコピー後に上記のコマンドを実施
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/script_sample_f1_ja.mp4)
