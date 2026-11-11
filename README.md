# 実機レビュー

クラウドで実装した変更を、PRを介してローカル実機でレビューするときに使うスキルです。
一人のユーザーとAIエージェントによる開発を対象にしています。

テストの合否に加え、実行速度から過剰な実装や設計上の問題を見つけ、不要な実装は確認待ちせず修正し、再検証まで進めます。
実行規則の正本は [SKILL.md](SKILL.md) です。

## 導入

このディレクトリを、ローカルで使うCodexのスキル配置先へコピーします。
ユーザー共通なら `~/.agents/skills/local-runtime-review/`、特定プロジェクトならそのルートの `.agents/skills/local-runtime-review/` に配置します。
配置先の直下に `SKILL.md` がある構造にします。

関連する次のスキルも、リンク先の導入方法に従って利用できるようにします。

- [repeated-path-cost](https://github.com/supersovaa/repeated-path-cost): 反復する実行経路のコスト分析。
- [pr-metadata-placement](https://github.com/supersovaa/pr-metadata-placement): リポジトリ・PR・CIの記録先の選択。

## 呼び出し例

> $local-runtime-review このPRを実機レビューして。https://github.com/owner/repository/pull/123

PRを取得・更新できるGitHub接続と、対象プロジェクトを実行できるローカル環境を使います。
この配布物はスキル定義です。実際のPRをレビューした結果は含みません。
