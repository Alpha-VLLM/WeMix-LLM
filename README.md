## WeMix-LLM

WeMix-LLM includes a series of LLMs and multimodal LLMs following the same paradigm. WeMix-LLM is trained with [LLaMA2-Accessory](https://github.com/Alpha-VLLM/LLaMA2-Accessory).

### Setup

Please follow the [Environment Setup](https://llama2-accessory.readthedocs.io/en/latest/install.html) of LLaMA2-Accessory.

### Models

#### WeMix-LLaMA2-7B: An Instruction-Following LLM
* Weight: [Alpha-VLLM/WeMix-LLaMA2-7B](https://huggingface.co/Alpha-VLLM/WeMix-LLaMA2-7B)
* Demo:
    ```bash
    wemix_weight=path/to/WeMix-LLaMA2-7B/

    python demos/multi_turn.py \
    --llama_config ${wemix_weight}/params.json --tokenizer_path ${wemix_weight}/tokenizer.model \
    --pretrained_path ${wemix_weight}
    ```
* Benchmark (OpenCompass):

| Model         | Vicuna-33B | WeMix-LLaMA2-7B | LLaMA-2-7B-Chat | Vicuna-7B | LLaMA-2-7B | Alpaca-7B | LLaMA-7B |
|---------------|------------|-----------------|-----------------|-----------|------------|-----------|----------|
| OVERALL       | 50         | 49.6            | 44.8            | 43.4      | 41.6       | 39.9      | 38.5     |
| EXAM          | 49.2       | 45.5            | 40.1            | 40.5      | 35.5       | 35.3      | 31.2     |
| LANGUAGE      | 44.9       | 45.1            | 44              | 39.6      | 44.1       | 39.5      | 40.5     |
| KNOWLEDGE     | 61.3       | 59.4            | 54.3            | 51.7      | 53.3       | 44.6      | 49.6     |
| UNDERSTANDING | 58.5       | 55.5            | 50.9            | 50.5      | 42.4       | 45.1      | 38       |
| REASONING     | 44.7       | 47.4            | 41.4            | 39.9      | 40.1       | 38.1      | 38.5     |

> Please refer to [benchmark.md](./benchmark.md) for mode details.

#### WeMix-LLaMA2-7B-MM: A Multimodal LLM

* Weight: [Alpha-VLLM/WeMix-LLaMA2-7B-MM](https://huggingface.co/Alpha-VLLM/WeMix-LLaMA2-7B-MM)
* Demo:
```bash
wemix_weight=path/to/WeMix-LLaMA2-7B-MM
python demos/single_turn_mm.py \
--llama_config ${wemix_weight}/params.json --tokenizer_path ${wemix_weight}/tokenizer.model \
--pretrained_path wemix_weight
```
* Multimodal Benchmark:

| Model                     | Zero-shot Captioning |           | General VQA |        |      |                    |                 |
|---------------------------|----------------------|-----------|-------------|--------|------|--------------------|-----------------|
|                           | NoCaps               | Flickr30K | VQAv2dev    | OK-VQA | GQA  | SciQA-Img (0-shot) | VizWiz (0-shot) |
| Flamingo-9B               | -                    | 61.5      | 51.8        | 44.7   | -    | -                  | 28.8            |
| Flamingo-80B              | -                    | 67.2      | 56.3        | 50.6   | -    | -                  | 31.6            |
| Unified-IO-XL             | 100.0                | -         | 77.9        | 54.0   | -    | -                  | -               |
| Kosmos-1                  | -                    | 67.1      | 51.0        | -      | -    | -                  | 29.2            |
| Kosmos-2                  | -                    | 66.7      | 45.6        | -      | -    | -                  | -               |
| BLIP-2 (Vicuna-13B)       | 103.9                | 71.6      | 65.0        | 45.9   | 32.3 | 61.0               | 19.6            |
| InstructBLIP (Vicuna-13B) | 121.9                | 82.8      | -           | -      | 49.5 | 63.1               | 33.4            |
| Shikra (Vicuna-13B)       | -                    | 73.9      | 77.36       | 47.16  | -    | -                  | -               |
| Qwen-VL (Qwen-7B)         | 121.4                | 85.8      | 78.8        | 58.6   | 59.3 | 67.1               | 35.2            |
| Qwen-VL-Chat              | 120.2                | 81.0      | 78.2        | 56.6   | 57.5 | 68.2               | 38.9            |
| WeMix-LLaMA2-7B-MM        | 114.7                | 86.0      |             |        |      |                    |                 |

### Contributors

### Citation

### Acknowledgement

### License