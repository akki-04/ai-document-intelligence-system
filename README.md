***screenshots***

****Workflow****
<img width="1847" height="785" alt="Screenshot 2026-05-26 134300" src="https://github.com/user-attachments/assets/fcb1146a-9d55-4a26-8c35-bb34b66f3c48" />
<img width="1430" height="638" alt="Screenshot 2026-05-26 134244" src="https://github.com/user-attachments/assets/740a7ee8-552d-48e5-851b-81b570c4938b" />

****Testing****
<img width="1460" height="315" alt="Screenshot 2026-05-26 134217" src="https://github.com/user-attachments/assets/f454dfb7-dbc5-46e5-bbc6-fa3c9b405b90" />
<img width="1917" height="815" alt="Screenshot 2026-05-26 133440" src="https://github.com/user-attachments/assets/7c384645-ec56-474e-87b7-a900052ff243" />
<img width="1899" height="788" alt="Screenshot 2026-05-26 133423" src="https://github.com/user-attachments/assets/63e89dd4-0783-4ad6-ab50-778582cb8111" />


***Architecture***

                ┌──────────────────┐
                │  Google Drive    │
                │   PDF Upload     │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Google Drive     │
                │ Trigger (n8n)    │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Download PDF     │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ PDF Data Loader  │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Text Splitter    │
                │ Chunking         │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Gemini           │
                │ Embeddings       │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Pinecone Vector  │
                │ Database         │
                └────────┬─────────┘
                         │
          User Question  │
                ─────────┘
                         ▼
                ┌──────────────────┐
                │ AI Agent         │
                │ Retrieval + RAG  │
                └────────┬─────────┘
                         │
                         ▼
                ┌──────────────────┐
                │ Gemini Chat      │
                │ Response         │
                └──────────────────┘
