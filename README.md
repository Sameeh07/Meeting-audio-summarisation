# 🎙️ Meeting Minutes Generator from Audio

This project demonstrates how to transcribe meeting audio into text and generate structured meeting minutes (summary, key points, takeaways, and action items) using **OpenAI Whisper**, **Hugging Face Transformers**, and **quantization** techniques for efficient model loading.

## 🚀 Features

* Transcribe audio files into text using:

  * [OpenAI Whisper](https://platform.openai.com/docs/guides/speech-to-text)
  * Open-source Hugging Face models
* Generate detailed **meeting minutes** in Markdown format:

  * Summary with attendees, date, and location
  * Key discussion points
  * Takeaways
  * Action items with owners
* **Quantization with BitsAndBytes**: Efficient 4-bit model loading using Hugging Face `BitsAndBytesConfig`
* **Tokenizer integration with Hugging Face API**: Apply chat templates and manage inputs for LLaMA models
* Supports GPU acceleration on Google Colab

## ⚙️ Installation

Run the following inside Colab to install dependencies:

```bash
!pip install -q --upgrade torch==2.5.1+cu124 torchvision==0.20.1+cu124 torchaudio==2.5.1+cu124 --index-url https://download.pytorch.org/whl/cu124
!pip install -q requests bitsandbytes==0.46.0 transformers==4.48.3 accelerate==1.3.0 openai
```

## 🔑 Setup

1. **Mount Google Drive** (to load your audio file):

   ```python
   from google.colab import drive
   drive.mount("/content/drive")
   audio_filename = "/content/drive/MyDrive/folder/audio_extract.mp3"
   ```

2. **Add API Keys**:

   * Hugging Face: `HF_TOKEN`
   * OpenAI: `OPENAI_API_KEY`

   Store them in **Colab Secrets** for security:

   ```python
   from google.colab import userdata
   hf_token = userdata.get("HF_TOKEN")
   openai_api_key = userdata.get("OPENAI_API_KEY")
   ```

## 🧠 Models & Techniques

* **Whisper (OpenAI)** for audio-to-text transcription
* **Meta-LLaMA 3.1 (8B-Instruct)** for meeting minutes generation
* **Quantization with BitsAndBytes** to run large models on limited GPU(T4 free) memory:


## ▶️ Usage

1. Upload or mount your audio file.
2. Run the transcription cell to convert audio to text.
3. Generate meeting minutes with LLaMA by adjusting the system and user prompts.
4. View results in Markdown format inside Colab.


## 🤝 Contributing

Feel free to fork the repo, open issues, and submit PRs.

