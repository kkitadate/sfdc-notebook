# ワークフロー/プロセスの自動化

アドミニストレーター試験での割合 : 12%

## 試験範囲

- 与えられたシナリオに従って、<b>ワークフロー/プロセス</b>の機能を使用した<b>適切な自動化ソリューション</b>を特定する
- <b>承認プロセス</b>の機能とユースケースを説明する


ワークフロー/プロセス
---


### ワークフロー
[ワークフロー](https://help.salesforce.com/articleView?err=1&id=customize_wf.htm&type=5)により、標準的な社内手続きやプロセスを自動化する。例えば次の種別のアクションがある。

- ToDo - ユーザ、ロール、またはレコードの所有者に新規 ToDo を割り当て
- メールアラート - 指定した 1 人以上の受信者にメールを送信
- 項目自動更新 - レコード上の項目の値を更新
- アウトバウンドメッセージ - API メッセージ (XML 形式) を指定のリスナーに送信


### ワークフロールール
ワークフロールールは、一連のワークフロー手順のメインコンテナであり、if/then ステートメントに要約できる。

各ワークフロールールは、次の要素から構成される。

- ワークフロールールを実行する条件 
- レコードが条件に一致したときに実行する[ルール適用時のアクション]
- 条件一致時にキューに追加され、タイムトリガに従って実行される[時間ベースのアクション]

※ワークフローを実行する条件(評価条件)に「作成されたとき、および編集されるたび」を選択した場合、[時間ベースのアクション] は追加できない。

[ワークフロールールの作成](https://help.salesforce.com/articleView?err=1&id=workflow_rules_new.htm&type=5)


### プロセスビルダー
[Lightning プロセスビルダー](https://help.salesforce.com/articleView?id=process_overview.htm&type=5)

- 作成時のプロセスを視覚的に表現できる
- 設定 > [プロセスビルダー]


プロセスビルダーでは、自動化ニーズに応じて 3 種別のプロセスがサポートされる。

- レコード変更プロセス: レコードの作成または更新時
- イベントプロセス: プラットフォームイベントの発生時
- 呼び出し可能なプロセス: 別のプロセスなど、他の何かによって呼び出された時


各プロセスは、次の要素から構成されます。

- アクショングループをいつ実行するかを決定する条件
- アクショングループ: ルール適用時のアクション, スケジュール済みアクション。レコード変更プロセスのみ、スケジュール済みアクションがサポートされる。


### プロセスビルダーとワークフローの比較
- ワークフローと同じアクションを実行する場合、より強力で柔軟になったプロセスビルダーを使用する
- Apex またはフローをプロセスからコールすることも可能


適切な自動化ソリューション
---
[使用する自動化ツール](https://help.salesforce.com/articleView?id=process_which_tool.htm&type=5)

- レコードの承認：承認プロセス
- レコードが特定の値を持つ場合
 - if/then ステートメントに簡略化できる：プロセスビルダー
 - アウトバウンドメッセージを送信：ワークフロー、プロセスから Apex コードをコール
 - 複雑なプロセス、高度な機能を必要とするプロセスの場合：Cloud Flow Designer[^3]

 [^3]: Spring ’19 releaseからFlow Builderが導入されるようです。 : [Get Ready for the New Flow Builder - Salesforce Admins](https://admin.salesforce.com/flowbuilder)


承認プロセス
---
[承認プロセスの設定](https://help.salesforce.com/articleView?id=approvals_getting_started.htm&type=5)

- レコードの承認に必要な一連のステップを指定可能
- ユーザは、[承認申請] をクリックしたときにどの承認プロセスが起動されるかわからない
- 各承認プロセスの条件と実施内容をユーザに理解してもらう必要がある

[ユーザの承認申請](https://help.salesforce.com/articleView?id=approvals_users.htm&type=5)

- 承認履歴の状況を確認するには、[承認履歴] 関連リストを参照する


参照
===
- [適切な自動化ツールの選択 単元 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/business_process_automation/process_whichtool)
- [ビジネスプロセスの自動化](https://help.salesforce.com/articleView?id=extend_click_process.htm&type=5)
