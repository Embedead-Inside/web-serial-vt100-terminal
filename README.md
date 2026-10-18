# Web Serial VT100 Terminal

Web Serial API と [Xterm.js](https://xtermjs.org/) をベースとし、 **「ターミナル（ブラウザ）側にコマンド履歴およびデバッグログ保存機能を持たせる」** ことで、組み込み機器側のCLI・デバッグロジックを極限までシンプルに保てるよう設計されています。

![License: MIT-0](https://img.shields.io/badge/License-MIT--0-blue.svg)

![Web Serial VT100 Terminal](https://raw.githubusercontent.com/Embedead-Inside/web-serial-vt100-terminal/refs/heads/main/web-serial-vt100-terminal.png)

---

## 主な機能

- **単一ファイル・オフライン対応**: 複雑なビルドツールやサーバーは不要です。`web-serial-vt100-terminal.html` をブラウザ（ChromeやEdgeなど）で開くだけで使用できます。
- **高度なローカル行編集**: 
  - ブラウザ側でコマンドをバッファリングし、左右のカーソル移動 (`←`/`→`)、バックスペース、Deleteキーによる編集が可能。
  - マイコン側のプロンプト（`>` や `uart:~$` など）を消去してしまわない安全な部分再描画方式を採用。
- **充実した履歴機能**:
  - 矢印キー (`↑`/`↓`) によるコマンド履歴の呼び出し（LocalStorageに最大100件保存）。
  - 直近20件の履歴をすばやく選択・送信できるクイック送信ドロップダウン。
- **ログ保存 & ユーティリティ**:
  - ミリ秒精度のタイムスタンプ付与機能。
  - 受信・送信ログを `.log` ファイルとして一括保存。
  - ログバッファとターミナル画面を一括クリア。
- **自動フォーカス管理**: 接続や各種ボタン操作の完了と同時にターミナルへ自動フォーカスし、すぐにキーボード入力が可能。

---

## 使用技術

- HTML5 / Vanilla JavaScript (ES6+)
- [Web Serial API](https://developer.mozilla.org/en-US/docs/Web_API/Web_Serial_API)
- [Xterm.js v5.3.0](https://xtermjs.org/) (`xterm-addon-fit`)

---

## 使い方

1. このリポジトリをクローンまたはダウンロードします。
2. Web Serial API対応ブラウザ（Google Chrome、Microsoft Edgeなど）で `web-serial-vt100-terminal.html` を開きます（※ブラウザの仕様上、ローカルサーバー経由での実行を推奨します）。
3. ボーレート（デフォルト: `115200 bps`）を選択し、**「接続」** ボタンをクリックします。
4. 接続するシリアルデバイス（マイコンボードなど）を選択します。

---

## ライセンス

このプロジェクトはMIT-0ライセンスのもとで公開されています。詳細は[LICENSE](LICENSE)ファイルをご覧ください。
- 商用利用・個人利用を問わず、完全自由に使用できます。
- 著作権表示やライセンス文言の保持・記載義務すらありません。
- ソースコードの改変、流用、再配布、自社製品への組み込み等、制限なくご活用いただけます。

