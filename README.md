# Diffusion SDXL DreamBooth LoRA Finetuning

This project provides a Google Colab-compatible pipeline for fine-tuning [Stability AI's SDXL](https://huggingface.co/stabilityai/stable-diffusion-xl-base-1.0) using **DreamBooth** and **LoRA (Low-Rank Adaptation)** techniques on a few custom images (5-20 images). It leverages memory-friendly training, enabling personalized model generation based on user-provided images.

## 🚀 Features

- Fine-tune SDXL using DreamBooth with LoRA.
- Hugging Face model loading and Drive mounting.
- Custom instance and class prompts with dataset uploads.
- Saves trained LoRA weights to Google Drive.

## 📦 Requirements

### Pre-requisites

1. **Hugging Face API Token**  
   - Required to download the SDXL base model.  
   - Get it from: [https://huggingface.co/settings/tokens](https://huggingface.co/settings/tokens)

2. **Google Drive Access**  
   - Notebook saves model outputs and handles training datasets via Google Drive.

3. **Training Dataset**  
   - Prepare a folder (e.g., `my_data/subject_name`) with ~10–20 images of the subject/class you wish to train on.

## ⚙️ Setup & Usage

1. **Open the Notebook in Google Colab**  
   Use [Google Colab](https://colab.research.google.com/) to run `SDXL_DreamBooth_LoRA_.ipynb`.

2. **Run Each Cell Sequentially**  
   - Mount Google Drive.
   - Enter Hugging Face token when prompted.
   - Upload or connect your training data.
   - Set prompts and training hyperparameters.

3. **Result**  
   Trained LoRA weights will be saved in the `output` directory within your Google Drive.

## 📂 Example Directory Structure
```bash
SDXL_DreamBooth_LoRA_.ipynb
/drive/MyDrive/
├── lora/
│   ├── my_model/                # Output directory for trained LoRA weights
│   │   ├── adapter_config.json
│   │   ├── pytorch_lora_weights.safetensors
│   └── my_data/                 # Training dataset
│       └── sks_person/          # Folder containing instance images
│           ├── image1.jpg
│           ├── image2.jpg

```

## 🧠 Notes

- Use a **rare token** in the instance prompt (e.g., `a photo of sks person`) to ensure the model learns the specific concept without interfering with existing model knowledge.
- Adjust training parameters such as `network_dim`, learning rates, and number of steps depending on dataset size and expected output quality.

## 📜 License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgement
Very thankful to the awesome open source community and examples at https://github.com/huggingface/diffusers

## Contact 
kalia.megha84@gmail.com

