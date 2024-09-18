# obsidian-amatzk-template

> [!IMPORTANT]
> このREADMEは、自分のリポジトリを作成したときに削除してください。

## コンセプト

ノートを取ることに集中できる環境。
認知負荷が低くなるように設計した、シンプルな構成のテンプレートです。
迷いを生むような、認知負荷を上げる原因となる機能や、視覚的情報をできるだけ削っています。

## 設計思想

このテンプレートは、以下の設計思想に基づいています。

**ネットワーク構造の情報**
- リンクを使って情報をネットワーク構造で繋ぐ
- Obsidian グラフビュー や Dataview（プラグイン）で、情報の関連性を視覚化および俯瞰する

**検索による情報アクセス**
- Obsidianの検索機能やVSCodeの検索機能を使用して、情報を見つける
- Googleなどの検索エンジンと同じようなアプローチ

**シンプルさの維持**
- シンプルなディレクトリ構造
	- ディレクトリ構造による分類は、不整合が発生しやすいので避ける
	- 年単位のディレクトリによるファイリング
	- 日記やノートの新規作成時、自動でファイル配置
- 必要最低限のタグ
	- タグ付けによる分類は、認知負荷が大きいので避ける
	- 使用するタグは、日記 #diary とノート #note のみ
	- 日記やノートの新規作成時、タグの自動付与

**認知負荷の低減**
- 不要な機能（プラグインや設定）をOFF
- Minimalテーマなどで視覚情報を削る

## テンプレートの使い方

> [!WARNING]
> このテンプレートを使用する際は、必ずプライベートリポジトリとして設定してください。個人情報や機密データの保護は利用者の責任となります。公開リポジトリでの使用は推奨されません。

「Use this template」から新規リポジトリを作成した場合は、不要なファイルが含まれているので削除しコミットしてください。

削除対象の不要なファイルおよびディレクトリ：
- README.md
- LICENSE
- 01_diary/2024/2024-09-16.md
- 02_notes/2024/SampleNote.md
- 03_assets/2024/sample/
- 03_assets/2024/sample/sample.drawio
- 03_assets/2024/sample/sample.png
- 03_assets/2024/sample/sample.svg
- 04_canvas/SampleCanvas.canvas

## ディレクトリの用途

- 00_template
	- テンプレート
- 01_diary
	- 日記
- 02_notes
	- ノート
- 03_assets
	- .md と .canvas 以外のファイル置き場
- 04_canvas
	- .canvas ファイル置き場
- 05_dataview
	- データ一覧表示

## 運用ルール（参考）

自身の用途に合わせてカスタマイズしてください。

**日々の記録**
- #diary ノートを毎日作成
	- 毎日の出来事、感想
	- その日限りの思考や感情
	- 1つの事柄に対して短い記述（10行以下）
	- 長くなるなら #note に書く
- 01_diary/YYYY 配下にファイルを配置（YYYYは年）
	- 1年で最大365~366ファイルのため、月別でディレクトリを別けない

**知識の蓄積**
- #diary から #note へのリンクを記載し、内容を記述
- 1つの事柄、1つのノート
	- Zettelkastenと同様に、1つのノートには1つの概念、アイデア、事柄のみを書く
- 書くこと：
	- 論題のタイトルに沿った事柄
	- 日付に依存しない情報や考え
	- 抽象的な概念や一般化された知識
	- 一般的、普遍的な内容
- 02_notes/YYYY 配下にファイルを配置（YYYYは年）
	- ノートを新規作成した年のディレクトリ配下にファイルが配置される
	- 年ごとのディレクトリ分割により、1ディレクトリあたりのファイル数を抑制
		- 大量のファイルによるパフォーマンス低下やファイルシステムの制限を回避
		- 長期的な運用でも安定したファイル管理が可能

**アセットの管理**
- アセットを使用するのは基本的に #note のみ
- 03_assets/YYYY 配下にアセットのグループごとにディレクトリを作成（YYYYは年）
	- 年ディレクトリは手動で作成
	- 関連する #note と同じ年になるように
- 図の作成：
	- VSCodeでdrawio拡張機能を使用
	- ソースファイルは *.drawio 形式で保存
	- 作成した図は *.png や *.svg などの形式で保存（drawio拡張機能で作成）
- ディレクトリ構成例：
	- 03_assets/2024/sample/
		- アセットグループディレクトリ
	- 03_assets/2024/sample/sample.drawio
		- drawioファイル
	- 03_assets/2024/sample/sample.png
		- drawioから出力した画像ファイル

**リンクの管理**
- リンクの作成方法：
	- `[[ノート名]]`の形式でリンクを作成する
	- リンクとなるノート名は、文章中に自然に登場できるような名称にする
		- 例：`[[バージョン管理]]には[[Git]]を使用している`
- #diary から #note へのリンク：
	- #diary では簡潔に書き、詳細を #note のリンクを作成し書く
		- 例：`今日は[[git branch コマンド]]について学んだ`
- #note 同士のリンク：
	- 現在のノートの内容と直接関連するノート間でリンクを作成
	- 例：
		```markdown
		# Git branch コマンド

		[[Git]]のブランチ操作に使用するコマンド。主な用途は[[バージョン管理]]における並行開発の実現。[[git merge コマンド]]と組み合わせて使用することが多い。

		## 基本的な使い方
		...
		```
- Map of Contents (MOC)：
	- 必要に応じて特定のトピックに関するMOCを作成可能
	- MOCは一階層のみとし、複雑な階層構造は避ける
	- 例：
		```markdown
		# Git (MOCとなるノート)
		- [[git branch コマンド]]
		- [[git init コマンド]]
		- [[git commit コマンド]]
		```
- リンクの見直し：
	- 定期的にリンクの妥当性を確認し、必要に応じて更新や削除を行う

### #diary と #note の区分基準

1. 時間性：
	- #diary: 今日の出来事、その日限りの思考や感情
	- #note: 日付に依存しない情報や考え
2. 記述量：
	- #diary: 短い記述（10行以下）
	- #note: より長い、詳細な記述
3. 具体性vs抽象性：
	- #diary: 具体的な出来事や行動（例：今日の予定、実際に行ったこと）
	- #note: 抽象的な概念や一般化された知識
4. 個人的vs一般的：
	- #diary: 個人的な経験や感想
	- #note: より一般的、普遍的な内容
5. 再利用性：
	- #diary: 一時的な情報や、その日限りの記録
	- #note: 将来的に参照する可能性が高い情報

例：
- 「今日の朝食はパンだった」→ #diary
- 「効果的な朝食の取り方について」→ #note
- 「明日の会議の準備をした」→ #diary
- 「プロジェクト管理の方法論」→ #note
- 「今日学んだこと：プログラミングの新概念X」→ #diary に簡潔に記述し、詳細は #note にリンクを張って記載

## Obsidian 設定

[ここからはじめる - Obsidian 日本語ヘルプ - Obsidian Publish](https://publish.obsidian.md/help-ja/%E3%81%93%E3%81%93%E3%81%8B%E3%82%89%E3%81%AF%E3%81%98%E3%82%81%E3%82%8B)
デフォルト設定から変更している部分を記載します。

### ファイルとリンク

- 内部リンクを毎回更新する
	- ON
- 新規ノートの作成場所
	- 以下で指定されたフォルダ
- 新規ノートを作成するフォルダ
	- 02_notes
- 新規添付ファイルの作成場所
	- 以下で指定されたフォルダ
- 添付ファイルフォルダのパス
	- 03_assets

### 外観

テーマ
- [Minimal](https://github.com/kepano/obsidian-minimal)
#### フォント

デフォルトは、中国語フォントになっています。
自分好みの日本語フォントを設定するとよいでしょう。
ここでは [M+ FONTS](https://mplusfonts.github.io) を設定しています。

- インターフェースフォント
	- M PLUS 1
- テキストフォント
	- M PLUS 1
- モノスペースフォント
	- M PLUS 1 Code

#### Interface

タブタイトルバーでファイル名が編集できるけれど、ファイル内でも編集できるので不要だと判断しました。
ヘッダーのメニューは使いません。機能はコマンドパレットから使います。

- タブタイトルバーを表示
	- OFF

## [コアプラグイン](https://publish.obsidian.md/help-ja/%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3/%E3%82%B3%E3%82%A2%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3) 設定

使用するコアプラグインを選択します。

ON のコアプラグインは以下

- アウトゴーイングリンク
- アウトライン
- クイックスイッチャー
- グラフビュー
- コマンドパレット
- デイリーノート
- ファイルエクスプローラ
- ページビュー
- ワークスペース
- 検索
- キャンバス

### [デイリーノート](https://publish.obsidian.md/help-ja/%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3/%E3%83%87%E3%82%A4%E3%83%AA%E3%83%BC%E3%83%8E%E3%83%BC%E3%83%88)

`01_diary/YYYY/YYYY-MM-DD.md` のディレクトリ構造となります。
年ディレクトリ配下に、一年で最大で365~366ファイルが生成されるだけなので、月ごとにフォルダ分けするのは不要と判断しました。

- 日付の書式
	- YYYY/YYYY-MM-DD
- 新規ファイルの場所
	- 01_diary
- テンプレートファイルの場所
	- 00_template/[[01_diary]]
- 起動時にデイリーノートを開く
	- ON

### [キャンバス](https://help.obsidian.md/Plugins/Canvas)

- 新規キャンバスファイルのデフォルトロケーション
	- 以下で指定されたフォルダ
- 新規キャンバスファイルが作成されるフォルダ
	- 04_canvas

## コミュニティプラグイン 設定

### [Auto Link Title](https://github.com/zolrath/obsidian-auto-link-title)

URLを貼ったら、自動的にウェブページを取得してリンクタイトルを抽出し、正しいタイトルが設定されたマークダウンリンクを作成するプラグイン

設定の変更なし

### [Calendar](https://github.com/liamcain/obsidian-calendar-plugin)

シンプルなカレンダーを表示するプラグイン

設定の変更なし

### [Dataview](https://github.com/blacksmithgu/obsidian-dataview)

Obsidian Vaultをクエリ可能なデータベースとして扱うプラグイン

日記 #diary とノート #note を一覧表示するために使用します。
05_dataview配下に使いそうな一覧表示を用意しています。
自分自身の用途に合わせてカスタムしてください。

- [[00_all_by_filename_asc]]
	- 日記とノートの全ファイルをファイル名昇順で表示
- [[00_all_by_updated_desc]]
	- 日記とノートの全ファイルを最終更新日降順で表示
- [[01_diary_by_filename_asc]]
	- 日記の全ファイルをファイル名昇順で表示
- [[01_diary_by_updated_desc]]
	- 日記の全ファイルを最終更新日降順で表示
- [[02_notes_by_filename_asc]]
	- ノートの全ファイルをファイル名昇順で表示
- [[02_notes_by_updated_desc]]
	- ノートの全ファイルを最終更新日降順で表示

### [Hider](https://github.com/kepano/obsidian-hider)

Obsidian UI の特定の部分を隠すことができるプラグイン

デフォルトから変更した設定：
- Hide properties in Reading view → ON
	- リーディングビューでプロパティを隠す
- その他
	- 自身の好みで設定してください

### [Templater](https://github.com/SilentVoid13/Templater)

Templaterプラグインは、テンプレート言語を定義しています。
それによって、変数や関数の結果をノートに挿入することができます。
また、それらの変数や関数を操作するJavaScriptコードを実行することもできます。

デフォルトから変更した設定：

- Template folder location → 00_templates
	- テンプレートフォルダの場所
- Trigger Templater on new file creation → ON
	- 新規ファイル作成でTemplaterをトリガーするか

Template hotkeys
- 00_templates/[[10_current_time]].md
	- [[10_current_time]]は、H3で時間を挿入するテンプレート
	- Hotkey設定：
		- Templater: Insert 00_templates/10_current_time.md → Alt + ;

Folder templates
- 02_notes ... 00_templates/[[02_note]].md
	- 02_notesフォルダ配下に、新規ファイル作成したときに適応するテンプレートの設定

### [Git](https://github.com/Vinzent03/obsidian-git)

Gitで保管庫を管理するプラグイン

方針：
- mainブランチ1本
- コミットは手動で行う
	- Backup で一括操作
	- Backup = Staging → Commit → Pull → Push
- プッシュとプルは定期的に自動で行う
	- リポジトリの競合を可能な限り防ぐ
- Obsidianの起動時は自動的にプル
- Obsidianの終了方法はショートカット（Ctrl + Q）を使用
	- `Git: Create backup and close`
		- Backup
		- Obsidianを閉じる

デフォルトから変更した設定：

Automatic：
- Split automatic commit and push → ON
	- 自動コミットとプッシュを分割
- Vault commit interval (minites) → 0 (OFF)
	- 自動で`git commit`を行う周期
- Vault push interval (minutes) → 20
	- 自動で`git push`を行う周期
- Auto pull interval (minites) → 60
	- 自動で`git pull`を行う周期

Backup：
- Pull updates on startup → ON
	- Obsidian起動時に最新の変更を取得
- Push on backup → ON
	- バックアップをプッシュする
- Pull changes before push → ON
	- プッシュ前にプルを行う

Hotkey 設定：
- Git: Create backup and close → Ctrl + Q
	- バックアップの作成とObsidianの終了

### [Outliner](https://github.com/vslinko/obsidian-outliner)

WorkflowyやRoamResearchのようなリストの操作感にするためのプラグイン

個人的に、VSCodeと同じような操作感にするために入れています。
- Alt + ↑ でリストを上に移動
- Alt + ↓ でリストを下に移動

Outliner 設定：
- Stick the cursor to the content → Stick cursor out of bullets and checkboxes
	- カーソルをコンテンツに固定 → カーソルを箇条書きやチェックボックスの外に固定
- Enhance the Tab key → OFF
	- Tabキーの機能拡張
- Enhance the Enter key → OFF
	- Enterキーの機能拡張
- Enhance the Ctrl+A or Cmd+A behavior → ON
	- Ctrl+AまたはCmd+Aの動作拡張
- Improve the style of your lists → OFF
	- リストのスタイル改善
- Draw vertical indentation lines → OFF
	- 垂直インデントラインの描画
- Vertical indentation line click action → Toggle Folding
	- 垂直インデントラインクリック時の動作 → 折りたたみの切り替え
- Drag-and-Drop → ON
	- ドラッグアンドドロップ
- Debug mode → ON
	- デバッグモード

Hotkey 設定：
- Outliner：Move list and sublists down → Alt + ↓
	- アウトライナー：リストとサブリストを下に移動
- Outliner：Move list and sublists up → Alt + ↑
	- アウトライナー：リストとサブリストを上に移動

### [Minimal Theme Settings](https://github.com/kepano/obsidian-minimal-settings)

Minimal Theme 付属のプラグイン
Obsidianの設定パネルからテーマをカスタマイズすることができます。

デフォルトから変更した設定：
- フォントサイズの設定はご自由に

Features：
- Underline internal links → OFF
	- 内部リンクに下線を引く
- Maximize media → OFF
	- 画像と動画を行幅分埋める

Typography：

- Text font size → 16
	- テキストのフォントサイズ
- Small font size → 13
	- 小さいフォントサイズ
- Line height → 2
	- 行の高さ
- Normal line witdh → 40
	- 通常の行の幅

### [Style Settings](https://github.com/mgmeyers/obsidian-style-settings)

スニペット、テーマ、プラグインのCSSファイルで設定オプションのセットを定義することができるプラグイン

デフォルトから変更した設定：
- フォントサイズの設定はご自由に

Minimal → Headings → Level 1 Headings：
- H1 font size → 2em
	- H1のフォントサイズ

Minimal → Headings → Level 2 Headings：
- H2 font size → 1.6em
	- H2のフォントサイズ
- H2 divider line → ON
	- H2の区切り線

Minimal → Headings → Level 3 Headings：
- H3 font size → 1.4em
	- H3のフォントサイズ
- H3 divider line → ON
	- H3の区切り線

Minimal → Headings → Level 4 Headings：
- H4 font size → 1.2em
	- H4のフォントサイズ
- H4 divider line → ON
	- H4の区切り線

Minimal → Properties：
- Hide properties heading → ON
	- プロパティの見出しを隠す
- Hide "Add property" button → ON
	- "プロパティの追加"ボタンを隠す

Minimal → Sidebars：
- Hide help button → ON
	- ヘルプボタンを隠す
