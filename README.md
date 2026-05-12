# 🤖 WhatsApp AI Destek Asistanı (n8n + RAG)

Bu proje, kurum içi BT (Bilgi Teknolojileri) destek süreçlerini otomatize etmek, personele anında çözüm sunmak ve sıkça sorulan teknik soruları yapay zeka gücüyle yanıtlamak amacıyla geliştirilmiş **kurumsal bir WhatsApp Asistanı** altyapısıdır.

Sistem, **n8n** (Node-based Workflow Automation), **Groq LLM**, **Twilio/Meta API** ve **RAG (Retrieval-Augmented Generation)** mimarisi üzerine inşa edilmiştir.

---

## 🚀 Özellikler

- **7/24 Otomatik Destek:** Personelden gelen WhatsApp mesajlarını anında karşılar ve bağlama uygun profesyonel yanıtlar üretir.
- **Kurumsal Bilgi Bankası (RAG):** `/rag_files` klasörüne eklenen PDF ve TXT uzantılı kurum içi kılavuzları okuyarak (Vektör veritabanı ile) kuruma özel ve doğru cevaplar verir. Halüsinasyon riski minimuma indirilmiştir.
- **İzole ve Güvenli Çalışma:** Tüm sistem **Docker** ve **Docker Compose** üzerinde izole bir ortamda (Container) çalışır.
- **Esnek Tünelleme:** Yerel sunucuları dış dünyaya güvenle açmak için HTTPS destekli webhook altyapısına sahiptir.

---

## 🛠️ Kullanılan Teknolojiler

- **Orkestrasyon:** [n8n](https://n8n.io/)
- **Yapay Zeka & LLM:** Groq API (Llama-3 / Mixtral modelleri)
- **Hafıza & RAG:** n8n Simple Vector Store & HuggingFace Embeddings
- **Mesajlaşma Entegrasyonu:** Twilio WhatsApp API (Opsiyonel: Meta Cloud API)
- **Konteynerizasyon:** Docker & Docker Compose

---

## 📁 Klasör Yapısı

```text
whatsapp_Ai/
│
├── docker-compose.yml         # Sistemin ana kurulum ve yapılandırma dosyası
├── My_workflow.json           # n8n iş akışının (otomasyonun) kaynak kodu
└── rag_files/                 # Yapay zekanın okuyacağı kurum içi rehberler (PDF/TXT)
    └── it_rehber.txt          # Örnek BT Çözüm Kılavuzu
