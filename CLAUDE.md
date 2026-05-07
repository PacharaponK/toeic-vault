# CLAUDE.md — TOEIC Study Vault

## Project Context
- Vault path: ~/Documents/TOEIC-Vault
- Study goal: TOEIC 800+
- Language for explanations: Thai (ภาษาไทย)
- Language for content/examples: English

## Folder Structure Rules
- Grammar rules (ทฤษฎี) → Grammar/Rules/[nn]-[Topic].md
- Grammar exercises Part 5 (แบบฝึกหัด) → Grammar/Exercises/Part5/[nn]-[Topic]-Ex[nn].md
- Grammar exercises Part 6 (text completion) → Grammar/Exercises/Part6/Part6-Ex[nn].md
- Vocabulary → Vocabulary/[Category].md
- Reading practice → Reading/[YYYY-MM-DD]-[type].md
- Daily notes → Daily/[YYYY-MM-DD].md
- Session logs → Logs/[YYYY-MM-DD]-session.md

## Frontmatter Requirements

### Every Grammar/Rules/ file must have:
---
topic: [name]
chapter: [nn]
type: rules
toeic_parts: [5, 6]
exercises: []
last_reviewed:
---

### Every Grammar/Exercises/ file must have:
---
topic: [name]
chapter: [nn]
type: exercise
exercise_num: [n]
date: [YYYY-MM-DD]
score:
linked_rule: "[[[nn]-[Topic]]]]"
---

### Every Daily note must have:
---
date: [YYYY-MM-DD]
type: daily
part5_score:
part6_score:
part7_score:
topics_studied: []
---

### Every Logs/ file must have:
---
date: [YYYY-MM-DD]
type: session-log
session_num: [n]
topics_covered: []
files_created: []
weak_points: []
---

## Exercise Rules (IMPORTANT)
- ห้ามแสดงเฉลย (✅ หรือ correct answer) ปะปนกับตัวเลือก (A)(B)(C)(D) เด็ดขาด
- เฉลยและคำอธิบายต้องอยู่ใน section แยก ถัดจากส่วนโจทย์ทั้งหมด
- ต้องมีตารางให้ผู้ใช้บันทึกคำตอบของตัวเองก่อนเปิดดูเฉลย

## Linking Rules (IMPORTANT)
1. ทุก Exercise ต้องมี section "## 📖 อ้างอิงทฤษฎี" 
   พร้อม wikilink [[Grammar/Rules/nn-Topic]]
2. คำอธิบายแต่ละข้อต้องมี link ไปยัง section ที่เกี่ยวข้อง
   เช่น [[Grammar/Rules/01-Tenses#present-perfect]]
3. หลังสร้าง Exercise ทุกครั้ง ให้ append wikilink ของ Exercise
   นั้นลงใน section "แบบฝึกหัดที่เชื่อมกับบทนี้" ของ Rules note
4. ใช้ Obsidian wikilinks [[...]] เสมอ ห้ามใช้ markdown links

## Session Logging
เมื่อผู้ใช้พิมพ์ "บันทึก log" หรือ "log session":
สร้าง/อัปเดต Logs/[วันนี้]-session.md ให้มี:
- สรุปสิ่งที่ทำในวันนี้
- รายชื่อไฟล์ที่สร้างพร้อม path
- หัวข้อที่ครอบคลุม
- จุดที่ผู้ใช้ยังอ่อน (ถ้ามีข้อมูล)
- คำแนะนำ session ถัดไป

## Chapter Map
01-Tenses | 02-Verb-Forms | 03-Passive-Voice
04-Conditionals | 05-Articles | 06-Prepositions
07-Conjunctions | 08-Pronouns | 09-Adjectives-Adverbs
10-Comparatives | 11-Relative-Clauses | 12-Noun-Clauses
13-Subject-Verb-Agreement | 14-Word-Forms
15-Modals | 16-Reported-Speech | 17-Parallel-Structure
