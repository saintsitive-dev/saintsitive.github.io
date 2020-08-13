---
title: C# 8.0
tags: C#
---

![c# and switch case expression](c-sharp-8/csharp-8.png)

เรื่องมันเริ่มมาจาก เมื่อคืนลง extension ใน visual studio code แล้วพบว่า warning งอกทั่วทุกหัวระแหงก่อนจะค่อยๆ rebuild แล้วกลับเป็นปกติยกเว้นบางไฟล์ที่ยังแดงเถือกไม่หาย และ 1 ในนั้นก็พาให้เราไปเจอกับ code ชุดนึงเข้า

![unreachable code](c-sharp-8/unreachable-break.png)

## มีคนวาง break ไว้หลัง return

ใจดำอำมหิตอะไรเยี่ยงนี้ 5555 break จะไม่มีวันได้เห็นเดือนเห็นตะวัน ไม่มีวันได้สัมผัสการ debug ใดใด เพราะ cursor ทั้งหลายจะโดน return ดีดออกจาก method ไปจนหมด

### แต่ก่อนจะใจบุญลบ code ออกไป สมองดันสงสัยซะก่อน

แต่ switch case มันใช้กับ break และ default นี่หว่า 4 สหายที่ใช้กันมาแต่โบราณกาล แล้วถ้าไม่มี break ทิ้งไว้แค่ return มันจะได้เหรอ มันทำงานคนละอย่างกันเลยนะ...

*(สาระ - break จะดีดเราออกจาก switch case แล้วไปต่อบรรทัดล่างของ method นี้ ในขณะที่ return จะดีดเราออกจาก method ไปเลย)*

งั้น use case ที่ใช้ switch case + return นี่มันใช้กับอะไรละเนี่ย พอสงสัยก็เลยเริ่มเซิสค่ะ แต่พอเซิสกลับพบว่ามันมีรูปแบบการเขียน switch case ใหม่ๆโผล่อีกมากมาย และจุดเปลี่ยนล่าสุดแห่งวงการ switch case ก็เป็น feature ที่ปรับ concept ของ switch case ที่มาพร้อมกับ C# version 8.0 ที่เพิ่งจุดระเบิดเปิดตัวไปเมื่อไม่นานนี้เอง

From Statement to Expression

switch case new style