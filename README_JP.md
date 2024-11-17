<p align="left">
    <a href="README.md">English</a>&nbsp ｜ <a href="README_CN.md">中文</a>&nbsp ｜ 日本語</a>
</p>
<br><br>

<p align="center">
 <img src="https://dscache.tencent-cloud.cn/upload/uploader/hunyuan-64b418fd052c033b228e04bc77bbc4b54fd7f5bc.png" width="400"/> <br>
</p><p></p>

<p align="center">
    🫣&nbsp<a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large"><b>Hugging Face</b></a>&nbsp&nbsp |  &nbsp&nbsp🖥️&nbsp&nbsp<a href="https://llm.hunyuan.tencent.com/" style="color: red;"><b>公式サイト</b></a>&nbsp&nbsp｜&nbsp&nbsp🕖&nbsp&nbsp <a href="https://cloud.tencent.com/product/hunyuan" ><b>混元API</b></a>&nbsp&nbsp｜&nbsp&nbsp🐳&nbsp&nbsp <a href="https://gitee.com/Tencent/Tencent-Hunyuan-Large" ><b>Gitee</b></a>
</p><p align="center">
    <a href="https://arxiv.org/abs/2411.02265" style="color: red;"><b>技術報告</b></a>&nbsp&nbsp｜&nbsp&nbsp <a href="https://huggingface.co/spaces/tencent/Hunyuan-Large"><b>デモ</b></a>&nbsp&nbsp&nbsp｜&nbsp&nbsp <a href="https://cloud.tencent.com/document/product/851/112032" style="color: red;"><b>Tencent Cloud TI</b></a>&nbsp&nbsp&nbsp</p>
<p><br></p>
<p>
    <table align="center">
        <tbody>
            <tr>
                <td align="center" colspan="3"><strong>モデルのダウンロード</strong></td>
            </tr>
            <tr>
                <td align="center" style="width: 100px;" >モデル</td>
                <td align="center" style="width: 500px;">Huggingface ダウンロードURL</td>
                <td align="center" style="width: 500px;">Tencent Cloud ダウンロードURL</td>
            </tr>
            <tr>
                <td style="width: 100px;">Hunyuan-A52B-Instruct-FP8</td>
                <td style="width: 500px;"><a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large/tree/main/Hunyuan-A52B-Instruct-FP8" style="color: red;">Hunyuan-A52B-Instruct-FP8</a></td>
                <td style="width: 500px;"><a href="https://hunyuan-large-model-1258344703.cos.ap-guangzhou.myqcloud.com/Hunyuan-A52B-Instruct-128k-fp8.zip" style="color: red;">Hunyuan-A52B-Instruct-FP8</a></td>
            </tr>
            <tr>
                <td style="width: 100px;">Hunyuan-A52B-Instruct</td>
                <td style="width: 500px;"><a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large/tree/main/Hunyuan-A52B-Instruct" style="color: red;">Hunyuan-A52B-Instruct</a></td>
                <td style="width: 500px;"><a href="https://hunyuan-large-model-1258344703.cos.ap-guangzhou.myqcloud.com/Hunyuan-A52B-Instruct-128k.zip" style="color: red;">Hunyuan-A52B-Instruct</a></td>
            </tr>
            <tr>
                <td style="width: 100px;">Hunyuan-A52B-Pretrain</td>
                <td style="width: 500px;"><a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large/tree/main/Hunyuan-A52B-Pretrain" style="color: red;">Hunyuan-A52B-Pretrain</a></td>
                <td style="width: 500px;"><a href="https://hunyuan-large-model-1258344703.cos.ap-guangzhou.myqcloud.com/Hunyuan-A52B-Pretrain-256k.zip" style="color: red;">Hunyuan-A52B-Pretrain</a></td>
            </tr>
        </tbody>
    </table>
</p>

<p></p>


## モデル紹介

人工知能技術の急速な発展に伴い、大規模言語モデル（LLMs）は自然言語処理、コンピュータビジョン、科学タスクなどの分野で顕著な進展を遂げました。しかし、これらのモデルの規模が拡大するにつれて、高性能を維持しながらリソース消費を最適化することが重要な課題となっています。この課題に対処するために、私たちは専門家の混合（MoE）モデルを研究しました。現在公開されているHunyuan-Large（Hunyuan-MoE-A52B）モデルは、業界で最大のオープンソースのTransformerベースのMoEモデルであり、総パラメータ数は3890億、アクティブパラメータ数は520億です。

Hunyuan-Largeの技術成果をオープンソース化することで、より多くの研究者に革新的なアイデアを提供し、AI技術の進歩と応用を共に推進することを期待しています。私たちのオープンソースコミュニティに参加し、未来のAIモデルを共に探求し、最適化しましょう！

### 技術的な利点の紹介

#### モデル
- **高品質な合成データ**：合成データを用いたトレーニングにより、Hunyuan-Largeはより豊かな表現を学習し、長いコンテキスト入力を処理し、未見のデータに対しても優れた一般化能力を発揮します。

- **KVキャッシュ圧縮**：グループ化クエリアテンション（GQA）とクロスレイヤーアテンション（CLA）戦略を採用し、KVキャッシュのメモリ使用量と計算オーバーヘッドを大幅に削減し、推論スループットを向上させます。

- **専門家特定の学習率スケーリング**：異なる専門家に異なる学習率を設定し、各サブモデルがデータから効果的に学習し、全体のパフォーマンスに貢献することを確保します。

- **長いコンテキスト処理能力**：事前トレーニングモデルは最大256Kのテキストシーケンスをサポートし、Instructモデルは最大128Kをサポートし、長いコンテキストタスクの処理能力を大幅に向上させます。

- **広範なベンチマークテスト**：さまざまな言語とタスクにわたる広範な実験を行い、Hunyuan-Largeの実際の応用効果と安全性を検証します。

#### 推論フレームワーク
- Hunyuan-Largeモデルは、TRT-LLMバックエンドと[vLLMバックエンド](https://github.com/quinnrong94/vllm/tree/dev_hunyuan)の推論フレームワークをサポートしています。オープンソースフレームワークに基づいてHunyuan-Largeモデルを適応させました。たとえば、新たに追加されたCLA構造はKVキャッシュのメモリ使用量を大幅に削減し（50％節約）、超長テキストシナリオを保証します。さらに、FP8の量子化最適化により、FP16/BF16の通常の量子化と比較して、精度を最大限に確保しながらメモリ使用量を50％削減し、スループットを70％向上させます。同時に、TRT-LLMの効率的なオペレーターに基づいて、その性能はvLLMと比較して30％以上向上しています。現在、TRT-LLMソリューションはTencentのHunyuanプロジェクトで広く使用されています。今回はvLLMフレームワークを優先的にオープンソース化し、TRT-LLMは近日中に公開予定です。

#### トレーニングフレームワーク
- Hunyuan-Largeオープンソースモデルは、huggingface形式をサポートしており、ユーザーがhf-deepspeedフレームワークを使用してモデルの微調整を行うことができます。また、flash-attnを利用したトレーニングの高速化もサポートしています。これにより、関連するトレーニングスクリプトとモデル実装をコミュニティに公開し、研究者がこれを基に後続のモデルトレーニングと微調整を行うことができます。

&nbsp;

## ニュース
* 2024.11.5 [TIプラットフォーム](https://cloud.tencent.com/product/ti)はすでにHunyuan-Largeモデルを統合しており、数ステップで簡単にトレーニングとデプロイが可能です。[Chat with Hunyuan-Large](https://console.cloud.tencent.com/tione/v2/aimarket/detail/hunyuan_series?PublicAlgoGroupId=hunyuan-large-chat&detailTab=demo)にアクセスしてモデルとのリアルタイム対話を体験し、TI上での[Hunyuan-Large Best Practice](https://cloud.tencent.com/document/product/851/112032)を探索して、独自のカスタマイズHunyuan-Largeを作成してください。
* 2024.11.5 Hugging Faceで**Hunyuan-A52B-Pretrain**、**Hunyuan-A52B-Instruct**、および**Hunyuan-A52B-Instruct-FP8**をオープンソース化しました。また、技術報告書とトレーニングおよび推論の操作マニュアルを公開し、モデルの能力とトレーニングおよび推論の操作手順を詳しく紹介しています。
<br>


## ベンチマーク評価

**Hunyuan-Large 事前トレーニングモデル**は、同様のアクティブパラメータサイズを持つDenseおよびMoEの競合モデルと比較して、全体的なパフォーマンスで最良の結果を達成しました。
MMLU、MMLU-pro、CMMLUなどのベンチマーク評価では、Hunyuan-Largeのパフォーマンスは常に最高水準を維持しており、統合タスクにおける総合的な能力を証明しています。
Hunyuan-Largeは、常識理解と推論、およびQAや読解タスク（CommonsenseQA、PIQA、TriviaQAなど）の古典的なNLPタスクでも優れたパフォーマンスを示しています。
数学能力においては、Hunyuan-LargeはGSM8KおよびMath数学データセットで全てのベースラインを上回り、CMATH中国語データセットでも最良の成績を収めました。
また、Hunyuan-Largeは全ての中国語タスク（例：CMMLU、C-Eval）で全体的に最良のパフォーマンスを実現しました。

| モデル            | LLama3.1-405B | LLama3.1-70B | Mixtral-8x22B | DeepSeek-V2 | Hunyuan-Large |
|------------------|---------------|--------------|---------------|-------------|---------------|
| MMLU             | 85.2          | 79.3         | 77.8          | 78.5        | **88.4**          |
| MMLU-Pro         | **61.6**          | 53.8         | 49.5          | -           | 60.2          |
| BBH              | 85.9          | 81.6         | 78.9          | 78.9        | **86.3**          |
| HellaSwag        | -             | -            | **88.7**      | 87.8        | 86.8          |
| CommonsenseQA    | 85.8          | 84.1         | 82.4          | -           | **92.9**          |
| WinoGrande       | 86.7          | 85.3         | 85.0          | 84.9        | **88.7**          |
| PIQA             | -             | -            | 83.6          | 83.7        | **88.3**          |
| NaturalQuestions | -             | -            | 39.6          | 38.7        | **52.8**          |
| DROP             | 84.8          | 79.6         | 80.4          | 80.1        | **88.9**          |
| ARC-C            | **96.1**          | 92.9         | 91.2          | 92.4        | 95.0          |
| TriviaQA         | -             | -            | 82.1          | 79.9        | **89.2**          |
| CMMLU            | -             | -            | 60.0          | 84.0        | **90.2**          |
| C-Eval           | -             | -            | 59.6          | 81.7        | **91.9**          |
| C3               | -             | -            | 71.4          | 77.4        | **82.3**          |
| GSM8K            | 89.0          | 83.7         | 83.7          | 79.2        | **92.8**          |
| MATH             | 53.8          | 41.4         | 42.5          | 43.6        | **69.8**          |
| CMATH            | -             | -            | 72.3          | 78.7        | **91.3**          |
| HumanEval        | 61.0          | 58.5         | 53.1          | 48.8        | **71.4**          |
| MBPP             | **73.4**          | 68.6         | 64.2          | 66.6        | 72.6          |

**Hunyuan-Large-Instruct**は、同様のアクティブパラメータを持つLLMと比較して、ほとんどのタスクで一貫した性能向上を実現しており、私たちのポストトレーニングが非常に効果的であることを示しています。
異なるカテゴリのベンチマークテストにおいて、私たちのInstructモデルはMMLUおよびMATHデータセットで最良の性能を達成しました。
特に、MMLUデータセットでは、私たちのモデルはLLama3.1-405Bモデルを2.6％上回る顕著な向上を示しました。
この向上は、Hunyuan-Large-Instructが広範な言語理解タスクにおいて優れた理解と推論能力を持っていることを示しています。
このモデルのMATHデータセットでのパフォーマンスは、その実力をさらに強調しており、LLama3.1-405Bを3.6％上回っています。
注目すべきは、わずか520億のアクティブパラメータで精度の飛躍を実現していることであり、Hunyuan-Large-Instructの卓越した能力を証明しています。

| モデル                | LLama3.1 405B Inst. | LLama3.1 70B Inst. | Mixtral 8x22B Inst. | DeepSeekV2.5 Chat | Hunyuan-Large Inst. |
|----------------------|---------------------|--------------------|---------------------|-------------------|---------------------|
| MMLU                 | 87.3                | 83.6               | 77.8                | 80.4              | **89.9**            |
| CMMLU                | -                   | -                  | 61.0                | -                 | **90.4**            |
| C-Eval               | -                   | -                  | 60.0                | -                 | **88.6**            |
| BBH                  | -                   | -                  | 78.4                | 84.3              | **89.5**            |
| HellaSwag            | -                   | -                  | 86.0                | **90.3**          | 88.5                |
| ARC-C                | **96.9**            | 94.8               | 90.0                | -                 | 94.6                |
| GPQA_diamond         | **51.1**            | 46.7               | -                   | -                 | 42.4                |
| MATH                 | 73.8                | 68.0               | 49.8                | 74.7              | **77.4**            |
| HumanEval            | 89.0                | 80.5               | 75.0                | 89.0              | **90.0**            |
| AlignBench           | 6.0                 | 5.9                | 6.2                 | 8.0               | **8.3**             |
| MT-Bench             | 9.1                 | 8.8                | 8.1                 | 9.0               | **9.4**             |
| IFEval strict-prompt | **86.0**            | 83.6               | 71.2                | -                 | 85.0                |
| Arena-Hard |  69.3            | 55.7               |  -                | 76.2                 | **81.8**            |
| AlpacaEval-2.0 | 39.3            | 34.3               | 30.9                | 50.5                 | **51.8**            |

&nbsp;
## データ

Hunyuan-Largeは、モデルトレーニングに関連するプロセスを提供しています。このセクションでは、トレーニングデータ形式を処理してモデルトレーニングに使用する方法を説明します。

### トレーニングデータ形式と処理

トレーニングデータは以下の形式でmessages形式に処理されます。トレーニングと推論のデフォルトのシステムプロンプトは「You are a helpful assistant.」です。以下に単一ターンデータとマルチターンデータのサンプルを示します：

```python
# 単一ターンデータ形式
messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "海水はなぜ塩辛いのですか？" },
    {"role": "assistant", "content": "海水が塩辛いのは、主に水中に溶けている多くの塩類や鉱物質が含まれているためです。これらの塩類や鉱物質は、地球表面の岩石や土壌からの化学物質であり、時間の経過とともに海洋に運ばれました。海水が蒸発すると、水分は蒸発しますが、塩類や鉱物質は水中に残り、海水がより塩辛くなります。したがって、海水の塩辛さは、その中の塩類や鉱物質の含有量によって決まります。"}
]

# マルチターンデータ形式
messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "重慶森林という映画を知っていますか？" },
    {"role": "assistant", "content": "知っていますよ、王家衛監督の作品です。" },
    {"role": "user", "content": "主演には王菲もいて、公開されるとすぐに人気を博しました。" },
    {"role": "assistant", "content": "そのため、この映画は第14回香港映画金像奨で最優秀作品賞を受賞しました。"}
]

from tokenizers import ByteLevelBPETokenizer
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("./models", use_fast=False, trust_remote_code=True)

ids = tokenizer.apply_chat_template(messages)

```

詳細な使用方法については、`./models/test.py`ファイルを参照してください。

&nbsp;

## クイックスタート

<a href="examples/README.md">クイックスタートガイド</a>の内容を参照して、すぐに始めることができます。

## モデルトレーニング

トレーニングプロセスを簡素化するために、HunyuanLLMは事前構築されたDockerイメージを提供しています：

 [hunyuaninfer/hunyuan-large](https://hub.docker.com/repository/docker/hunyuaninfer/hunyuan-large/general) 。

### ハードウェア要件

H20でテストされ、`make_moe_param_leaf_module`を有効にせず、`zero3+offload`を使用し、`max_seq_length`が2048の場合、フルファインチューニングには少なくとも32枚のGPUが必要であり、LoRAファインチューニングには少なくとも8枚のGPUが必要です。

### トレーニングパフォーマンス

最小構成（8枚のGPUでのLoRAファインチューニング）でテストした場合、`per_device_train_batch_size`が1、`gradient_accumulation_steps`が1で、1イテレーションあたり約35秒かかります。

### 起動方法

参照：[HuggingFace Transformers Trainer](https://huggingface.co/docs/transformers/v4.19.2/en/main_classes/trainer)

#### 単一マシンでのトレーニング

`train`ディレクトリで、以下を実行します：

```sh
pip install -r requirements.txt
bash train.sh
```

#### 複数マシンでのトレーニング

複数のマシンでトレーニングを開始するには、以下の手順に従い、すべてのマシンが同じクラスター内にあることを確認してください。

##### マシン間のパスワードなしSSHログインの設定

以下の手順では、2台のマシンを例に使用し、それぞれのIPを`${ip1}`および`${ip2}`と表記します。これらの操作はDockerコンテナ内で実行されます。

まず、各マシンでコンテナ間のパスワードなしSSHを設定します。

```sh
ssh-keygen			# パスワードなしログイン用のid_rsaおよびid_rsa.pubを生成
ssh-keygen -t rsa -A    # 後でSSHリッスンを開始するための/etc/ssh/ssh_host_rsa_keyおよびssh_host_ecdsa_keyを生成
/usr/sbin/sshd -p 36005 -o ListenAddress=0.0.0.0        # SSHリッスンを開始
echo "Port 36005" > ~/.ssh/config   # SSH接続ポートを36005に変更
passwd root    # ルートパスワードを設定して、監視プラットフォームからのアラートを回避
```

注意：ここでの`36005`は例です。任意のポートを選択できますが、そのポートが**開いている**ことと**他のプロセスによって占有されていない**ことを確認してください。

次に、各マシンのコンテナ内で以下を実行します：

```sh
cat ~/.ssh/id_rsa.pub
```

**出力されたSSH公開鍵をコピーし、`~/.ssh/authorized_keys`ファイルに貼り付けます。各行に1つの公開鍵を記載し、すべてのマシンでこの操作を行います。**最終的に、各マシンの`~/.ssh/authorized_keys`ファイルの内容は一致し、すべてのマシンの公開鍵が含まれている必要があります。

注意：マルチノードトレーニング中、各ノードで実行されるコードは一貫している必要があります。共有ネットワークドライブをマウントすることをお勧めします。共有ネットワークドライブをマウントできない場合は、データセット、スクリプト、およびコードを手動で複数のマシンの同じディレクトリにコピーする必要があります。

##### 複数マシンでのトレーニングの開始

準備手順が完了し、依存関係がインストールされていることを確認したら（インストールされていない場合は、`pip install -r requirements.txt`を実行してインストール）、`train.sh`の冒頭に以下の設定を追加します：

```shell
export HOST_GPU_NUM=8
# 現在のマシンのIP
export LOCAL_IP=${ip1}
# 複数ノードのマシンIP、カンマで区切る
export NODE_IP_LIST="${ip1}:8,${ip2}:8"
# マシンノードの数
export NODES=2
export NODE_NUM=$((${NODES} * ${HOST_GPU_NUM}))
```

注意：上記の`${ip1}`および`${ip2}`を実際のIPアドレスに置き換えてください！

次に、`${ip1}`のマシンで、`train/`ディレクトリで`bash train.sh`を実行します。最初の実行時には、以下の出力が表示される場合があります：

```ssh
The authenticity of host '[ip]:36005 ([ip]:36005)' can't be established.
ECDSA key fingerprint is xxxxxx.
ECDSA key fingerprint is MD5:xxxxxx.
Are you sure you want to continue connecting (yes/no)?
```

この時点で`yes`と入力して続行します。

##### 重要なパラメータ

スクリプト内の重要なパラメータは以下の通りです：

- `--deepspeed`: このパラメータはDeepSpeedの設定ファイルを指す必要があります。`train`フォルダには3つのデフォルトのDeepSpeed設定ファイルが提供されています：`ds_zero2_no_offload.json`、`ds_zero3_no_offload.json`、`ds_zero3_offload.json`。これらの設定ファイルは必要なGPUメモリが順に減少します。
- `--model_name_or_path`: HF事前トレーニングモデルの重みをロードするパス。このパスには`modeling_hunyuan.py`および`configuration_hunyuan.py`ファイルが含まれている必要があります。そうでない場合、ロードできません。
- `--tokenizer_name_or_path`: トークナイザーフォルダのパス。このパスには`tokenization_hy.py`ファイルが含まれている必要があります。そうでない場合、ロードできません。
- `--train_data_file`: トレーニングファイルのパス。JSONLファイルである必要があります。
- `--output_dir`: 出力ディレクトリ。ログ、テンソルボードファイル、およびモデルの重みがこのパスに保存されます。
- `--per_device_train_batch_size`: 各GPUのバッチサイズ。
- `--gradient_accumulation_steps`: 勾配累積ステップ数。グローバルバッチサイズは`per_device_train_batch_size * gradient_accumulation_steps * dp_size`です。
- `--max_steps`: トレーニングの総ステップ数。
- `--save_steps`: チェックポイントを保存するステップ数。
- `--use_lora`: LoRAを使用してトレーニングするかどうか。このパラメータは`--lora_rank`、`--lora_alpha`、および`--lora_dropout`パラメータも受け入れます。LoRAはデフォルトで「q_proj」、「k_proj」、「v_proj」、「o_proj」パラメータに適用されます。これを変更する必要がある場合は、コード内で変更してください。注意：**LoRAを使用してトレーニングする場合、保存されるのはLoRAの重みのみであり、ベースモデルの重みは保存されません**。LoRAの重みをマージする必要がある場合は、以下の「LoRAの重みのマージ」セクションを参照してください。
- `--make_moe_param_leaf_module`: zero3およびMoEトレーニングを使用する場合、MoEモジュールをリーフモジュールとして扱い、そのパラメータはzero3によって分割されません。このオプションはメモリ使用量を大幅に増加させると予想されます。
- `--gradient_checkpointing`: 勾配チェックポイントを有効にします。
- `--train_attention_params_only`: アテンションパラメータのみをトレーニングするかどうか。
- `--learning_rate`: トレーニング中の最大学習率。
- `--min_lr`: トレーニング中の最小学習率。
- `--use_flash_attn`: フラッシュアテンションを使用してトレーニングを高速化します。

**注意：**

- 以前に保存されたチェックポイントからトレーニングを続行する場合、事前トレーニングされた重みをロードするのではなく、`--resume_from_checkpoint`を以前のトレーニングで保存されたチェックポイントのパスに指定します。`--model_name_or_path`を指定しないでください。これにより、重みのみがロードされ、トレーニング状態はロードされません。
- チェックポイントからトレーニングを続行する場合、いくつかの非決定論的アルゴリズムによるランダム性のために、損失にわずかな偏差が生じることがあります。これは正常な現象です。参照：[HuggingFace Transformers Trainer Randomness](https://huggingface.co/docs/transformers/main/en/perf_train_gpu_one#randomness)
- `--model_name_or_path`が有効な場合、すべてのモデル関連のパラメータは無視されます。
- バッチ内のサンプルは、バッチ内の最長のサンプルに合わせてパディングされ、各サンプルの長さは最大`max_seq_length`です。超過部分は切り捨てられます。
- バイアス重みがロードされていないという警告が表示された場合、無視してかまいません。Hunyuan-Largeではバイアスは使用されません。

#### メモリ不足の場合の対処方法

参照：[DeepSpeed Configuration](https://www.deepspeed.ai/docs/config-json/)

DeepSpeedの設定を変更して、以下のパラメータのauto属性を削除し、値を小さくしてみてください：

- `stage3_param_persistence_threshold`
- `stage3_prefetch_bucket_size`
- `stage3_max_reuse_distance`
- `stage3_max_reuse_distance`

#### LoRAモデルのマージ

保存されたLoRAの重みは、トレーニング中にzero3モデルにマージすることはできません。zero3が有効な場合、モデルの重みは異なるデータ並列ランクに分割されるためです。LoRAの重みをベースモデルにマージする場合、オフラインでマージしてマージされた重みファイルを取得できます。`merge_lora_weight.sh`を実行して、LoRAの重みとベースモデルの重みをマージします。パラメータは以下の通りです：

- `--base_model_path`: ベースモデルの重みのディレクトリ
- `--adapter_model_path`: LoRAの重みのディレクトリ
- `--output_path`: マージされた重みを保存するディレクトリ
- `--save_dtype`: マージされた重みを保存するデータ形式。選択肢：fp16、bf16、fp32

&nbsp;

## 推論とデプロイ

HunyuanLLMは、TRT-LLMとvLLMの2つのデプロイ方法をサポートしています。今回は[vLLMバックエンド](https://github.com/quinnrong94/vllm/tree/dev_hunyuan)のデプロイ方法をオープンソース化し、TRT-LLMのデプロイ方法は近日中に公開予定です。

## TRT-LLMを使用した推論

近日公開予定

## vLLMを使用した推論

### Docker:

デプロイプロセスを簡素化するために、HunyuanLLMは事前構築されたDockerイメージを提供しています：

 [hunyuaninfer/hunyuan-large](https://hub.docker.com/repository/docker/hunyuaninfer/hunyuan-large/general) 。モデルファイルをダウンロードし、以下のコードを使用してDockerコンテナを起動するだけで、モデルの推論を開始できます。

```shell
docker run --name hunyuanLLM_infer -itd --privileged --user root --net=host --ipc=host --gpus=8 hunyuaninfer/hunyuan-large:infer-open-source
```

注意：Dockerコンテナの特権モード（`--privileged`）を使用してコンテナを起動すると、コンテナに高い権限が付与され、データ漏洩やクラスターのセキュリティリスクが増加します。特権モードの使用は必要な場合を除いて避けることをお勧めします。特権モードが必要な場合は、徹底的なセキュリティ評価を行い、適切なセキュリティ監視と強化対策を実施してください。

### マシン間のパスワードなしSSHログインの設定

以下の手順では、2台のマシンを例に使用し、それぞれのIPを`${ip1}`および`${ip2}`と表記します。これらの操作はDockerコンテナ内で実行されます。

まず、両方のマシンで`passwd`を実行してパスワードを設定します。例：`Tmp123,./`

`inference/login_ssh.py`をコンテナにコピーし、以下のコマンドを実行します。IPとパスワードが正しく入力されていることを確認してください。

```shell
python3 login_ssh.py --ips ${ip1},${ip2} --port 36000 --password=Tmp123,./
```

**注意📢：開始前に、VLLMのデバッグスクリプトを使用してマルチマシン通信を確認してください：https://docs.vllm.ai/en/latest/getting_started/debugging.html**

### BF16デプロイ

BF16は16枚のH800またはH20 GPUを必要とします。マルチマシン通信が正しいことを確認した後、以下の手順を実行します：

コマンドを実行する前に、以下の環境変数を設定します：

```shell
${LOCAL_IP}: 現在のマシンのbond1に対応するIP
${MODEL_PATH}: Hunyuan LLMモデルのパス
```

#### ステップ1：Rayの起動

Rayは、並列および分散Pythonのオープンソースライブラリです。このセクションでは、Rayを使用してマルチマシン通信を実現します。

Rayコンポーネントの設定強化：Rayコンポーネントのデフォルト設定では、サービスポート（例：6379、8265）に認証メカニズムが有効になっておらず、未承認アクセスやコマンド実行のリスクがあります。Rayコンポーネントを信頼できる内部ネットワーク環境でのみデプロイするか、これらのポートに対して厳格なアクセス制御リスト（ACL）ポリシーを実施して、未承認のネットワークアクセスを防止することをお勧めします。

まず、各ノードでRayを起動します（バックグラウンドで起動するか、ターミナルを保持して実行します）：

ヘッドノードで：
```shell
export VLLM_HOST_IP=${LOCAL_IP}
export NCCL_SOCKET_IFNAME=bond1
export GLOO_SOCKET_IFNAME=bond1
ray start --block --head --node-ip-address=${LOCAL_IP} --port=6379
```

すべてのワーカーノードで：

注意：{ヘッドノード$LOCAL_IP}をヘッドノードの実際の${LOCAL_IP}に置き換えます。
```shell
export VLLM_HOST_IP=${LOCAL_IP}
export NCCL_SOCKET_IFNAME=bond1
export GLOO_SOCKET_IFNAME=bond1
ray start --block --address={ヘッドノード$LOCAL_IP}:6379 --node-ip-address=${LOCAL_IP}
```
Rayの起動に失敗した場合、`ray stop`を実行してから再度上記のコマンドを実行します。

#### ステップ2：推論の実行

#### 方法1：コマンドライン推論

以下は、`vLLM`を使用してチャットモデルにリクエストを送信するコードスニペットです：

注意：vLLMコンポーネントのリモートコード実行保護。以下のコードでは、vLLMコンポーネントの`trust-remote-code`設定オプションが有効になっている場合、リモートモデルリポジトリからコードをロードして実行することが許可され、悪意のあるコードの実行につながる可能性があります。ビジネスニーズが明確に要求しない限り、この設定オプションを無効にしておくことをお勧めします。

```python
import os
from vllm import LLM, SamplingParams

model_path=os.environ.get('MODEL_PATH')

llm = LLM(model=model_path,
        tokenizer=model_path,
        trust_remote_code=True,
        max_model_len=10240,
        dtype='bfloat16',
        tensor_parallel_size=16,
        pipeline_parallel_size=1,
        disable_log_stats=False,
        gpu_memory_utilization=0.98,
        disable_custom_all_reduce=True,
        #distributed_executor_backend='ray',
        enforce_eager=True,
        max_num_seqs=8,
        use_v2_block_manager=True,
        quantization=None)

prompts = ["海水はなぜ塩辛いのですか？"]

sampling_params = SamplingParams(
    temperature=0.7, top_p=0.6, max_tokens=200, top_k=20, repetition_penalty=1.05)

outputs = llm.generate(prompts, sampling_params)

# 出力を表示
for output in outputs:
    prompt = output.prompt
    generated_text = output.outputs[0].text
    print(f"Prompt: {prompt!r}, Generated text: {generated_text!r}")
``

#### 方法2: サービスベースの推論

以下では、`vLLM` を使ってモデルをサービスベースでデプロイし、リクエストを行う方法を示します。

ヘッドノードで以下を実行する:

```shell
export VLLM_HOST_IP=${LOCAL_IP}
export NCCL_SOCKET_IFNAME=bond1
export GLOO_SOCKET_IFNAME=bond1
```

次に、以下を実行してサービスを開始します:

```shell
cd inference
sh run_server.sh
```

*Tips*: 以下のエラーが発生した場合のトラブルシューティング:

```python
ray.exceptions.RaySystemError: System error: No module named 'transformers_modules' traceback: Traceback (most recent call last):
ModuleNotFoundError: No module named 'transformers_modules'
```

ヘッドノードから `~/.cache/huggingface/modules/` ディレクトリをすべてのワーカーノードの対応するパスにコピーする。

`run_server.sh` の実行に成功したら、リクエストスクリプトを実行する:

```shell
sh openapi.sh
```

`openapi.sh` の `${LOCAL_IP}` と `${MODEL_PATH}` を、対応するサービスと同じ値に変更してください。


### 量子化モデルのデプロイ:

このセクションでは、vLLM を使用して量子化モデルを展開するプロセスについて説明します。

イメージ: デプロイイメージはBF16と同じです。

#### Int8 量子化モデルのデプロイ:

Int8-weight-only バージョンの Hunyuan-L モデルをデプロイするには、`run_server_int8.sh` で環境変数を設定するだけです:

```shell
${MODEL_PATH}: BF16 モデルへのパス
${LOCAL_IP}: 現在のマシンの bond1 に対応する IP
```

次に、以下を実行して Int8 サービスを開始します:

```shell
sh run_server_int8.sh
```

run_server_int8.sh`の実行に成功したら、リクエストスクリプトを実行する:

```shell
sh openapi.sh
```

#### FP8 量子化モデルのデプロイ:

W8A8C8 バージョンの Hunyuan-L モデルをデプロイするには、`run_server_fp8.sh` で環境変数を設定するだけです:

```shell
${MODEL_PATH}: FP8 モデルへのパス
${LOCAL_IP}: 現在のマシンの bond1 に対応する IP
```

次に、FP8サービスを開始します:

```shell
sh run_server_fp8.sh
```

`run_server_fp8.sh` の実行に成功したら、リクエストスクリプトを実行する:

```shell
sh openapi.sh
```

#### FP8 BENCHMARK

このパートでは、Hunyuan Large Instruct のベンチマークFP8定量モデルを紹介します。

| Dataset | BF16 | W8A8C8-FP8 |
|---------|------|------------|
| ARC-C   | 94.6 | 94.2       |
| C-Eval  | 88.6 | 89.2       |
| CMMLU   | 90.4 | 89.8       |
| MMLU    | 89.9 | 88.9       |

### 推論性能

本節では、vLLMを用いて様々なモデル（オリジナルと量子化）を導入した際の効率性テストの結果を、異なるバッチサイズ下での推論速度（トークン/秒）を含めて示す。

| 推論フレームワーク      | モデル                                                                                                  | GPU数 (H20)         | input_length | batch=1 | batch=4 |
| ------------------- | ------------------------------------------------------------------------------------------------------ | -------------------- | ------------ |---------|---------|
| vLLM                | Hunyuan-Large                                                                                              | 16                   | 2048         | 20.2    | 75.5    |
| vLLM                | Hunyuan-Large(int8 weight only)                                                                            | 8                    | 2048         | 19.3    | 73.6    |
| vLLM                | Hunyuan-Large(W8A8C8-FP8)                                                                                  | 8                    | 2048         | 19.8    | 74.9    |

## トークナイザー

HunYuan-Large モデルで使用されているトークナイザーは、圧縮率と有効性のバランスをとり、埋め込みが十分に学習されるようにしている。語彙にはtiktokenから統合された10万トークンが含まれています。さらに、モデルの中国語能力とトークナイザーの圧縮率を向上させるために、大量の高品質な中国語学習データを使用して、29Kの中国語トークンを追加学習しました。この新しいトークナイザーを組み合わせると、LLaMA3トークナイザーと比較して圧縮率が向上し、2.78文字/トークンから3.13文字/トークンに増加しました。

## Hunyuan API

TencentクラウドでHunyuan-Largeモデルを体験できます。詳細は: https://cloud.tencent.com/document/product/1729/97730 。

## インタラクティブデモ Web

Hunyuan-Large のウェブデモがオープンしました。https://huggingface.co/spaces/tencent/Hunyuan-Large にアクセスして、当社のモデルを簡単に体験してください。

## TIでのトレーニング/推論
Tencent Cloud の [TI Platform](https://cloud.tencent.com/product/ti) は、AI エンジニアのために作られた包括的な機械学習プラットフォームです。Hunyuan-Large モデルがすでに統合されているため、わずか数ステップで簡単にトレーニングし、展開することができます。 [Chat with Hunyuan-Large](https://console.cloud.tencent.com/tione/v2/aimarket/detail/hunyuan_series?PublicAlgoGroupId=hunyuan-large-chat&detailTab=demo) にアクセスして、モデルとのリアルタイムの会話を体験してください、また [Hunyuan-Large Best Practice on TI](https://cloud.tencent.com/document/product/851/112032) を参照して、カスタマイズした Hunyuan-Large モデルを作成してください。


## 引用
私たちの仕事が役に立ったと思ったら、遠慮なく引用してください。

```
@misc{sun2024hunyuanlargeopensourcemoemodel,
      title={Hunyuan-Large: An Open-Source MoE Model with 52 Billion Activated Parameters by Tencent},
      author={Xingwu Sun and Yanfeng Chen and Yiqing Huang and Ruobing Xie and Jiaqi Zhu and Kai Zhang and Shuaipeng Li and Zhen Yang and Jonny Han and Xiaobo Shu and Jiahao Bu and Zhongzhi Chen and Xuemeng Huang and Fengzong Lian and Saiyong Yang and Jianfeng Yan and Yuyuan Zeng and Xiaoqin Ren and Chao Yu and Lulu Wu and Yue Mao and Tao Yang and Suncong Zheng and Kan Wu and Dian Jiao and Jinbao Xue and Xipeng Zhang and Decheng Wu and Kai Liu and Dengpeng Wu and Guanghui Xu and Shaohua Chen and Shuang Chen and Xiao Feng and Yigeng Hong and Junqiang Zheng and Chengcheng Xu and Zongwei Li and Xiong Kuang and Jianglu Hu and Yiqi Chen and Yuchi Deng and Guiyang Li and Ao Liu and Chenchen Zhang and Shihui Hu and Zilong Zhao and Zifan Wu and Yao Ding and Weichao Wang and Han Liu and Roberts Wang and Hao Fei and Peijie She and Ze Zhao and Xun Cao and Hai Wang and Fusheng Xiang and Mengyuan Huang and Zhiyuan Xiong and Bin Hu and Xuebin Hou and Lei Jiang and Jiajia Wu and Yaping Deng and Yi Shen and Qian Wang and Weijie Liu and Jie Liu and Meng Chen and Liang Dong and Weiwen Jia and Hu Chen and Feifei Liu and Rui Yuan and Huilin Xu and Zhenxiang Yan and Tengfei Cao and Zhichao Hu and Xinhua Feng and Dong Du and Tinghao She and Yangyu Tao and Feng Zhang and Jianchen Zhu and Chengzhong Xu and Xirui Li and Chong Zha and Wen Ouyang and Yinben Xia and Xiang Li and Zekun He and Rongpeng Chen and Jiawei Song and Ruibin Chen and Fan Jiang and Chongqing Zhao and Bo Wang and Hao Gong and Rong Gan and Winston Hu and Zhanhui Kang and Yong Yang and Yuhong Liu and Di Wang and Jie Jiang},
      year={2024},
      eprint={2411.02265},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2411.02265}, ￥
}
```
<br>

## お問い合わせ

私たちの研究開発チームや製品チームにメッセージを残したい場合は、私たちのオープンソースチームにご連絡ください。また、電子メール (hunyuan_opensource@tencent.com) でもお問い合わせいただけます。


