# Product Requirements Document: ShikenAI

## 1. Ringkasan Eksekutif
- **Produk**: ShikenAI - Platform latihan CPNS berbasis AI (HackerRank style).
- **Misi**: "The ultimate CPNS drill-engine powered by AI."
- **Target**: Lulusan D3/S1 (20-35 tahun), target utama formasi CPNS.
- **Keunggulan**: AI Tutor (Google NotebookLLM), Simulasi CAT presisi, Mastery Heatmap, Monthly Leaderboard.
- **Tech Stack**: Laravel 13, Filament v4, PostgreSQL, Redis, Google Vision OCR, NotebookLLM.

## 2. Market Opportunity
- **Pasar**: Persiapan ujian CPNS Indonesia. Permintaan tinggi untuk solusi digital.
- **Kompetitor**: SMARTCASN, JadiASN, AYOCPNS. Kekurangan mereka: kurang personalisasi AI, feedback generik, CAT simulasi kurang presisi.
- **Peluang**: Rebut market share dengan pengalaman belajar AI-driven & analytics mendalam.

## 3. Target User & Segmen
| Segmen | Detail | Prioritas |
| :--- | :--- | :--- |
| **Lulusan D3/S1 (20-35 thn)** | Formasi S1 terbanyak (60-70%), daya beli tinggi, butuh efisiensi waktu. | **Utama (MVP)** |
| **Mahasiswa Akhir** | Persiapan sebelum lulus, budget terbatas. | Sekunder |
| **Lulusan SMA/SMK (18-25 thn)** | Formasi SMA (admin/teknisi), volume besar, daya beli rendah. | Phase 2 |
| **Career Switcher** | Profesional mau pindah ke PNS, willing to pay tinggi. | Utama |

### Persona User:
- **Rina (26, S1 Akuntansi)**: Kerja swasta, mau jadi PNS, butuh latihan efisien + AI Tutor.
- **Andi (22, Fresh Grad TI)**: Baru lulus, waktu banyak, butuh drill + leaderboard.
- **Budi (19, Lulusan SMA)**: Budget pas, butuh paket murah.

## 4. Jobs-to-be-Done (JTBD)
- `JTBD-PRACTICE-001`: Latihan soal CPNS efisien.
- `JTBD-WEAKNESS-001`: Identifikasi & perbaikan area lemah (TWK, TIU, TKP).
- `JTBD-SIMULATION-001`: Simulasi CAT kondisi nyata.
- `JTBD-AI-TUTOR-001`: Penjelasan personal untuk jawaban salah.
- `JTBD-COMPETITION-001`: Benchmark performa & naikin ranking.

## 5. Pain Points
- `PAIN-GENERIC-FEEDBACK-001`: Feedback generik, bukan personal.
- `PAIN-UI-LAG-001`: UI CAT lambat / nggak akurat.
- `PAIN-INACCURATE-SOAL-001`: Soal nggak sesuai standar BKN.
- `PAIN-COST-VALUE-001`: Paket premium mahal, nilai tambah kurang.

## 6. Value Proposition
- **AI-Driven Mastery**: Latihan personal + penjelasan AI (Google NotebookLLM).
- **Real-time CAT**: Simulasi identik BKN.
- **Competitive Edge**: Leaderboard musiman (Monthly Season).

## 7. Fitur Produk (Scope)

### 7.1 Core Capabilities (MVP)
- **Practice Modules**: TWK, TIU, TKP.
- **CAT Simulation**: UI persis BKN, timer, navigasi soal.
- **Performance Analytics**: Heatmap mastery, skor trends.
- **AI Tutor**: Chat tanya-jawab, penjelasan kontekstual.
- **Leaderboard**: Ranking nasional, reset bulanan.

### 7.2 AI Features
- `AI-TUTOR-CHAT-001`: Tanya soal → AI jelasin + referensi materi (NotebookLLM).
- `AI-ADAPTIVE-PLAN-001`: Analisis performa → AI buat rencana belajar fokus kelemahan.
- `AI-PERF-ANALYSIS-001`: Prediksi skor + identifikasi area kritis.

### 7.3 Use Case
- `UC-STUDENT-DRILL-001`: User lemah TIU Analogy → Drill mode → AI Tutor jelasin → User retry.
- `UC-LIVE-COMPETITION-001`: User ikut CAT musiman → Skor tinggi → Ranking naik → Motivasi.

## 8. AI & Teknis

### 8.1 Tech Stack
| Layer | Teknologi |
| :--- | :--- |
| Backend | Laravel 13 (API-first) |
| Admin | Filament v4 |
| Database | PostgreSQL |
| Cache/Leaderboard | Redis |
| AI Tutor | Google NotebookLM (MVP) → RAG sendiri (Phase 2) |
| OCR | Google Vision API |
| Format Soal | GPT-4o-mini |
| Frontend | TBD (Vue/React/Blade) |

### 8.2 Flow Data Soal
1. Foto Guru → OCR (Google Vision) → Teks.
2. Teks → LLM (GPT-4o-mini) → JSON (Soal, Opsi, Kunci).
3. SME Review → Approve.
4. Masuk Database + NotebookLM (untuk AI Tutor).

### 8.3 Biaya AI Estimasi (1000 user/bulan)
| Item | Biaya |
| :--- | :--- |
| NotebookLM | **Rp 0** (Gratis) |
| Google Vision OCR | ~Rp 50.000 |
| GPT-4o-mini (format) | ~Rp 150.000 |
| **Total** | **~Rp 200.000/bulan** |

### 8.4 NFR
- Scalability: 1000+ concurrent user.
- Security: PII terenkripsi.
- Usability: Intuitif, mobile-first.

## 9. Go-to-Market

### 9.1 Pricing
| Paket | Harga | Fitur |
| :--- | :--- | :--- |
| **Free** | Rp0 | 3x tryout, basic analytics. |
| **Pro** | Rp59.000/bln | Unlimited tryout, AI Tutor, Drill Mode, Heatmap. |
| **Pro Season** | Rp149.000/3 bln | Pro + Priority AI Tutor. |
| **Premium** | Rp199.000/1 thn | Pro + Video Pembahasan + Bank Soal Premium. |

### 9.2 Phased Rollout
- **Phase 1 (Beta)**: CAT Sim + AI Tutor dasar + Leaderboard.
- **Phase 2 (Public)**: Adaptive path + Bank soal premium.
- **Phase 3 (Scale)**: Mobile app + AI generate soal.

### 9.3 Kompetitor Analysis
- **SMARTCASN**: Jago ranking nasional, tapi kurang AI.
- **JadiASN**: Punya live class & journey, tapi mahal.
- **AYOCPNS**: Fokus bimbel, bukan teknologi.
- **Kita**: AI Tutor jadi *unfair advantage*.

### 9.4 Marketing
- Partnership: Kampus karir center, influencer pendidikan.
- Social: CPNS aspirant communities.
- Model: Freemium (basic free, advanced AI premium).

## 10. Risk & Mitigasi
| Risiko | Mitigasi |
| :--- | :--- |
| AI Tutor halusinasi | Pakai NotebookLM (source verified). |
| Soal nggak akurat | SME review wajib. |
| Server down saat ramai | Redis cache + VPS scalable. |
| NotebookLM rate limit | Migrasi ke RAG sendiri saat user banyak. |

## 11. Lampiran
- Link referensi CAT repo.
- Link referensi NotebookLM.
- Link referensi AI pricing.