# Simutrans 開発セットアップ
まだ書き途中です。全然検証してません。

## gitの整備
gitを使って開発を進めます。

## コンパイル方法
1. msys2をインストール。（ http://www.msys2.org/ ）原則としてx86_64とついてるやつをインストールしましょう。
2. msys2を起動し（64bit版を起動する） `pacman -Syuu` を実行する。  
「msysを閉じろ」というメッセージが出てくるので一度閉じるボタンで閉じてmsys2をもう一度起動する。その後もう一度`pacman -Syuu` を実行する。    
3. 以下のコマンドを順に実行する。  
`pacman -S make`  
`pacman -S gcc`  
`pacman -S mingw-w64-i686-libpng`  
`pacman -S mingw-w64-i686-pkg-config`  
今回はいらないがSDL版を作りたい時は以下も追加で実行する。   
`pacman -S SDL`   
`pacman -S SDL2`   
4. msys2の32bit版を起動し、cdコマンドでソースコードのフォルダに移動する。  
例：ソースコードのフォルダがC¥:users/himeshi/desktop/simutrans である場合
`cd C:users/himeshi/desktop/simutrans`  
5. config.defaultを作る。以下の記述をエディタにコピペし、ソースコードフォルダ（のトップディレクトリ）に「config.default」という名前で保存する。  

    BACKEND = gdi #どのライブラリ？  
    COLOUR_DEPTH =16 #このまま使う  
    OSTYPE = mingw #winはmingwです  
    DEBUG = 3 #ログをたくさん出す  
    WITH_REVISION = 8128 #バージョン。とりあえずテキトーでよい。  
    WIN32_CONSOLE = 1  
    #winでコマンドプロンプトを出す  
    MULTI_THREAD = 1 #マルチスレッドON  
    STATIC = 1 #Windowsでのみ書く  
    #以下はよくわからないおまじない  
    MAKEOBJ_PROGDIR = $(shell pwd)  
    NETTOOL_PROGDIR = $(shell pwd)  
    PROGDIR  = $(shell pwd)  
    
6. コマンド`make -j4` を実行（-j4で4並列でコンパイルしてくれる。）
