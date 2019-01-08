# サービスアプリケーションとサポートアプリケーション

アドミニストレーター試験での割合 : 12%

## 試験範囲

- <b>ケース管理</b>の機能を説明する (例: <b>ケースのプロセス、ケース設定、ケースコメント</b>)
- 与えられたシナリオに従って、<b>ケース管理の自動化</b>の方法を特定する (例: <b>ケースの割り当て、自動レスポンス、エスカレーション、Web-to-ケース、メール-to-ケース、ケースチーム</b>)
- <b>ソリューション管理</b>や <b>Salesforce ナレッジ</b>の機能を説明する
- <b>コミュニティアプリケーション</b>の機能を説明する (例: <b>アイデア、アンサー</b>)


ケース管理
---
ケース管理とは、以下を目的として行うものである。

- 優れたサービスで顧客を感動させること
- 作業を最小限にするカスタムプロセスを介してケースを転送すること


### ケース
標準オブジェクトの一つ。Service Cloud の根幹と言える要素である。

- 顧客をあらゆる角度から把握することが可能
- 顧客に関する情報の例：取引先、取引先責任者、履歴、商品、メールのやりとりの有無、アラームタスク、知識ベースの記事など
- コラボレーション機能を備える。例：[ケースフィード](https://help.salesforce.com/articleView?id=case_interaction_overview.htm&type=5)、[ケースチーム](service-and-support-application.md#ケースチーム)


### ケースのプロセス
サポートプロセス。レコードタイプ毎にケースの進行状況の項目を設定できる。

- 設定 > [サポートプロセス]
- 顧客の問題を継続的に追跡してすばやく解決する


### サポートプロセスのカスタマイズ
ケースの [状況] 項目に使用する選択リストの値をカスタマイズできる。

- 作成したサポートプロセスを使用するには、ケースレコードタイプに関連付ける必要がある。
- レコードタイプを使用する場合は、ページレイアウトに追加する。


### Service Cloud
- カスタマーサービスおよびサポートアプリケーション
- 顧客が希望するコミュニケーションツールでサポートできる(オムニチャネル)
- バックグラウンド機能: アクションやワークフローをトリガする処理、ケースを適切な担当者や部署に転送する処理の自動化


### ケース設定
- 設定 > [サポート設定]
- [デフォルトのケース所有者], [自動ケース更新ユーザ], など


### ケースコメント
- 非公開 or 公開(カスタマーポータル、セルフサービスポータル、取引先責任者)
- [ケースコメント](https://help.salesforce.com/articleView?id=case_comments.htm&type=5)
- [Salesforce Classic でのケースフィードの使用](https://help.salesforce.com/articleView?id=case_interaction_overview.htm&type=5)


ケース管理の自動化
---
ケース管理の自動化について主な参照箇所をあげる。

- [ルールおよびキューの設定](https://help.salesforce.com/articleView?id=automation_rules_queues_parent.htm&type=5)
- [ルールの実行順序](https://help.salesforce.com/articleView?id=rules_processing_order.htm&type=0)
- [ルールごとの制限](https://help.salesforce.com/articleView?id=rules_limits.htm&type=0)


### キュー
- サポートチームのワークロードに優先度を付ける
- 特定の種類のケースを特定のエージェントが解決するためのリストを作成しておく
- 設定 > [キュー] > 作成・編集画面にて[サポートされるオブジェクト] > [ケース]を選択


#### サポートされるオブジェクト
- ケース、リード、カスタムオブジェクトなどが設定可能
- 取引先、取引先責任者、商談などは設定不可


### ケース の割り当て
- 受信したケースを適切なエージェントに割り当て
- 設定 > [ケースの割り当てルール] > [ルール名]を選択 > [エントリ]の作成・編集
- 複数のルール作成できますが、一度に有効にできるのは 1 つのルールのみ


### 自動レスポンス
- 顧客向けにカスタマイズされたメールレスポンスを送信
- 設定 > [ケース自動レスポンスルール] > [ルール名]を選択 > [エントリ]の作成・編集


### エスカレーション
- 一定時間内に解決されなかったケースを適切な人にエスカレーション (営業時間の考慮可)
- 設定 > [エスカレーションルール] > [ルール名]を選択 > [エントリ]の作成・編集 > [エスカレーションアクション]の作成・編集


### マクロ
- 適切なメールテンプレートの選択など、ケースに関する反復作業を実行
- [マクロの設定および使用 | Salesforce Help](https://help.salesforce.com/articleView?id=macros_def.htm&type=5)


### Web-to-ケース
- 自社の Web サイトからサービス要求を収集
- 最大 5,000 件 / 日の新規ケースを自動的に生成
- 設定 > [Web-to-ケース]
- [レコード情報を非表示]: ケースの作成に失敗した場合に顧客に送信されるメールでケース情報を非表示にする


### Web-to-ケース HTML ジェネレータ
- 設定 > [Web-to-ケース HTML ジェネレータ]
- 生成されたHTML コードをWeb サイトにて公開可能
- [Web-to-ケースを使用した Web フォームの提供](https://help.salesforce.com/articleView?id=customize_casecapture.htm)


### メール-to-ケース
- 設定 > [メール-to-ケース]
- [メール-to-ケースの設定] > [メール-to-ケースの有効化], [オンデマンドサービスの有効化]
- [メール-to-ケースの設定] > [ルーティングアドレス] > [新規]or[ルーティング名]を選択
- ルーティング情報の作成・編集画面 > [ケース優先度], [ケース発生源]を選択
- 会社のメールセキュリティポリシーとチームが扱うメール添付のサイズにより使い分ける


#### メール-to-ケース
- 会社のメールセキュリティポリシー: ファイアウォール内に保持
- チームが扱うメール添付のサイズ: 25MBを超える
- メール-to-ケースエージェントをダウンロードしてネットワークにインストール必要


#### オンデマンドメール-to-ケース
- 会社のメールセキュリティポリシー: ファイアウォール外で送信
- チームが扱うメール添付のサイズ: 25MB未満
- Apex メールサービスを使用してメールをケースに変換

[メール-to-ケースを使用したメールの送受信](https://help.salesforce.com/articleView?id=customizesupport_email.htm&type=5)


### ケースチーム
- 設定 > [ケースチーム内の役割]、[定義済みのケースチーム]
- [ページレイアウト] > [関連リスト]に表示可能、[ケースチームメンバーの更新]が利用可能
- ケースのクローズに向けて協力するグループのメンバーとそのロールの定義、各メンバーのアクセスレベルの定義
- [ケースチームの設定 | Salesforce Help](https://help.salesforce.com/articleView?id=caseteam_setup.htm&type=5)


ソリューション管理
---
- [ソリューションの概要 | Salesforce Help](https://help.salesforce.com/articleView?id=sol_def.htm&type=5)
- [Solutions Implementation Guide(英語)](https://resources.docs.salesforce.com/216/latest/en-us/sfdc/pdf/salesforce_solutions_implementation_guide.pdf)


Salesforce ナレッジ
---
[Salesforce ナレッジ | Salesforce Help](https://help.salesforce.com/articleView?id=knowledge_whatis.htm&type=5)


### ナレッジ記事とは
- サポートプロセスにおける役立つ情報を保存
- よくある質問への回答、有益な FAQ、エージェントによる顧客のサポート、ケースのクローズ、など


### ナレッジの主な利点
- 各ケースの詳細に基づいてエージェントに有益な情報が自動的に推奨される
- エージェントがケースを解決すると同時に記事を作成できる
- 同じような問題を抱える次の顧客やエージェントが解決策をすばやく見つけられる
- ケースの解決に役立つ記事は、そのケースに添付される
- よく似たタイトルのケースが開かれると、同じようなケースに添付された記事が一番上に表示される


コミュニティアプリケーション
---
設定 > [コミュニティ設定]を選択 > [コミュニティの有効化]を選択 > ドメイン名の設定が可能　※保存後は変更不可

[Salesforce コミュニティの有効化](https://help.salesforce.com/articleView?id=networks_enable.htm&type=5)


### アイデア、アンサー
- アイデア：[Salesforce コミュニティでのアイデアの作成と共有の促進](https://help.salesforce.com/articleView?id=ideas_salesforce_communities.htm&type=5)
- アンサー：[Chatter の質問の概要 | Salesforce Help](https://help.salesforce.com/articleView?id=collab_chatter_questions_overview.htm&type=5)

※アンサー(Chatter アンサー)についてはサポート終了 ([Salesforce の Q&A 機能の相違点](https://help.salesforce.com/articleView?id=questions_q_and_a_features.htm&type=0))


参照
===
- [Salesforce Classic の Service Cloud | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/service_basics?trailmix_creator_id=00550000006yDdKAAU&trailmix_id=prepare-for-your-salesforce-administrator-credential)
- [Service Cloud プラットフォーム: クイックルック | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/service-cloud-platform-quick-look)
- [Service Cloud | Salesforce Help](https://help.salesforce.com/articleView?id=service_cloud.htm&type=0)

※割合、試験範囲は受験ガイド([資格一覧ページ](http://tandc.salesforce.com/credentials)よりダウンロード)の記載より抜粋
