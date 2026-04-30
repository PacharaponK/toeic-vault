# 📚 TOEIC Study Vault — คู่มือการใช้งาน

> ระบบเรียน TOEIC ด้วย Claude Code + Obsidian  
> เป้าหมาย: TOEIC 800+

---

## โครงสร้าง Vault

```
TOEIC-Vault/
├── Grammar/
│   ├── Rules/          ← ทฤษฎีทุกบท (01–17)
│   ├── Exercises/      ← แบบฝึกหัด (สร้างใหม่ทุกวัน)
│   └── Grammar-Index.md
├── Vocabulary/
├── Reading/
├── Listening/
├── Daily/              ← daily notes + scores
├── Logs/               ← บันทึก session ทุกวัน
├── Templates/
│   └── daily-template.md
├── Dashboard.md
├── CLAUDE.md
└── README.md           ← ไฟล์นี้
```

---

## วิธีเริ่ม Session ทุกวัน

```bash
cd ~/Documents/TOEIC-Vault
claude
```

---

## Phase 5 — Daily Workflow (ทำทุกวัน)

### Step 1 — สร้าง Daily Note เช้าวันใหม่

```
สร้าง daily note สำหรับวันนี้ใน Daily/[วันที่วันนี้].md
ใช้ template จาก Templates/daily-template.md
จากนั้นแนะนำว่าวันนี้ควรเรียนหัวข้อ Grammar บทไหน
โดยดูจากไฟล์ใน Grammar/Rules/ ว่าบทไหนยังไม่มี exercise
```

---

### Step 2 — สร้าง Grammar Exercise เชื่อมกับ Rules

> เปลี่ยน `[nn]` = เลขบท และ `[Topic]` = ชื่อบท เช่น `01` / `Tenses`

```
อ่านไฟล์ Grammar/Rules/[nn]-[Topic].md ให้ครบก่อน
แล้วสร้างแบบฝึกหัดใน Grammar/Exercises/[nn]-[Topic]-Ex[n].md

โจทย์ 10 ข้อ TOEIC Part 5 style ต้องครอบคลุมทุก sub-rule ในไฟล์นั้น
แต่ละข้อต้องมี:
- โจทย์ + 4 ตัวเลือก
- เฉลยพร้อมเครื่องหมาย ✅
- คำอธิบายภาษาไทย
- wikilink ไปยัง section ที่เกี่ยวข้องใน Rules note
  เช่น → [[Grammar/Rules/01-Tenses#present-perfect]]

หลังสร้างเสร็จ ให้ append wikilink ของไฟล์ exercise นี้
ลงใน section "แบบฝึกหัดที่เชื่อมกับบทนี้" ของ Rules note ด้วย
```

---

### Step 3 — สร้าง Vocabulary

```
สร้าง Vocabulary/Business-Day[n].md
คำศัพท์ Business English 5 คำสำหรับ TOEIC
แต่ละคำมี: ความหมายไทย, 2 ประโยคตัวอย่าง TOEIC-style,
synonyms 2–3 คำ, TOEIC frequency (High/Med/Low)
เพิ่ม tag #flashcard ทุกคำเพื่อใช้กับ Spaced Repetition plugin
```

---

### Step 4 — สร้าง Reading Practice

```
สร้าง Reading/[วันที่]-double-passage.md
TOEIC Part 7 double passage:
- Doc 1: Email เรื่อง [หัวข้อ] (150 คำ)
- Doc 2: Memo ตอบรับ (120 คำ)
- โจทย์ 5 ข้อ (ข้อ 5 ต้องใช้ข้อมูลจากทั้ง 2 docs)
- เฉลยพร้อม line reference
- คำศัพท์ยาก 3 คำ + link ไป Vocabulary/
```

---

### Step 5 — สร้าง Listening Script

```
สร้าง Listening/[วันที่]-Part3.md
TOEIC Part 3: บทสนทนา 3 คู่ ในออฟฟิศ
แต่ละบทสนทนา:
- Script 8–10 turns พร้อม [M] / [W] บอกผู้พูด
- โจทย์ 3 ข้อ (purpose / detail / next action)
- เฉลยพร้อมคำอธิบาย
- คำศัพท์สำคัญ 5 คำ → link ไป Vocabulary/
```

---

### Step 6 — บันทึก Score ลง Daily Note

```
อัปเดต score ใน Daily/[วันที่].md ดังนี้:
grammar_score: [x]/10
vocab_score: [x]/5
reading_score: [x]/5
listening_score: [x]/9
```

---

## Phase 6 — Conversation Log (ทำทุกวัน)

### ท้าย Session — บันทึก Log

> พิมพ์ก่อนปิด Terminal ทุกครั้ง

```
บันทึก log session นี้และแนะนำ session ต่อไป
```

Claude จะสร้าง `Logs/[วันที่]-session.md` อัตโนมัติ ประกอบด้วย:
- สรุปสิ่งที่ทำในวันนี้
- รายชื่อไฟล์ที่สร้างพร้อม path
- จุดที่ยังอ่อน
- คำแนะนำ session วันถัดไป

---

### เริ่ม Session ใหม่ — ต่อจากวันก่อน

```
อ่าน Logs/[วันที่เมื่อวาน]-session.md
สรุปว่าเมื่อวานทำอะไรไปแล้ว และวันนี้ควรเริ่มที่ไหน
```

---

### วิเคราะห์จุดอ่อนรายสัปดาห์ (ทำทุกวันอาทิตย์)

```
อ่าน Logs/ และ Daily/ ทั้งหมดใน 7 วันที่ผ่านมา
สรุปว่า:
1. หัวข้อไหนที่ score ต่ำกว่า 70% บ่อยที่สุด
2. คำหรือ pattern ไหนที่ปรากฏใน "จุดที่ยังไม่แม่น" ซ้ำหลายวัน
3. แนะนำ focus สัปดาห์หน้า
บันทึกผลการวิเคราะห์ลงใน Logs/weekly-[สัปดาห์].md
```

---

## Grammar Chapter Map

| บท | ไฟล์ | หัวข้อ | ออกสอบ |
|----|------|--------|--------|
| 01 | `Grammar/Rules/01-Tenses.md` | Tenses | ~18% |
| 02 | `Grammar/Rules/02-Verb-Forms.md` | Verb Forms | ~12% |
| 03 | `Grammar/Rules/03-Passive-Voice.md` | Passive Voice | ~10% |
| 04 | `Grammar/Rules/04-Conditionals.md` | Conditionals | ~8% |
| 05 | `Grammar/Rules/05-Articles.md` | Articles | ~10% |
| 06 | `Grammar/Rules/06-Prepositions.md` | Prepositions | ~12% |
| 07 | `Grammar/Rules/07-Conjunctions.md` | Conjunctions | ~8% |
| 08 | `Grammar/Rules/08-Pronouns.md` | Pronouns | ~8% |
| 09 | `Grammar/Rules/09-Adjectives-Adverbs.md` | Adjectives & Adverbs | ~10% |
| 10 | `Grammar/Rules/10-Comparatives.md` | Comparatives | ~6% |
| 11 | `Grammar/Rules/11-Relative-Clauses.md` | Relative Clauses | ~7% |
| 12 | `Grammar/Rules/12-Noun-Clauses.md` | Noun Clauses | ~6% |
| 13 | `Grammar/Rules/13-Subject-Verb-Agreement.md` | S-V Agreement | ~8% |
| 14 | `Grammar/Rules/14-Word-Forms.md` | Word Forms | ~15% |
| 15 | `Grammar/Rules/15-Modals.md` | Modals | ~8% |
| 16 | `Grammar/Rules/16-Reported-Speech.md` | Reported Speech | ~5% |
| 17 | `Grammar/Rules/17-Parallel-Structure.md` | Parallel Structure | ~7% |

---

## หมายเหตุสำคัญ

- **ทุกครั้งที่เปิด Terminal ใหม่** ต้อง `cd` เข้า vault folder ก่อนรัน `claude` เสมอ
- **CLAUDE.md** ต้องอยู่ใน root ของ vault — Claude Code จะอ่านอัตโนมัติทุก session
- **Obsidian** ต้องเปิดค้างไว้เพื่อดูไฟล์ที่ Claude Code สร้างแบบ real-time
- **Dashboard.md** ดูใน Reading view (Ctrl/Cmd+E) เพื่อให้ Dataview แสดงผล