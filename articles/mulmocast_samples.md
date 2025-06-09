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

コマンド

```sh
mulmo movie output/nagasima_shigeo.json
```

- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/nagasima_shigeo.json)
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/nagasima_shigeo.mp4)

コマンド

```sh
mulmo movie output/acclimate.json -l ja
```

- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/acclimate.json)
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/acclimate.mp4)

## 写真から動画生成

https://github.com/yuki0627/zenn-content/blob/main/scripts/foods/

```sh
mulmo movie food.json
```
- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/foods/food.json)
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/food.mp4)


## AIでHTML作成から動画生成

```sh
mulmo movie ai2027_html.json
```
- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/ai2027_html/ai2027_html.json)
  - 作成方法
    1. Claudeに[ai2027.json](https://github.com/receptron/mulmocast-cli/blob/main/scripts/samples/ai2027.json)をアップロード
    1. [プロンプト(サンプル)](https://github.com/yuki0627/zenn-content/blob/main/scripts/ai2027_html/prompt/textToHTML.md)を貼り付けて実行
    - 現状のOpenAI(o3)だとシンプルなHTMLだったため、Claude(Sonnet 4)がおすすめです
    - 修正や調整が可能なので、現状では、ビジネスプレゼン向きな作成方法としてよいかなとおもいます。
- [アウトプット mp4](https://github.com/yuki0627/zenn-content/blob/main/output/food.mp4)

