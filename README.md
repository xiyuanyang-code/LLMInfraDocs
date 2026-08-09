# LLM Codebase Document

## Deployment

```bash
# install hugo
wget https://github.com/gohugoio/hugo/releases/download/v0.162.1/hugo_0.162.1_linux-amd64.deb

dpkg -i hugo*.deb

# check hugo install
hugo version
```

```bash
git clone git@github.com:xiyuanyang-code/LLMInfraDocs.git
cd LLMInfraDocs

hugo serve

# add new posts
hugo new content content/posts/my-first-post.md
```

## Update Plans

- LLM Inference: [vllm](https://github.com/vllm-project/vllm)
- MS Swift (LLM Training): [ms-swift](https://github.com/modelscope/ms-swift)
- Slime (Agentic RL): [slime](https://github.com/THUDM/slime)
- harbor (Docker and Agentic Evaluation): [harbor](https://github.com/harbor-framework/harbor)
- Megatron-LM (GPU-optimized library): [megatron-lm](https://github.com/nvidia/megatron-lm)

## TODO

- slime 讲解 rollout-routing-replay