<p align="left">
    <a href="README_CN.md">中文</a>&nbsp ｜ English</a>
</p>
<br><br>

<p align="center">
 <img src="https://dscache.tencent-cloud.cn/upload/uploader/hunyuan-64b418fd052c033b228e04bc77bbc4b54fd7f5bc.png" width="400"/> <br>
</p><p></p>

<p align="center">
    🫣&nbsp<a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large"><b>Hugging Face</b></a>&nbsp&nbsp |  &nbsp&nbsp🖥️&nbsp&nbsp<a href="https://llm.hunyuan.tencent.com/" style="color: red;"><b>official website</b></a>&nbsp&nbsp｜&nbsp&nbsp🕖&nbsp&nbsp <a href="https://cloud.tencent.com/product/hunyuan" ><b>HunyuanAPI</b></a>&nbsp&nbsp｜&nbsp&nbsp🐳&nbsp&nbsp <a href="https://gitee.com/Tencent/Tencent-Hunyuan-Large" ><b>Gitee</b></a>
</p><p align="center">
    <a href="https://arxiv.org/abs/2411.02265" style="color: red;"><b>Technical Report</b></a>&nbsp&nbsp｜&nbsp&nbsp <a href="https://huggingface.co/spaces/tencent/Hunyuan-Large"><b>Demo</b></a>&nbsp&nbsp&nbsp｜&nbsp&nbsp <a href="https://cloud.tencent.com/document/product/851/112032" style="color: red;"><b>Tencent Cloud TI</b></a>&nbsp&nbsp&nbsp</p>
<p><br></p>
<p>
    <table align="center">
        <tbody>
            <tr>
                <td align="center" colspan="3"><strong>Download Models</strong></td>
            </tr>
            <tr>
                <td align="center" style="width: 100px;" >Models</td>
                <td align="center" style="width: 500px;">Huggingface Download URL</td>
                <td align="center" style="width: 500px;">Tencent Cloud Download URL</td>
            </tr>
            <tr>
                <td style="width: 100px;">Hunyuan-A52B-Instruct-FP8</td>
                <td style="width: 500px;"><a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large/tree/main/Hunyuan-A52B-Instruct-FP8" style="color: red;">Hunyuan-A52B-Instruct-FP8</a></td>
                <td style="width: 500px;"><a href="https://cdn-large-model.hunyuan.tencent.com/Hunyuan-A52B-Instruct-128k-fp8-20241116.zip" style="color: red;">Hunyuan-A52B-Instruct-FP8</a></td>
            </tr>
            <tr>
                <td style="width: 100px;">Hunyuan-A52B-Instruct</td>
                <td style="width: 500px;"><a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large/tree/main/Hunyuan-A52B-Instruct" style="color: red;">Hunyuan-A52B-Instruct</a></td>
                <td style="width: 500px;"><a href="https://cdn-large-model.hunyuan.tencent.com/Hunyuan-A52B-Instruct-128k-20241116.zip" style="color: red;">Hunyuan-A52B-Instruct</a></td>
            </tr>
            <tr>
                <td style="width: 100px;">Hunyuan-A52B-Pretrain</td>
                <td style="width: 500px;"><a href="https://huggingface.co/tencent/Tencent-Hunyuan-Large/tree/main/Hunyuan-A52B-Pretrain" style="color: red;">Hunyuan-A52B-Pretrain</a></td>
                <td style="width: 500px;"><a href="https://cdn-large-model.hunyuan.tencent.com/Hunyuan-A52B-Pretrain-256k.zip" style="color: red;">Hunyuan-A52B-Pretrain</a></td>
            </tr>
        </tbody>
    </table>
</p>

<p></p>


## Model Introduction

With the rapid development of artificial intelligence technology, large language models (LLMs) have made significant progress in fields such as natural language processing, computer vision, and scientific tasks. However, as the scale of these models increases, optimizing resource consumption while maintaining high performance has become a key challenge. To address this challenge, we have explored Mixture of Experts (MoE) models. The currently unveiled Hunyuan-Large (Hunyuan-MoE-A52B) model is the largest open-source Transformer-based MoE model in the industry, featuring a total of 389 billion parameters and 52 billion active parameters. This is currently the largest open-source Transformer-based MoE model in the industry, featuring a total of 389 billion parameters and 52 billion active parameters. 

By open-sourcing the Hunyuan-Large model and revealing related technical details, we hope to inspire more researchers with innovative ideas and collectively advance the progress and application of AI technology. We welcome you to join our open-source community to explore and optimize future AI models together!
 
### Introduction to Technical Advantages

#### Model
- **High-Quality Synthetic Data**: By enhancing training with synthetic data, Hunyuan-Large can learn richer representations, handle long-context inputs, and generalize better to unseen data.

- **KV Cache Compression**: Utilizes Grouped Query Attention (GQA) and Cross-Layer Attention (CLA) strategies to significantly reduce memory usage and computational overhead of KV caches, improving inference throughput.

- **Expert-Specific Learning Rate Scaling**: Sets different learning rates for different experts to ensure each sub-model effectively learns from the data and contributes to overall performance.

- **Long-Context Processing Capability**: The pre-trained model supports text sequences up to 256K, and the Instruct model supports up to 128K, significantly enhancing the ability to handle long-context tasks.

- **Extensive Benchmarking**: Conducts extensive experiments across various languages and tasks to validate the practical effectiveness and safety of Hunyuan-Large.

#### Inference Framework
- This open-source release offers two inference backend options tailored for the Hunyuan-Large model: the popular [vLLM-backend](https://github.com/quinnrong94/vllm/tree/dev_hunyuan) and the TensorRT-LLM Backend. Both solutions include optimizations for enhanced performance. For instance, the introduction of a new CLA structure significantly reduces GPU memory usage, achieving a 50% savings in the KV-Cache portion, which ensures efficient handling of long text scenarios. Additionally, by employing FP8 quantization, we achieve a 50% reduction in memory usage compared to traditional FP16/BF16 quantization, while maintaining precision and resulting in a 70% increase in throughput. Meanwhile, by leveraging the efficient operators at the core of TRT-LLM, the performance of the TRT-LLM solution surpasses that of vLLM by over 30%. The TRT-LLM solution is widely used in Tencent's Hunyuan project. In this release, we are initially open-sourcing the vLLM solution, with plans to release the TRT-LLM solution in the near future.

#### Training Framework

- The Hunyuan-Large open-source model is fully compatible with the Hugging Face format, enabling researchers and developers to perform model fine-tuning using the hf-deepspeed framework. Additionally, we support training acceleration through the use of flash attention. To further assist in the adoption process, we have made the corresponding training scripts and model implementations publicly available to the community through this release, facilitating subsequent model training and fine-tuning operations based on these resources.

&nbsp;

## Related News
* 2024.11.25 Our self-developed long-context benchmark, i.e., PenguinScrolls, has been officially released! You can explore the project on [GitHub](https://github.com/Penguin-Scrolls/PenguinScrolls) and access the dataset on [Hugging Face](https://huggingface.co/datasets/Penguin-Scrolls/PenguinScrolls).
* 2024.11.18 **Hunyuan-A52B-Instruct** and **Hunyuan-A52B-Instruct-FP8** model update. 
* 2024.11.5 [TI Platform](https://cloud.tencent.com/product/ti) has integrated Hunyuan-Large model already, you can easily train and deploy it in just a few steps. Visit [Chat with Hunyuan-Large](https://console.cloud.tencent.com/tione/v2/aimarket/detail/hunyuan_series?PublicAlgoGroupId=hunyuan-large-chat&detailTab=demo) to experience real-time conversations with the model, and explore [Hunyuan-Large Best Practice on TI](https://cloud.tencent.com/document/product/851/112032) to create your own customized Hunyuan-Large model. 
* 2024.11.5 We have open-sourced **Hunyuan-A52B-Pretrain**, **Hunyuan-A52B-Instruct**, and **Hunyuan-A52B-Instruct-FP8** on Hugging Face. We also released a technical report and a training and inference operations manual, providing detailed information on the model's capabilities and the procedures for training and inference.




## Benchmark Evaluation
**Hunyuan-Large pre-trained model** achieves the best overall performance compared to both Dense and MoE based 
competitors having similar activated parameter sizes.  For aggregated benchmarks such as MMLU, MMLU-Pro, and CMMLU, 
Hunyuan-Large consistently achieves the best performance, confirming its comprehensive abilities on aggregated tasks.
Hunyuan-Large also shows superior performance in commonsense understanding and reasoning, and classical NLP tasks 
such as QA and reading comprehension tasks (e.g., CommonsenseQA, PIQA and TriviaQA).  
For the mathematics capability, Hunyuan-Large outperforms all baselines in math datasets of GSM8K and MATH, 
and also gains the best results on CMATH in Chinese.We also observe that Hunyuan-Large achieves the overall 
best performance in all Chinese tasks (e.g., CMMLU, C-Eval).

| Model            | LLama3.1-405B | LLama3.1-70B | Mixtral-8x22B | DeepSeek-V2 | Hunyuan-Large |
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

**Hunyuan-Large-Instruct** achieves consistent improvements on most types of tasks compared to LLMs having similar 
activated parameters, indicating the effectiveness of our post-training.    Delving into the model performance 
in different categories of benchmarks, we find that our instruct model achieves the best performance on MMLU and MATH dataset.  
Notably, on the MMLU dataset, our model demonstrates a significant improvement, outperforming the LLama3.1-405B model by 2.6%.   
This enhancement is not just marginal but indicative of the Hunyuan-Large-Instruct’s superior understanding and reasoning 
capabilities across a wide array of language understanding tasks. The model’s prowess is further underscored in its performance 
on the MATH dataset, where it surpasses the LLama3.1-405B by a notable margin of 3.6%.  
Remarkably, this leap in accuracy is achieved with only 52 billion activated parameters, underscoring the efficiency of our model.

| Model                | LLama3.1 405B Inst. | LLama3.1 70B Inst. | Mixtral 8x22B Inst. | DeepSeekV2.5 Chat | Hunyuan-Large Inst. |
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

## Data

Hunyuan-Large provides model training-related processes. In this section, you can process the training data format for use in model training.

### Training Data Format and Processing

Training data is processed into a messages format as follows. The default system prompt for training and inference is "You are a helpful assistant." Below are examples of single-turn and multi-turn data:


```python
# Single-Turn Data Format

messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "海水为什么是咸的" },
    {"role": "assistant", "content": "海水是咸的主要是因为其中含有许多溶解在水中的盐类和矿物质。这些盐类和矿物质来自于地球表面的岩石和土壤中的化学物质，随着时间的推移，它们被带到了海洋中。当海水蒸发时，水分蒸发掉了，但盐类和矿物质仍然留在水中，导致海水变得更加咸味。因此，海水的咸度是由其中的盐类和矿物质的含量决定的。"}
]

# Multi-Turn Data Format
messages = [
    {"role": "system", "content": "You are a helpful assistant."},
    {"role": "user", "content": "知道重庆森林这部电影吗？" },
    {"role": "assistant", "content": "知道呀，是一部由王家卫导演的片子。" },
    {"role": "user", "content": " 而主演里更是有王菲，一上映便受到追捧。" },
    {"role": "assistant", "content": "所以此片获得了第14届香港电影金像奖最佳影片奖。"}
]

from tokenizers import ByteLevelBPETokenizer
from transformers import AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("./models", use_fast=False, trust_remote_code=True)

ids = tokenizer.apply_chat_template(messages)

```



For more usage references, see the `./models/test.py` file.

&nbsp;

## Quick Start

You can quickly get started by referring to the content in the <a href="examples/README.md">Quick Start Guide</a>.

## Model Training

To simplify the Training process, HunyuanLLM provides a pre-built Docker image:

 [hunyuaninfer/hunyuan-large](https://hub.docker.com/repository/docker/hunyuaninfer/hunyuan-large/general). 

### Hardware Requirements

Tested on H20, without enabling `make_moe_param_leaf_module` and using `zero3+offload`, with a `max_seq_length` of 2048, full fine-tuning requires at least 32 GPUs, and LoRA fine-tuning requires at least 8 GPUs.

### Training Performance

With the minimum configuration (8 GPUs for LoRA fine-tuning), `per_device_train_batch_size` is set to 1, and `gradient_accumulation_steps` is set to 1, resulting in approximately 35 seconds per iteration.

### Launch Method

Refer to: [HuggingFace Transformers Trainer](https://huggingface.co/docs/transformers/v4.19.2/en/main_classes/trainer)

#### Single-Machine Training

In the `train` directory, execute:

```sh
pip install -r requirements.txt
bash train.sh
```

#### Multi-Machine Training

To start training on multiple machines, follow the steps below and ensure that all machines are within the same cluster.

##### Configure Passwordless SSH Login Between Machines

The following steps use two machines as an example, with their IPs represented as `${ip1}` and `${ip2}`. These operations are performed within a Docker container.

First, configure passwordless SSH between containers on each machine.


```sh
ssh-keygen			# Generate id_rsa and id_rsa.pub for passwordless login
ssh-keygen -t rsa -A    # Generate /etc/ssh/ssh_host_rsa_key and ssh_host_ecdsa_key for starting 'SSH listen' later
/usr/sbin/sshd -p 36005 -o ListenAddress=0.0.0.0        # Start SSH listen
echo "Port 36005" > ~/.ssh/config   # Change SSH connection port to 36005
passwd root    # Set root password to avoid alerts from monitoring platforms
```


Note: The `36005` here is an example. You can choose any port, but ensure that the port is **open** and **not occupied by other processes**.

Next, within the container on each machine, execute:

```sh
cat ~/.ssh/id_rsa.pub
```

**Copy the output SSH public key and paste it into the `~/.ssh/authorized_keys` file, with one public key per line. This must be done on every machine.** Ultimately, the `~/.ssh/authorized_keys` file on each machine should be identical and contain the public keys of all machines.

It's important to note that during multi-node training, the code executed on each node must be consistent. It is recommended to mount a shared network drive. If mounting a shared drive is not possible, you need to manually copy the dataset, scripts, and code to the same directory on all machines.

##### Start Multi-Machine Training

Once the preparation steps are completed and dependencies are confirmed to be installed (if not, execute `pip install -r requirements.txt` to install), you can add the following configuration at the beginning of `train.sh`:

```shell
export HOST_GPU_NUM=8
# Current machine IP
export LOCAL_IP=${ip1}
# Multi-node machine IPs, separated by commas
export NODE_IP_LIST="${ip1}:8,${ip2}:8"
# Number of machine nodes
export NODES=2
export NODE_NUM=$((${NODES} * ${HOST_GPU_NUM}))
```

Note: Replace `${ip1}` and `${ip2}` with the actual IP addresses!

Then, on the machine with `${ip1}`, execute `bash train.sh` in the `train/` directory. Note that on the first run, you might see the following output:

```ssh
The authenticity of host '[ip]:36005 ([ip]:36005)' can't be established.
ECDSA key fingerprint is xxxxxx.
ECDSA key fingerprint is MD5:xxxxxx.
Are you sure you want to continue connecting (yes/no)?
```

At this point, type `yes` to continue.

##### Key Parameters

The key parameters in the script are as follows:

- `--deepspeed`: This parameter should point to a DeepSpeed configuration file. The `train` folder provides three default DeepSpeed configuration files: `ds_zero2_no_offload.json`, `ds_zero3_no_offload.json`, `ds_zero3_offload.json`. The required GPU memory decreases in this order.
- `--model_name_or_path`: The path to the HF pre-trained model. Ensure this path contains the `modeling_hunyuan.py` and `configuration_hunyuan.py` files; otherwise, it cannot be loaded.
- `--tokenizer_name_or_path`: The path to the tokenizer folder. Ensure this path contains the `tokenization_hy.py` file; otherwise, it cannot be loaded.
- `--train_data_file`: The path to the training file, which should be a JSONL file.
- `--output_dir`: The output directory where logs, tensorboard files, and model weights will be stored.
- `--per_device_train_batch_size`: The batch size per GPU.
- `--gradient_accumulation_steps`: The number of gradient accumulation steps. The global batch size is `per_device_train_batch_size * gradient_accumulation_steps * dp_size`.
- `--max_steps`: The total number of training steps.
- `--save_steps`: The number of steps between saving checkpoints.
- `--use_lora`: Whether to use LoRA for training. This also accepts `--lora_rank`, `--lora_alpha`, and `--lora_dropout` parameters. LoRA is applied by default to the 'q_proj', 'k_proj', 'v_proj', 'o_proj' parameters. If you need to change this, modify it in the code. Note: **When using LoRA for training, only the LoRA weights are saved, not the base model weights**. If you need to merge LoRA weights, see the "LoRA Weight Merging" section below.
- `--make_moe_param_leaf_module`: When using zero3 and MoE training, treat the MoE module as a leaf module, meaning its parameters are not split by zero3. This option is expected to significantly increase memory usage.
- `--gradient_checkpointing`: Enable gradient checkpointing.
- `--train_attention_params_only`: Whether to train only the attention parameters.
- `--learning_rate`: The maximum learning rate during training.
- `--min_lr`: The minimum learning rate during training.
- `--use_flash_attn`: Enable flash-attention to accelerate training.

**Note:**

- If you want to continue training from a previously saved checkpoint instead of loading pre-trained weights, specify `--resume_from_checkpoint` with the path to the checkpoint from the previous training. Do not specify `--model_name_or_path`, as this will only load the weights and not the training state.
- When continuing training from a checkpoint, there might be slight deviations in loss due to randomness introduced by some non-deterministic algorithms, which is considered normal. Refer to: [HuggingFace Transformers Trainer Randomness](https://huggingface.co/docs/transformers/main/en/perf_train_gpu_one#randomness)
- When `--model_name_or_path` is specified, all model-related parameters will be ignored.
- Samples within a batch will be padded to align with the longest sample in the batch, with each sample having a maximum length of `max_seq_length`. Any excess will be truncated.
- If you encounter warnings about bias weights not being loaded, you can ignore them, as biases are not used in Hunyuan-Large.


#### What to Do If Out of Memory?

Refer to: [DeepSpeed Configuration](https://www.deepspeed.ai/docs/config-json/)

You can try modifying the DeepSpeed configuration by removing the auto attribute from these parameters and reducing their values:

- `stage3_param_persistence_threshold`
- `stage3_prefetch_bucket_size`
- `stage3_max_reuse_distance`
- `stage3_max_reuse_distance`

#### Merging LoRA Models

The saved LoRA weights cannot be merged into the zero3 model during training because, with zero3 enabled, model weights are split across different data parallel ranks. If you want to merge LoRA weights into the base model, you can do so offline to obtain the merged weight file. Execute `merge_lora_weight.sh` to merge the LoRA weights with the base model weights. The parameters include:

- `--base_model_path`: Directory of the base model weights
- `--adapter_model_path`: Directory of the LoRA weights
- `--output_path`: Directory to save the merged weights
- `--save_dtype`: Data format for storing the merged weights, available options include: fp16, bf16, fp32

&nbsp;

## Inference and Deployment

HunyuanLLM uses TRT-LLM and vLLM for deployment. We are open sourcing the [vLLM-backend](https://github.com/quinnrong94/vllm/tree/dev_hunyuan) deployment (see Reasoning with vLLM), and the TRT-LLM deployment (see Reasoning with TRT-LLM) will be available in the near future.

## Using TRT-LLM for Inference

To be opened

## Using vLLM for Inference

### Docker:

To simplify the deployment process, HunyuanLLM provides a pre-built Docker image:

 [hunyuaninfer/hunyuan-large](https://hub.docker.com/repository/docker/hunyuaninfer/hunyuan-large/general). You only need to download the model files and start the Docker container using the code below to begin model inference.

```shell
docker run --name hunyuanLLM_infer -itd --privileged --user root --net=host --ipc=host --gpus=8 hunyuaninfer/hunyuan-large:infer-open-source
```

Note: Docker container privilege management. The above code uses privileged mode (`--privileged`) to start the Docker container, which grants the container higher privileges, increasing the risk of data leakage and cluster security threats. It is recommended to avoid using privileged mode unless necessary to reduce security risks. For scenarios where privileged mode is required, conduct a thorough security assessment and implement appropriate security monitoring and hardening measures.

### Configure Passwordless SSH Login Between Machines

The following steps use two machines as an example, with their IPs represented as `${ip1}` and `${ip2}`. These operations are performed within a Docker container.

First, run `passwd` on both machines to set a password, for example: `Tmp123,./`

Copy `inference/login_ssh.py` into the container and execute the following command, ensuring the IP and password are correctly entered.

```shell
python3 login_ssh.py --ips ${ip1},${ip2} --port 36000 --password=Tmp123,./
```

**Note 📢: Before starting, be sure to verify multi-machine communication using VLLM's debugging script: https://docs.vllm.ai/en/latest/getting_started/debugging.html**

### BF16 Deployment

BF16 requires 16 H20 GPUs for deployment. After verifying that multi-machine communication is correct, execute the following steps:

Before running the commands, set the following environment variables:

```shell
${LOCAL_IP}: The IP corresponding to bond1 on the current machine
${MODEL_PATH}: Path to the Hunyuan LLM model
```

#### Step 1: Start Ray

Ray is an open-source library for parallel and distributed Python. In this section, we use Ray to achieve multi-machine communication.

Ray Component Configuration Hardening: The default configuration of Ray components does not enable authentication mechanisms for service ports (e.g., 6379, 8265), posing risks of unauthorized access and command execution. It is recommended to deploy Ray components only in trusted internal network environments or ensure strict access control list (ACL) policies are implemented for these ports to prevent unauthorized network access.

First, start Ray on each node (either in the background or by keeping the terminal running):

On the head node:
```shell
export VLLM_HOST_IP=${LOCAL_IP}
export NCCL_SOCKET_IFNAME=bond1
export GLOO_SOCKET_IFNAME=bond1
ray start --block --head --node-ip-address=${LOCAL_IP} --port=6379
```

On all worker nodes:

Note: Replace `{HEAD NODE $LOCAL_IP}` with the actual `${LOCAL_IP}` of the head node.
```shell
export VLLM_HOST_IP=${LOCAL_IP}
export NCCL_SOCKET_IFNAME=bond1
export GLOO_SOCKET_IFNAME=bond1
ray start --block --address={HEAD NODE $LOCAL_IP}:6379 --node-ip-address=${LOCAL_IP}
```
If Ray fails to start, execute `ray stop` and then run the above commands again.

#### Step 2: Execute Inference

#### Method 1: Command Line Inference

Below is a code snippet demonstrating how to quickly request the chat model using `vLLM`:

Note: vLLM Component Remote Code Execution Protection. In the code below, if the `trust-remote-code` configuration option of the vLLM component is enabled, it will allow loading and executing code from remote model repositories, which may lead to the execution of malicious code. Unless explicitly required by business needs, it is recommended to keep this configuration option disabled to reduce potential security threats.

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

prompts = ["海水为什么是咸的"]

sampling_params = SamplingParams(
    temperature=0.7, top_p=0.6, max_tokens=200, top_k=20, repetition_penalty=1.05)

outputs = llm.generate(prompts, sampling_params)

# Print the outputs.
for output in outputs:
    prompt = output.prompt
    generated_text = output.outputs[0].text
    print(f"Prompt: {prompt!r}, Generated text: {generated_text!r}")
```

#### Method 2: Service-Based Inference

Below we demonstrate how to deploy the model using `vLLM` in a service-based manner and make requests.

Run the following on the head node:

```shell
export VLLM_HOST_IP=${LOCAL_IP}
export NCCL_SOCKET_IFNAME=bond1
export GLOO_SOCKET_IFNAME=bond1
```

Next, start the service by running:

```shell
cd inference
sh run_server.sh
```

*Tips*: Troubleshooting, if you encounter the following error:

```python
ray.exceptions.RaySystemError: System error: No module named 'transformers_modules' traceback: Traceback (most recent call last):
ModuleNotFoundError: No module named 'transformers_modules'
```

Copy the `~/.cache/huggingface/modules/` directory from the head node to the corresponding path on all worker nodes.

After successfully running `run_server.sh`, execute the request script:

```shell
sh openapi.sh
```

Be sure to modify `${LOCAL_IP}` and `${MODEL_PATH}` in `openapi.sh` to values match the corresponding service.


### Quantized Model Deployment:

This section describes the process of deploying a quantized model using vLLM.

Image: The deployment image is the same as for BF16.

#### Int8 Quantized Model Deployment:

To deploy the Int8-weight-only version of the Hunyuan-L model, simply set the environment variables in `run_server_int8.sh`:

```shell
${MODEL_PATH}: Path to the BF16 model
${LOCAL_IP}: The IP corresponding to bond1 on the current machine
```

Then, start the Int8 service by running:

```shell
sh run_server_int8.sh
```

After successfully running `run_server_int8.sh`, execute the request script:

```shell
sh openapi.sh
```

#### FP8 Quantized Model Deployment:

To deploy the W8A8C8 version of the Hunyuan-L model, simply set the environment variables in `run_server_fp8.sh`:

```shell
${MODEL_PATH}: Path to the FP8 model
${LOCAL_IP}: The IP corresponding to bond1 on the current machine
```

Then, start the FP8 service by running:

```shell
sh run_server_fp8.sh
```

After successfully running `run_server_fp8.sh`, execute the request script:

```shell
sh openapi.sh
```

#### FP8 BENCHMARK

This part introduces the Benchmark of Hunyuan Large Instruct FP8 quantitative model.

| Dataset | BF16 | W8A8C8-FP8 |
|---------|------|------------|
| ARC-C   | 94.6 | 94.2       |
| C-Eval  | 88.6 | 89.2       |
| CMMLU   | 90.4 | 89.8       |
| MMLU    | 89.9 | 88.9       |

### Inference Performance

This section presents the efficiency test results of deploying various models (original and quantized) using vLLM, including inference speed (tokens/s) under different batch sizes.

| Inference Framework | Model                                                                                                  | Number of GPUs (H20) | input_length | batch=1 | batch=4 |
| ------------------- | ------------------------------------------------------------------------------------------------------ | -------------------- | ------------ |---------|---------|
| vLLM                | Hunyuan-Large                                                                                              | 16                   | 2048         | 20.2    | 75.5    |
| vLLM                | Hunyuan-Large(int8 weight only)                                                                            | 8                    | 2048         | 19.3    | 73.6    |
| vLLM                | Hunyuan-Large(W8A8C8-FP8)                                                                                  | 8                    | 2048         | 19.8    | 74.9    |

## Tokenizer

The tokenizer used in the HunYuan-Large model balances compression rate and effectiveness, ensuring that embeddings are sufficiently trained. The vocabulary includes 100K tokens integrated from tiktoken. Additionally, we trained an extra 29K Chinese tokens using a large amount of high-quality Chinese training data to enhance the model's Chinese capabilities and the tokenizer's compression rate. Combined, our new tokenizer improves the compression rate compared to the LLaMA3 tokenizer, increasing from 2.78 characters/token to 3.13 characters/token.

## Hunyuan API

You can experience our Hunyuan-Large model on Tencent Cloud. For details, please visit: https://cloud.tencent.com/document/product/1729/97730.

## Interactive Demo Web

The Hunyuan-Large web demo is now open. Visit https://huggingface.co/spaces/tencent/Hunyuan-Large to easily experience our model.

## Training/Inference on TI
Tencent Cloud's [TI Platform](https://cloud.tencent.com/product/ti) is a comprehensive machine learning platform tailored for AI engineers. With the Hunyuan-Large model already integrated, you can easily train and deploy it in just a few steps. Visit [Chat with Hunyuan-Large](https://console.cloud.tencent.com/tione/v2/aimarket/detail/hunyuan_series?PublicAlgoGroupId=hunyuan-large-chat&detailTab=demo) to experience real-time conversations with the model, and explore [Hunyuan-Large Best Practice on TI](https://cloud.tencent.com/document/product/851/112032) to create your own customized Hunyuan-Large model. 


## Citation
If you find our work helpful, feel free to give us a cite.

```
@misc{sun2024hunyuanlargeopensourcemoemodel,
      title={Hunyuan-Large: An Open-Source MoE Model with 52 Billion Activated Parameters by Tencent}, 
      author={Xingwu Sun and Yanfeng Chen and Yiqing Huang and Ruobing Xie and Jiaqi Zhu and Kai Zhang and Shuaipeng Li and Zhen Yang and Jonny Han and Xiaobo Shu and Jiahao Bu and Zhongzhi Chen and Xuemeng Huang and Fengzong Lian and Saiyong Yang and Jianfeng Yan and Yuyuan Zeng and Xiaoqin Ren and Chao Yu and Lulu Wu and Yue Mao and Tao Yang and Suncong Zheng and Kan Wu and Dian Jiao and Jinbao Xue and Xipeng Zhang and Decheng Wu and Kai Liu and Dengpeng Wu and Guanghui Xu and Shaohua Chen and Shuang Chen and Xiao Feng and Yigeng Hong and Junqiang Zheng and Chengcheng Xu and Zongwei Li and Xiong Kuang and Jianglu Hu and Yiqi Chen and Yuchi Deng and Guiyang Li and Ao Liu and Chenchen Zhang and Shihui Hu and Zilong Zhao and Zifan Wu and Yao Ding and Weichao Wang and Han Liu and Roberts Wang and Hao Fei and Peijie She and Ze Zhao and Xun Cao and Hai Wang and Fusheng Xiang and Mengyuan Huang and Zhiyuan Xiong and Bin Hu and Xuebin Hou and Lei Jiang and Jiajia Wu and Yaping Deng and Yi Shen and Qian Wang and Weijie Liu and Jie Liu and Meng Chen and Liang Dong and Weiwen Jia and Hu Chen and Feifei Liu and Rui Yuan and Huilin Xu and Zhenxiang Yan and Tengfei Cao and Zhichao Hu and Xinhua Feng and Dong Du and Tinghao She and Yangyu Tao and Feng Zhang and Jianchen Zhu and Chengzhong Xu and Xirui Li and Chong Zha and Wen Ouyang and Yinben Xia and Xiang Li and Zekun He and Rongpeng Chen and Jiawei Song and Ruibin Chen and Fan Jiang and Chongqing Zhao and Bo Wang and Hao Gong and Rong Gan and Winston Hu and Zhanhui Kang and Yong Yang and Yuhong Liu and Di Wang and Jie Jiang},
      year={2024},
      eprint={2411.02265},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2411.02265}, 
}
```
<br>

## Contact Us

If you would like to leave a message for our R&D and product teams, Welcome to contact our open-source team . You can also contact us via email (hunyuan_opensource@tencent.com).


