# Realworld with clean archtecture and Golang

[realworld](https://codebase.show/projects/realworld?category=backend&language=go)で見つけた, clean architectureによるMediumクローン.

https://github.com/err0r500/go-realworld-clean

- domain下にArticle型とUser型
- uc下にusecases
    - uc/INTERACTOR.go にinput portのinterface定義
    - uc/HANDLER.go にoutput portのinterface定義
    - usecaseごとに1ファイル, interactorにinput portを定義している.
- implem下にimplementations
    - ディレクトリ名称はドット区切り
- infra下にconfigとgin
    - httpサーバは"github.com/gin-gonic/gin"
- 設定の管理には"github.com/spf13/viper"を使用
    - 環境変数や各種ファイルからConfig構造体を構築してくれるようだ. 便利.
- CLI機能は"github.com/spf13/cobra"
- jwt周りが勉強になりそう.
    - ログイン成功したら, ユーザ名からtokenを求めて返す.
    - tokenからユーザ名が得られる
    - "github.com/dgrijalva/jwt-go"
    - サーバは状態を持たなくていい?
- `(rH *RouterHandler)`のような略称
- populateオプションをつけると, fixturesがdbに登録される
- apiテストにpostmanを使っている, らしい


