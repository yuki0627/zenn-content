---
title: "MulmoCastサンプル集"
emoji: "💬"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["MulmoCast", "サンプル"]
published: true
---
## はじめに

この記事は、**MulmoCast**をこれから使ってみたい方や、具体的にどのような動画・プレゼンテーション作成ができるのかを知りたい方向けのサンプル集です。

MulmoCastは、mulmoスクリプト（JSONファイル）を使って音声付きのプレゼンテーション動画やPDFスライドを自動生成できるツールです。テキストスライド、チャート、図表、画像、HTMLなど様々な形式のコンテンツを組み合わせて、プロフェッショナルな動画コンテンツを効率的に作成することができます。

この記事では、実際に動作するmulmoスクリプトのサンプルを通じて、MulmoCastの機能と可能性を具体的に紹介します：

- **PDF生成**: スライド形式のプレゼンテーション資料作成
- **動画生成**: 音声ナレーション付きの解説動画
- **メディア活用**: 画像や音声ファイルを組み合わせた動画作成
- **AI連携**: AIツールと組み合わせたコンテンツ制作ワークフロー

各サンプルには実際のmulmoスクリプトと完成した動画へのリンクが含まれているため、すぐに試してみることができます。MulmoCastがどのようなコンテンツ作成に活用できるかを理解し、自分のプロジェクトに応用するためのヒントを得ることができるでしょう。

**注意**: MulmoCastを実際に利用する場合、機能によってはOpenAI APIキーやGoogle Cloud Platform（GCP）などの外部サービスのAPIキーが必要になる場合があります。特に音声合成や画像生成機能を使用する際は、事前に必要な設定を確認してください。

## PDF生成

コマンド

```sh
mulmo pdf scripts/samples/attention.json
```

インプット

:::details attention.json
{
  "$mulmocast": {
    "version": "1.0",
    "credit": "closing"
  },
  "title": "Sample Title",
  "canvasSize": {
    "width": 1536,
    "height": 1024
  },
  "imageParams": {
    "style": "Style appropriate for business environment."
  },
  "speechParams": {
    "speakers": {
      "Presenter": {
        "voiceId": "shimmer",
        "displayName": {
          "en": "Presenter",
          "ja": "語り手"
        }
      }
    }
  },
  "textSlideParams": {
    "cssStyles": [
      "body { padding: 40px; padding-top: 60px; font-family: Arial, sans-serif;color:#333; font-size: 36px }",
      "h1 { font-size: 50px; text-align: center }",
      "ul { margin-left: 36px } ",
      "pre { background: #eeeecc; font-size: 24px; padding:10px }",
      "p { margin-left: 36px }",
      "table { font-size: 36px; margin: auto; border: 1px solid gray; border-collapse: collapse }",
      "th { border-bottom: 1px solid gray }",
      "td, th { padding: 8px }",
      "tr:nth-child(even) { background-color: #eee }"
    ]
  },
  "lang": "en",
  "beats": [
    {
      "speaker": "Presenter",
      "text": "In 2017, a revolutionary paper was published that would fundamentally change the landscape of artificial intelligence. Today, we'll explore 'Attention Is All You Need' - one of the most influential research papers in AI history.",
      "image": {
        "type": "textSlide",
        "slide": {
          "title": "Attention Is All You Need",
          "bullets": ["Published 2017", "Revolutionary AI architecture", "173,000+ citations as of 2025"]
        }
      },
      "textSlideParams": {
        "cssStyles": ["h1 { margin-top: 300px }"]
      }
    },
    {
      "speaker": "Presenter",
      "text": "This groundbreaking paper was authored by eight researchers at Google: Ashish Vaswani, Noam Shazeer, Niki Parmar, Jakob Uszkoreit, Llion Jones, Aidan Gomez, Łukasz Kaiser, and Illia Polosukhin. Their work has accumulated over 173,000 citations in just eight years - a testament to its profound impact.",
      "image": {
        "type": "textSlide",
        "slide": {
          "title": "The Authors",
          "bullets": ["Ashish Vaswani", "Noam Shazeer", "Niki Parmar", "Jakob Uszkoreit", "Llion Jones", "Aidan Gomez", "Łukasz Kaiser", "Illia Polosukhin"]
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "What makes this paper so significant? It introduced the Transformer - an architecture that would become the foundation for virtually all modern large language models and many other AI systems. From GPT to BERT to Claude, from image generators to video creators - the Transformer architecture powers them all.",
      "image": {
        "type": "mermaid",
        "title": "Transformer's Influence on AI",
        "code": {
          "kind": "text",
          "text": "graph TD\n    A[Transformer 2017] --> B[BERT]\n    A --> C[GPT Series]\n    A --> D[Claude]\n    A --> E[T5]\n    A --> F[Vision Transformer]\n    A --> G[DALL-E/Stable Diffusion]\n    A --> H[Sora]\n    style A fill:#f9f,stroke:#333,stroke-width:4px"
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "Before the Transformer, AI researchers faced significant challenges in sequence transduction tasks like machine translation. The existing models relied on complex architectures that had fundamental limitations. ",
      "image": {
        "type": "textSlide",
        "slide": {
          "title": "The Pre-Transformer Landscape",
          "bullets": [
            "Sequence transduction models (e.g., machine translation)",
            "Dominated by RNNs and CNNs",
            "Fundamental limitations in performance and efficiency"
          ]
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "Recurrent Neural Networks, or RNNs, were the standard approach. While powerful, they processed tokens sequentially - word after word, character after character. This sequential nature made them impossible to parallelize effectively, resulting in painfully slow training times as sequence lengths increased.",
      "image": {
        "type": "mermaid",
        "title": "RNN Sequential Processing",
        "code": {
          "kind": "text",
          "text": "graph LR\n    A[Input 1] --> B[RNN Cell]\n    B --> C[Hidden State]\n    C --> D[RNN Cell]\n    E[Input 2] --> D\n    D --> F[Hidden State]\n    F --> G[RNN Cell]\n    H[Input 3] --> G\n    G --> I[Hidden State]\n    style B fill:#f96,stroke:#333,stroke-width:2px\n    style D fill:#f96,stroke:#333,stroke-width:2px\n    style G fill:#f96,stroke:#333,stroke-width:2px\n    style C fill:#69f,stroke:#333,stroke-width:2px\n    style F fill:#69f,stroke:#333,stroke-width:2px\n    style I fill:#69f,stroke:#333,stroke-width:2px"
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "Convolutional Neural Networks, or CNNs, offered some parallelization advantages, but they struggled with long-range dependencies. The further apart two related words or concepts were in a text, the harder it became for CNNs to capture their relationship effectively - a critical limitation for complex language understanding.",
      "image": {
        "type": "chart",
        "title": "Performance vs. Sequence Distance",
        "chartData": {
          "type": "line",
          "data": {
            "labels": ["1", "5", "10", "20", "50", "100"],
            "datasets": [
              {
                "label": "RNN Performance",
                "data": [95, 90, 82, 70, 45, 30],
                "backgroundColor": "rgba(255, 99, 132, 0.2)",
                "borderColor": "rgba(255, 99, 132, 1)",
                "borderWidth": 2,
                "pointRadius": 4
              },
              {
                "label": "CNN Performance",
                "data": [95, 92, 85, 65, 40, 25],
                "backgroundColor": "rgba(54, 162, 235, 0.2)",
                "borderColor": "rgba(54, 162, 235, 1)",
                "borderWidth": 2,
                "pointRadius": 4
              }
            ]
          },
          "options": {
            "responsive": true,
            "animation": false,
            "scales": {
              "x": {
                "title": {
                  "display": true,
                  "text": "Distance Between Related Tokens"
                }
              },
              "y": {
                "title": {
                  "display": true,
                  "text": "Model Performance (%)"
                },
                "min": 0,
                "max": 100
              }
            }
          }
        }
      }
    }
  ]
}
:::

アウトプット

https://speakerdeck.com/yuki_ss_radio/attention-is-all-you-need-mulmocastsanpuru

## テスト動画

コマンド

```sh
mulmo movie scripts/test/test_media.json
```

インプット

:::details test_media.json

```json
{
  "$mulmocast": {
    "version": "1.0"
  },
  "title": "Media Test",
  "references": [
    {
      "url": "https://www.mulmocast.com",
      "title": "Mulmocast",
      "type": "article"
    }
  ],
  "speechParams": {
    "speakers": {
      "Presenter": {
        "voiceId": "shimmer",
        "displayName": {
          "en": "Presenter"
        }
      }
    }
  },
  "beats": [
    {
      "id": "first",
      "speaker": "Presenter",
      "text": "This is a local image.",
      "image": {
        "type": "image",
        "source": {
          "kind": "path",
          "path": "../../assets/images/mulmocast_credit.png"
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a reference beat.",
      "duration": 0.5,
      "image": {
        "type": "beat",
        "id": "first"
      }
    },
    {
      "speaker": "Presenter",
      "text": "",
      "duration": 0.5,
      "image": {
        "type": "textSlide",
        "slide": {
          "title": "No Audio",
          "bullets": ["0.5 seconds"]
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a remote image.",
      "image": {
        "type": "image",
        "source": {
          "kind": "url",
          "url": "https://raw.githubusercontent.com/receptron/mulmocast-cli/refs/heads/main/assets/images/mulmocast_credit.png"
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "",
      "duration": 2,
      "image": {
        "type": "textSlide",
        "slide": {
          "title": "No Audio",
          "bullets": ["2 seconds"]
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a local movie with audio.",
      "image": {
        "type": "movie",
        "source": {
          "kind": "url",
          "url": "https://github.com/receptron/mulmocast-media/raw/refs/heads/main/test/pingpong.mov"
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "",
      "image": {
        "type": "textSlide",
        "slide": {
          "title": "Local Audio Test",
          "bullets": ["Something"]
        }
      },
      "audio": {
        "type": "audio",
        "source": {
          "kind": "path",
          "path": "../../assets/audio/local_voice.mp3"
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a bulleted list in text slide format.",
      "image": {
        "type": "textSlide",
        "slide": {
          "title": "Human Evolution",
          "bullets": [
            "Early Primates",
            "Hominids and Hominins",
            "Australopithecus",
            "Genus Homo Emerges",
            "Homo erectus and Migration",
            "Neanderthals and Other Archaic Humans",
            "Homo sapiens"
          ]
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a table in markdown format.",
      "image": {
        "type": "markdown",
        "markdown": [
          "# Markdown Table Example",
          "### Table",
          "| Item              | In Stock | Price |",
          "| :---------------- | :------: | ----: |",
          "| Python Hat        |   True   | 23.99 |",
          "| SQL Hat           |   True   | 23.99 |",
          "| Codecademy Tee    |  False   | 19.99 |",
          "| Codecademy Hoodie |  False   | 42.99 |",
          "### Paragraph",
          "This is a paragraph."
        ]
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a chart in chart format.",
      "image": {
        "type": "chart",
        "title": "Sales and Profits (from Jan to June)",
        "chartData": {
          "type": "bar",
          "data": {
            "labels": ["January", "February", "March", "April", "May", "June"],
            "datasets": [
              {
                "label": "Revenue ($1000s)",
                "data": [120, 135, 180, 155, 170, 190],
                "backgroundColor": "rgba(54, 162, 235, 0.5)",
                "borderColor": "rgba(54, 162, 235, 1)",
                "borderWidth": 1
              },
              {
                "label": "Profit ($1000s)",
                "data": [45, 52, 68, 53, 61, 73],
                "backgroundColor": "rgba(75, 192, 192, 0.5)",
                "borderColor": "rgba(75, 192, 192, 1)",
                "borderWidth": 1
              }
            ]
          },
          "options": {
            "responsive": true,
            "animation": false
          }
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a diagram in mermaid format.",
      "image": {
        "type": "mermaid",
        "title": "Business Process Flow",
        "code": {
          "kind": "text",
          "text": "graph LR\n    A[Market Research] --> B[Product Planning]\n    B --> C[Development]\n    C --> D[Testing]\n    D --> E[Manufacturing]\n    E --> F[Marketing]\n    F --> G[Sales]\n    G --> H[Customer Support]\n    H --> A"
        }
      }
    },
    {
      "speaker": "Presenter",
      "text": "This is a tailwind html format.",
      "image": {
        "type": "html_tailwind",
        "html": [
          "<main class=\"flex-grow\">",
          "  <!-- Hero Section -->",
          "  <section class=\"bg-blue-600 text-white py-20\">",
          "    <div class=\"container mx-auto px-6 text-center\">",
          "      <h1 class=\"text-4xl md:text-5xl font-bold mb-4\">Welcome to Mulmocast</h1>",
          "      <p class=\"text-lg md:text-xl mb-8\">A modern web experience powered by Tailwind CSS</p>",
          "      <a href=\"#features\" class=\"bg-white text-blue-600 px-6 py-3 rounded-lg font-semibold shadow hover:bg-gray-100 transition\">",
          "        Learn More",
          "      </a>",
          "    </div>",
          "  </section>",
          "",
          "  <!-- Features Section -->",
          "  <section id=\"features\" class=\"py-16 bg-gray-100\">",
          "    <div class=\"container mx-auto px-6\">",
          "      <div class=\"grid grid-cols-1 md:grid-cols-3 gap-8 text-center\">",
          "        <div>",
          "          <div class=\"text-blue-600 text-4xl mb-2\">⚡</div>",
          "          <h3 class=\"text-xl font-semibold mb-2\">Fast</h3>",
          "          <p class=\"text-gray-600\">Built with performance in mind using modern tools.</p>",
          "        </div>",
          "        <div>",
          "          <div class=\"text-blue-600 text-4xl mb-2\">🎨</div>",
          "          <h3 class=\"text-xl font-semibold mb-2\">Beautiful</h3>",
          "          <p class=\"text-gray-600\">Styled with Tailwind CSS for clean, responsive design.</p>",
          "        </div>",
          "        <div>",
          "          <div class=\"text-blue-600 text-4xl mb-2\">🚀</div>",
          "          <h3 class=\"text-xl font-semibold mb-2\">Launch Ready</h3>",
          "          <p class=\"text-gray-600\">Easy to deploy and extend for your next big idea.</p>",
          "        </div>",
          "      </div>",
          "    </div>",
          "  </section>",
          "</main>",
          "",
          "<!-- Footer -->",
          "<footer class=\"bg-white text-gray-500 text-center py-6 border-t\">",
          "  2025 Mulmocast.",
          "</footer>"
        ]
      }
    }
  ]
}
```
:::

アウトプット

https://youtu.be/EespG2cSdNw

## 動画生成

コマンド

```sh
mulmo movie scripts/snakajima/spacex_shorts.json
```

インプット

:::details spacex_shorts.json
{
  "$mulmocast": {
    "version": "1.0"
  },
  "title": "SpaceX: Changing the Future of Space Travel",
  "lang": "en",
  "references": [
    {
      "url": "https://www.spacex.com/vehicles/falcon-9/",
      "title": "SpaceX Vehicles Overview",
      "type": "article"
    },
    {
      "url": "https://x.com/snakajima/status/1930781602935968142",
      "title": "Sample output",
      "type": "article"
    }
  ],
  "movieParams": {
    "provider": "google"
  },
  "beats": [
    {
      "text": "What if a private company could take humanity to Mars? SpaceX, founded by Elon Musk, is revolutionizing the way we think about space travel.",
      "imagePrompt": "A futuristic SpaceX rocket launching into a starry sky, crowds watching in awe.",
      "moviePrompt": "A cinematic shot of a SpaceX rocket lifting off with dramatic lighting, people cheering in the foreground."
    },
    {
      "text": "SpaceX started in 2002 with a big dream—making space affordable and accessible for everyone.",
      "imagePrompt": "Young Elon Musk in a lab surrounded by rocket models and blueprints, a sense of ambition in the air.",
      "moviePrompt": "A movie scene showing Elon Musk sketching rocket designs, transitioning to early SpaceX engineers working together."
    },
    {
      "text": "After several failures, SpaceX became the first private company to launch a liquid-fueled rocket into orbit with Falcon 1 in 2008.",
      "imagePrompt": "Falcon 1 rocket launching over an island at sunset, flames and smoke trailing dramatically.",
      "moviePrompt": "A dramatic launch sequence of Falcon 1, slow motion flames and a backdrop of the setting sun."
    },
    {
      "text": "The breakthrough: In 2015, Falcon 9 successfully landed its first stage booster upright, proving reusable rockets were possible.",
      "imagePrompt": "Falcon 9 booster landing vertically on a floating drone ship at sea, ocean spray all around.",
      "moviePrompt": "A close-up of a rocket stage gently touching down on a drone ship, waves crashing nearby."
    },
    {
      "text": "In 2020, SpaceX made history again—becoming the first private company to launch astronauts to the ISS with Crew Dragon.",
      "imagePrompt": "Crew Dragon spacecraft docking with the International Space Station, astronauts visible through the window.",
      "moviePrompt": "A view from inside Crew Dragon as it approaches and connects with the ISS, astronauts exchanging excited looks."
    },
    {
      "text": "SpaceX’s Starlink project now brings high-speed internet across the globe with thousands of satellites in orbit.",
      "imagePrompt": "A glowing network of Starlink satellites encircling Earth, connecting continents with shimmering lines.",
      "moviePrompt": "A cinematic animation of satellites orbiting Earth, beams of light connecting remote villages and cities."
    },
    {
      "text": "Next up: Starship—a fully reusable spacecraft aiming for the Moon, Mars, and beyond.",
      "imagePrompt": "Starship soaring past the Moon toward Mars, the red planet shining in the distance.",
      "moviePrompt": "A majestic shot of Starship leaving lunar orbit, Mars coming into view on the cosmic horizon."
    },
    {
      "text": "SpaceX isn’t just changing how we launch rockets—it’s changing humanity’s future in space.",
      "imagePrompt": "A group of diverse people looking up at a rocket launch, faces lit by the glow, symbolizing hope and exploration.",
      "moviePrompt": "A slow pan over people gazing at a rocket soaring skyward, music swelling, with text: 'Our Future Begins Now.'"
    }
  ],
  "canvasSize": {
    "width": 720,
    "height": 1280
  },
  "imageParams": {
    "style": "Photo realistic, cinematic."
  }
}
:::

アウトプット

https://youtube.com/shorts/6ffTE8OCwRw

---

コマンド

```sh
mulmo movie output/nagasima_shigeo.json
```

- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/nagasima_shigeo.json)
- [アウトプット mp4](https://mulmocast-samples.s3.amazonaws.com/videos/nagasima_shigeo.mp4) (5.8MB - 直接プレビュー可能)

コマンド

```sh
mulmo movie output/acclimate.json -l ja
```

- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/acclimate.json)
- [アウトプット mp4](https://mulmocast-samples.s3.amazonaws.com/videos/acclimate.mp4) (7.2MB - 直接プレビュー可能)

## 写真から動画生成

https://github.com/yuki0627/zenn-content/blob/main/scripts/foods/

```sh
mulmo movie food.json
```
- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/foods/food.json)
- [アウトプット mp4](https://mulmocast-samples.s3.amazonaws.com/videos/food.mp4) (2.4MB - 直接プレビュー可能)


## クリップボードから動画生成

クリップボードにコピーしたスクリプトを元に動画を生成します。「-c ja」で同時に日本語のテロップを作成しています。

コマンド

```sh
mulmo movie __clipboard -c ja
```

- [インプット JSON](https://github.com/yuki0627/zenn-content/blob/main/scripts/script-sumple-f1.json) このスクリプトをコピー後に上記のコマンドを実施
- [アウトプット mp4](https://mulmocast-samples.s3.amazonaws.com/videos/script_sample_f1_ja.mp4) (8.4MB - 直接プレビュー可能)

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
- [アウトプット mp4](https://mulmocast-samples.s3.amazonaws.com/videos/ai2027_html.mp4) (9.3MB - 直接プレビュー可能)

