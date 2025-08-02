# ⚖️ Bangla Legal AI Chatbot

An AI-powered multilingual chatbot designed to assist with **Bangladeshi legal documents, government laws, announcements, and regulations**, all written in **Bangla**. This system uniquely handles English queries over Bangla documents, providing detailed, dual-language answers with structured formatting and citations.

---

## 🚀 Key Features

- 📚 **Bangla Document RAG**: Uses retrieval-augmented generation (RAG) over markdown-converted Bangla legal documents for highly accurate responses.
- 🌐 **Multilingual Query Support**:
  - **English Query** → English summary + translated rule + `"This excerpt..."` note → full Bangla section.
  - **Bangla Query** → Bangla summary + rule + citation only (no English part).
- 🧠 Powered by **Gemini Pro** (via `litellm`) and **LaBSE** sentence transformer embeddings.
- 📂 Handles legacy corrupted PDFs by converting them into structured markdown files.
- 💾 Uses **ChromaDB** for fast, persistent vector search over legal content.
- 📝 Renders Streamlit-based chat interface with support for both English and Bangla input/output.

---

## 📂 Project Structure
├── POC.py # Main Streamlit chatbot interface
\n├── vector_store.py # Embedding + vector storage (Chroma)
├── requirements.txt # Python dependencies
├── chroma_db/ # Auto-generated vector database
└── Source_Markdowns/ # Preprocessed legal documents (Markdown format)

## ⚙️ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/MohammadTaseen/Multilingual-AI-Chatbot-for-Bangla-Law-Support.git
cd Multilingual-AI-Chatbot-for-Bangla-Law-Support
```
2. Install Dependencies
Use pip or a virtual environment:
```bash
pip install -r requirements.txt
```
3. Configure Environment Variables
Create a .env file in the root directory with your Gemini API key:
```bash
GEMINI_API_KEY=your_gemini_api_key_here
```
4. (Optional) Rebuild Vector Store
If you want to reprocess the markdown files and recreate the vector database:
```bash
python vector_store.py
```
This will embed all markdown files in Source_Markdowns/ and store them in chroma_db/.
5. Run the Chatbot App
```bash
streamlit run POC.py
```
💬 Example Queries
🔸 English Query:
"How do VAT rates differ between branded and non-branded ready-made garment sales in Bangladesh?"

Response includes:

✅ English summary

✅ English rule statement

✅ Notice: “This excerpt was sourced from a Bangla document...”

✅ Bangla summary, rule, and citation

🔸 Bangla Query:
"কোন কোন রেস্তোরাঁকে মূল্য সংযোজন কর (ভ্যাট) দেওয়া থেকে অব্যাহতি দেওয়া হলো?"

Response includes:

✅ Bangla summary

✅ Bangla rule statement

✅ Bangla citation (in strict format)

## 📌 Citation Format

**[নথির শিরোনাম, আইন/নিয়ম/বিধির নাম, ধারা নম্বর, জারি: কার্যকর তারিখ]**


## 🛡️ Disclaimer
This chatbot is designed to assist with interpreting publicly available legal documents of Bangladesh. It does not offer legal advice. All answers are strictly sourced from uploaded legal markdown files.

## 👨‍💻 Author
Built by Mohammad Taseen — specializing in AI/ML + Generative AI
Reach out for improvements, integration, or suggestions!
