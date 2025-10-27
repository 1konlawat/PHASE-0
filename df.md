# กรณีที่ 5 — ใช้ apply เมื่อเงื่อนไขซับซ้อนและไม่มี vectorized ที่เหมาะ

ใน pandas เราควรใช้ vectorized ให้มากที่สุดเพราะเร็ว ชัด และลด bug  
แต่มีบางกรณีที่ “ไม่มี vectorized solution ที่อ่านง่าย” เช่น logic หลายชั้น, อ่านหลายคอลัมน์พร้อมกัน, ได้ผลลัพธ์เป็นข้อความ

## ตัวอย่างโจทย์
สร้างคอลัมน์ `Remark` ตามเงื่อนไขซับซ้อน:

- ถ้า `Liked == "Yes"` และ `Total Rating >= 15` → `"Popular & High Rated"`
- ถ้า `Liked == "Yes"` แต่ `Total Rating < 15` → `"Popular but Moderate"`
- ถ้า `Liked == "No"` และ `Total Rating >= 10` → `"Not Liked but Decent"`
- อื่น ๆ → `"Weak & Not Liked"`

## โค้ด (apply + lambda)

```python
def remark_row(x):
    if x["Liked"] == "Yes" and x["Total Rating"] >= 15:
        return "Popular & High Rated"
    elif x["Liked"] == "Yes" and x["Total Rating"] < 15:
        return "Popular but Moderate"
    elif x["Liked"] == "No" and x["Total Rating"] >= 10:
        return "Not Liked but Decent"
    else:
        return "Weak & Not Liked"

df["Remark"] = df.apply(lambda x: remark_row(x), axis=1)
