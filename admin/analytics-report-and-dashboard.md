# 分析 - レポートとダッシュボード

アドミニストレーター試験での割合 : 10%

## 試験範囲

- <b>レポート</b>の作成またはカスタマイズ時に利用できるオプションを説明する (例: <b>レポートタイプ、レポート形式、項目、データの集計、データの絞り込み、 グラフ、スケジュール、条件付き強調表示</b>)
- <b>レポートにおける共有モデル</b>の影響を説明する
- <b>ダッシュボード</b>の作成および変更時に利用できるオプションを説明する (例: <b>ダッシュボードコンポーネント、データソース、グラフの種類、スケ ジュール、実行ユーザ</b>)
- <b>カスタムレポートタイプ</b>の機能を説明する


レポート
---
- 定義した条件を満たすレコードのリスト
- 行と列で表示され、絞り込み、グループ化、グラフィカルなグラフでの表示が可能

レポートを使用すると、Salesforce データにアクセスできる。 ※データへのアクセス権が必要


#### レポートビルダー
[レポート]タブ > [新規レポート] or 既存のレポートで[カスタマイズ]

[Salesforce Classic でのレポートの作成](https://help.salesforce.com/articleView?err=1&id=reports_builder_editing.htm&type=5)


### レポートタイプ
レポートには、レポートタイプで定義された条件を満たすレコードのみが表示される。

- レポートタイプによって、レポート作成時に使用可能な項目とレコードが決まる
- 主オブジェクトと関連オブジェクト間のリレーションに基づく


### レポート形式
レポートには、表形式、サマリー、マトリックス、または結合形式を使用できる。

- レポートビルダーで[形式]メニューを使用して選択可能
- デフォルトは表形式


#### レポート形式の変更
形式を変更すると、条件とグルーピングに影響する。(下記ヘルプページ参照)

[レポート形式の選択](https://help.salesforce.com/articleView?err=1&id=reports_changing_format.htm&type=5)


### 項目
レポートビルダーの[項目]ペインには、選択したレポートタイプの項目がフォルダごとに分類されて表示される。

[レポート項目](https://help.salesforce.com/articleView?id=reports_builder_fields.htm&type=5)


### データの集計
[レポートデータの集計](https://help.salesforce.com/articleView?id=reports_builder_fields_summaries.htm&type=5)

- レポートビルダーでは、[合計]、[平均]、[最小]、[最大] の 4 つの組み込み関数を使用可能。
- 集計項目を追加する前に、レポートデータをグループ化する。集計項目列には少なくとも 1 つのグループが必要
- １つのレポートに許可される総計値の数(集計項目など) : 最大 5 個

[集計項目を使用したレポートデータの評価](https://help.salesforce.com/articleView?id=reports_builder_fields_formulas.htm&type=5)


### データの絞り込み
Salesforce Classic では、レポートの絞り込みはレポートビルダーで行う。[^1]

- レポートビルダーで [追加] ドロップダウンメニューを開き、条件種別を選択
- [項目] ペインから [条件] ペインに項目をドラッグして、レポート検索条件を追加可能

[レポートデータの絞り込み](https://help.salesforce.com/articleView?id=reports_builder_filtering.htm&type=5)

[^1]: Lightning Experience ではレポート表示中に絞り込みが可能。


### グラフ
グラフをレポートに追加するだけの場合、レポートグラフを使用する。 ※ダッシュボード(後述)を作成しない場合に適している

[レポートデータのグラフィカル表示](https://help.salesforce.com/articleView?id=reports_graphic.htm&type=5)

- レポートテーブルのすぐ上に表示される
- ダッシュボードコンポーネントにも表示できる

グラフを追加するには、レポートに少なくとも 1 つのグルーピングが必要。


### スケジュール
[Salesforce Classic でのレポートのスケジュール](https://help.salesforce.com/articleView?id=reports_schedule_overview.htm&type=5)

[レポート]タブ > [レポート実行]ドロップダウンメニュー > [実行のスケジュール]

- レポートが保存されているフォルダにアクセスできる実行ユーザを指定
- 実行ユーザが無効になると、レポートが実行されず管理者へ通知メールが送信される
- 希望開始時刻 : スケジュールを設定したユーザのタイムゾーンに基づいて実行される


### 条件付き強調表示
条件付き強調表示を有効化するには、レポートに集計項目またはカスタム集計項目が少なくとも 1 つ含まれている必要がある。(１つのレポートに3つまで設定可能)

[データ範囲の強調表示](https://help.salesforce.com/articleView?id=reports_builder_highlighting.htm&type=5)


### レポートのエクスポート
- [印刷用に表示] : レポートの形式とサマリー情報を保持したままエクスポートが可能
- [詳細のエクスポート] : 詳細行のみを表示 (表形式となる)

以下参照

[レポートの「印刷用に表示」が Excel への「詳細のエクスポート」と異なるのはなぜですか？](https://help.salesforce.com/articleView?id=000005095&language=ja&type=1)


レポートにおける共有モデル
---
レポートとダッシュボードを共有するには、レポートまたはダッシュボード自体ではなくフォルダを共有する。

[レポートフォルダおよびダッシュボードフォルダ](https://help.salesforce.com/articleView?id=analytics_sharing.htm&type=5)


#### フォルダ
- フォルダを作成すると、作成者がそのフォルダのマネージャになる
- フォルダを表示できるのは、作成者とシステム管理者権限を持つ他のユーザのみ


フォルダは公開、非表示、または共有することができ、「参照のみ」か「参照・更新」に設定できる

- アクセス権を持つユーザの制御は、ロール、権限、公開グループ、ライセンスの種類に基づいて行う
- 組織全体で使用できるようにしたり、非公開にして所有者のみにアクセス権を与えることも可能


レポートまたはダッシュボードを開くには、次の権限が必要となる。

- レポートまたはダッシュボードの保存先フォルダへのアクセス権
- 必要なユーザ権限(例：レポート実行の場合「レポート実行」ユーザ権限が必要)


#### レポート制限、制限および割り当て

[レポート制限、制限および割り当て](https://help.salesforce.com/articleView?id=rd_reports_limits.htm&type=5)


ダッシュボード
---
- 組織のレコードの主要な総計値とトレンドを視覚化されたコンポーネントとして表示する
- グラフ、ゲージ、テーブル、総計値、または Visualforce ページなど

[Salesforce Classic ダッシュボードの操作](https://help.salesforce.com/articleView?id=dashboard_builder_editing.htm&type=5)


#### フォルダ
- レポートと同様、ダッシュボードもフォルダ単位でユーザのアクセスが制御される
- ダッシュボードコンポーネント(次項参照)を表示するには、基礎となるレポートへのアクセス権も必要

Chatter でダッシュボードをフォローして、フィードに投稿されたダッシュボードに関する更新を取得することも可能。


### ダッシュボードコンポーネント
- レポートと1対1で対応
- 同じレポートを 1 つのダッシュボード内の複数コンポーネントで使用できる

[Salesforce Classic でのダッシュボードコンポーネントの追加](https://help.salesforce.com/articleView?id=dashboards_add_component.htm&type=5)


### データソース
- レポート: グラフ、ゲージ、統計値、テーブル(レポートデータを列形式で表示)
- Visualforce ページ(Classicのみ): カスタムコンポーネントや、別のコンポーネントの種類では表示できない情報を表示する場合に使用


### グラフの種類
レポートとダッシュボードで、データを横棒、縦棒、折れ線、図形などの要素の形式で表示可能。

[グラフの種類](https://help.salesforce.com/articleView?id=chart_types.htm&type=5)


### スケジュール
ダッシュボードの更新をスケジュールできる。更新されたダッシュボードの結果をメールで受信する。[^2]

[Salesforce Classic でのダッシュボードの更新のスケジュール設定](https://help.salesforce.com/articleView?id=dashboards_schedule_refresh.htm&type=5)

[^2]: Developer Editionでは使用不可のよう。実際にやろうとしてもできませんでした。[更新のスケジュール]ボタンが表示されず([更新]を押すと即時更新となってしまう) 参考：[Salesforce Classic でのダッシュボードの更新のスケジュール設定](https://help.salesforce.com/articleView?id=dashboards_schedule_refresh.htm&type=5) > 「使用可能なエディション」の欄


### 実行ユーザ
- 実行ユーザのセキュリティ設定によってダッシュボードに表示されるデータが決まる。
- 情報が必要以上に開示されないように、実行ユーザは慎重に選択する必要がある。


#### 動的ダッシュボード
- 実行ユーザが常にログインユーザであるダッシュボード
- ユーザにはそれぞれのアクセスレベルに応じたダッシュボードが表示される

必要以上のアクセス権が付与されることに懸念がある場合は、動的ダッシュボードを検討すべきである。


カスタムレポートタイプ
---
定義済みの標準レポートタイプに必要項目がない場合、カスタムレポートタイプの作成が必要となる。

- 表示するオブジェクトを選択する
- 表示するオブジェクトのリレーションを定義する
- 列として使用できる各オブジェクトの項目を選択する


#### カスタムレポートタイプを使用したレポートの作成
レポートタイプに含まれるオブジェクトに対するユーザのアクセス権によって、カスタムレポートタイプが使用できるか(レポート作成時のウィザードに表示されるか)が制御される。


参照
===
- [Salesforce Classic のレポートおよびダッシュボード | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/reports_dashboards?trailmix_creator_id=00550000006yDdKAAU&trailmix_id=prepare-for-your-salesforce-administrator-credential)


### Salesforce help
- [レポートとダッシュボード](https://help.salesforce.com/articleView?id=analytics_overview.htm&type=5)
- [レポートとダッシュボードのカスタマイズ](https://help.salesforce.com/articleView?id=customize_reports_and_dashboards.htm&type=5)
- [レポート制限、制限および割り当て](https://help.salesforce.com/articleView?id=rd_reports_limits.htm&type=5)
