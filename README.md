# VPLLM: Next Frame Video Prediction with LLMs

## 📌 About
This project presents a **training-free pipeline** for predicting the next frame in a video using **Large Language Models (LLMs)**.  
Instead of training complex models, we leverage **BLIP2**, **YOLO**, and **GPT-4** to convert frames into detailed text descriptions and use LLMs to predict the next frame's content.

---

## 🧠 Key Features

- **No model training required** – uses pre-trained vision-language models.
- **Image-to-text and text-to-text pipelines** for frame prediction.
- **Supports BLIP2, YOLO, and GPT-4** in various combinations.
- Evaluated on the **UCF101 dataset** using cosine similarity and t-tests.

---

## 🛠 Technologies Used

- Python 3.10  
- PyTorch  
- BLIP2 (`transformers`)  
- OpenCV, PIL  
- YOLOv5  
- ChatGPT API  
- Sentence Transformers & CLIP for evaluation  

---

## 🧪 Method Overview

1. **Frame Extraction**: Split video into N-1 frames.  
2. **Frame Captioning**: Use BLIP2 (+YOLO optionally) to describe each frame.  
3. **LLM Prediction**: Feed frame captions to an LLM (e.g., GPT-4) to predict the next frame's caption.  
4. **(Optional)**: Generate image from caption using a text-to-image model.

---

## 📊 Evaluation

- **Cosine similarity** between text and image embeddings (CLIP + Sentence Transformers).
- **Statistical significance testing** via *t*-tests between configurations.
- Evaluated on real-world action videos like *bowling*, *gymnastics*, and *blowing candles*.

---

## 🔍 Ablation Study

| Setup                       | Best For                       |
|----------------------------|--------------------------------|
| BLIP2                      | Direct prediction (best avg.)  |
| BLIP2 + GPT-4              | Richer descriptions            |
| BLIP2 + Edge Detection     | Emphasize object shapes        |
| BLIP2 + YOLO + GPT-4       | Object-enhanced descriptions   |

---

## 📁 Files

- `VPLLM.ipynb`: Main notebook with full pipeline and experiments.
- `Report.pdf`: Full technical report and methodology.


