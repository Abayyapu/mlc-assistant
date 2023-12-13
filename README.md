# MLC Assistant
Chat with your documents and improve your writing using large-language models in your browser.

## Getting Started

### 1. Install Git LFS

Follow the instructions [here](https://git-lfs.com) to install Git LFS.

### 2. Create Conda environment (optional)
```bash
conda create --name mlc_assistant python=3.10
conda activate mlc_assistant
```

**Note: For quick start, skip Steps 3-5, run `./startup.sh`, and continue from [Step 6](#step6).**

### 3. Set up MLC LLM

Follow the steps below (only for CPU on macOS, Windows, or Linux) to set up MLC LLM on your local machine. For usage with GPU, follow the instructions [here](https://llm.mlc.ai/docs/install/mlc_llm.html).

```bash
python -m pip install --pre -U -f https://mlc.ai/wheels mlc-chat-nightly mlc-ai-nightly
git lfs install
mkdir -p mlc-llm/dist/prebuilt
git clone https://github.com/mlc-ai/binary-mlc-llm-libs.git mlc-llm/dist/prebuilt/lib
cd mlc-llm/dist/prebuilt && git clone https://huggingface.co/mlc-ai/mlc-chat-Llama-2-7b-chat-hf-q4f16_1
cd ../..
```

### 4. Build the Chrome extension (optional)
```bash
npm run build
npm run install
```

### 5. Launch the local server
```bash
cd mlc-llm
python -m mlc_chat.rest --model Llama-2-7b-chat-hf-q4f16_1
```

### 6. Install the Chrome extension <a id='step6'></a>
Launch Google Chrome and navigate to the extensions page by entering `chrome://extensions`. Enable Developer Mode by clicking the toggle switch next to Developer mode. Click the Load unpacked button and select the `mlc-assistant/dist` directory.

![extensions-page-e0d64d89a6acf_1920](https://github.com/mlc-ai/mlc-assistant/assets/11940172/cdb18fb3-24c5-41bf-9a40-484692c2150a)


You can now go to any Overleaf document, and select `Alt + Shift + 3` to invoke the MLC Assistant!