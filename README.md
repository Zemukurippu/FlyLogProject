FlyLogProject — README
[FlyLogProjectとは]
FlyLogProject は、
簡単かつ軽量に更新ログを記述できる専用言語「FlyLog」を提供するプロジェクトです。

一般的な JSON 形式よりも圧倒的に軽量で、
ソフトウェアの更新履歴を低コストで記述できます。

[特徴]
軽量：JSON の半分以下の容量でログを記述可能

読みやすい：人間が直感的に理解できる構造

構造化されている：パースしやすく、機械処理にも向く

更新ログに特化：余計な情報を排除した最適化された記法

[FlyLog v1.0 の例（約 272 bytes）]
txt
/lang = FlyLog1.0
/log

/groupstart
#Groupname = (FlyLog)

#mainversion = (None)

-version = (v1.0 legacy)
-time{No data} = (No Data)
@Lgc

#mainversion = (1.x)

-version = (v1.0)
-time{+9} = (2026/09/27)
[JSON の場合（約 614 bytes）]
json
{
  "lang": "FlyLog1.0",
  "log": {
    "group": {
      "name": "FlyLog",
      "mainversion": [
        {
          "version": "None",
          "entries": [
            {
              "version": "v1.0 legacy",
              "time": "No Data",
              "tag": "Lgc"
            }
          ]
        },
        {
          "version": "1.x",
          "entries": [
            {
              "version": "v1.0",
              "time": "2026/09/27",
              "timezone": "+9"
            }
          ]
        }
      ]
    }
  }
}
[容量比較（UTF‑8 バイト数）]
形式	バイト数	備考
FlyLog	272 bytes	専用言語のため極めて軽量
JSON	614 bytes	FlyLog の約 2.26倍


[FlyLog が向いている用途]
ソフトウェアの更新履歴

バージョン管理ログ

軽量な構造化データが欲しい場面

JSON よりも短く書きたい CLI / Web ツール

GitHub Pages / 静的サイトでの履歴管理
