# Lean Quiz Template

証明アシスタント Lean4 を使用して，クイズを出題するためのテンプレートです．

## 出題者の方へ

1. まず，このリポジトリをローカルにクローンします．

```bash
git clone https://github.com/Seasawher/lean-quiz-template.git
```

2. そのままだと GitHub に push できませんので，このリポジトリを `upstream` に設定します．

```bash
git remote remove origin
git remote add upstream https://github.com/Seasawher/lean-quiz-template.git
```

3. 問題を用意します．回答者に証明してほしい命題を `your_theorem` として，`Solution.lean` ファイルに次のコードを書きます．

```lean
import LeanGrader.Basic

def solution : {your_theorem} := by
  sorry

#type_hash solution
```

4. `#type_hash` の出力をコピーして，`.github/classroom/autograding` の `lake exe grade ****` の `****` の箇所に代入します．

5. `Solution.lean` から `import LeanGrader` と `#type_hash` の行を削除して，問題文だけにしておきます．

6. 必要に応じてこの `README.md` の内容も編集します．

7. GitHub に push して，回答を受け付けます．

## 回答者の方へ

1. このリポジトリを Fork します

2. `Solution.lean` にある命題を，`sorry` を使わずに証明してください. それ以外の無関係のファイル，特に `.github` ディレクトリ配下のファイルは編集しないでください．

3. 終わったらこのリポジトリに Pull Request を投げてください．自動的に GitHub Action によって採点がなされて，以下ををチェックします．
   1. 回答が正しいこと
   2. 証明した命題が最初の課題と等しいこと
   3. GitHub アクションが変更されていないこと
