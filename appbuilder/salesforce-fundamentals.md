# SALESFORCE の基本

アプリケーションビルダー試験での割合 : 8%

## 試験範囲

- Salesforce スキーマの[主要な CRM オブジェクトの機能](salesforce-fundamentals.md#主要なCRMオブジェクトの機能)を説明する
- 与えられたシナリオに従って、[宣言的カスタマイズ](salesforce-fundamentals.md#宣言的カスタマイズ)の限界と[プログラミングによるカスタマイズ](salesforce-fundamentals.md#プログラミングによるカスタマイズ)のユースケースを特定する
- [AppExchangeを使用した組織拡張](salesforce-fundamentals.md#AppExchangeを使用した組織拡張)の一般的なシナリオを特定する

### 主要なCRMオブジェクトの機能

[Lightning Experience の CRM の基礎学習 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/trails/crm-essentials-lightning-experience)

#### CRM

- カスタマーリレーション管理 (Customer Relationship Management)
- 顧客および見込み客とのリレーションを管理, データを追跡
- チームによる社内外のコラボレーション, ソーシャルメディアからのインサイトの収集, 重要な総計値の追跡, 各種チャネル経由のコミュニケーションをサポート

#### 主要な標準オブジェクト

- 取引先, 取引先責任者, リード, 商談

### 宣言的カスタマイズ

[システム管理者初級 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/trails/force_com_admin_beginner)

- フォームとドラッグアンドドロップツールを使用し, コードを記述せずにカスタマイズが可能

### プログラミングによるカスタマイズ

[開発者初級 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/trails/force_com_dev_beginner)

- 宣言的カスタマイズでは手の届かない, より複雑な機能や独自のインターフェースの実装など

### 宣言的カスタマイズとプログラミングによるカスタマイズのユースケース

[Visual Development – When to Click Instead of Write Code | Developer Force Blog](https://developer.salesforce.com/blogs/engineering/2014/12/forcedotcom-declarative-development.html)

宣言型か, コードを書いて開発を行うかについては, 以下の要素を考慮する。

- Cost and time : 開発のためのリソースにかかるコスト, および時間
- Maintenance : コードのメンテナンスが可能か(誰が行うのか)
- Complexity and Scalability : コードの複雑化によるスケーラビリティの制限, ガバナ制限への考慮
- Update Path : Salesforceのリリースに対応できるか
- Usability and User Productivity : ユーザビリティとユーザーの生産性への影響

### AppExchangeを使用した組織拡張

[AppExchange の基礎 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/appexchange_basics)

AppExchange戦略として, 以下を考慮する。

- リスト種別 : 以下のどちらが適しているか
  - ソリューション : Salesforce プラグイン(Lightning コンポーネントなど)
  - コンサルティングサービス : ビジネス上の問題を解決するカスタムソリューションの作成に関する支援
- 機能 : 優先度付け(必須のもの, あると便利なもの, など)
- 予算 : 無料 or 有料
  - 有料の場合は価格設定モデル : 一括払い or サブスクリプション
- 関係者のニーズ : 使用する側とのミーティングを行う
  - 期待事項, タイムライン についても把握する
- テスト : 本番組織へのインストール前に DE組織 または Sandbox環境 でテストを行う
- 技術的な考慮事項 : 組織固有の特性を検討する
  - エディションや機能ごとの互換性
  - Lightning Experience または Salesforce アプリケーション

## 参照

- [Salesforce Platform の基礎 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/starting_force_com?trail_id=force_com_admin_beginner)
