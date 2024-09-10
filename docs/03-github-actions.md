# GitHub Actions - デモ

## 概要

ワークフロー内容: [demo.yml](./../.github/workflows/demo.yml)

playgroundディレクトリ配下のmarkdownファイルを更新してPR作成・更新した際、放送禁止用語が含まれていないかチェックを行う例となります。  
主な要素として下記を含みます。

- PRトリガー（ファイルパス指定込み）
- npm install実行（キャッシュ設定込み）
- 放送禁止用語チェック実行
- gh CLI実行（GITHUB_TOKEN, permissions使用例）

また、ブランチ保護ルール設定（status checkなど）を行うことで、放送禁止用語チェックを通過しない限りマージできないといった設定も可能です。

動作確認方法は、playgroundディレクトリ配下にマークダウンファイルを作成し、プルリクエストを作成することで確認できます。  
放送禁止用語定義 [rule.yml](./../prh-rules/rule.yml) に含まれる文言があった場合に、ワークフローが失敗します。  
動作結果はActionsタブから確認可能です。

## 参考ドキュメント

- [ギットハブ　アクション　のワークフロー構文 - GitHub Docs](https://docs.github.com/ja/actions/writing-workflows/workflow-syntax-for-github-actions#onpushpull_requestpull_request_targetpathspaths-ignore)
- [依存関係をキャッシュしてワークフローのスピードを上げる - GitHub Docs](https://docs.github.com/ja/actions/writing-workflows/choosing-what-your-workflow-does/caching-dependencies-to-speed-up-workflows)
- [GitHub - actions/setup-node: Set up your GitHub Actions workflow with a specific version of Node.js](https://github.com/actions/setup-node#caching-global-packages-data)
- [自動トークン認証 - GitHub Docs](https://docs.github.com/ja/actions/security-for-github-actions/security-guides/automatic-token-authentication)
- [ワークフローで GitHub CLI を使用する - GitHub Docs](https://docs.github.com/ja/actions/writing-workflows/choosing-what-your-workflow-does/using-github-cli-in-workflows)
