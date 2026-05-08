---
type: dashboard
---

# 🏠 TOEIC Study Dashboard

## 📊 คะแนน 7 วันล่าสุด
```dataview
TABLE part5_score AS "Part 5",
      part6_score AS "Part 6",
      part7_score AS "Part 7"
FROM "Daily"
WHERE type = "daily" AND date >= date(today) - dur(7 days)
SORT date DESC
```

## 📈 บทที่ยังไม่มีแบบฝึกหัด
```dataview
LIST topic
FROM "Grammar/Rules"
WHERE length(file.inlinks) = 0
```

## ✏️ Grammar Exercises ล่าสุด
```dataview
TABLE topic, date, score, linked_rule AS "Rules Note"
FROM "Grammar/Exercises"
WHERE score != null
SORT date DESC
LIMIT 8
```

## 🎧 Listening ล่าสุด
```dataview
TABLE toeic_part AS "Part", conversations AS "บทสนทนา", score AS "คะแนน"
FROM "Listening"
WHERE type = "listening-script"
SORT date DESC
LIMIT 5
```

## 📋 Session Logs ล่าสุด
```dataview
TABLE topics_covered, weak_points
FROM "Logs"
WHERE type = "session-log"
SORT date DESC
LIMIT 5
```
