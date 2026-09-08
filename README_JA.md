# VRMLiveViewer-AutoCamera

VRM Live Viewer の「手動カメラ設定（Auto Camera Settings）」用カメラワークを、ChatGPTやGeminiなどの生成AIを利用して作成・調整するための非公式資料とサンプルです。

**[English README](README.md)**

## はじめに

初めて利用する場合は、まず [生成AIを用いた手動カメラ設定のはじめかた](docs/Getting_Started_JA.md)参照してください。

生成AIに仕様書とサンプルJSONを渡し、BPM、フレーム数、キャラクター番号、希望するカメラワークを自然言語で伝えることで、VRM Live Viewer用のAutoCamera JSONを作成できます。

## ファイル

- `docs/Getting_Started_JA.md` - 手動カメラ設定を生成AIで作成する手順
- `docs/AutoCamera_JSON_Spec_JA.pdf` - AutoCamera JSONの設定値、UIとの対応、カメラパーツの組み合わせ規則
- `samples/full_camera_sample_6660f_160bpm.json` - カメラワーク生成のアウトプット例

サンプルJSONは特定の楽曲用プリセットではありません。水平オービット、ロール、ダッチアングル、横倒し構図、ズーム、ドリー、Jitterなどを組み合わせたAutoCamera JSONの出力例です。フレーム配置の例として全長6660フレーム、160 BPMを想定しています。

## 注意事項

- 本プロジェクトは非公式です。VRM Live Viewerの開発者による公式プロジェクトではありません。
- 本資料を利用して制作した動画をYouTube等へ投稿・公開する場合は、使用する楽曲、モデル、モーション、振付、ステージ、衣装、その他の素材について、それぞれの利用規約・権利関係を確認してください。
- モーションや振付等を利用する場合は、配布者・制作者・踊り手等が定めるクレジット表記や利用条件を確認し、必要な謝辞・クレジットを記載してください。
- 本プロジェクトに関する問い合わせをVRM Live Viewerの開発者へ送ることはお控えください。本プロジェクトについてVRM Live Viewer開発者がサポートを行うものではありません。

## 用語

- **カメラワーク**：カメラの動き・構図・演出全体
- **フレーム**：タイムライン上の位置を示す単位
- **カメラデータ**：AutoCamera JSONの `datas[]` の1要素
- **カメラパーツ**：再利用可能なカメラ設定。1個または複数のカメラデータで構成

## License

MoonaWorksが本リポジトリで独自に作成した文書およびサンプルデータは、CC0 1.0 Universalの対象とする予定です。これはVRM Live Viewer本体、VRM Live Viewerの名称・ロゴ、または第三者が制作した楽曲、モデル、モーション、振付、ステージ、衣装その他の素材には適用されません。
