# Google Colab - Remote Ollama

A Google Colab notebook that runs [Ollama](https://ollama.com/) and exposes it to the internet, enabling you to do the heavy lifting in the cloud and access it from your local machine .

Collab URL: [Google Collab](https://colab.research.google.com/drive/1Eq47JU1Swj1eBkr38Dk_SFDZHryfNIaN?usp=sharing)

## Prerequisites
- Google Colab or a similar Jupyter notebook environment
- Internet connection for installing packages and creating the tunnel

## Usage
1. Open the notebook in Google Colab
2. Run each cell sequentially:
   - Cell 1: Installs Ollama and dependencies
   - Cell 2: Starts the Ollama server in the background
   - Cell 3: Creates a public tunnel and outputs a URL for accessing Ollama
3. Use the generated URL to connect to Ollama from any external application
4. Once the tunnel is active, you can use Ollama like this:
```bash
export OLLAMA_HOST=http://<generated-url>
ollama run granite4:3b --prompt "What is the capital of France?"
ollama ls
ollama ps
``` 

### Models you can run with collab T4-GPU (16GB VRAM limit):
1. `granite4:3b` (3 billion parameters)
2. `gpt-oss:20b` (20 billion parameters)
3. `qwen3.5:9b` (9 billion parameters)
4. same alike.....

## Configuration
- **Port**: `11434` (exposed on all interfaces)
- **Context Length**: 128,000 tokens
- **Tunnel Service**: [Pinggy](https://pinggy.io/) (free SSH tunnel)

## License

MIT
