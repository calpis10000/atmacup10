# atmaCup10 [Public 9th / Private 3rd]

## このリポジトリについて
- atmaCup10(https://www.guruguru.science/competitions/16) の最終sub再現コードです。
- 解法はこちら: 
  - https://www.guruguru.science/competitions/16/discussions/b14d0693-fe4b-4ba8-9e67-533f84dd87ad/
  - https://speakerdeck.com/calpis10000/atmacup-number-10-zhen-rifan-rihui-3rd-place-solution

## 環境構築
```
1. 適当なディレクトリにclone
2. clone後のフォルダ直下にて、`poetry install`を実行
    - poetry未導入の場合: こちらを参考に導入する→ https://python-poetry.org/docs/
    - または、pyproject.tomlの[tool.poetry.dependencies]を参考にライブラリをインストール
3. `00_input`フォルダに`atmacup10_dataset.zip`の中身を配置
    - `../00_input/atmacup10_dataset/train.csv`のような配置になる。
4. `99_bin`フォルダにfasttextのモデルを配置
    - ↓から`lid.176.bin`をダウンロード
    - https://fasttext.cc/docs/en/language-identification.html
```

## Notebookについて
`01_nb`配下に、以下2点を配置しています。
```
- 056_Model_nb053ベースでハイパラチューニング.ipynb
  → ハイパラチューニング＆W2V特徴作成用
- 067_056のハイパラで再学習（057修正_再現性確保）.ipynb
  → 056で作成したハイパラ, W2Vで学習&予測
```

## 実行手順
`067_056のハイパラで再学習（057修正_再現性確保）.ipynb`を上から全セル実行すると、  
特徴作成〜学習・予測の一連の動作が実行されます。  

正しく実行されると、`02_outputs`フォルダ配下にnotebook番号のフォルダ(今回は`067`)が作成され、  
その配下に`submission.csv`およびfeature_importanceの画像が出力されます。  

もし、ハイパラチューニング含めた再現を行いたい場合は、  
`056_Model_nb053ベースでハイパラチューニング.ipynb`を全セル実行すると、  
`03_feature`配下のチューニング済みモデル・パラメータのpickleが更新されます。  
※ こちらは再現確認していません。
