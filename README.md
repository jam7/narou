Narou.rb ― 「小説家になろう」「小説を読もう！」ダウンローダ＆縦書用整形スクリプト
============================================================

概要 - Summary
--------------
このアプリは[小説家になろう](http://syosetu.com/)、[小説を読もう！](http://yomou.syosetu.com/)で公開されている小説の管理、
及び電子書籍データへの変換を支援します。縦書き用に特化されており、
横書き用に特化されたWEB小説を違和感なく縦書きで読むことが出来るようになります。
また、若干の校正機能もありますので、小説としての一般的な整形ルールに矯正します。（例：感嘆符のあとにはスペースが必ずくる）

[ノクターンノベルズ](http://noc.syosetu.com/)及び[ムーンライトノベルズ](http://mnlt.syosetu.com/)にも対応しています。

全てコンソールで操作するCUIアプリケーションです。

主な機能は小説家になろうの小説のダウンロード、更新管理、テキスト整形、AozoraEpub3・kindlegen連携によるEPUB/MOBI出力です。

詳細な説明やインストール方法は **[Narou.rb 説明書](https://github.com/whiteleaf7/narou/wiki)** を御覧ください。

![ScreenCapture](https://raw.github.com/wiki/whiteleaf7/narou/images/narou_cap.gif)

更新履歴 - ChangeLog
--------------------

2013/10/30 : **1.3.3**
* 追加機能もしくは仕様変更
	- 送信対応端末に SonyReader(PRS-T2) を追加
		+ `narou setting device=reader` で切り替えることが出来ます

2013/10/29 : **1.3.2**
* 追加機能もしくは仕様変更
	- `default_args.*` の設定が使われるのは、各コマンドの引数が省略された時だけに変更
	- 各端末のボリュームラベルを大文字小文字区別しないで認識するように変更（Windowsのみ）
	- ダイジェスト化の自動検知機能を搭載。更新するかしないか、凍結してしまうかを選択可能に

2013/09/13 : **1.3.1**
* Bug Fix
	- 章情報の編集に対応できていなかったので修正
		+ 本アップデート以前にダウンロードした小説には反映されません。 `narou d -f` コマンドで強制上書きして下さい
	- 1.3.0.1 の修正で※が正しく区切り記号として認識されなくなっていたのを修正
	- タイトルが数字だけの場合に余分に空白が入ってしまうのを修正
* 追加機能もしくは仕様変更
	- 漢数字化しない場合、一桁のアラビア数字は全角化するように変更
	- タイトルのアラビア半角数字で特殊な処理を追加
		+ 行頭にある3桁の半角アラビア数字は全角化せず縦中横にする

2013/09/03 : **1.3.0.1**
* Bug Fix
	- ※記号の外字注記化コードによって正常に変換できなくなった問題を修正

2013/09/02 : **1.3.0**
* Bug Fix
	- `<PBR>` を使った場合にクラッシュする問題を修正
	- `1,000` のようにカンマで区切られた半角数字の変換が変なふうに縦中横になっていたのを横に倒すように修正
	- ※記号の直後に縦中横などの青空注記が来る場合に外字注記と誤認識されてしまう問題を修正
	- `enable_kanji_num_with_units` が `enable_convert_num_to_kanji` の設定を無視して有効になっていたのを修正
	- `enable_convert_num_to_kanji` がサブタイトルでも有効になっていたのを修正
		+ サブタイトルでは漢字変換を無効にする方針（原文尊重）
	- 漢数字の再変換がおかしかったのを修正
* 追加機能もしくは仕様変更
	- 漢字の二じゃなくて間違えてカタカナのニを使ってるのを校正する
	- `list` コマンドで新着を取得してから6時間以内の小説だけ新着色になるように修正
	- `⇒` が Kindle Paperwhite のフォントで縦書き時に回転しないので、 `→` に置換するようにした
		+ 他の端末では確認できていないので、とりあえず narou s device=kindle に設定してある場合のみ置換する
	- かぎ括弧内のとじ開きが正しくされているかどうか調査する設定を、デフォルトでオフに変更
		+ すでに setting.ini が書きだされている小説は対象外
	- 携帯用改行タグ `<KBR>` でも改行するように変更

----

「小説家になろう」は株式会社ヒナプロジェクトの登録商標です
