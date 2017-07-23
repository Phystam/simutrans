# デバッガの走らせ方
あまりちゃんと検証してません。上手く行かなかった時は@himeshi_hobに連絡をお願いします。
## デバッガを使う理由
Simutransのコードの特性上、想定外のエラーが起きた時に「プログラムが動作を停止しました」と出るだけで「なぜ止まったのか？」という情報を得ることができません。  
そこでgdbというデバッガ上でsimutransを走らせることで、エラーが起きたときの原因特定がとてもやりやすくなります。皆様ご協力をお願いします。
## デバッガの導入
1. msys2をインストール。（ http://www.msys2.org/ ）原則としてx86_64とついてるやつをインストールしましょう。  
2. msys2を起動し（64bit版を起動する） `pacman -Syuu` を実行する。  
「msysを閉じろ」というメッセージが出てくるので一度閉じるボタンで閉じてmsys2をもう一度起動する。その後もう一度`pacman -Syuu` を実行する。  
アップデート対象がなくなるまで`pacman -Syuu`を繰り返し実行する。  
（コレでmsys2のいろいろがアプデされる。）  
3. msys2上で以下のコマンドを実行する。  
`pacman -S gcc gdb`
## デバッガ上でのSimutransの起動
1. msys2の**32bit版**を起動し、cdコマンドでソースコードのフォルダに移動する。  
例：SimutransのフォルダがC:\users\himeshi\desktop\simutrans である場合  
`cd /c/users/himeshi/desktop/simutrans`
2. `gdb sim.exe`（「sim.exe」は実行ファイルの名前）を実行。いろいろgdbが準備をしてくれる  
3. 準備が終わったら`r`と入力すれば起動する。  
4. 終了する時は通常どおりSimutransを終了した後、gdbで`q`と入力する。
## プログラムが動作を停止した時は
たぶんこんなのを出してくれます。（実際の表示はシチュエーションによって大きく異なります。気にしないでください。）  
    Program terminated with signal 11, Segmentation fault.  
    ...  
    0  0x0804846a in treeadd (pp=0xcfb14c, val=50) at treesort1.c:39  
    39        else if ((*pp)->value > val)  
エラーっぽいのが出たら
1. 最初にデータエラーメッセージ  
2. バックトレース  
の2つを報告してください。どちらかというと2のバックトレースの方が重要です。
###バックトレースの見方
シムトラがエラーを吐いて止まったら、msys2上で`bt`と入力してください。  
いろいろゴチャゴチャ出てくるのでそれをそのまま報告してください。  
↓たぶんこんな感じのやつが出てくる  
    (gdb) bt  
    0  0x0804846a in treeadd (pp=0xcfb14c, val=50) at treesort1.c:39  
    1  0x080484aa in treeadd (pp=0xbf526008, val=50) at treesort1.c:44  
    2  0x080484aa in treeadd (pp=0xcfb23c, val=50) at treesort1.c:44  
    3  0x08048485 in treeadd (pp=0xbfead7ac, val=50) at treesort1.c:40  
    4  0x080483f6 in main (argc=1, argv=0xbfead844) at treesort1.c:20  
