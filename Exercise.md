# Exercise1
### モデル1-コンビニのおにぎり売り上げ予測-
説明変数の情報からコンビニ店舗のおにぎりの日ごとの売り上げを学習し、店舗の今後のおにぎりの売り上げを予測する。

##### 説明変数
|  変数名  |  単位  |
| ---- | ---- |
|  住所  |  都道府県・市町村・区  |
|  来店人数  |  人  |
|  周辺1kmのライバル店（スーパー・コンビニ）の件数  |  件  |
|  周辺1kmの同系列店の件数  |  件  |
|  周辺1kmで開催されるイベント件数  |  件  |
|  天気  |  天気名  |
|  気温  |  ℃  |
|  駅からの距離  |  km  |
|  値引きキャンペーンの有無  |  あり or なし  |
|  深夜営業の有無  |  あり or なし  |
|  店舗の形式  |  駅構内 or オフィスビル内 or 商業施設内 or 独立 or その他  |
|  おにぎりコーナーの規模  |  ㎡  |

##### 目的変数
|  変数名  |  単位  |
| ---- | ---- |
|  売り上げ個数  |  個  |

##### モデル
一般化推定方程式。

### モデル2-富士山登山ツアーの勧誘メールによる契約予測-
旅行会社が会員に1泊2日の富士山登山ツアー勧誘メールを送付したとき、契約してもらえるか。
説明変数は会員登録を行った際に登録した個人情報や顧客旅行履歴等の蓄積情報、会員に定期的に行っている興味関心のアンケート結果などから取得する。

##### 説明変数
|  変数名  |  単位  |
| --- | --- |
|  住所  |  都道府県・市町村・区  |
|  アウトドアに興味がある  |  ある or ない  |
|  登山経験  |  ある or ない  |
|  スポーツ経験  | ある　or　ない  |
|  運動で大きなけがをしたことがある  |  ある or ない  |
|  結婚  |  している or していない  |
|  家族人数  |  人  |
|  1旅行当たりの予算  |  円  |
|  本旅行会社のツアーを活用した旅行回数  |  回  |
|  本旅行会社の保有ポイント  |  ポイント  |
|  決済方法  |  現金 or クレジットカード or 口座振り込み  |
|  平均旅行期間  |  泊日  |
|  参加したツアーの種類  |  ツアーの種類（クルーズツアー、ハイキングツアーなど）  |

##### 目的変数
|  変数名  |  単位  |
| ---- | ---- |
|  本ツアーを契約するか  |  する or  しない |

##### モデル
決定木モデル。

### モデル3-クルーズ客船ツアーの金額設定予測-
クルーズ客船のツアー金額予測。
過去のクルーズ客船ツアーのデータから、これから企画するツアーの金額を予測し、金額設定に要する時間を効率化する。

##### 説明変数
|  変数名  |  単位  |
| --- | --- |
|  出発地  |  出発地名  |
|  到着地  |  到着地名  |
|  船内滞在期間  |  日  |
|  客室数  |  部屋数  |
|  収容可能乗客数  |  人  |
|  乗員数  |  人  |
|  部屋の等級  |  等級名  |
|  船の全長  |  m  |
|  船内の娯楽施設数  |  個  |
|  船の築年数  |  年  |
|  船内の飲食施設の数  |  件  |
|  目的地までの寄港回数  |  回  |

##### 目的変数
|  変数名  |  単位  |
| ---- | ---- |
|  ツアー金額  |  円  |

##### モデル
重回帰分析モデル。

# Exercise2
### モデル1-コンビニのおにぎり売り上げ予測-
##### 本タスクの目的、モチベーション。
店舗ごとにおにぎりの売り上げ数を予測することによって仕入れ数を最適化、廃棄などを削減することを目的とする。  
また、新しくオープンさせる店舗においても、本予測データからオープン時の仕入れ数の最適化などを見込める。

##### 機械学習である必要性。
対象のコンビニは全国に店舗を展開しており、収集できる情報量も多いため、その膨大な情報、店舗があるため人が予測するのは現実的でない。  
また、膨大な情報があるということで精度の高い予測モデルの作成が見込める。

##### データの収集方法とその方法によるデータの偏りの考察。
来客数や売り上げ情報などは各店舗の情報から取得する。  
天気は気象庁が発表している天気情報から収集する。  
周辺ライバル店や駅からの距離はGooglemap等の地図情報から情報を収集する。  
イベントについては周辺施設や地方自治体などのHPから収集する。

データの偏りについては本コンビニは全国規模で展開しており、全国で満遍なくデータを収集することができることからデータの偏りは少ないと考えられる。  
しかし、店舗が売り上げデータを記録し始めた時期が異なっている場合や、記録している2020年までのデータで、2021年以降のデータがない場合、時間軸に
おいてデータの偏りが発生すると考えられる。  
これによって今後のデータを予測する際に、その時の社会情勢などを多面的に考えてモデルを検証し、予測する必要がある。


### モデル2-富士山登山ツアーの勧誘メールによる契約予測-
##### 本タスクの目的、モチベーション。
本タスクではメールの送信先を予測によって最適化することで、メールを受け取った会員に高確率でメールの内容をきちんと読んでもらい、契約につなげることを目的としている。  

##### 機械学習である必要性。
顧客の興味関心は会員の数だけ違いがあり、それを一人一人予測していくのは難しく、時間がかかる。  
そのため蓄積したデータから学習したモデルによって、様々な興味関心を持つ会員に対応できる機械学習が適している。

##### データの収集方法とその方法によるデータの偏りの考察。
会員の登録情報や旅行履歴は、会員登録を行った際に登録した個人情報や顧客旅行履歴等の蓄積情報から収集する。  
会員の経験や興味は会員に定期的に行っている興味関心のアンケート結果などから取得する。  

データの偏りについては、会社が新しく参入した種類のツアーがあった場合、サンプルの数が少ないためデータに偏りが発生する可能性がある。  
この偏りによって、新規参入ツアーに興味がある会員の契約の予測精度が低くなる可能性がある。


### モデル3-クルーズ客船ツアーの金額設定予測-
##### 本タスクの目的、モチベーション。
過去のクルーズ客船ツアーのデータから、これから企画するツアーの金額を予測し、金額設定に要する時間を効率化する。  
金額設定に要する時間を効率化することで企画者はツアー内容の企画に集中できる。

##### 機械学習である必要性。
料金設定のマニュアルがあれば料金の予測・設定は機械学習を行わずとも人によって可能である。  
しかし、想定した機械学習導入の目的が業務の効率化のため、機械学習で予測・設定することによって人の労働を減らして、効率化できる。  
また、マニュアルの数値などを超えた客船ツアーが企画された際、マニュアルに基づく場合、新しくその企画に沿ったマニュアルを作成しないといけないが、機械学習なら予測データから新しい金額をすぐに予測することができる。

##### データの収集方法とその方法によるデータの偏りの考察。
客船の全長や部屋数などの情報は船舶所有会社から情報を取得する。  

この方法では船舶所有会社から信頼性の高い情報を取得できる。  
また、船舶所有会社から情報を取得することですべてのツアーの客船の情報を取得できるため、データの偏りは発生しないと考えられる。