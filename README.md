# 🎤 XTTS Fine-Tuning on Apple Silicon M1 Pro 🖥️

Welcome to the XTTS model fine-tuning repository! This project allows you to fine-tune XTTS (Cross-lingual Text-To-Speech) models specifically optimized for Apple's M1 Pro chipset using Python 3.10.

---

## 💻 About

This project was tested on an **M1 Pro Mac** with **16GB RAM**, focusing on the fine-tuning of XTTS models for TTS applications. The repository includes model compression techniques to optimize model performance. The main file you will run is `xtts_demo_with_model_compression.py`.

- Compatable with [ebook2audiobookxtts](https://github.com/DrewThomasson/ebook2audiobookXTTS)


---

## 🚀 Installation

Follow these steps to set up the project on your machine:

1. **Clone the repo**: 
   ```bash
   git clone [fineTuneXTTS-apple-Silicone](https://github.com/DrewThomasson/finetuneXtts_apple_silicone.git)
   cd finetuneXtts_apple_silicone
   ```

2. **Install dependencies**:
   The installation requires the `no-dependencies` option since it's built from a `pip freeze`.
   ```bash
   pip install --no-dependencies -r requirements.txt
   ```

---

## 🐳 Docker usage 

```docker
docker run -it -v ${PWD}/training:/tmp/xtts_ft/ athomasson2/fine_tune_xtts:M1
```

- Docker Usage on x86(You need 12 gb Vram at minimum)
```docker
docker run --gpus all -it -v ${PWD}/training:/tmp/xtts_ft/ athomasson2/fine_tune_xtts:v5
```
- Taken from [my dockerhub](https://hub.docker.com/r/athomasson2/fine_tune_xtts)

## 🛠️ Usage

To fine-tune and run the XTTS model, use the provided demo script.

### **Run the Fine-Tuning Script**
```bash
python3 xtts_demo_with_model_compression.py --port 5003 --out_path /your/output/path --num_epochs 6 --batch_size 2
```

### **Available Arguments**:
- `--port`: Specify the port to run Gradio demo (default: 5003)
- `--out_path`: Output directory for saved models (default: `/tmp/xtts_ft/`)
- `--num_epochs`: Number of epochs (default: 10)
- `--batch_size`: Batch size for training (default: 4)
- `--grad_acumm`: Gradient accumulation steps (default: 1)
- `--max_audio_length`: Maximum audio length in seconds (default: 11)

---

## 📝 File Overview

- **`xtts_demo_with_model_compression.py`**: Main script to fine-tune, load, and run the XTTS model.
- **`train_gpt.py`**: Handles the GPT training aspects during fine-tuning.
- **`format_audio_list.py`**: Preprocesses the dataset for training.
- **`export_model()`**: Compresses and exports the fine-tuned model as a `.zip` file.

---

## ✨ Features
- 🔥 Fine-tune XTTS models efficiently on Apple Silicon.
- 📂 Automatically compress and export the best model after fine-tuning.
- 🧠 Leverage model compression to optimize performance.
- 🌍 Supports various languages for training and inference.

---

## ⚠️ Notes

- This project was tested on an **M1 Pro** Mac with **16GB RAM**.
- Ensure that all Python packages are compatible with Apple Silicon (M1/M2) architecture.
  
---

Feel free to contribute, suggest improvements, or raise any issues. Happy fine-tuning! 😎
