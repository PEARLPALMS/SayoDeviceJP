# スクリプトを使いこなそう
<br>

単純にキーボードのキーを割り当てたり、文字列をペーストするだけでは、SayoDevice のごく一部の機能しか使いこなせていません。<br>
スクリプトを使うと細かい制御が可能になります。<br>
スクリプトと言うとプログラムを書くと思われますが、実際には制御機能がありませんので、単に手順を羅列するだけです。<br>
<br>
もちろんプログラム経験も不要です。ただしミリ秒単位で制御しますので、根気よくトライし続けることが必要になります。<br>
要は根気さえあれば、思ったように動くスクリプトが完成します。慣れてくればコツも分かってきます。<br>
<br>
※ ドキュメントなどを参考に独自に解釈した内容です。誤りやもっと効率的な記述が可能な場合があります。<br>
<br>

## ちょっと概要的なことを。。。
<br>

スクリプトを日本語で言い換えると、以下のような感じになります。<br>
```
A を押す
0.3秒 待機
A を離す
0.5 秒 待機

B を押す
0.3秒 待機
B を離す
0.5秒 待機

B を押す
0.3秒 待機
B を離す
```
実行結果は ABB と表示されるだけです。0.3秒 や 0.5秒 はゲームや PC の性能により調整します。<br>
単純に「A を押す」「A を離す」だけでは、スクリプトが早すぎて A が入力されなかったり、入力されたままになったりします。<br>
<br>
では、どの程度の数字が適当か？を、ここで記述することは出来ません。入力したいプログラムや PC の性能によって
異なるため、一概に 0.3秒 ですとは言い切れませんので、何度もトライが必要になります。<br>
<br>
根気よく頑張りましょう。<br>
<br>

## スクリプト容量には制限があります。
<br>

1本のスクリプトには 4,096行(ステップ)までしか登録できません。<br>
またスクリプトも 64本 までしか登録できません。<br>
それに 64本 と言っても、全ての合計が 4,096行 までしか登録できませんので、100行であれば 40本 しか登録できません。<br>
先述した ABB と表示するだけのスクリプトでも、11行もありますので、単純化するように心がけていないと、あっという間に足りなくなります。<br>
とはいえ、ゲームの連射や、プログラムのメニューを開いて設定を変更する程度であれば、ボタン一杯まで搭載可能です。<br>
<br>

# スクリプトを書いてみよう
<br>

「スクリプト」タブを押して、「No.01」と書かれたプルダウンを選択します。<br>
<img src="script_01.png" width="50%">

「No.0001」をクリックするとポップアップが開いて詳細を入力します。
```
「モード」    Modifier-value-press
「修飾キー」  左CTRL
```
<img src="script_02.png" width="50%">

ざっと入力していくと以下のようになります。
```
No.0001 Modifier-value-press [左CTRL]
No.0002 General-value-pressd [Ii]
No.0003 Duration-x1 [35]
No.0004 General-value-release [Ii]
No.0005 Duration-x256 [4]
No.0006 General-value-pressd [Ii]
No.0007 Duration-x1 [35]
No.0008 General-value-release [Ii]
No.0009 Duration-x1 [35]
No.0010 Modifier-value-release [左CTRL]
No.0011 Exit the script
No.0012 end
```
やっていることは CTRL+i を押して、1秒後に再度 CTRL+i を押すというだけです。<br>
とあるプログラムで CTRL+i を押すとインフォメーションが表示されるのですが、1秒後にインフォメーションを消すために再度 CTRL+i を押すスクリプトです。<br>
<br>
詳しく横に日本語を記述します。<br>
```
No.0001 Modifier-value-press [左CTRL]   | CTRL押下
No.0002 General-value-pressd [Ii]       | i押下
No.0003 Duration-x1 [35]                | 35ミリ秒待機
No.0004 General-value-release [Ii]      | i離す
No.0005 Duration-x256 [4]               | 1秒待機
No.0006 General-value-pressd [Ii]       | i押下
No.0007 Duration-x1 [35]                | 35ミリ秒待機
No.0008 General-value-release [Ii]      | i離す
No.0009 Duration-x1 [35]                | 35ミリ秒待機
No.0010 Modifier-value-release [左CTRL] | CTRL離す
No.0011 Exit the script                 | 終了
No.0012 end                             | 
```
ここで No.0005 Duration-x256 [4] を Duration-x1 [1000] でも同じ動作をするように思うのですが、Duration-x1 は 255 までしか指定できません。<br>
Duration-x256 は、名前の通り 256ミリ秒待機 ですので、約1秒である x4 を指定しています。<br>


## スクリプト容量には制限があります。
<br>

<img src="script_03.png" width="50%">
<img src="script_04.png" width="50%">
<img src="script_05.png" width="50%">
<img src="script_06.png" width="50%">
