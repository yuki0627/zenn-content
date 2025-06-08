ファイルは、プレゼンテーションの情報です。
beatsの下のオブジェクトには、今は、セリフとなるtextしか存在しないです。
beatsの下のオブジェクトに以下のようにHTMLでプレゼンテーションにあう横向きのページを作成してJSONに追記してください。
追加する属性のサンプルは以下です。
HTMLは、Tailwind CSSに対応させてください。

```json
    {

      "text": "test",

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

    },
```

可能であれば、imageParamsの情報を参考に作成してください。
言語は、langを参照してください。
JSONにcanvasSizeの情報があれば、それにしたがってください。
各ページは、プレゼンテーションに最適な大きさにし、余白がないようにしてください。