# 常にフレームワークを使うこと #

> すべての汎用 PHP フレームワークはクソ!
>
> -- [ラスマス・ラードフ](https://www.youtube.com/watch?v=DuB6UjEsY_Y)

PHP コミュニティにおいて、実に良くないトレンドが、Web アプリケーションを開発するためのデファクトスタンダードになってしまいました。流行っている汎用フレームワークを使う方法です。

このトレンドは、それがとにかく開発プロセスの結果を向上させるからでも、技術と構造的視点から行うことが正しいからでもありません。このトレンドが大衆化したのは、いくらかのフレームワーク開発者が、「車輪の再発明をするな!」「自分でするな、他者のほうがあなたより熟練している!」といったお決まりの文句に立脚して、プログラミングを論じる輩の排除に成功したためです。

今日のプログラマの多くは、健全なプログラミングの基本原則を完全に無視し、彼らは、よりクレバーに、よりクールに、仲間とみなしたどんな人にもより受け入れやすく見えるよう、新たな複雑さの層を幻想的にするがために多くの時間を費やしています。

こういった人々は、他の人が自分たちの「やり方」に従うこと、PHP コミュニティのリーダーか何かになること、そして彼らの最新版の「イケてる」オープンソースツールを他の人に使ってもらうことに夢中になり、彼らが提供している助言が健全かつ堅実であるか確かめるのを忘れているようです。

ソフトウェア業界では、汎用フレームワークを、建造済みの家で比喩することができます。建造済みの家をまとめるだけでは大工になれないように、汎用フレームワークを使ってソフトウェアを構築しても、コーダーやプログラマーにはなれません。

このウェブサイトでは、フレームワークとライブラリを次のように区別します:

* ライブラリは、C 標準ライブラリや Go 標準ライブラリのような、再利用可能なコードの集合と見なされます。それは、上限や制約を何ら強制することなく、あなた自身のプロジェクトに簡単に統合できるコードで構成されています。それは、単一の特定機能を備えた、小さなコードで構成されます。
* フレームワークは単なる再利用可能なコードの集合ではありません、つまり、単純にフレームワークからコードを取り出して自分のプロジェクトに統合する、といったことはできません。フレームワークとは、ソフトウェアを構築するのに役立つシステムですが、同時に、フレームワーク自体の上限や制約の範囲内で作業するように強制します。フレームワーク自体には多くの相互依存を持つ機能があります。いっぽうは、他方がなければ機能しません。

Python と Ruby の世界では、当初から Python も Ruby もウェブサイトを構築するために作られていなかったため、ウェブサイトを構築するのは面倒でした。その結果、[Django](https://en.wikipedia.org/wiki/Django_%28web_framework%29) や [Ruby on Rails](https://en.wikipedia.org/wiki/Ruby_on_Rails) などの汎用フレームワークが、これらの言語でウェブサイトを構築するために急速に普及しました。

いっぽう PHP は当初から、ラスマス・ラードフによって C 言語で書かれた一連のツールとして、動的 HTML を簡単かつ迅速に開発してもらえるようにと作成されました。今なおそうなのですが、そのような PHP は、**それ自体がフレームワーク** でした。

PHP はそれからずいぶん進化していて、今日、PHP は HTML やウェブサイトを構築する以外にも使用できるとはいえ、PHP 自体を一種のフレームワークとみなすことは間違いではありません。PHP は生まれつき、もっぱら手続き型の C 言語で書かれていた Web アプリケーション開発のための抽象化層です。

プロジェクト内でライブラリを使用するのは当然です。PHP 自体には、独自のコードを拡張するために使用できる一連のライブラリがバンドルされています。例えば、PDO は PHP でデータベースにアクセスするための一貫したインターフェースを提供する軽量ライブラリです。

それに対して PHP の上でフレームワークを使用することは、まったく別の問題です。

PHP でフレームワークを使用すると、抽象レイヤーを別の抽象レイヤーの上に追加してしまいます。一方は最初から使えるよう用意されているのに。フレームワークから提供される抽象概念の追加レイヤーが与えてくれるのは、コードをあらかじめ決められた一定のパターンに編成することか、あるいは、何百何千ものクラスとメソッドを依存関係の悪夢に絡み合わせて過剰な複雑さを追加することか、どちらにしても、コードに複雑なレイヤーを追加することになり、不要です!

すべての経験はインターフェースから始まります。インターフェースの経験は、基盤技術と抽象レイヤの量の結果です。使用した抽象が多くなれば、インターフェースの効率が低下し、アプリケーションはエラーが発生しやすくなります。抽象度が高いほど、詳細と効率が失われます。

はっきりと理解すること: **どんなプロジェクトでも、コードの理想は、可能な限り少ない行数で、可能な限り明確かつ可読であること!**

> 誰も必要としていないのは、万能なフレームワークです。みんながみんな一般的な問題を抱えているわけではなく、みな非常に特殊な問題を抱え解決しようと試みています。
>
> -- [ラスマス・ラードフ](https://www.youtube.com/watch?v=anr7DQnMMs0)

ある企業は、PHP フレームワークに関する誇大宣伝を耳にして、そういった流行っている汎用フレームワークのひとつを使って次のプロジェクトを開始しましたが、災害に終わっただけでした。汎用フレームワークは、彼らの非常に特別なニーズを解決するにあたって本当に悪いものだと発見しただけでなく、それは稼働中も究極的に遅かったのです。スケール不可能で、その結果、彼らは本当に必要のないものすべてを抜き出すために、絶望的な試みのなか、フレームワークを切断分割し始めました。

常に実用的なアプローチを使用すること:

> 行動や方針は、理論や教義ではなく、直接的な実践的結果を考慮して、決定される。
>
> -- コリンズ英語辞典, Complete and Unabridged, 第 12 版 2014

**間違った方法**: PHP 上で常にフレームワークを使うこと。 ![だめ](/img/thumbs-down.png)
