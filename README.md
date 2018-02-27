# mackerel-plugin-apache2

## 概要
mackerelで複数のApacheの死活監視を行うためのプラグイン

## ビルド方法
```
$ go version
go version go1.9.2 darwin/amd64

$ GOOS=linux GOARCH=amd64 go build
```
作成するバイナリのサイズを小さくしたい場合は下記のようにビルドする
```
$ GOOS=linux GOARCH=amd64 go build -ldflags '-s -w'
$ upx mackerel-multi-port-apache-plugin
```

## プラグインの配置場所
ap1かapm2サーバの`/usr/local/bin/multi-apache2`として配置する
新しく配置した後はmackerelをサービスを再起動する
```
/etc/init.d/mackerel-agent restart
```

## 参考資料
元にしたコード
https://github.com/mackerelio/mackerel-agent-plugins/tree/master/mackerel-plugin-apache2
