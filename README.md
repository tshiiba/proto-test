# protoc-test

Buf + `protoc-gen-doc` で `proto/` から API ドキュメントを生成するサンプルです。

## サンプルAPI

- `proto/sogage/v1/game_api.proto`
  - `Login`
  - `LinkIdentity`
  - `RefreshSession`
  - `GetAccountStatus`
  - `GetHome`
  - `DrawGacha`
  - `StartQuest`
  - `PurchaseProduct`

よく使う要素（enum / repeated / map / oneof / Timestamp / Wrappers）を一通り含めています。

## ドキュメント生成（HTML / Markdown）

前提:

- `buf` がインストール済み
- `protoc-gen-doc` が PATH にある（バイナリ名: `protoc-gen-doc`）

### Buf のインストール例

Go が使える場合:

```bash
go install github.com/bufbuild/buf/cmd/buf@latest
export PATH="$PATH:$(go env GOPATH)/bin"
```

`go` が無い場合は、公式のリリースバイナリをインストールしてください。

### protoc-gen-doc のインストール例

例: Go が使える場合

```bash
go install github.com/pseudomuto/protoc-gen-doc/cmd/protoc-gen-doc@latest
export PATH="$PATH:$(go env GOPATH)/bin"
```

生成:

```bash
buf generate
```

※ `buf generate` は `protoc-gen-doc` をローカル実行するため、`protoc-gen-doc` が PATH に無いと失敗します。
（インストール例は上の手順を参照）

出力:

- `docs/index.html`
- `docs/api.md`
