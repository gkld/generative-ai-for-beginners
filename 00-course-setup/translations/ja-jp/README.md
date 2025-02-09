# このコースを始めるために

私たちは、皆様がこのコースを開始し生成 AI で何を創り出すのかを見るのが、とても楽しみです！

皆様がこのレッスンを成功できるよう、セットアップ手順と技術要件そして必要な時に情報を得る方法を、このページにまとめました。  

## セットアップ手順

このコースを始める前に、下記の手順を実施してください。  

### 1. リポジトリのフォーク

コードを修正したりレッスンの課題を完了するため、このリポジトリ全てをご自身の GitHub アカウントで[フォーク](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-yoterada)してください。また、簡単にこのリポジトリを見つけれるよう、[スター（🌟）をつける](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-yoterada)こともできます。  

### 2. codespaces を作成

コードを実行する際、依存関係の問題を避けるため、GitHub codespaces で、このコースを実行することをお勧めします。  

codespaces は、上記でフォークしたリポジトリの `Code` を選択し、**Codespaces** オプションを選択することで作成できます。  

### 3. API　キーの保管

アプリケーションを構築する際、API キーを安全に管理することはとても重要です。公開リポジトリにこうした機密情報をコミットすると、不正利用による想定外のコストや問題が発生する可能性があります。そこで、作業中のコードに直接 API キーを保存しないようにしてください。  

![codespaceを作成するボタンを示すダイアログ](../../images/who-will-pay.webp?WT.mc_id=academic-105485-yoterada)

## ローカルのコンピュータで実行する方法

ローカルのコンピュータ上で、コードを実行するためには、[Python のインストール](https://www.python.org/downloads/?WT.mc_id=academic-105485-yoterada)が必要です。

そして、リポジトリを使用するためクローンする必要があります

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

これですべての準備が整いましたので、学習と作業を始めることができます。  

### miniconda　のインストール　（オプションの手順）

**[miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-yoterada)** のインストールをお勧めします - これは、異なる Python **仮想環境**で `conda` パッケージ・マネージャをサポートする、比較的軽量なインストーラーです。`conda` を利用すると、異なる Python のバージョンやパッケージを簡単にインストールでき、切り替えるもできます。さらに、`pip` 経由で入手できないパッケージのインストールもできます。  

miniconda をインストールした後、リポジトリをクローンしてください（まだ行っていない場合）。そして、このレッスン用の仮想環境を作成してください：  

下記の手順を実行する前に、まず *environment.yml* ファイルが存在していることをご確認ください。*environment.yml* ファイルは、conda　環境の構築に必要な依存関係を定義した設定ファイルで、下記のような内容を記述します：  

```yml
name: <environment-name>
channels:  
 - defaults
dependencies:  
- python=<python-version>  
- openai  
- python-dotenv
```

`<environment-name>` には、この conda 環境名を設定し、`<python-version>` には使用する Python のバージョンを記述してください。作成した *environment.yml* ファイルはリポジトリ内の *.devcontainer* フォルダ配下に置いてください。  

*environment.yml* ファイルを作成した後、下記のコマンドを実行し、conda 環境を作成します：  

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml
conda activate ai4beg
```

仮に何らかの問題が発生した場合は、ユーザ・ガイドの [conda 環境](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-yoterada)をご参照ください。  

### Python の拡張機能をインストールした Visual Studio Code の使用

本カリキュラムを進めていく上で最もお勧めの方法は、[Python の拡張機能を](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-yoterada)インストールした [Visual Studio Code](http://code.visualstudio.com/?WT.mc_id=academic-105485-yoterada) のご利用です。

> **ご注意**: クローンした後、VS Code でディレクトリを開くと、自動的に Python 拡張機能のインストールが提案されます。上記で説明したように miniconda もインストールする必要があります。

> **ご注意**: ローカルにインストールした Python を利用したい場合、VS Code がコンテナでリポジトリを再度開くことを提案した際、コンテナでの起動を拒否してください。
  
### ブラウザで Jupyter の使用

ご自身のコンピュータの Web ブラウザから直接、Jupyter 環境を使用することもできます。実際クラシックな Jupyter と Jupyter Hub は、自動補完、コード・ハイライトなどの機能を備えた非常に便利な開発環境を提供します。  

Jupyter をローカルで起動するには、レッスン・コースのディレクトリに移動し、下記のコマンドを実行します：  

```bash
jupyter notebook
```

もしくは

```bash
jupyterhub
```

次に任意の `.ipynb` ファイルに移動し、ファイルを開いて作業を開始できます。  

### コンテナでの実行

ローカル環境に Python をインストールする代わりに、コンテナ上で実行することもできます。このプロジェクトを fork するとレポジトリ内に、コンテナ環境を構築するために必要な設定を含む `.devcontainer` フォルダが存在します。そこで、VS Code は起動時にコンテナで実行することを提案します。コンテナで実行する為には、事前に Docker のインストールが必要で、少し複雑になるため経験豊富なユーザーにお勧めします。

GitHub codespaces を使用して API キーを安全に管理するためには、Codespace Secrets の利用が最適です。[codespaces のシークレットを管理](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-yoterada)する方法については、このガイドをご参照ください。  

## レッスンと技術要件

このコースは、6 つの概念レッスンと 6 つのコーディング・レッスンがあります。

コーディング・レッスンでは、Azure OpenAI サービスを使用します。コードを実行するには、Azure OpenAI サービスへのアクセスと API キーが必要です。[このアプリケーション・フォームを完了](https://go.microsoft.com/fwlink/?linkid=2222006&clcid=0x409?WT.mc_id=academic-105485-yoterada)することで Azure OpenAI へアクセス申請できます。  

アプリケーション・フォーム申請処理の完了を待つ間、何もできないわけではなく、各レッスン中に、`README.md` ファイルとサンプル・コードが含まれていますので、申請処理の完了前でもレッスンの内容をご確認いただけます。

## Azure OpenAI サービスをはじめて使用する場合  

仮に Azure OpenAI サービスをはじめて使用する場合は、[Azure OpenAI サービス・リソースを作成しデプロイする方法](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-yoterada)はこちらのガイドをご参照ください。  

## 他の学習者との交流

他の学習者と交流できるように、私たちは公式 [Discord AI コミュニティ・サーバー](https://aka.ms/genai-discord?WT.mc_id=academic-105485-yoterada)にチャンネルを作成しました。生成 AI の技術を向上したいと考える他の方々、たとえば、志の同じ起業家、開発者、学生、そして、どなたとでも交流していただく事が可能です。  

[![Discord チャンネルに参加](https://dcbadge.vercel.app/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-yoterada)

このプロジェクトを開発したチーム・メンバーも、この Discord サーバーに参加し学習者を支援しています。  

## 貢献

本レッスンはオープンソース・プロジェクトとして公開しています。仮に改善すべき点や問題を発見したら、[プルリクエスト](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-yoterada)をお送りいただくか、もしくは、[GitHub の Issue](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-yoterada) で報告していただければ幸いです。

このプロジェクトの開発チームは全ての貢献を確認しています。オープンソースにご貢献いただくことは、生成 AI の分野で新しいキャリアを築くのに良い方法かもしれません。

多くの場合、貢献者はコントリビューター・ライセンス契約（CLA）に同意して頂く必要があります。これは貢献者が持っている権利を、私たちに、皆様の貢献を使用する権利を実際に与えて頂くことを宣言するための契約です。詳細については [CLA、コントリビューターライセンス契約のウェブサイト](https://cla.microsoft.com?WT.mc_id=academic-105485-yoterada)をご覧ください。

重要なお知らせ：このリポジトリ内に含まれるテキストを翻訳する場合、機械翻訳の使用は避けてください。翻訳の内容はコミュニティで検証するため、ご自身が熟知している言語でのみ翻訳作業にご協力ください。

プル・リクエストを提出すると、CLA-bot が自動的に CLA（コントリビューター・ライセンス契約）の提出が必要かどうかを判断し、プル・リクエストに適切なマーク（例：ラベル、コメント）を付けます。bot の指示にお従いください。この処理は、CLA を使用するすべてのリポジトリで一度だけ行う必要があります。

このプロジェクトは、[Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-yoterada) を採用しています。詳細は、Code of Conduct FAQ をご覧いただくか、追加の質問やコメントがある場合は、[メールで opencode](opencode@microsoft.com) にお問い合わせください。  

## それでは、始めましょう

このレッスンを修了するために必要な手順をすべて完了したので、[生成 AI と大規模言語モデルの紹介](../../../01-introduction-to-genai/translations/ja-jp/README.md?WT.mc_id=academic-105485-yoterada) から始めましょう。
