### Omotesando.rb #53
- - -

## reline に
## GitHub Actions を追加した話

---

#### 自己紹介
- - -

* なまえ  : おしょー
* Twitter : [@pink_bangbi](https://twitter.com/pink_bangbi)
* github  : [osyo-manga](https://github.com/osyo-manga)
* ブログ  : [Secret Garden(Instrumental)](http://secret-garden.hatenablog.com)
  * [ピュア Ruby で Ruby 2.7 の Numbered parameter を実装してみよう！ - Secret Garden(Instrumental)](http://secret-garden.hatenablog.com/entry/2019/12/01/154607)   <!-- .element: class="fragment" -->
  * [一人 Ruby Advent Calendar 2017 - Qiita](https://qiita.com/advent-calendar/2017/ruby_pink_bangbi)                        <!-- .element: class="fragment" -->

---

# 今日話すこと

---

## reline に GitHub Actions を追加した話

---

## reline とは

---

#### readline とは
- - -

* Ruby ではコマンドライン入力インタフェースとして raedline というモジュールを内包している                              <!-- .element: class="fragment" -->
* このモジュールを利用して irb や pry などが実装されている                              <!-- .element: class="fragment" -->
* これは GNU Readline という外部ライブラリに依存している                              <!-- .element: class="fragment" -->

>>>

```ruby
# モジュールを読み込み
 require "readline"

# 補完の設定
Readline.completion_proc = Readline::FILENAME_COMPLETION_PROC

# 入力 IO を呼び出す
# 戻り値に実行結果が返ってくる
expr = Readline.readline("> ")

# 戻り値を eval で評価して出力
puts eval(expr)
```

---

#### readline の問題点
- - -

* この readline は外部ライブラリの GNU Readline に依存している                            <!-- .element: class="fragment" -->
* なので Ruby 自体も GNU Readline に依存してしまっている                            <!-- .element: class="fragment" -->
* これにより GNU Readline が存在しない環境では irb が使えないことがある                            <!-- .element: class="fragment" -->
* オワタ／(^o^)＼                            <!-- .element: class="fragment" -->

---


#### reline とは
- - -

* GNU Readline に依存せずに ピュア Ruby で readline を再実装した reline というモジュールが開発されている                        <!-- .element: class="fragment" -->
* reline を使用することで GNU Readline に依存する事なく irb や pry を使用する事が出来る                        <!-- .element: class="fragment" -->
* また readline にはないマルチラインが実装されている（！）                        <!-- .element: class="fragment" -->
* これは RUby 2.7 に入る予定                        <!-- .element: class="fragment" -->

---

## GitHub Actions とは

---

#### GitHub Actions とは
- - -

* リポジトリにワークフローを設定できる GitHub の機能                        <!-- .element: class="fragment" -->
  * ビルドやテスト、パッケージング、デプロイなど出来る
* この機能を利用して GitHub 上で CI を実行できる                        <!-- .element: class="fragment" -->
* Linux、macOS、Windows の 3つの環境で実行する事が出来る                        <!-- .element: class="fragment" -->
* パブリックリポジトリは無料で使える！                        <!-- .element: class="fragment" -->
* 詳しくはこちら                        <!-- .element: class="fragment" -->
  * [GitHub Actionsについて](https://help.github.com/ja/actions/automating-your-workflow-with-github-actions/about-github-actions)

---

## 一言でいうと
## Linux、macOS、Windows の3つの環境で実行できる
## めっちゃ便利な CI サービス

---

#### Github Actions のここが便利
- - -

* Linux だけではなくて macOS、Windows 環境でも実行できる！                        <!-- .element: class="fragment" -->
  * reline に関していえば様々な環境でテストする必要があるのでマルチプラットフォームで実行できるのはめっちゃありがたい
* Ruby 本体でも GitHub Actions が使われている！                        <!-- .element: class="fragment" -->
  * 便利
  * [rake](https://github.com/ruby/rake) や [rdoc](https://github.com/ruby/rdoc) でも使われている


---

#### Github Actions のここがダメ
- - -

* 何もしてないのに CI がぶっ壊れる                    <!-- .element: class="fragment" -->
* ログが見づらい                    <!-- .element: class="fragment" -->

---

#### まとめ
- - -

* GitHub Actions めっちゃ便利なのでみんなも使おう！

---

## ご清聴
## ありがとうございました
