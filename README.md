<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0D3B66&height=220&section=header&text=Depression%20Detection%20from%20Social%20Media%20Text%20Using%20Different%20Language%20Datasets%20and%20Deep%20Learning%20Techniques&fontSize=15&fontColor=FFD700&animation=fadeIn&fontAlignY=40&desc=NCCIT%202025%20Best%20Paper%20%7C%20Thai%20NLP%20Research&descAlignY=62&descSize=16&descColor=ffffff" width="100%"/>

# 🧠 การจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย<br/>โดยใช้ชุดข้อมูลต่างภาษา และเทคนิคการเรียนรู้เชิงลึก

**Cross-lingual depression classification using English datasets to build Thai-language models**

<br>

[![Best Paper Award](https://img.shields.io/badge/🏆_Best_Paper-NCCIT_2025-FFD700?style=for-the-badge&labelColor=0D3B66)](#-award--รางวัล)
[![Conference](https://img.shields.io/badge/NCCIT-21st_Edition-4A90D9?style=for-the-badge&labelColor=1a1a2e)](#-award--รางวัล)
[![Thailand](https://img.shields.io/badge/Kanchanaburi-Thailand_🇹🇭-EF4444?style=for-the-badge&labelColor=1a1a2e)](#)

![Task](https://img.shields.io/badge/Task-Text_Classification-8B5CF6?style=flat-square)
![Language](https://img.shields.io/badge/Language-Thai_%2F_English-06B6D4?style=flat-square)
![Domain](https://img.shields.io/badge/Domain-NLP_·_Mental_Health-10B981?style=flat-square)
![Models](https://img.shields.io/badge/Models-Transformers_·_LLM-F59E0B?style=flat-square)

<br>

![divider](https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=0,2,12,20,30&height=4&width=100%25)

*Computer Science, Faculty of Science — Kasetsart University*

</div>

---

## 📄 Abstract / บทคัดย่อ

> **🇬🇧 English**
>
> Due to the limited availability of Thai-language datasets for social-media text and depression detection, this research presents a method for **leveraging English-language datasets to develop a classification model** for detecting depression from Thai social-media text. The approach compares **English→Thai translation techniques** against **language-agnostic representation techniques**, and applies text classification using **PhayaThaiBERT**, **WangchanBERTa**, **SimCSE + RoBERTa + Thai**, and **LaBSE**. All models were evaluated on Thai-language datasets.
>
> **The best-performing pipeline combined Qwen (LLM) translation with PhayaThaiBERT classification.**

> **🇹🇭 ภาษาไทย**
>
> งานวิจัยนี้นำเสนอวิธีการใช้ชุดข้อมูลจากภาษาอังกฤษในการพัฒนาโมเดลจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย โดยใช้เทคนิคการแปลภาษาอังกฤษเป็นภาษาไทย เปรียบเทียบกับเทคนิคการแทนค่าแบบไม่ขึ้นกับภาษา ผลการทดลองพบว่า **เทคนิคการแปลภาษาด้วยโมเดล QWEN (LLM) ร่วมกับการจำแนกข้อความด้วย PhayaThaiBERT มีประสิทธิภาพดีที่สุด**

---

## 🔬 Methodology / วิธีดำเนินงานวิจัย

```mermaid
flowchart TD
    A["📥 English Reddit Dataset<br/>(Kayalvizhi & Thenmozhi, 2022)"] --> B["🧹 English Text Cleaning<br/>remove emojis · HTML · URLs<br/>punctuation · stopwords"]

    B --> C1["🤖 QWEN (LLM)<br/>Translation"]
    B --> C2["🔁 NLLB-200<br/>Neural MT"]
    B --> C3["🌐 LaBSE<br/>Language-Agnostic<br/>Representation"]

    C1 --> D["🇹🇭 Thai Text Cleaning<br/>PyThaiNLP · stopwords · NER removal"]
    C2 --> D

    D --> E["⚖️ Class Weight Balancing"]

    E --> G1["WangchanBERTa"]
    E --> G2["PhayaThaiBERT ⭐"]
    E --> G3["SimCSE + RoBERTa + Thai"]
    C3 --> G4["LaBSE Classifier"]

    G1 --> H["🎯 Evaluate on Thai Dataset<br/>(Storylog & Blogspot)"]
    G2 --> H
    G3 --> H
    G4 --> H

    style A fill:#1e3a5f,stroke:#4A90D9,color:#fff
    style C1 fill:#5b21b6,stroke:#8B5CF6,color:#fff
    style G2 fill:#92400e,stroke:#F59E0B,color:#fff
    style H fill:#065f46,stroke:#10B981,color:#fff
```

The study contrasts **two cross-lingual strategies**:

1. **Translation-based** — translate the English training data into Thai (via **Qwen** LLM or **NLLB-200** NMT), then fine-tune Thai transformers.
2. **Language-agnostic** — embed text directly with **LaBSE** without translation.

⭐ The winning combination was **Qwen translation → PhayaThaiBERT**.

---

## 🛠️ Models & Tools / เครื่องมือที่ใช้

| Component | Tool / Model |
|---|---|
| 🤖 Translation (LLM) | `Qwen/Qwen2.5-72B-Instruct` |
| 🔁 Translation (NMT) | `facebook/nllb-200-3.3B` |
| 🇹🇭 Thai NLP | `PyThaiNLP` |
| 🧩 Classifier 1 ⭐ | **PhayaThaiBERT** |
| 🧩 Classifier 2 | WangchanBERTa |
| 🧩 Classifier 3 | SimCSE + RoBERTa + Thai |
| 🧩 Classifier 4 | LaBSE |

---

## 📁 Dataset / ชุดข้อมูล

<table>
<tr>
<th align="left">🟦 Training Source (English)</th>
<th align="left">🟩 Test Source (Thai)</th>
</tr>
<tr>
<td valign="top">

**Reddit dataset**
Kayalvizhi & Thenmozhi (2022)

**Subreddits:**
`r/MentalHealth` · `r/depression`
`r/loneliness` · `r/stress` · `r/anxiety`

</td>
<td valign="top">

**Storylog & Blogspot**
Hämäläinen et al. (2021)

Thai-language social-media posts
used purely for evaluation

</td>
</tr>
</table>

**Classes:** `Depression` / `Non-Depression`

**Split:** `Train 75%` · `Validation 10%` · `Test 15%`

---

## 🏆 Award / รางวัล

<div align="center">

### 🥇 Best Paper Award

</div>

| | |
|---|---|
| 🏅 **Award** | Best Paper Award |
| 🎓 **Conference** | NCCIT 2025 — The 21st National Conference on Computing and Information Technology |
| 🏛️ **Organizer** | The Association of Council of IT Deans (CITT), KMUTNB & Kanchanaburi Rajabhat University |
| 📅 **Date** | May 15–16, 2025 |
| 📍 **Venue** | Kanchanaburi, Thailand |

---

### Connect Us

</div>
 🤖 Thitima and team. 🤖

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0D3B66&height=120&section=footer&fontColor=FFD700" width="100%"/>

</div>
