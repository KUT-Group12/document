# document

### LaTeXコンパイル用ワークフロー

- **目的**: リポジトリ内の `.tex` ファイルを GitHub Actions で自動コンパイルし、PDFを生成する  
- **処理内容**:  
  - `uplatex` を2回実行して参照解決  
  - `.dvi` が生成された場合のみ `dvipdfmx` で PDF 化  
  - PDFは元の `.tex` ファイルと同じディレクトリに生成  
  - GitHub Actions のアーティファクトとして収集  

- **トリガー**: `main` ブランチへの push または pull request  
- **注意点**:  
  - コンパイルエラーがある場合はPDF生成されない  
  - ファイル名にスペース・特殊文字があっても安全に処理可能  
