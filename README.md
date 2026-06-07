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
