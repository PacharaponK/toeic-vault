---
type: dashboard
---

# 🏠 TOEIC Study Dashboard

## 📊 คะแนน 7 วันล่าสุด
```dataview
TABLE grammar_score AS "Grammar",
      vocab_score AS "Vocab",
      reading_score AS "Reading",
      listening_score AS "Listening"
FROM "Daily"
WHERE type = "daily" AND date >= date(today) - dur(7 days)
SORT date DESC
```

## 📈 ค่าเฉลี่ยรายทักษะ
```dataview
TABLE WITHOUT ID
  round(average(rows.grammar_score)) AS "Grammar avg",
  round(average(rows.vocab_score)) AS "Vocab avg",
  round(average(rows.reading_score)) AS "Reading avg",
  round(average(rows.listening_score)) AS "Listening avg"
FROM "Daily"
WHERE type = "daily" AND grammar_score != null
GROUP BY true
```

## ✏️ Grammar Exercises ล่าสุด
```dataview
TABLE topic, date, score, linked_rule AS "Rules Note"
FROM "Grammar/Exercises"
WHERE score != null
SORT date DESC
LIMIT 8
```

## ❌ บทที่ยังไม่มีแบบฝึกหัด
```dataview
LIST topic
FROM "Grammar/Rules"
WHERE length(file.inlinks) = 0
```

## 📋 Session Logs ล่าสุด
```dataview
TABLE topics_covered, files_created, weak_points
FROM "Logs"
WHERE type = "session-log"
SORT date DESC
LIMIT 5
```
