# yahoo-japan-article-crawler

## 概要
[Yahoo! Japan (Sportsnavi)](https://sports.yahoo.co.jp/list/news/ws?genre=ws)の海外サッカーニュース一覧を取得します。

記事のタイトルとURLのみを取得します。(本文は取得しません。)

## 使い方
- Python 3, [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/), [Selenium](https://selenium-python.readthedocs.io/index.html), [ChromeDriver](https://chromedriver.chromium.org/home)を使用しています。
- タイトル内の人名判別(後述)を行う場合、[GiNZA](https://megagonlabs.github.io/ginza/)も使用します。
- [Google Colab](https://research.google.com/colaboratory/)で動作します。(上記ライブラリをインストールすれば、ローカルでも動作可能です。)
- **last_article**に最後に読んだ記事のURLをセットしておくと、それ以降の記事URLは取得しません。
- **exclude_list**に除外するキーワードリストをセットすることで、タイトルに該当キーワードを含む記事を除外します。

## タイトル内の人名判別
**flag_nlp_name**でタイトル内の人名判別を行うかを指定します。タイトル内に漢字の人名が含まれている場合、記事を除外します。以下の3種類から選択します。
- **ginza_electra** : ja_ginza_electraを用いてタイトル解析を行います。ライブラリのインストール及び解析に時間がかかりますが、精度が高いです。
- **ginza** : ja_ginzaを用いてタイトル解析を行います。ja_ginza_electraに比べて速いですが、精度は低いです。
- **none** : タイトル解析は行いません。

### 背景
海外のサッカーニュースのみを読みたいのですが、国内のニュースが含まれている事があるので除外したいと思い実装しました。

### 注意事項
単純にタイトルをGiNZAで形態素解析し人名に漢字が含まれていたら除外しているだけなので、海外の記事でも漢字の人名が含まれていると除外されます。
