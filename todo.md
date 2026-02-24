# 中学2年 理科 天気クイズアプリ開発 TODO & メモ

## 今回やったこと（2026-02-24）
*   **概要**: 理科の天気が苦手な子供向けに、基礎用語を覚えるためのスマホ用Webクイズアプリを作成した。
*   **使用したベースデザイン**: `kenkoushogai1/all_quiz.html` のスタイル（HTML/CSS/JS）を流用し、コンテンツを差し替え。
*   **実装内容**:
    *   気圧と風・雲のでき方 (10問)
    *   前線と天気の変化 (10問)
    *   日本の天気（四季の特徴） (10問)
    *   誤記修正（空気11㎥ → 空気1㎥）を適用して push。
    *   問題内容の正確性チェックを実施し、`quality_check_report.md` を作成。

## 実行した主なコマンド・プロンプト情報
1.  **既存ファイルの検索**:
    *   `mdfind "kMDItemFSName == 'all_quiz.html'"` でベースとなるHTMLファイルを特定。
2.  **リポジトリの作成と初期化**:
    *   `mkdir -p repos/kodomo`
    *   生成したHTMLを `index.html` として保存。
    *   `git init`, `git commit`
    *   `gh repo create kodomo --public --source=. --remote=origin --push`
3.  **GitHub Pages の有効化**:
    *   `gh api -X POST /repos/miiichiii/kodomo/pages -F "source[branch]=master" -F "source[path]=/"`
4.  **誤植の修正**:
    *   `edit` ツールで「空気11㎥」を「空気1㎥」に置換。
    *   `git commit -m "Fix typo in question text" && git push origin master`

## 今後の展望（次やること）
*   現状はテキストのみの基礎編（語句暗記メイン）。
*   **実践編の追加**:
    *   天気図、前線記号、飽和水蒸気量のグラフなどの画像を利用した問題を追加する。
    *   画像アセット（PNG/JPG）を `kodomo` リポジトリ（例: `assets/images/` フォルダ）に追加する。
    *   HTMLのJavaScriptロジックと問題データスキーマを改修し、問題文や選択肢に画像（`<img src="...">`）を表示できる仕組みを実装する。