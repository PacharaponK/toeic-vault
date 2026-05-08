 # 📚 TOEIC Study Vault — คู่มือการใช้งาน

> ระบบเรียน TOEIC ด้วย Claude Code + Obsidian  
> เป้าหมาย: TOEIC 800+

---

## โครงสร้าง Vault

```
TOEIC-Vault/
├── Grammar/
│   ├── Rules/              ← ทฤษฎีทุกบท (01–17)
│   ├── Exercises/
│   │   ├── Part5/          ← แบบฝึกหัด Part 5  [nn]-[Topic]-Ex[nn].md
│   │   ├── Part6/          ← Text Completion Part 6  Part6-Ex[nn].md
│   │   └── Part7/          ← Reading Comprehension Part 7  Part7-Ex[nn].md
│   └── Grammar-Index.md
├── Vocabulary/
│   └── sentence-mining-log.md  ← บันทึกคำศัพท์ + my sentence ทุกวัน
├── Listening/              ← Listening practice Part 3/4
├── Daily/                  ← daily notes + scores
├── Logs/                   ← บันทึก session ทุกวัน
├── Templates/
│   └── daily-template.md
├── Dashboard.md
├── CLAUDE.md
└── README.md               ← ไฟล์นี้
```

---

## วิธีเริ่ม Session ทุกวัน

```bash
cd ~/Documents/TOEIC-Vault
claude
```

---

## Phase 5 — Daily Workflow (ทำทุกวัน)

### เริ่ม Session ใหม่ — ต่อจากวันก่อน

```
อ่าน Logs/[วันที่เมื่อวาน]-session.md
สรุปว่าเมื่อวานทำอะไรไปแล้ว และวันนี้ควรเริ่มที่ไหน
```

---

### Step 1 — สร้าง Daily Note เช้าวันใหม่

```
สร้าง daily note สำหรับวันนี้ใน Daily/[วันที่วันนี้].md
ใช้ template จาก Templates/daily-template.md
จากนั้นแนะนำว่าวันนี้ควรเรียนหัวข้อ Grammar บทไหน
โดยดูจากไฟล์ใน Grammar/Rules/ ว่าบทไหนยังไม่มี exercise
```

---

### Step 2 — สร้าง Grammar Exercise (Part 5)

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

### Step 3 — สร้าง Text Completion Exercise (Part 6)

```
สร้าง Grammar/Exercises/Part6-Ex[n].md
TOEIC Part 6 Text Completion (เลือกหัวข้อบทความได้อิสระ):
- บทความ/อีเมล/ประกาศ ยาว 130–150 คำ มี 4 ช่องว่าง (131), (132), (133), (134)
- แต่ละช่องว่างมีตัวเลือก (A)(B)(C)(D) 4 ตัว
  - บางข้อทดสอบ grammar (verb form, tense, passive, connector)
  - บางข้อทดสอบ vocabulary (word choice in context)
  - 1 ข้อในนั้นต้องเป็น sentence insertion (เลือกประโยคทั้งประโยคที่เชื่อมเนื้อหาได้ดีที่สุด)
- เฉลยแต่ละข้อต้องมี wikilink ไปยัง Rules note ที่เกี่ยวข้อง
  เช่น → [[Grammar/Rules/03-Passive-Voice#passive--modal-verbs]]
- เฉลยพร้อมคำอธิบายภาษาไทยอยู่ใน section แยกถัดจากโจทย์ทั้งหมด
- ต้องมีตารางบันทึกคำตอบก่อนเปิดดูเฉลย
```

---

### Step 4 — สร้าง Reading Practice (Part 7)

```
สร้าง Grammar/Exercises/Part7/Part7-Ex[nn].md
TOEIC Part 7 (single หรือ double passage):
- Double: Doc 1 Email (150 คำ) + Doc 2 Memo (120 คำ)
- Single: Passage เดียว (150–200 คำ)
- โจทย์ 5 ข้อ (double passage: ข้อ 5 ต้องใช้ข้อมูลจากทั้ง 2 docs)
- เฉลยพร้อม line reference
- คำศัพท์ยาก 3 คำ + link ไป Vocabulary/
- บันทึกคำศัพท์ใหม่ลงใน Vocabulary/sentence-mining-log.md ด้วย
```

---

### Step 5 — บันทึก Score ลง Daily Note

```
อัปเดต score ใน Daily/[วันที่].md ดังนี้:
part5_score: [x]/10
part6_score: [x]/4
part7_score: [x]/5
topics_studied: [ชื่อหัวข้อที่เรียนวันนี้]
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

| บท  | ไฟล์                                         | หัวข้อ               | ออกสอบ |
| --- | -------------------------------------------- | -------------------- | ------ |
| 01  | `Grammar/Rules/01-Tenses.md`                 | Tenses               | ~18%   |
| 02  | `Grammar/Rules/02-Verb-Forms.md`             | Verb Forms           | ~12%   |
| 03  | `Grammar/Rules/03-Passive-Voice.md`          | Passive Voice        | ~10%   |
| 04  | `Grammar/Rules/04-Conditionals.md`           | Conditionals         | ~8%    |
| 05  | `Grammar/Rules/05-Articles.md`               | Articles             | ~10%   |
| 06  | `Grammar/Rules/06-Prepositions.md`           | Prepositions         | ~12%   |
| 07  | `Grammar/Rules/07-Conjunctions.md`           | Conjunctions         | ~8%    |
| 08  | `Grammar/Rules/08-Pronouns.md`               | Pronouns             | ~8%    |
| 09  | `Grammar/Rules/09-Adjectives-Adverbs.md`     | Adjectives & Adverbs | ~10%   |
| 10  | `Grammar/Rules/10-Comparatives.md`           | Comparatives         | ~6%    |
| 11  | `Grammar/Rules/11-Relative-Clauses.md`       | Relative Clauses     | ~7%    |
| 12  | `Grammar/Rules/12-Noun-Clauses.md`           | Noun Clauses         | ~6%    |
| 13  | `Grammar/Rules/13-Subject-Verb-Agreement.md` | S-V Agreement        | ~8%    |
| 14  | `Grammar/Rules/14-Word-Forms.md`             | Word Forms           | ~15%   |
| 15  | `Grammar/Rules/15-Modals.md`                 | Modals               | ~8%    |
| 16  | `Grammar/Rules/16-Reported-Speech.md`        | Reported Speech      | ~5%    |
| 17  | `Grammar/Rules/17-Parallel-Structure.md`     | Parallel Structure   | ~7%    |

---

## หมายเหตุสำคัญ

- **ทุกครั้งที่เปิด Terminal ใหม่** ต้อง `cd` เข้า vault folder ก่อนรัน `claude` เสมอ
- **CLAUDE.md** ต้องอยู่ใน root ของ vault — Claude Code จะอ่านอัตโนมัติทุก session
- **Obsidian** ต้องเปิดค้างไว้เพื่อดูไฟล์ที่ Claude Code สร้างแบบ real-time
- **Dashboard.md** ดูใน Reading view (Ctrl/Cmd+E) เพื่อให้ Dataview แสดงผล