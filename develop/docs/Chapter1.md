# プログラミングを始める前に

実際にProcessingを使ってプログラミングを始める前に、プログラミングとは何か、どう書くかなどを解説していきます。

## プログラミングとは

プログラミングとはプログラムを書くことで、プログラムはコンピュータに与える命令の集合です。コンピュータにどんな命令を与えるかはプログラミング言語によって様々で、プログラミング言語にも得意な処理、不得意な処理があります。Processingはコンピュータグラフィックスを描くことを得意とするプログラミング言語です。

## 関数
プログラムはコンピュータに与える命令の集合だと言いました。その命令の集合の基本的な要素に関数というものがあります。関数を使うことで画面上に図形を描いたり、色を付けたり、計算したりすることができます。関数を使うときは関数名を書いて、そのあとに丸カッコが続きます。丸カッコの中にはその関数がどんな働きをするかを決めるパラメータと呼ばれるものを書き、パラメータが２つ以上あるときはコンマで区切ります。パメータがない関数もあります。*size*関数はProcessingで図形を描く舞台であるウィンドウサイズを指定する関数で、ほとんど全てのProcessingプログラムに登場します。Processingエディターに

`size(960, 540);`

と書いて実行してみてください。最後のセミコロンも忘れないでください。幅960ピクセル、高さ540ピクセルのウィンドウが出てくるはずです。*size*関数の1つ目のパラメータにはウィンドウの幅を、2つ目のパラメータには高さをピクセルを単位とした数値で与えます。最後のセミコロンは命令の区切り文字です。これがないとコンピュータはどこからどこまでが一つの命令なのか理解できません。*size(960, 540)*が一つの命令だとコンピュータに理解させるために最後にセミコロンを付けます。

もう一つ、ウィンドウの背景色を指定する*background*関数を紹介します。さっきの続きで以下のように書いて実行してみてください。

`
size(960, 540);
background(255);
`

さっきは灰色だったウィンドウの背景が真っ白になっているはずです。*background*関数には0～255までの数値をパラメータとして与えることができます。この0～255の数値が色を表していて、*background*関数に0を与えると黒色の、255を与えると白色の、128を与えると中間的な灰色のウィンドウが出来上ります。なんで0～255のような中途半端な数値を使うのか疑問に思うかもしれません。0～255は全部で256個の数値です。256というのは2の8乗です。コンピュータは最終的に全ての情報を0と1の文字列(2進数)で扱います。なので2の何乗という数値はコンピュータにとって何かと都合がいいのです。色についてはChapter3で詳しく解説します。

## 大文字と小文字

プログラムは大文字と小文字を厳密に区別します。例えば以下のように書くとメッセージエリアに「Size関数なんてないよ」という意味のエラーが出ます。

`
Size(960, 540);
BackGround(255);
`

*size*と*background*は全て小文字で記述しなければいけません。プログラム内で大文字を使ってはいけないというわけではありません。*size*と*background*は全て小文字で書くように定義されているというだけです。また、プログラム内の文字は全て(後述のコメントを除いて)半角文字で記述しなければいけません。

間違ったプログラムを書くとメッセージエリアにエラーが表示されます。このエラー表示を消すには[ファイル]-[設定]の*"エラーのために継続的にチェックする"*と*"ワーニングを表示する"*のチェックを外します。プログラミングに慣れないうちはチェックを入れておくといいでしょう。チェックを外しても、プログラム実行時にはエラーが表示されます。

## スペースの扱いと見やすいプログラム

スペースはプログラム内でどんな使い方をしても許されます。
例えば以下のような書き方でもプログラムはちゃんと動きます。

[Chapter1/sketch01.pde](github:Chapter1/sketch01/sketch01.pde)

```processing
size      (
    960      ,
540     )      ;
background     (      255
   )    ;
```

ただし*size*や*background*の途中にスペースを入れると関数として認識されなくなります。

上のプログラムでのスペースの使い方は100%冗談です。スペースはプログラムを見やすくするために適度に使うものです。例えば*size*関数に与える２つのパラメータの間のスペースなどが適切な使い方の例です。スペースももちろん半角でないといけません。全角スペースは見つけにくいので注意してください。

## コメント

コメントはプログラムに加えるちょっとした解説のようなものです。次のように使います。

[Chapter1/sketch02.pde](github:Chapter1/sketch02/sketch02.pde)

```processing
// この行はコメントです

/*
複数行のコメントは
このようにして書くことができます
コメントはプログラムから無視されます
*/

// 幅960px高さ540pxのウィンドウを作成
size(960, 540);
// 背景色を黒色に
background(0);
```

Processingのエディタに日本語を書けるようにするには、[ファイル] → [設定] → *"エディタとコンソールのフォント"*で日本語を扱えるフォントを選んでください。*"複雑なテキスト入力を有効にする"*にもチェックを入れてください(PDEの再起動が必要です)。[ファイル] → [設定] → *"エディタウィンドウでスムーズテキストを使う"*にチェックを入れておくとエディタ画面で文字が滑らかに表示されるのでこれもチェックを入れておくといいでしょう。

//から始まる行はコメントとみなされます。また/**/で囲んだ中の文字もコメントとみなされ、複数行のコメントを書くときに便利です。コメントはプログラムから無視されるので実行結果に影響はありません。コメントには例外的に全角文字が使えます。

長いプログラムを書くようになってくると、後でそのプログラムを見直したときに、自分で書いたプログラムであったとしても「この処理なんで書いたんだったっけ？」と思うことがあります。プログラムに適切なコメントを書くことでそのような事態を防げます。また、いずれ自分の作ったプログラムをネット上に公開することもあるでしょう。ほかの人が自分のプログラムを読んだときに理解しやすいようにするためにもコメントは重要です。プログラムの最初にプログラムの作成日や作成者の情報を付け加える、などの使い方もあります。

## コンソール画面

Processingエディターの下の黒い画面はコンソール画面と呼ばれています。プログラムの実行中に起きたエラーなどがここに表示されるのですが、*print*関数と*println*関数を使えばここに文字を書き込むこともできます。

[Chapter1/sketch03.pde](github:Chapter1/sketch03/sketch03.pde)

```processing
println("text 1");
print("text 2");
print("text 3");
```

*println*関数の*ln*はline(行)を意味していて、文字の出力後に改行をします。*print*関数は改行をしません。パラメータには文字を渡すことができて、文字は*ダブルクオーテーション("")*で囲みます。他のプログラミング言語では、コンソール画面に文字を出力することでプログラムの途中経過や結果を確認したりします。Processingの場合は他のプログラミング言語ほどコンソール画面を使う機会はありません。Processingではコンソール画面の代わりに、ウィンドウに描かれる図形の形や色によって結果を確認するからです。でも全く使わないわけではなくて、図形では確認しにくいようなことはコンソール画面に文字を出力して確認したりします。コンソール画面の使い方は必要に応じてこの先のChapterで解説していきます。

お疲れさまでした。Chapter1はこれで終了です。Chapter2から本格的にProcessingプログラムを解説していきます。