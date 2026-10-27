# SHSCSTelemetry_custom

SimHub を Euro Truck Simulator 2（ETS2）/ American Truck Simulator（ATS）で利用する際のテレメトリプラグイン `SHETS2Telemetry_x64.dll` を置き換える、カスタム版プラグインです。

## 追加機能

`car_job` 用の実装を追加し、Road Trip での貨物配送時にも、配送情報を SimHub に渡せるようにしています。

取得した情報を既存の配送情報フィールドにも反映することで、SimHub のダッシュボードで貨物名や配送元・配送先などを表示できます。実際に表示される項目は、ゲームから提供される情報とダッシュボードの設定に依存します。

## 導入方法

1. ETS2 / ATS を終了します。
2. 利用するゲームのインストール先にある `bin\win_x64\plugins` フォルダーを開きます。
3. 既存の `SHETS2Telemetry_x64.dll` を、プラグインフォルダーの外へバックアップします。
4. カスタム版の `SHETS2Telemetry_x64_kuramochia.dll` を `SHETS2Telemetry_x64.dll` にリネームし、同じプラグインフォルダーへ配置します。
5. SimHub とゲームを起動し、Road Trip の貨物配送中に配送情報が表示されることを確認します。

ETS2 と ATS の両方で利用する場合は、それぞれのゲームに導入してください。

### 注意事項

- 元のプラグインとカスタム版を同時に読み込ませないでください。バックアップは必ずプラグインフォルダーの外へ保存してください。
- SimHub によるプラグインの再インストールや更新で元の DLL に戻った場合は、再度カスタム版へ置き換えてください。
- 元に戻す場合は、ゲームを終了してカスタム版を削除し、バックアップした DLL を元の場所へ戻してください。

## ビルド

Visual Studio の「C++ によるデスクトップ開発」と Windows SDK が必要です。プロジェクトでは C++17 とプラットフォームツールセット `v145` を指定しています。

1. [ソリューション](SHETS2Telemetry_x64_kuramochia/SHETS2Telemetry_x64_kuramochia.sln)を Visual Studio で開きます。
2. 構成を `Release`、プラットフォームを `x64` に設定してビルドします。
3. `bin\win_x64\SHETS2Telemetry_x64_kuramochia.dll` が生成されます。

SCS Telemetry SDK のヘッダーは [scs_sdk](scs_sdk/) に含まれています。

## ライセンス

[LICENSE](LICENSE) を参照してください。SCS SDK のライセンスについては [sdk_license.txt](scs_sdk/sdk_license.txt) を参照してください。