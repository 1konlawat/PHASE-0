นี่คือเวอร์ชัน Markdown เต็ม ๆ — Copy ได้เลย

# 📌 Pandas — ฟังก์ชันแกนหลักที่ควรรู้ (Scope ใช้งานจริง)

---

## 1) `groupby` + `agg` — การสรุปข้อมูลแบบจัดกลุ่ม

**ใช้เมื่อ:**  
- ต้องการจัดกลุ่มข้อมูล เช่น ตาม `City`, `CustomerID`  
- ต้องการหาค่าสถิติ เช่น `mean()`, `sum()`, `count()`

**ตัวอย่าง**
```python
df.groupby('City')['Age'].mean()
df.groupby('City').agg({'Age':'mean', 'Salary':'sum'})


⸻

2) merge — รวมข้อมูลจากหลายตาราง

ใช้เมื่อ:
	•	มี DataFrame หลายชุด และต้องรวมเข้าด้วยกันตามคีย์ร่วม เช่น ID

ตัวอย่าง

pd.merge(df1, df2, on='ID', how='left')


⸻

3) apply + lambda — คำนวณหรือสร้างคอลัมน์แบบ custom

ใช้เมื่อ:
	•	เงื่อนไขการคำนวณซับซ้อนเกินกว่าใช้ .map() หรือฟังก์ชันสำเร็จรูป

ตัวอย่าง

df['Group'] = df['Age'].apply(lambda x: 'Teen' if x < 18 else 'Adult')


⸻

4) Filtering — เลือกแถวตามเงื่อนไข (2 วิธี)

✅ วิธีที่ 1: Boolean Filter

df[df['Age'] > 30]

✅ วิธีที่ 2: .query() (อ่านคล้าย SQL)

df.query("Age > 30 and City == 'London'")

Note: ทั้งคู่ทำงานเหมือนกัน แต่ query อ่านง่ายขึ้นเมื่อเงื่อนไขยาว

⸻

5) Sorting & Ranking — จัดเรียงและจัดอันดับข้อมูล

Sorting

df.sort_values('Age', ascending=False)

Ranking

df['Rank'] = df['Age'].rank(ascending=False)


⸻

🔖 Summary Map

ฟังก์ชัน	หน้าที่	ใช้เมื่อ
groupby + agg	สรุปข้อมูลตามกลุ่ม	วิแยกตามเมือง/ประเภท ฯลฯ
merge	รวมตาราง	ดึงข้อมูลข้ามไฟล์/ตาราง
apply + lambda	สร้าง logic เฉพาะเอง	กรณีไม่มีฟังก์ชันตรงตัว
Filter / Query	เลือกข้อมูลตามเงื่อนไข	คัดเฉพาะแถวที่ต้องการ
Sort / Rank	จัดเรียง & จัดอันดับ	ทำรายงาน/จัดลำดับ


⸻

✅ สรุปสั้น ๆ

ถ้าทำ Data Analysis จริง ๆ — รู้ 5 ชุดนี้ = ทำงานได้ 80% แล้ว

⸻


