# statistical-tests
各種検定を実施するデータ分析用リポジトリ

## セットアップ
1. 仮想環境を作成して有効化します。
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```
2. 依存パッケージをインストールします。
   ```bash
   pip install -r requirements.txt
   ```

## Jupyterノートブックでの検定手順
1. ノートブックサーバーを起動します。
   ```bash
   jupyter notebook
   ```
2. `click_ratio_ttest.ipynb` を開き、`data_path` を解析したいCSVファイル（`playback_seconds`, `imp`, `click`列を含む）に置き換えて実行します。
3. `ratio = click / imp` を計算した上で、再生時間ごとの差がWelchのt検定で統計的に有意かを確認できます。サンプルデータは `data/sample_clicks.csv` に入っています。

## 含まれる指標
- 箱ひげ図による再生時間別クリック率の分布可視化
- 再生時間ごとの件数・平均・標準偏差
- Welchのt検定による再生時間間のクリック率差の有意性判定（Bonferroni補正を併記）
