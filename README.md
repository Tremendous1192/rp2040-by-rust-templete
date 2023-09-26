# rp2040-by-rust-templete
[rp-rs/rp2040-project-template: A basic rp2040-hal project with blinky and rtt logging example code. With this you can quickly get started on a new rp2040 project](https://github.com/rp-rs/rp2040-project-template)の自分用テンプレート

# 事前準備
1. ```rustup target install thumbv6m-none-eabi```でビルド対象CPUを追加する
2. ```cargo install flip-link elf2uf2-rs```でRaspberry pi用のビルドツールをインストールする

# 使用方法
1. ```cargo install cargo-generate```コマンドで```cargo-generate```をインストールする
2. ```cargo generate --git https://github.com/rp-rs/rp2040-project-template```でテンプレートをダウンロードする

プロジェクト名を設定してください。

3. ```root/.cargo/config.toml```ファイルのビルド対象を変更する
```rust
#runner = "probe-run --chip RP2040" # デフォルトではビルドできないのでコメントアウト
# runner = "elf2uf2-rs -d"
# runner = "probe-rs run --chip RP2040 --protocol swd"
runner = "elf2uf2-rs -d" # ビルドするためのおまじないを追加
```
4. ```cargo run```