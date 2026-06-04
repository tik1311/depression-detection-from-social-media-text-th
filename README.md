<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=8B1A1A&height=200&section=header&text=Depression%20Detection&fontSize=40&fontColor=FFD700&animation=fadeIn&fontAlignY=38&desc=from%20Social%20Media%20Text%20%7C%20Thai%20NLP%20Research&descAlignY=58&descSize=18&descColor=ffffff" width="100%"/>
🧠 การจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย
Depression Detection from Social Media Text
<br/>
Show Image
Show Image
Show Image
Show Image
<br/>

📍 May 15–16, 2025 · Kanchanaburi, Thailand

</div>

🏅 Award
<div align="center">
╔══════════════════════════════════════════════════════════════════╗
║                    🏆  BEST PAPER AWARD                         ║
║                                                                  ║
║   The 21st National Conference on Computing                      ║
║   and Information Technology — NCCIT 2025                       ║
║                                                                  ║
║   Organizer: CITT, KMUTNB & Kanchanaburi Rajabhat University    ║
║   Date: May 15–16, 2025 · Kanchanaburi, Thailand                ║
╚══════════════════════════════════════════════════════════════════╝
</div>

👥 Team / ทีมวิจัย
<div align="center">
👩‍💻 Researcher👩‍🏫 AdvisorThitima KhamgongAsst. Prof. Dr. Aurawan Imsombutธิติมา คำกองผศ.ดร. อรวรรณ อิ่มสมบัติthitima.khamg@ku.thaurawan.i@ku.th
🏫 Department of Computer Science, Faculty of Science, Kasetsart University
</div>

📄 Abstract / บทคัดย่อ
<table>
<tr>
<td width="50%">
🇬🇧 English
Due to the limited availability of Thai-language datasets for social media text and depression detection, this research presents a method using English-language datasets to develop a depression classification model from social media text.
The approach compares:

🔄 English-to-Thai translation (QWEN LLM / NLLB-200 NMT)
🌐 Language-agnostic representation (LaBSE)

Applied classifiers: PhayaThaiBERT, WangchanBERTa, SimCSE + RoBERTa + Thai, LaBSE
✅ Best result: QWEN + PhayaThaiBERT → Accuracy 0.90, Precision 0.89, Recall 0.89
</td>
<td width="50%">
🇹🇭 ภาษาไทย
งานวิจัยนี้นำเสนอวิธีการใช้ชุดข้อมูลจากภาษาอังกฤษในการพัฒนาโมเดลจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย
แนวทางที่เปรียบเทียบ:

🔄 การแปลภาษาอังกฤษเป็นไทย (QWEN / NLLB-200)
🌐 การแทนค่าแบบไม่ขึ้นกับภาษา (LaBSE)

โมเดลที่ใช้จำแนก: PhayaThaiBERT, WangchanBERTa, SimCSE + RoBERTa + Thai, LaBSE
✅ ผลดีที่สุด: QWEN + PhayaThaiBERT → Accuracy 0.90, Precision 0.89, Recall 0.89
</td>
</tr>
</table>

🔬 Methodology / ขั้นตอนการวิจัย
┌─────────────────────────────────────────────────┐
│     English Reddit Dataset                       │
│  (Kayalvizhi & Thenmozhi, 2022)                  │
└───────────────────┬─────────────────────────────┘
                    │
                    ▼
        ┌───────────────────────┐
        │   English Text Cleaning│
        │  • Remove emojis/HTML  │
        │  • Remove URLs         │
        │  • Remove stopwords    │
        └──────────┬────────────┘
                   │
        ┌──────────┴──────────────────────┐
        │                                 │
        ▼                                 ▼
┌───────────────────┐           ┌──────────────────────┐
│  NLLB-200 (NMT)   │           │   QWEN 2.5-72B (LLM) │
│  Neural Machine   │           │   Large Language     │
│  Translation      │           │   Model Translation  │
└────────┬──────────┘           └──────────┬───────────┘
         │                                 │
         └──────────────┬──────────────────┘
                        │
                        ▼
            ┌───────────────────────┐
            │   Thai Text Cleaning  │
            │  • PyThaiNLP (newmm)  │
            │  • Thai Stopwords     │
            │  • NER Removal        │
            └───────────┬───────────┘
                        │
                        ▼
            ┌───────────────────────┐
            │  Class Weight Balance │
            │  (Imbalance Handling) │
            └───────────┬───────────┘
                        │
                        ▼
            ┌───────────────────────┐
            │   TF-IDF + NER        │
            │   Vectorization       │
            └──┬─────────┬──────────┘
               │         │          │
               ▼         ▼          ▼
        ┌──────────┐ ┌──────────┐ ┌─────────────────┐
        │WangChan  │ │PhayaThai │ │SimCSE+RoBERTa   │
        │BERTa     │ │BERT      │ │+Thai            │
        └──────────┘ └──────────┘ └─────────────────┘
               │         │          │
               └────┬─────┘──────────┘
                    │
                    ▼
        ┌───────────────────────┐
        │  Evaluate on Thai     │
        │  Dataset (Storylog    │
        │  & Blogspot)          │
        └───────────────────────┘

─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
      Also tested: Language-Agnostic Path
         English Dataset → LaBSE Embedding
                        → Classification
─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─

📊 Results / ผลการทดลอง
✅ Tested on Thai Dataset — QWEN (LLM) Translation
ModelAccuracyRecallF1-ScorePrecision🥇 PhayaThaiBERT0.900.890.900.89SimCSE + RoBERTa + Thai0.870.880.870.87WangchanBERTa0.680.690.690.69
✅ Tested on Thai Dataset — NLLB-200 (NMT) Translation
ModelAccuracyRecallF1-ScorePrecision🥇 SimCSE + RoBERTa + Thai0.830.820.830.83PhayaThaiBERT0.680.680.630.79WangchanBERTa0.580.580.560.59
✅ Language-Agnostic Representation
ModelAccuracyRecallF1-ScorePrecisionLaBSE0.640.640.620.67

🛠️ Models & Tools / เครื่องมือที่ใช้
CategoryComponentModel / Tool🔄 TranslationLLMQwen/Qwen2.5-72B-Instruct🔄 TranslationNMTfacebook/nllb-200-3.3B🇹🇭 Thai NLPTokenizer & CleanerPyThaiNLP🤖 ClassifierThai BERTPhayaThaiBERT🤖 ClassifierThai RoBERTaWangchanBERTa🤖 ClassifierSentence EmbeddingSimCSE + RoBERTa + Thai🌐 Cross-lingualMultilingual BERTLaBSE

📁 Dataset / ชุดข้อมูล
TrainingTestingSourceEnglish Reddit postsThai Storylog & BlogspotReferenceKayalvizhi & Thenmozhi (2022)Hämäläinen et al. (2021)Subredditsr/depression, r/MentalHealth, r/loneliness, r/stress, r/anxiety—ClassesDepression / Non-DepressionDepression / Non-DepressionSplitTrain 75% · Val 10% · Test 15%—

📚 Citation / การอ้างอิง
bibtex@inproceedings{khamgong2025depression,
  title     = {Depression Detection from Social Media Text Using
               Different Language Datasets and Deep Learning Techniques},
  author    = {Khamgong, Thitima and Imsombut, Aurawan},
  booktitle = {Proceedings of the 21st National Conference on
               Computing and Information Technology (NCCIT 2025)},
  pages     = {311--316},
  year      = {2025},
  month     = {May},
  address   = {Kanchanaburi, Thailand}
}

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=8B1A1A&height=100&section=footer" width="100%"/>
© 2025 Thitima Khamgong & Aurawan Imsombut
Department of Computer Science · Faculty of Science · Kasetsart University
</div><div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=8B1A1A&height=200&section=header&text=Depression%20Detection&fontSize=40&fontColor=FFD700&animation=fadeIn&fontAlignY=38&desc=from%20Social%20Media%20Text%20%7C%20Thai%20NLP%20Research&descAlignY=58&descSize=18&descColor=ffffff" width="100%"/>
🧠 การจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย
Depression Detection from Social Media Text
<br/>
Show Image
Show Image
Show Image
Show Image
<br/>

📍 May 15–16, 2025 · Kanchanaburi, Thailand

</div>

🏅 Award
<div align="center">
╔══════════════════════════════════════════════════════════════════╗
║                    🏆  BEST PAPER AWARD                         ║
║                                                                  ║
║   The 21st National Conference on Computing                      ║
║   and Information Technology — NCCIT 2025                       ║
║                                                                  ║
║   Organizer: CITT, KMUTNB & Kanchanaburi Rajabhat University    ║
║   Date: May 15–16, 2025 · Kanchanaburi, Thailand                ║
╚══════════════════════════════════════════════════════════════════╝
</div>

👥 Team / ทีมวิจัย
<div align="center">
👩‍💻 Researcher👩‍🏫 AdvisorThitima KhamgongAsst. Prof. Dr. Aurawan Imsombutธิติมา คำกองผศ.ดร. อรวรรณ อิ่มสมบัติthitima.khamg@ku.thaurawan.i@ku.th
🏫 Department of Computer Science, Faculty of Science, Kasetsart University
</div>

📄 Abstract / บทคัดย่อ
<table>
<tr>
<td width="50%">
🇬🇧 English
Due to the limited availability of Thai-language datasets for social media text and depression detection, this research presents a method using English-language datasets to develop a depression classification model from social media text.
The approach compares:

🔄 English-to-Thai translation (QWEN LLM / NLLB-200 NMT)
🌐 Language-agnostic representation (LaBSE)

Applied classifiers: PhayaThaiBERT, WangchanBERTa, SimCSE + RoBERTa + Thai, LaBSE
✅ Best result: QWEN + PhayaThaiBERT → Accuracy 0.90, Precision 0.89, Recall 0.89
</td>
<td width="50%">
🇹🇭 ภาษาไทย
งานวิจัยนี้นำเสนอวิธีการใช้ชุดข้อมูลจากภาษาอังกฤษในการพัฒนาโมเดลจำแนกภาวะซึมเศร้าจากข้อความโซเชียลมีเดีย
แนวทางที่เปรียบเทียบ:

🔄 การแปลภาษาอังกฤษเป็นไทย (QWEN / NLLB-200)
🌐 การแทนค่าแบบไม่ขึ้นกับภาษา (LaBSE)

โมเดลที่ใช้จำแนก: PhayaThaiBERT, WangchanBERTa, SimCSE + RoBERTa + Thai, LaBSE
✅ ผลดีที่สุด: QWEN + PhayaThaiBERT → Accuracy 0.90, Precision 0.89, Recall 0.89
</td>
</tr>
</table>

🔬 Methodology / ขั้นตอนการวิจัย
┌─────────────────────────────────────────────────┐
│     English Reddit Dataset                       │
│  (Kayalvizhi & Thenmozhi, 2022)                  │
└───────────────────┬─────────────────────────────┘
                    │
                    ▼
        ┌───────────────────────┐
        │   English Text Cleaning│
        │  • Remove emojis/HTML  │
        │  • Remove URLs         │
        │  • Remove stopwords    │
        └──────────┬────────────┘
                   │
        ┌──────────┴──────────────────────┐
        │                                 │
        ▼                                 ▼
┌───────────────────┐           ┌──────────────────────┐
│  NLLB-200 (NMT)   │           │   QWEN 2.5-72B (LLM) │
│  Neural Machine   │           │   Large Language     │
│  Translation      │           │   Model Translation  │
└────────┬──────────┘           └──────────┬───────────┘
         │                                 │
         └──────────────┬──────────────────┘
                        │
                        ▼
            ┌───────────────────────┐
            │   Thai Text Cleaning  │
            │  • PyThaiNLP (newmm)  │
            │  • Thai Stopwords     │
            │  • NER Removal        │
            └───────────┬───────────┘
                        │
                        ▼
            ┌───────────────────────┐
            │  Class Weight Balance │
            │  (Imbalance Handling) │
            └───────────┬───────────┘
                        │
                        ▼
            ┌───────────────────────┐
            │   TF-IDF + NER        │
            │   Vectorization       │
            └──┬─────────┬──────────┘
               │         │          │
               ▼         ▼          ▼
        ┌──────────┐ ┌──────────┐ ┌─────────────────┐
        │WangChan  │ │PhayaThai │ │SimCSE+RoBERTa   │
        │BERTa     │ │BERT      │ │+Thai            │
        └──────────┘ └──────────┘ └─────────────────┘
               │         │          │
               └────┬─────┘──────────┘
                    │
                    ▼
        ┌───────────────────────┐
        │  Evaluate on Thai     │
        │  Dataset (Storylog    │
        │  & Blogspot)          │
        └───────────────────────┘

─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
      Also tested: Language-Agnostic Path
         English Dataset → LaBSE Embedding
                        → Classification
─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─

📊 Results / ผลการทดลอง
✅ Tested on Thai Dataset — QWEN (LLM) Translation
ModelAccuracyRecallF1-ScorePrecision🥇 PhayaThaiBERT0.900.890.900.89SimCSE + RoBERTa + Thai0.870.880.870.87WangchanBERTa0.680.690.690.69
✅ Tested on Thai Dataset — NLLB-200 (NMT) Translation
ModelAccuracyRecallF1-ScorePrecision🥇 SimCSE + RoBERTa + Thai0.830.820.830.83PhayaThaiBERT0.680.680.630.79WangchanBERTa0.580.580.560.59
✅ Language-Agnostic Representation
ModelAccuracyRecallF1-ScorePrecisionLaBSE0.640.640.620.67

🛠️ Models & Tools / เครื่องมือที่ใช้
CategoryComponentModel / Tool🔄 TranslationLLMQwen/Qwen2.5-72B-Instruct🔄 TranslationNMTfacebook/nllb-200-3.3B🇹🇭 Thai NLPTokenizer & CleanerPyThaiNLP🤖 ClassifierThai BERTPhayaThaiBERT🤖 ClassifierThai RoBERTaWangchanBERTa🤖 ClassifierSentence EmbeddingSimCSE + RoBERTa + Thai🌐 Cross-lingualMultilingual BERTLaBSE

📁 Dataset / ชุดข้อมูล
TrainingTestingSourceEnglish Reddit postsThai Storylog & BlogspotReferenceKayalvizhi & Thenmozhi (2022)Hämäläinen et al. (2021)Subredditsr/depression, r/MentalHealth, r/loneliness, r/stress, r/anxiety—ClassesDepression / Non-DepressionDepression / Non-DepressionSplitTrain 75% · Val 10% · Test 15%—

📚 Citation / การอ้างอิง
bibtex@inproceedings{khamgong2025depression,
  title     = {Depression Detection from Social Media Text Using
               Different Language Datasets and Deep Learning Techniques},
  author    = {Khamgong, Thitima and Imsombut, Aurawan},
  booktitle = {Proceedings of the 21st National Conference on
               Computing and Information Technology (NCCIT 2025)},
  pages     = {311--316},
  year      = {2025},
  month     = {May},
  address   = {Kanchanaburi, Thailand}
}

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=8B1A1A&height=100&section=footer" width="100%"/>
© 2025 Thitima Khamgong & Aurawan Imsombut
Department of Computer Science · Faculty of Science · Kasetsart University
</div>
