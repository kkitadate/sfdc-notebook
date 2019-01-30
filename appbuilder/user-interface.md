# ユーザインターフェース

アプリケーションビルダー試験での割合 : 14%

## 試験範囲

- [ユーザインターフェースのカスタマイズオプション](user-interface.md#ユーザインターフェースのカスタマイズオプション)を説明する
- [カスタムボタン、リンク、およびアクションの機能とユースケース](user-interface.md#カスタムボタン、リンク、およびアクションの機能とユースケース)を説明する
- [アプリケーションにLightningコンポーネントを組み込む](user-interface.md#アプリケーションにLightningコンポーネントを組み込む)場合に利用できる 宣言的オプションを説明する
- 与えられたシナリオに従って、適切な[ユーザインターフェース設計](user-interface.md#ユーザインターフェース設計)を決定する

### ユーザインターフェースのカスタマイズオプション

[ユーザインターフェースの設定](https://help.salesforce.com/articleView?id=customize_ui_settings.htm&type=5)

### カスタムボタン、リンク、およびアクションの機能とユースケース

[アクション、ボタン、およびリンクの提供](https://help.salesforce.com/articleView?id=working_with_buttons_links_actions.htm&type=5)

- ボタン,リンク: Salesforceデータや外部サイト,外部サービスとのやりとりが可能となる
- アクション: Chatterパブリッシャー, Salesforceアプリケーションでレコードの作成など

#### カスタムボタンとカスタムリンク

[カスタムボタンとカスタムリンク](https://help.salesforce.com/articleView?id=customize_enterprise.htm&type=5)

- 表示ウィンドウプロパティ
  - リンク/ボタンの実行対象をどのように表示するかが決定される
- 一部の標準ボタンのデフォルトアクションの上書きが可能
  - 組織のニーズに合うようにタブのホームページ動作をカスタマイズできる
- 例: [カスタムボタンとカスタムリンクの例](https://help.salesforce.com/articleView?id=links_useful_custom_buttons.htm&type=5)

##### カスタムリンク
- 外部URLにリンク可能
  - www.google.com
  - Visualforceページ
  - 会社のイントラネット など

##### カスタムボタン
- 外部アプリケーションに接続する
  - 取引先責任者の住所への対応づけを表示するWebページ など
- カスタムリンクを起動する

#### クイックアクション

[クイックアクション](https://help.salesforce.com/articleView?id=actions_overview.htm&type=5)

### アプリケーションにLightningコンポーネントを組み込む

#### Lightning ページ

[Lightning ページ](https://help.salesforce.com/articleView?id=lightning_page_overview.htm&type=5)

- ページレイアウトとVisualforceページの中間
- Lightningコンポーネントを使用して作成される
  - 設定および再利用が可能
  - ページ範囲にドラッグアンドドロップできる
- アプリケーションページを作成
  - ナビゲーションに追加できる
  - 最も重要なオブジェクトや項目にすばやくアクセスできるようになる
- レコードページやホームページの作成
- コンソールアプリケーションでは, レコード表示操作するための固定領域を使用して作成できる
- [Lightning ページの標準コンポーネント](https://help.salesforce.com/articleView?id=lightning_page_components.htm&type=5)
  - 最大 25 個のコンポーネントを配置できる

##### Lightning ページの種別

[Lightning ページの種別](https://help.salesforce.com/articleView?id=lightning_page_types.htm&type=5)

- アプリケーションページ
- ホームページ
- レコードページ
- メールアプリケーションペイン

### ユーザインターフェース設計

#### Lightning アプリケーションビルダー

[Lightning アプリケーションビルダー](https://help.salesforce.com/articleView?id=lightning_app_builder_overview.htm&type=5)

- 以下を簡単に作成するためのポイント&クリックツール
  - Salesforceモバイルアプリケーション
  - Lightning Experienceのカスタムページ
- Lightningアプリケーションを一元的に設定できる
- [Lightning アプリケーションビルダーの考慮事項](https://help.salesforce.com/articleView?id=lightning_app_builder_customize_lex_pages_considerations.htm&type=5)

## 参照

- トレイル
  - [Lightning Experience への移行 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/trails/lex_admin_migration)
- モジュール
  - [アプリケーションの簡易カスタマイズ](https://trailhead.salesforce.com/ja/content/learn/modules/lex_migration_customization?trail_id=lex_admin_migration)
  - [Lightning アプリケーション](https://trailhead.salesforce.com/ja/content/learn/modules/lightning_apps?trail_id=lex_admin_migration)
  - [Lightning アプリケーションビルダー](https://trailhead.salesforce.com/ja/content/learn/modules/lightning_app_builder?trail_id=lex_admin_migration)