🏆 Depression Detection from Social Media Text
การจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย

🏅 Best Paper Award — The 21st National Conference on Computing and Information Technology (NCCIT 2025)
May 15–16, 2025 | Kanchanaburi, Thailand


📄 Abstract / บทคัดย่อ
[English]
Due to the limited availability of Thai-language datasets for social media text and depression detection, this research presents a method for using English-language datasets to develop a classification model for detecting depression from social media text. The approach uses English-to-Thai translation techniques compared with language-agnostic representation techniques, and applies text classification using PhayaThaiBERT, WangchanBERTa, SimCSE + RoBERTa + Thai, and LaBSE. Models were evaluated on Thai-language datasets.

[ภาษาไทย]
งานวิจัยนี้นำเสนอวิธีการใช้ชุดข้อมูลจากภาษาอังกฤษในการพัฒนาโมเดลจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย โดยใช้เทคนิคการแปลภาษาอังกฤษเป็นภาษาไทย เปรียบเทียบกับเทคนิคการแทนค่าแบบไม่ขึ้นกับภาษา ผลการทดลองพบว่าเทคนิคการแปลภาษาด้วยโมเดล QWEN (LLM) ร่วมกับการจำแนกข้อความด้วย PhayaThaiBERT มีประสิทธิภาพดีที่สุด

🔬 Methodology / วิธีดำเนินงานวิจัย
English Reddit Dataset (Kayalvizhi & Thenmozhi, 2022)
         │
         ▼
  English Text Cleaning
  (Remove emojis, HTML, URLs, punctuation, stopwords)
         │
    ┌────┴────┐
    │         │
    ▼         ▼
NLLB-200    QWEN (LLM)          Language-Agnostic
  (NMT)    Translation           Representation
    │         │                       │
    └────┬────┘                       │
         ▼                            │
  Thai Text Cleaning                  │
  (PyThaiNLP, stopwords,              │
   NER removal)                       │
         │                            │
         ▼                            ▼
  Class Weight Balancing           LaBSE
         │
         ▼
     TF-IDF Vectorization
         │
    ┌────┼────┐
    ▼    ▼    ▼
WangChan PhayaThai SimCSE+
BERTa    BERT     RoBERTa+Thai
         │
         ▼
  Evaluate on Thai Dataset
  (Storylog & Blogspot)


🛠️ Models & Tools Used / เครื่องมือที่ใช้
ComponentTool / ModelTranslation (LLM)Qwen/Qwen2.5-72B-InstructTranslation (NMT)facebook/nllb-200-3.3BThai NLPPyThaiNLPClassifier 1PhayaThaiBERTClassifier 2WangchanBERTaClassifier 3SimCSE + RoBERTa + ThaiClassifier 4LaBSE

📁 Dataset / ชุดข้อมูล

Training source: English Reddit dataset — Kayalvizhi & Thenmozhi (2022)
Subreddits: r/Mental Health, r/depression, r/loneliness, r/stress, r/anxiety
Test source (Thai): Storylog & Blogspot — Hämäläinen et al. (2021)
Classes: Depression / Non-Depression
Split: Train 75% | Validation 10% | Test 15%


🏆 Award / รางวัล
<div align="center">
Award🥇 Best Paper AwardConferenceNCCIT 2025 — The 21st National Conference on Computing and Information TechnologyOrganizerThe Association of Council of IT Deans (CITT), KMUTNB & Kanchanaburi Rajabhat UniversityDateMay 15–16, 2025, Kanchanaburi, Thailand
</div>

Department of Computer Science, Faculty of Science, Kasetsart University


<div align="center">
<sub>© 2025 Thitima Khamgong & Aurawan Imsombut · Kasetsart University</sub>
</div>
