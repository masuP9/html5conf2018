# セマンティクスの作り方、これまで、今、そして未来

1. 私たち（1分）
2. 今日話すこと（1分）
3. なぜセマンティクスが重要なのか（10分）
   1. マシンリーダビリティ（5分）
   2. アクセシビリティ（5分）
     1. UIを知覚する云々
     2. アクセシビリティAPI
4. どうやってセマンティクスを作るのか（25分）
   1. HTML（5分）
     1. HTMLとは（いらなさそう）
     2. 
   2. WAI-ARIA（8分）
     1. WAI-ARIAとは
     2. WAI-ARIAで何ができる
       1. role, state, props の補強の話
     3. [WAI-ARIA ロードマップ](https://www.w3.org/WAI/ARIA/roadmap)
       1. 1.2 でHTMLのセマンティクスが網羅される
       2. それ以降
   3. AOM（12分）
     1. [AOMとは](http://wicg.github.io/aom/)
     2. AOMで何ができる
     3. AOM想定ユースケース
       1. 支援技術のログをGAに送る
       2. 支援技術かそうでないかによって挙動を変える
         1. Web Speech API or live region
