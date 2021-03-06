# ビジネスロジックとプロセスの自動化

アプリケーションビルダー試験での割合 : 27%

## 試験範囲

- [レコードタイプの機能とユースケース](buisiness-logic-and-process-automation.md#レコードタイプの機能とユースケース)を説明する
- [数式項目の機能とユースケース](buisiness-logic-and-process-automation.md#数式項目の機能とユースケース)を説明する
- [積み上げ集計項目の機能、ユースケースおよび影響](buisiness-logic-and-process-automation.md#積み上げ集計項目の機能、ユースケースおよび影響)を説明する
- [入力規則の機能とユースケース](buisiness-logic-and-process-automation.md#入力規則の機能とユースケース)を説明する
- [承認プロセスの機能とユースケース](buisiness-logic-and-process-automation.md#承認プロセスの機能とユースケース)を説明する
- [ワークフロー、VisualWorkflow、プロセスビルダーの機能とユースケース](buisiness-logic-and-process-automation.md#ワークフロー、VisualWorkflow、プロセスビルダーの機能とユースケース)を説明する
- 与えられた複数のビジネス要件に従って、[ビジネスプロセスを自動化する](buisiness-logic-and-process-automation.md#ビジネスプロセスを自動化する)ソリューションを推奨する
- [項目自動更新によって生じる問題と再帰の可能性](buisiness-logic-and-process-automation.md#項目自動更新によって生じる問題と再帰の可能性)を説明する

### レコードタイプの機能とユースケース

[ユーザごとのビジネスプロセスの調整](https://help.salesforce.com/articleView?id=customize_recordtype.htm&type=5)

- レコードタイプごとに以下をカスタマイズできる
  - ビジネスプロセス
  - 選択リストの値
  - ページレイアウト
- ユーザプロファイルごとに使用するレコードタイプを指定可能
- 例: 営業部門ごとに使用するリードソースの値を切り替える

### 数式項目の機能とユースケース

[数式を使用した項目値の計算](https://help.salesforce.com/articleView?id=customize_formuladef.htm&type=5)

- 他の項目, 差し込み項目, または式に基づいて, 値が自動的に計算される
- 特定の値への参照となるため, 数式項目自体の値は変更不可
  - 参照先を変更すると, 自動で値は変更される
- レコードを表示した際に数式が実行され値が取得される
- 数式にはコメント追加可能("/* ... */")
- ユースケースについてはヘルプを参照 -> [高度な数式項目の例](https://help.salesforce.com/articleView?id=useful_advanced_formulas.htm&type=5)

#### 数式項目の制限

[数式項目の制限および制約](https://help.salesforce.com/articleView?id=formula_field_limits.htm&type=5)

- 文字数制限: 最大 3,900 文字 (数式の評価後は 1,300 文字)
- 保存サイズ制限:  保存時に 4,000 バイト以下
- コンパイルサイズ制限: コンパイル時に 5,000 バイト以下 (コンパイルサイズの大きい関数に注意)

### 積み上げ集計項目の機能、ユースケースおよび影響

[積み上げ集計項目](https://help.salesforce.com/articleView?id=fields_about_roll_up_summary_fields.htm&type=5)

- 関連リストにある関連レコードから値を取得
- 従レコードの値に基づいて主レコードの値を集計し表示する
  - 従レコードは主従関係によって主レコードと関連付けが必要
    - 主オブジェクトに積み上げ集計項目が存在する場合, 従オブジェクトとの主従関係は変更できない
  - 計算の種類: COUNT, SUM, MAX, MIN
    - 数値、通貨、およびパーセント項目が使用可能
    - 上記に加え, MAX,MIN のみ[日付]および[日付/時間]項目が使用可能
- 例: 取引先のカスタム項目に, 関連レコードの持つ値の合計を表示する

### 入力規則の機能とユースケース

[入力規則](https://help.salesforce.com/articleView?id=fields_about_field_validation.htm&type=5)

- レコードを保存する前に, 入力したデータが指定の基準を満たしているか確認
- 設定する際に必須となる内容について
  - エラー条件数式
    - Boolean値が返却されるような式とする
  - エラーメッセージ
    - 具体的なメッセージ内容とし, 項目ラベルを含めるようにする(特にページ上部に表示の場合)
  - エラー表示場所
    - ページ上部 or 項目の直下
    - 削除済み項目, 参照のみ項目, ページレイアウトで非表示 の場合は自動でページ上部となる
- 例: 数字入力のみ, 日付や数値の範囲, Webサイトなど拡張子, 有効な国(2文字の国名コードを利用)
  - その他の例 -> [入力規則の例](https://help.salesforce.com/articleView?id=fields_useful_field_validation_formulas.htm&type=5)
- その他入力規則についての考慮事項はヘルプ参照 -> [入力規則の考慮事項](https://help.salesforce.com/articleView?id=fields_validation_considerations.htm&type=5)

### 承認プロセスの機能とユースケース

[承認](https://help.salesforce.com/articleView?id=what_are_approvals.htm&type=5)

- レコード承認の方法を自動化するため以下を設定
  - 承認に必要なステップ, 各ステップの承認者
  - 承認プロセス中の状況に基づいて実行されるアクション
- 承認の申請,承認/却下 の際に行われる処理を定義可能
  - メール通知, レコード値の更新, など
- 例: 有給休暇申請, 経費申請, 商談の割引, 求職者の採用
  - 詳しくはこちら -> [承認プロセスのサンプル](https://help.salesforce.com/articleView?id=approvals_useful_approval_processes.htm&type=5)
- その他承認の制限や考慮事項についてはヘルプ参照 -> [承認の制限および考慮事項](https://help.salesforce.com/articleView?id=approvals_considerations.htm&type=5)

### ワークフロー、VisualWorkflow、プロセスビルダーの機能とユースケース

#### ワークフロー

[ワークフロー](https://help.salesforce.com/articleView?id=customize_wf.htm&type=5)

#### VisualWorkflow

[Lightning フロー](https://help.salesforce.com/articleView?id=vpm_lightning_flow.htm&type=5)

> すでに廃止されていますが、フローの設計、管理、実行を行う製品の名称です。Visual Workflow に取って代わったのが、Lightning フロー [^1]

- 2つのポイント＆クリック自動化ツール
  - [プロセスビルダー](buisiness-logic-and-process-automation.md#プロセスビルダー)
  - クラウドフローデザイナ
    - ユーザ操作: ウィザードやガイド付きUIでのデータ入力など
    - バックグラウンドでの自動実行: ユーザロールが変更された時の自動レコード転送など
    - [フローの制限および考慮事項](https://help.salesforce.com/articleView?id=vpm_considerations.htm&type=5)
    - 例: [一般的なフロータスク](https://help.salesforce.com/articleView?id=vpm_designer_common.htm&type=5), [サンプルフロー](https://help.salesforce.com/articleView?id=vpm_designer_examples.htm&type=5)
    - [フローのリファレンス](https://help.salesforce.com/articleView?id=vpm_reference.htm&type=5)
    - [フローの配布](https://help.salesforce.com/articleView?id=vpm_admin_using_flows.htm&type=5)
      - 内部ユーザ,外部ユーザ,システム,その他の組織 への配布が可能

#### プロセスビルダー

[Lightning プロセスビルダー](https://help.salesforce.com/articleView?id=process_overview.htm&type=5)

### ビジネスプロセスを自動化する

[使用する自動化ツール](https://help.salesforce.com/articleView?id=process_which_tool.htm&type=5)

#### ニーズに最も適した自動化ツールを選択する
- レコードの承認方法
  - 例: 従業員の休暇申請など
  - 承認プロセスを利用
- レコードが特定の値を持つ場合の処理
  - 例: 関連ケースがエスカレーションされた場合に, 取引先所有者に通知する
  - ワークフロールール, プロセス, フロー が利用可能
    - if/then ステートメントに簡略化できる場合: プロセスビルダーを使用
    - 複雑な機能を必要とするプロセスの場合: フローを使用
      - 例: 複雑な分岐ロジック(特定の条件が true の場合, さらに条件を評価)を使用する
        - ケースがエスカレーションされたかどうか
        - エスカレーションされた場合は, 取引先の地域を確認
        - ケースを送信するかどうかを判断
      - 例: 複数のレコードで並び替え、反復処理、操作を行う
        - 商談が完了および成立
        - 商談の割引を計算
        - 割引額を関連商談商品に適用
- ユーザまたは顧客からの情報収集およびその情報を使用した処理
  - 情報収集するウィザードを使用する場合: フローを使用
- 詳細は[使用する自動化ツール](https://help.salesforce.com/articleView?id=process_which_tool.htm&type=5) ("自動ツールの機能"の表)を参照

### 項目自動更新によって生じる問題と再帰の可能性

[項目自動更新アクションの考慮事項](https://help.salesforce.com/articleView?id=workflow_field_update_considerations.htm&type=5)

- ケース割り当て, リード割り当て, 自動レスポンスの各ルールの後に実行される
- メールアラート, ToDO, アウトバウンドメッセージの前に実行される
- 項目レベルセキュリティとは独立して機能する
  - ユーザのページレイアウトで項目が非表示となっていても更新可能
- 関連リスト内の情報に影響する場合に注意
  - 例: 商談の[金額],[完了予定日]が自動更新されると, 商談の[フェーズの履歴]関連リストに影響
- 以前は有効だった項目が, 無効な内容に書き換えられる場合に注意
  - ワークフローやプロセスのスケジュール済みアクションでのレコード更新では, 入力規則が実行されないため
- [項目変更後にワークフロールールを再評価する]を有効にした場合
  - 関連づけられたオブジェクトのすべてのワークフロールールが再評価される
  - 最初の項目自動更新の後, 最大5回まで実行される
  - 再帰的ループを作成するように設定されていないことを確認しておく
    - 組織で1時間のワークフロータイムトリガの上限を超える可能性があるため
- 項目自動更新が特定のユーザを参照している場合, そのユーザは無効にできない

## 参照

- [ビジネスプロセスの自動化](https://help.salesforce.com/articleView?id=extend_click_process.htm&type=5)
- [プロセスの自動化を動画で学ぶ](https://help.salesforce.com/articleView?id=000264900&language=ja&type=1)

[^1]: ヘルプのメモより引用 -> [ワークフロールールとフローの違いは?](https://help.salesforce.com/articleView?id=vpm_faq_workflow_comparing.htm&type=5)