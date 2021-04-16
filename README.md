このページは
## Drupal 9 Web 開発ことはじめ / Drupal Meetup 豊田支部 著
## 「第4章 CentOS Stream 8を使ったDrupal 9サイト環境構築」

## Drupal 9 Web 開発をはじめるための薄い本 / Drupal Meetup 豊田支部 著
## 「第3章 CentOS 8を使ったDrupal 9サイト環境構築」
に関する補足ページです。

example.com.conf はTLS証明書の設定をnginxに行う場合の設定ファイル例です。

設定ファイル内では
/etc/letsencrypt/options-ssl-nginx.conf
/etc/letsencrypt/ssl-dhparams.pem
をインクルードしていますので、Let's EncryptでTLS証明書を取得する際には --nginx オプションをつけて取得するようにしてください。

設定ファイル内の example.com 部分をご自身が取得済みの独自ドメインに変更して利用してください。

(独自ドメイン umapon.jp での使用方法)
$ git clone https://github.com/takahiro-komatsu/centos8-drupal9
$ sed -e "s/example.com/umapon.jp/g" ./centos8-drupal9/example.com.conf > ./centos8-drupal9/umapon.jp.conf
$ sudo cp centos8-drupal9/umapon.jp.conf /etc/nginx/conf.d/umapon.jp.conf
$ sudo chown root:root /etc/nginx/conf.d/umapon.jp.conf
$ sudo restorecon -R /etc/nginx/conf.d

# (正誤表)
## Drupal 9 Web 開発ことはじめ / Drupal Meetup 豊田支部 著
## 「第4章 CentOS Stream 8を使ったDrupal 9サイト環境構築」

「TLS証明書の設定および更新」の節にある2つ目のコマンド群
(正) $ sudo cp centos8-drupal9/umapon.jp.conf /etc/nginx/conf.d/umapon.jp.conf
(誤) $ sudo cp centos8-drupal9/example.com.conf /etc/nginx/conf.d/umapon.jp.conf
