## HTML

- HTMLによる宣言的なセマンティクス
- 広義のセマンティクスとHTMLのセマンティクス
  - ブラウザ上のセマンティクス
- 静的な文字列（`.html`ファイル）をパースすればセマンティクスがある状態
  - (?) コンテンツの可搬性を高めた
    - RSS内部のHTML
    - 検索ボット含むクローラー、メタ情報
  - 静的なコンテンツとしてはまだまだ大事

### HTMLによるセマンティクス定義の課題

- セマンティクスは要素名に依存
- セマンティクスの変更 = DOMツリーの変更となる
- UAスタイルシートとの密結合
- 新しいセマンティクス = 新しい要素
- ウェブコンポーネントのセマンティクスが定義できない
- 状態やプロパティの欠如

背景 : 動的なウェブアプリケーションの隆盛

## WAI-ARIA

- HTMLの抱えるセマンティクスの課題を（主にアクセシビリティの面で）解決する
- 属性による宣言的なセマンティクス
- 要素名とセマンティクスが疎
- 関係性のセマンティクスを持てる
- UAスタイルシートとも疎
- 新しい語彙を作るのに要素を作る必要がない
  - (?) ホスト言語との相互進化 / UAがWAI-ARIAのセマンティクスに対応してから要素ができる
- 状態やプロパティを持てる `aria-*`

### WAI-ARIAの課題

- セマンティクスがDOMに依存（要素上の属性）
- 要素参照タイプのプロパティの場合、事前に参照されうる要素に参照用の `id` を振る必要がある
- Web components へのセマンティクスの定義が属性で露出する（問題ないかも知れない）
- 要素が無い場合に対応できない（e.g. `canvas` の中のUI）
- セマンティクスは付与できてもセマンティクスが持つべき機能（イベントの発火、リッスン）を付与できない（e.g. `input[type="range"]` の `increment` or `decrement`）
- セマンティクスの付与しかできず、探索ができない

### 合わせて話したほうが良い？

- アクセシビリティAPI - アクセシビリティツリー
- WAI-ARIA ロードマップ

## Accessibility Object Model

- アクセシビリティAPIに変換されうるセマンティクスをモデルとして定義しJavaScriptから操作・探索可能にしたもの
- 現在はWAI-ARIAやDOMの一部として提案されている
- IDLインターフェースを通じて、JavaScriptからARIA属性を付与できる
- 参照する要素の `id` ではなく、要素のインスタンス自身を参照先として持つことができる
- 属性に露出せず、属性によって上書き可能な暗黙のセマンティクスを（カスタムエレメントに）付与できる
- 仮想のアクセシビリティノードを要素下に作ることができる
- 支援技術が発火するイベントを扱うことができる
- セマンティクスがAccessibility Tree に変換された結果を探索することができる

背景: JavaScriptによるDOMツリー及びレンダリングツリーの構築、ウェブコンポーネント