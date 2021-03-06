# 実践パッチ開発ゼミ
## 当日までの課題
当日のスムーズな進行のためにいくつか課題を出します。ご協力をお願いします。  
各課題できるところまででかまいません。進めててわからないことがあれば遠慮なく@himeshi_hobに質問してください。できる限りすぐにお答えします。  
### 開発環境構築(最優先)
[setup.md](setup.md) を参考にしてGitを導入し、makeでコンパイルできるようにしてください。  
実際環境設定はある人のマシンではうまくいっても別の人のマシンではダメみたいなことが平気で起こるので詰まってしまった人には当日会場でサポートはします。が、できるだけ頑張っていただけるとうれしいです。  
やっている途中でわからないことが出てきたら遠慮なく@himeshi_hobに質問してください。

### 開発案の練り上げ
今回の開発テーマは「市道化防止パッチを作ろう」です。そこで
* パッチの目的（なにを、どうしたいのか。）
* 変更する挙動の内容。どんな挙動をするようになるか。
* 実現するためにどんな処理をすればよいか


を簡単に考えてきてください。ほかの人に説明できるようにちょっとしたドキュメントを作ってあげるとなおよいでしょう。  
どんな処理をすればいいかはしばしばソースの中身を覗かないとさっぱりわからないことがあります。ソースの覗き方は当日レクチャーしますがご自分でコードの海を泳いでみるのもいいでしょう。  

### C・C++の基礎
事前アンケートで案内したとおり「C言語は一通りわかっている（特にポインタまわり）」ことだけは前提にしてお話をします。もしC言語に不安があれば「苦しんで覚えるC言語」 http://9cguide.appspot.com/ などを参考にして復習しておいてください。  
また、上記のページの題目「20.複数のソースファイル」は目を通しておいてください。  
講座ではC++の知識は前提にしませんが、simutransのコードはオブジェクト指向で書かれているので事前にオブジェクト指向を軽く理解しているととてもスムーズになります。
「一週間で身につくC++言語の基本」（ http://cpp-lang.sevendays-study.com/day0.html ）をday0からday7まで一通り軽く読んでおいてください。内容をカンペキに理解する必要はありません。
