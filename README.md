# yahoo-japan-article-crawer

## 概要
[Yahoo! Japan (Sportsnavi)](https://sports.yahoo.co.jp/list/news/ws?genre=ws)の海外サッカーニュース一覧を取得します。

記事のタイトルとURLのみを取得します。(本文は取得しません。)

## 使い方
- Python 3, [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/), [Selenium](https://selenium-python.readthedocs.io/index.html), [ChromeDriver](https://chromedriver.chromium.org/home)を使用しています。
- **last_article**に最後に読んだ記事のURLをセットしておくと、それ以降の記事URLは取得しません。
- **exclude_list**に除外するキーワードリストをセットすることで、タイトルに該当キーワードを含む記事を除外します。
