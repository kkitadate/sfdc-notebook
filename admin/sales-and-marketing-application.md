# 営業アプリケーションとマーケティングアプリケーション

アドミニストレーター試験での割合 : 15%

## 試験範囲

- 与えられたシナリオに従って、<b>セールスプロセス</b>の機能と影響を特定する
- 与えられたシナリオに従って、<b>販売効率向上に役立つ機能</b>を適用するケースを特定する
- <b>商品と価格表</b>の機能を説明する
- <b>リード管理</b>の機能を説明する (例: <b>リード取引開始、リードソース、リード項目の マッピング</b>)
- 与えられたシナリオに従って、<b>リード管理を自動化する</b>方法を特定する (例: <b>キュー、割り当てルール、Web-to-リード、自動レスポンス</b>)
- <b>キャンペーン管理</b>の機能を説明する (例: <b>階層、影響、キャンペーンメンバー</b>)
- <b>Salesforce コンテンツ</b>の機能を説明する


セールスプロセス
---
セールスプロセスを使用することで、商談の [フェーズ] 項目にて、ユーザのプロファイルに応じて異なる選択リストの値を表示できる。


### 商談
- 商談とは、進行中の案件のこと
- 既存の取引先の商談を作成、評価済みリードの取引を開始


### 商談の設定
- 類似商談
- 商談アップデートリマインダー
- 大規模商談アラート
  - 商談が初めてしきい値に達したときに、商談のアラートにより通知が送信される。確度がその後さらに高くなった場合でも、追加のアラートのトリガとなることはない
  - ただし、すでにアラートのトリガとなり、その後確度がしきい値より下がった場合は、再びしきい値に達したときに 2 回目のアラートのトリガとなる。


### 商談フェーズ
- 商談フェーズ：実行する ToDo の種類、担当者、販売が成功する確度に関連付け
- 営業の種別ごとに異なるセールスプロセスを設定
- 設定 > [セールスプロセス]、レコードタイプとの関連づけが必要 (プロセスに関連づけられるプロファイルを決定するため)


### 商談での取引先責任者の役割
- 商談のどの取引先責任者とやりとりをしているのか
- 各取引先責任者が商談とどのように関係しているのか
- [商談]のレコードページ > [取引先責任者のロール]


### チームでの販売
- 設定 > [商談チームの設定] > チームセリング設定の有効化
- 設定 > [商談チーム] > チーム内の役割


販売効率向上に役立つ機能[^1]
---
- [Sales Cloud について知る | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/trails/discover-sales-cloud)
- [Sales Cloud の基本](https://help.salesforce.com/articleView?id=sales_core.htm&type=5)

[^1]: Sales Cloud全般のことと解釈した。


商品と価格表
---
- [商品と価格表](https://help.salesforce.com/articleView?id=products_pricebooks.htm&type=5)
- 商品とは、販売するすべての品目およびサービスとその標準価格の基本カタログ
- 価格表を使用すると、商品と関連する特定用途向けリスト価格のカスタムコレクションを作成できる


リード管理
---



### リード
- リードとは、潜在的な顧客として認識された人や会社
- パイプラインに何があるか理解する、適切な案件にエネルギーを注げる
- 追跡、レポート、キャンペーンの対象設定を適切に行う


### リードの割り当て
- 関与している業種や、関心を持っている商品の種類などの条件に基づいて所有者に割り当て
- 設定 > [リードの割り当てルール]


### リードの取引開始
- [リード]のレコードページ > [取引の開始]
- リードレコードに保存されている情報を使用して、取引先、取引先責任者、商談が作成される
- リードの取引開始の際、入力規則は評価される。(設定 > [リードの設定] ページの [取引開始済みのリードに入力規則が必須] チェックボックス)


### リードソース
- 広告、パートナー、Web などのリードソース
- デフォルト値：Web / Phone Inquiry / Partner Referral / Purchased List / Other


### リード項目の マッピング
- [リード取引開始項目の対応付け](https://help.salesforce.com/articleView?id=lead_conversion_mapping.htm&type=5)
- [リードの取引開始に対するリードのカスタム項目の対応付けに関するガイドライン](https://help.salesforce.com/articleView?id=customize_mapleads_guidelines.htm&type=5)


リード管理を自動化する
---
- [キューの設定](https://help.salesforce.com/articleView?id=setting_up_queues.htm&type=5) (ワークロードを共有するチームへのレコードの優先度付け、配布、割り当て)
  - 例: 各地域のセールスグループ毎にキューを作成する
- [割り当てルールの設定](https://help.salesforce.com/articleView?id=creating_assignment_rules.htm&type=5) (処理方法を決定する条件を定義)
  - ルールに含まれるエントリの処理順序(1,2,3,...)
  - 割り当てられるために必要な条件
    - カスタム項目を使用可能
    - ただしその項目が削除された場合, ルールのエントリも自動的に削除
  - 条件に一致した場合に割り当てられる ユーザ または キュー
    - ここで指定したユーザは無効にすることはできない
    - リードに対する参照権限を持つユーザのみ割り当て可能
- [営業チームの Web サイトからのリードの生成](https://help.salesforce.com/articleView?id=setting_up_web-to-lead.htm&type=5), [Web-to-リードの設定に関するガイドライン](https://help.salesforce.com/articleView?id=customize_leadpreparation.htm&type=5)
- [自動レスポンスルールの設定](https://help.salesforce.com/articleView?id=creating_auto-response_rules.htm&type=5) (Web-to-リードに対しレコードの属性に基づいてルールを作成)
  - 例: リードソース毎にレスポンスの内容を切り替える
    - メールテンプレートを複数作成
    - リードソースに基づき, どのテンプレートを使用するか自動レスポンスルールを作成

キャンペーン管理
---
- [キャンペーン階層の設定](https://help.salesforce.com/articleView?id=campaigns_hierarchy_setup.htm&type=5), [キャンペーン階層の表示](https://help.salesforce.com/articleView?id=campaigns_viewhierarchy.htm&type=5)
- [キャンペーンメンバーの管理](https://help.salesforce.com/articleView?id=campaigns_members_landing_page.htm&type=5)
- [キャンペーンインフルエンス](https://help.salesforce.com/articleView?id=campaign_influence_parent.htm&type=5) (キャンペーンが商談パイプラインにどう影響するか)

商談に影響のあるキャンペーンのリストを商談詳細ページで直接管理することができる。

[影響のあるキャンペーンの商談への追加](https://help.salesforce.com/articleView?id=campaigns_influence_using.htm&type=5)


Salesforce コンテンツ
---
- [Salesforce CRM Content の概要](https://help.salesforce.com/articleView?id=content_about.htm&type=5)
- 組織内や Salesforce の主要な領域内でコンテンツを整理、共有、検索、管理


参照
===
- [Salesforce Classic のリードと商談 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/admin_intro_opptys_leads?trailmix_creator_id=00550000006yDdKAAU&trailmix_id=prepare-for-your-salesforce-administrator-credential)
- [商品、見積、契約 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/sales_admin_products_quotes_contracts?trailmix_creator_id=00550000006yDdKAAU&trailmix_id=prepare-for-your-salesforce-administrator-credential)
- [Sales Cloud: クイックルック | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/sales-cloud-platform-quick-look)
- [Sales Cloud の基本 | Salesforce Help](https://help.salesforce.com/articleView?id=sales_core.htm&type=5)
- [キャンペーン管理実装ガイド | Salesforce Developers](https://developer.salesforce.com/docs/atlas.ja-jp.salesforce_campaign_implementation_guide.meta/salesforce_campaign_implementation_guide/campaign_management.htm)

※割合、試験範囲は受験ガイド([資格一覧ページ](http://tandc.salesforce.com/credentials)よりダウンロード)の記載より抜粋
