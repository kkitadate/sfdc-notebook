# データモデリングおよび管理

アプリケーションビルダー試験での割合 : 20%

## 試験範囲

- 与えられたシナリオに従って、[適切なデータモデルを決定する](data-modeling-and-management.md#適切なデータモデルを決定する)
- 各種[リレーション種別の機能](data-modeling-and-management.md#リレーション種別の機能)および、レコードアクセス、ユーザインターフェース、レポートについてそれぞれの[リレーション種別が与える影響](data-modeling-and-management.md#リレーション種別が与える影響)を説明する
- [項目のデータ型を変更する場合の考慮事項](data-modeling-and-management.md#項目のデータ型を変更する場合の考慮事項)を明確にする
- 与えられた複数の要件に従って、考慮事項を明確にし、[適切な項目データ型を選択する](data-modeling-and-management.md#適切な項目データ型を選択する)
- [スキーマビルダの機能と考慮事項](data-modeling-and-management.md#スキーマビルダの機能と考慮事項)を説明する
- [データをインポートおよびエクスポートする](data-modeling-and-management.md#データをインポートおよびエクスポートする)場合のオプションと考慮事項を説明する
- [外部オブジェクト](data-modeling-and-management.md#外部オブジェクト)の機能とユースケースを説明する


### 適切なデータモデルを決定する

[独自のデータモデルの設計](https://help.salesforce.com/articleView?id=schema_builder.htm&type=5)

- データを最適化し, ユーザ固有のニーズに適合させる。
- [スキーマビルダー](data-modeling-and-management.md#スキーマビルダの機能と考慮事項)を利用し, データモデルの視覚化と編集ができる。

### リレーション種別の機能

[オブジェクトリレーションの作成 単元 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/data_modeling/object_relationships?trail_id=force_com_admin_beginner)

#### 参照関係

- 2つのオブジェクトをリンクし, 他方のオブジェクトを関連項目から参照できるようにする。
- 一対一および一対多とすることができる。
  - 一対多の例 : 取引先と取引先責任者
  - 一対一の例 : DreamHouseアプリケーションにおける[Property(物件)]と[Home Seller(不動産会社)]

#### 主従関係

- 主オブジェクトは従オブジェクトの特定の動作を制御する。
  - 誰が従レコードを参照可能か, 関連する従レコードの一括削除, など
  - 例: DreamHouseアプリケーションにおける[Property(物件)]と [Offer(提案)]
- 主従関係を作成する場合, 従オブジェクト上にリレーション項目を必ず作成するようにする。
- 多対多リレーションが作成可能。
  - 1つのオブジェクトの各レコードを, 別のオブジェクトの複数レコードにリンクできる。
    - 例: [Bug(バグ)]というカスタムオブジェクトと, 標準オブジェクトの[ケース]
    - 1つのバグを複数のケースに, または 1つのケースを複数のバグに関連付け可能。
  - 多対多リレーションの作成には, 連結オブジェクトを使用して2つのオブジェクトを関連付ける。
    - [多対多リレーションの作成](https://help.salesforce.com/articleView?id=relationships_manytomany.htm&type=5)

#### 階層関係

- ユーザオブジェクトにのみ使用できる特殊な参照関係
  - ユーザを, そのユーザ自身を直接的にも間接的にも参照しない別のユーザと関連付けることができる。
  - 例: 各ユーザの直属マネージャを格納するカスタム階層項目を作成する

### リレーション種別が与える影響

[リレーションの考慮事項](https://help.salesforce.com/articleView?id=relationships_considerations.htm)

#### レコードアクセス

- 主従関係の場合, 従レコードは主レコードからセキュリティ設定と権限を継承する。
  - 従レコード独自での権限設定は不可
  - 組織のデフォルト共有設定については編集可能
    - 設定 > [共有設定]より, より, 従オブジェクトのデフォルトアクセス権を設定できる。
      - 非公開, 参照のみ, 参照・更新可能 に加え, [親レコードに連動]を指定可能

#### ユーザインターフェース

- 主従関係を作成すると, 主オブジェクトのカスタム関連リストに従オブジェクトのレコードが追加される。

#### レポート

- 参照関係により, 2つの関連オブジェクトから得られるデータを 1つのレポートに統合できる。
- 主従関係により, 主/従/参照 の3つのオブジェクトから得られるデータを 1つのレポートに統合できる。

### 項目のデータ型を変更する場合の考慮事項

[カスタム項目のデータ型の変更に関するメモ](https://help.salesforce.com/articleView?id=notes_on_changing_custom_field_types.htm&type=5)

- データの存在しないカスタム項目のみ変換するようにする。
- 以下の場合はデータ損失となる可能性がある。
  - 日付型 <-> 日付/時間型 同士の変更
  - 任意の型 -> 数値型, パーセント型, 通貨型, チェックボックス型 への変更
  - 選択リスト(複数選択)型 <-> 他の型 同士の変更
    - 選択リストを複数選択リストに変更しても, 現在定義されている選択リスト値は維持される。
    - 選択リスト定義にない値がレコードに含まれる場合, データ型を変更するとそれらの値はレコードから削除される。

### 適切な項目データ型を選択する

- 項目のデータ型により、その項目の情報の種類が決まる。
  - 例: 数値データ型の項目には、正または負の整数が入る
- カスタム項目のデータ型一覧についてチェックしておく。
  - [カスタム項目のデータ型](https://help.salesforce.com/articleView?id=custom_field_types.htm&type=5)
- 以下も参照
  - [データ品質の向上 単元 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/data_quality/data_quality_improve_quality)
    - 日付, 通貨(会社で使用する形式に合わせる)
    - 選択リスト(例: 国や都道府県を標準リストとして設定)

### スキーマビルダの機能と考慮事項

[スキーマビルダーの使用 単元 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/data_modeling/schema_builder?trail_id=force_com_admin_beginner)

- 項目の値, 必須項目, オブジェクトの関係などの詳細を表示できる。
- 以下のものが追加可能
  - カスタムオブジェクト
  - 参照関係
  - 主従関係
  - カスタム項目(地理位置情報を除く)

### データをインポートおよびエクスポートする

[データの管理 | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/lex_implementation_data_management)

#### データのインポート

[データの Salesforce へのインポート](https://help.salesforce.com/articleView?id=importing.htm&type=5)

- インポートウィザード
  - 5万レコードまで
  - インポート可能なオブジェクト種別
    - 取引先(法人/個人), 取引先責任者
    - リード, ソリューション
    - キャンペーンメンバー(キャンペーンは対象外)
    - カスタムオブジェクト
  - 主な対象外オブジェクト
    - 商談, キャンペーン, ケース, ユーザ
    - 商品, 契約, 輸入商品, ドキュメント
- データローダ
  - クライアントアプリケーション
  - 500万レコードまで可能
  - コマンドラインでの操作可能(Windowsのみ)
    - [データローダのコマンドラインインターフェース](https://help.salesforce.com/articleView?id=using_the_command_line_interface.htm&type=5)
  - SOAP APIを利用。ただし処理を迅速化する場合, Bulk APIを使用するように設定可能
    - [データローダの設定](https://help.salesforce.com/articleView?id=configuring_the_data_loader.htm&type=5)
- インポートする前に検討すべき事項
  - インポートファイルには、各レコードの所有者を含める
  - インポートファイルのデータ重複を排除する
- その他考慮事項
  - 数式項目は参照のみのため、インポートされたデータを受け入れない
  - 項目の入力規則に違反するレコードはインポートされない, など

#### データのエクスポート

[Salesforce からバックアップデータをエクスポートする](https://help.salesforce.com/articleView?id=admin_exportdata.htm&type=5)

- エクスポートウィザード
  - デフォルトではシステム管理者のみ権限あり
  - 設定 > [データのエクスポート]
    - [今すぐエクスポート]: 前回のエクスポートから十分な時間経過が必要
    - [エクスポートをスケジュール]
      - ウィークリーエクスポート
        - Enterprise,Performance,Unlimited Edition のみ
      - マンスリーエクスポート
  - Sandbox はサポート外
  - ファイルサイズに関する考慮事項
    - 組織のデータサイズが大きい場合、複数の .zip アーカイブが作成される
    - 各 .zip アーカイブの最大サイズは約 512 MB
- データローダ
  - クライアントアプリケーション(前述)
  - エクスポートプロセスの自動化やAPIを使用した別のシステムとの連携など

### 外部オブジェクト

[Salesforce Connect | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/lightning_connect)



#### ユースケース


## 参照

- [データモデリング | Salesforce Trailhead](https://trailhead.salesforce.com/ja/content/learn/modules/data_modeling?trail_id=force_com_admin_beginner)
