# Third-Party Licenses

本プラグイン (fudebako-agent) は、ホストである fudebako のスタンドアロン HTML 配布物に組み込まれて配布されます。本書は、fudebako-agent 起源のコンポーネント、fudebako 本体から継承される同梱コンポーネント、および運用に必要な第三者サービスを列挙します。

完全なライセンス本文は、各リリースに添付される `NOTICES.txt` に収録されます。

---

## 1. fudebako-agent 起源で同梱されるコンポーネント

**該当なし**。エージェントワーカーおよび UI はプロジェクト内コードのみで構成されており、ランタイムとしての npm パッケージ依存を持ちません。標準の `fetch` API と Server-Sent Events パーサのみで OpenRouter の OpenAI 互換エンドポイントと通信します。

ビルド時のバンドラ (MIT) がビルド成果物に注入する小規模なランタイムヘルパは permissive ライセンスの下にあり、追加の attribution 義務を課しません。

## 2. fudebako 本体から継承される同梱コンポーネント

本プラグインを含むスタンドアロン HTML には、ホストである fudebako 本体が同梱する以下の第三者コンポーネントが含まれます。これらの著作権・ライセンスは [jugoya-ai/fudebako](https://github.com/jugoya-ai/fudebako) の規定に従います。

### 2.1 ブラウザ実行時

| パッケージ | バージョン | ライセンス |
|---------|---------|---------|
| [Tailwind CSS](https://tailwindcss.com/) | 4.2.2 | MIT |
| [Noto Sans JP Variable](https://fontsource.org/fonts/noto-sans-jp) | 5.2.10 | OFL-1.1 |
| [Noto Sans Mono Variable](https://fontsource.org/fonts/noto-sans-mono) | 5.2.10 | OFL-1.1 |

### 2.2 Python ランタイム (WebAssembly)

| パッケージ | バージョン | ライセンス |
|---------|---------|---------|
| [Pyodide](https://pyodide.org/) | 0.29.3 | MPL-2.0 |
| [CPython 標準ライブラリ](https://www.python.org/) | 3.13.x | PSF-2.0 |

Pyodide のソースコードは https://github.com/pyodide/pyodide にて入手可能です (MPL-2.0 §3.2(b))。

### 2.3 WASM レンダラに静的リンクされる Rust クレート

| クレート | ライセンス |
|-------|---------|
| wasm-bindgen | MIT OR Apache-2.0 |
| js-sys | MIT OR Apache-2.0 |
| web-sys | MIT OR Apache-2.0 |
| serde | MIT OR Apache-2.0 |
| serde_json | MIT OR Apache-2.0 |
| serde_repr | MIT OR Apache-2.0 |

### 2.4 任意 Python パッケージ (バンドル構成依存)

配布物に特定の Python パッケージが含まれる場合は、各パッケージのライセンスが追加適用されます。詳細は同梱の `NOTICES.txt` を参照してください。

| パッケージ | upstream ライセンス |
|---------|------------------|
| matplotlib | PSF-2.0 AND Matplotlib License |
| numpy | BSD-3-Clause |
| pandas | BSD-3-Clause |
| httpx | BSD-3-Clause |
| micropip | MPL-2.0 |

### 2.5 ライセンスサマリ

すべてのライセンスは permissive または file-level weak copyleft であり、GPL / LGPL / AGPL は含まれません。

| ライセンス | 種別 |
|---------|------|
| MIT | Permissive |
| OFL-1.1 | Permissive (font) |
| MPL-2.0 | File-level weak copyleft |
| PSF-2.0 | Permissive |
| BSD-3-Clause | Permissive |
| Apache-2.0 | Permissive |

MPL-2.0 は配布側プロジェクトのオープンソース化を要求しません。改変された MPL ファイルについてのみ MPL での再配布を要求します。本配布物は MPL ライセンスのファイルを改変していません。

## 3. 運用に必要な第三者サービス (同梱物ではない)

fudebako-agent は、利用者の操作に基づき、以下の外部サービスに対して HTTPS 通信を行います。これらのサービスのコードは配布物に含まれませんが、利用には各社の利用規約への同意と、利用者自身による費用負担が必要です。

| サービス | 用途 | 規約・ポリシー |
|---|---|---|
| OpenRouter | LLM ゲートウェイ (`/v1/chat/completions`、`/api/v1/models`) | https://openrouter.ai/terms |
| 上流モデルプロバイダ (Anthropic、OpenAI、Google 等) | OpenRouter 経由で利用者が指定したモデルにルーティング | 各社利用規約 |

これらのサービスのデータ取扱い、可用性、料金、出力品質は当該サービス提供者の責任範囲となります。詳細は本リポジトリ直下の [`TERMS.md`](../TERMS.md) (第 0 条および第 3.2 条) を参照してください。

## 4. 完全なライセンス本文

上記コンポーネントの完全なライセンス本文は、各リリースに添付される `NOTICES.txt` に収録されます。fudebako-agent は本書 §1 の通り独自に同梱するコンポーネントを持たないため、`NOTICES.txt` に追加される fudebako-agent 起源の項目はありません。
