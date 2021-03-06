# 🥰 เทคนิคในการออกแบบ

![Image by Alexas\_Fotos on Pixabay](../../.gitbook/assets/image%20%28344%29.png)

หลังจากที่ได้เห็นตัวอย่างในการนำหลัก **\(OOP\) Object-Oriented Programming** ไปใช้ในการเขียนโค้ดของเราแล้ว ซึ่งจะเห็นว่าการออกแบบที่ดีนั้นทรงพลังอย่างมาก เพราะมันจะช่วยให้เวลามีความต้องการใหม่ๆเข้ามาปุ๊ป เราอาจจะแก้ไขโค้ดนิดหน่อยก็ปิดงานได้แล้ว หรือถ้าโชคดีมากก็อาจจะไม่ต้องทำอะไรเลยงานก็ปิดทันทีนั่นเอง ดังนั้นในรอบนี้เราจะมีปิดท้ายกันในเรื่องเทคนิคในการนำ OOP ไปใช้กันบ้างนะ

## ❤️ หัวใจหลักของ OOP

หัวใจหลักของการนำ OOP ไปใช้คือทำให้ **โค้ดที่เรามีถูกเปลี่ยนแปลงแก้ไขได้ง่าย** เพราะ ปัญหาที่ใหญ่ที่สุดในวงการพัฒนาซอฟต์แวร์คือเรื่องของ **Maintenance** ยังไงล่ะ ซึ่งการที่เราจะทำให้โค้ดของเราสามารถทำเรื่องที่ว่าได้ ส่วนหนึ่งคือ **การออกแบบ** ดังนั้นเราไปดูกันว่าถ้าราอยากจะใช้ OO ให้ได้เต็มประสิทธิภาพจริงๆ มันมีเรื่องอะไรบ้างให้เราต้องเรียนรู้กัน

{% hint style="success" %}
**แนะนำให้อ่าน**  
ทำไมการทำ Maintenance ถึงเป็นเรื่องใหญ่ที่สุดในการทำซอฟต์แวร์ สามารถอ่านได้จากบทความด้านล่างนี้เบยครัช[ ปัญหาที่ใหญ่ที่สุดในการทำซอฟต์แวร์](https://saladpuk.gitbook.io/learn/v/tips/why-software-fail)
{% endhint %}

## ✔️ อย่าใช้ Inheritance มั่วซั่ว

หลายคนอ่านมาถึงจุดนี้ก็อาจจะ งงๆ เพราะ **Inheritance** เป็นหนึ่งในหัวใจหลักของ OOP เลยนิ แต่ทำไมไม่ให้เราใช้มันล่ะ?? ซึ่งถ้าเราจะเข้าใจถึงแก่นแท้ของ Tip เรื่องนี้ได้ เราต้องเข้าใจ `ข้อดี` และ `ข้อเสีย` ของการทำ Inheritance เสียก่อนนั่นเอง

### 👍 ข้อดีของ Inheritance

* เราสามารถลดโค้ดที่มันทำงานเหมือนๆกันได้ โดยใช้ Base class เป็นตัวจัดการนั่นเอง
* โค้ดถูกเพิ่มเติมความสามารถใหม่ๆเข้าไปได้ โดยที่ไม่ต้องไปแก้โค้ดเดิมเลย

### 👎 ข้อเสียของ Inheritance

* การทำ Inheritance ที่ถูกหลัก **มันทำยาก** เพราะต้องเข้าใจและแยกความสัมพันธ์แบบ **IS A** กับ **HAS A** ได้อย่างถูกต้อง ถึงจะ **มีโอกาสออกแบบได้ถูก** นั่นเอง ซึ่งในโจทย์จริงบางทีมันไม่ได้แยกกันได้ง่ายเหมือนในตัวอย่าง
* **เปลี่ยนแปลงแก้ไขยาก** ลองคิดดูว่าถ้าโค้ดเราใช้ Inheritance กับคลาสหลายๆตัว แต่อยู่มาวันหนึ่งเราพบว่า เราไม่ควรทำโครงสร้างแบบนั้น หรือ อยากแก้โครงสร้างพวกนั้นล่ะ มันอาจจะต้องไปไล่แก้เป็นร้อยๆคลาสเลยก็เป็นได้ แล้วถ้าเกิดเราทำเป็น Library ไว้ แล้วคนที่เอาไปใช้ต่อนี่ต้องมาคอยไล่แก้ตามโครงสร้างใหม่เราด้วยนะอย่าลืม
* **คนเอาไปใช้ต่อเอาไปใช้ยาก** ลองคิดดูว่าถ้าเราจะต้องไปใช้คลาสที่คนอื่นเขียนไว้เราใช้ได้เลยไหม? ซึ่งคำตอบส่วนใหญ่ก็คือต้องไปทำความเข้าใจมันก่อน แต่มันจะยิ่งยากขึ้นหลายเท่าเมื่อมันเป็นโครงสร้างแบบ Inheritance นั่นเอง

จากตรงนี้เราก็น่าจะเห็นภาพคร่าวๆกันละว่า ถ้าเราใช้ Inheritance ไม่ถูกหลักแล้วล่ะก็ มันจะทำให้โครงสร้างของโค้ดเราซับซ้อนโดยไม่จำเป็น แถมยังกระทบถึงคนอื่นๆที่เอาของพวกนั้นไปใช้ด้วยนั่นเอง ดังนั้นก่อนทำ Inheritance เราจะต้องเคลียความเข้าใจเรื่อง **IS A** และ **HAS A** ให้เรียบร้อย พร้อมกับ **มีเหตุผลที่ชัดเจนพอ** ที่จะนำมันมาใช้นั่นเอง

## ✔️ Composition over Inheritance

หนึ่งในหลักปฎิบัติในการออกแบบที่ดีคือ **การใช้ Composition แทนการใช้ Inheritance** เพราะของต่างๆที่เป็น Composition มันแก้ได้ง่ายกว่า Inheritance และโครงสรา้งพวกนี้ถ้าถูกแก้ มันจะกระทบกับส่วนอื่นๆน้อยกว่าความสัมพันธ์แบบ Inheritance นั่นเอง

โดยปรกติหลักในการทำ Inheritance จะบอกให้เราแบ่งของออกเป็นกลุ่มๆ แล้วเมื่อก็ตามที่มีของในกลุ่มเกิดมีการทำงานที่ไม่เหมือนเพื่อน เราก็จะใช้ Inheritance แตกมันออกไปเรื่อยๆนั่นเอง ซึ่งถ้าเราทำแบบนี้ไปเรื่อยๆมันจะเกิดปัญหาทีผมเรียกว่า **ความสัมพันธ์แห่งนรก** เพราะโครงสร้างของเราจะดูวุ่นวายฝุดๆ

### 😈 ความสัมพันธ์แห่งนรก

\(รอบนี้ขี้เกียจทำรูปเองขอใช้จาก [Wikipedia ](https://en.wikipedia.org/wiki/Composition_over_inheritance)เลยละกัน\) อย่างที่บอกไปว่าถ้าเราแบ่งของออกเป็นกลุ่มๆมันจะทำให้โครงสร้างมันซับซ้อนไปเรื่อยๆ เช่น **กลุ่มของเป็ด \(Duck\)** ซึ่งเป็ดแต่ละสายพันธ์ก็มีรูปร่างที่ไม่เหมือนกัน เช่น เป็ดน้ำ \(Mallard\), เป็ดหัวแดง \(Readhead\), เป็ดยาง \(Rubber\), เป็ดล่อเป้า \(Decoy\) ซึ่งเจ้าของพวกนี้เรามองว่ามันเป็นเป็ดทั้งหมดเลยทำ inheritance มันมาซะเลย

![](../../.gitbook/assets/image%20%2850%29.png)

อ่อ อย่าลืมนะว่าเป็ดแต่ละแบบมันร้องไม่เหมือนกันถ้าจะทำหลัก Inheritance จริงๆแล้วล่ะก็มันก็ต้องเป็นกลุ่มของมันเองนิน่า ดังนั้นก็จัดกลุ่มเรื่องของการ **ส่งเสียงร้อง** \(Ducklike\) ซึ่งเสียงร้องมีหลายแบบ \(Quackable\) ดังนั้นก็จัดเลย

![](../../.gitbook/assets/image%20%28853%29.png)

อ่อแล้วก็อย่าลืมนะว่าเป็ดมันมีปีกดังนั้นก็จะกลุ่มความสามารถของ **การบิน** \(Flyable\) ด้วยนะ ตามรูปด้านล่างเบย

![](../../.gitbook/assets/image%20%28583%29.png)

สุดท้ายก็เอาของต่างๆที่จัดกลุ่มมายำรวมกันก็จะได้โครงสร้างเป็ดรวมมิตรตามรูปด้านล่าง \(ของอื่นๆที่ไม่ได้อธิบายก็ปล่อยมันไปนะเดี๋ยวมันจะยาวกว่านี้\)

![https://en.wikipedia.org/wiki/Composition\_over\_inheritance](../../.gitbook/assets/image%20%28469%29.png)

แค่เห็นรูปด้านบนก็สยองแล้ว ความสัมพันธ์ต่างๆเต็มไปหมดเบย แล้วถ้าเราจะเพิ่มความสามารถใหม่ๆ หรือ กลุ่มใหม่ให้กับเจ้าเป็ดพวกนี้เราจะเริ่มที่ไหนต่อดีเอ่ย ?? นี่แหละคือสิ่งที่เรียกว่า **ความสัมพันธ์แห่งนรก**

### 🎎 **Composition**

แทนที่เราจะใช้ Inheritance รัวๆ เราก็หันมาใช้ **Composition** หรือที่เรียกว่าความสัมพันธ์แบบ **HAS A** จะทำให้โครงสร้างเราง่ายขึ้นเยอะเลย เช่น **กลุ่มของการบิน** และ **กลุ่มของการร้อง** เราก็ยังคงมีไว้เช่นเดิม ตามรูปด้านล่าง \(นึกว่าจะไม่ได้ทำรูปซะละสุดท้ายก็ได้ทำ -\_-''\)

![](../../.gitbook/assets/image%20%28799%29.png)

แต่เราจะมองเจ้า 2 กลุ่มนั้นเป็นแค่เพียง **ความสามารถ** ที่เป็น **คนละเรื่องกับเป็ด** นั่นเอง ดังนั้นมุมมองจะถูกเปลี่ยนไปเป็นตามรูปนี้ \(นึกว่าจะไม่ได้ทำรูปซะละสุดท้ายก็ได้ทำ -\_-''\)

![\(&#xE1E;&#xE27;&#xE01; members &#xE41;&#xE25;&#xE30; methods &#xE15;&#xE48;&#xE32;&#xE07;&#xE46;&#xE22;&#xE31;&#xE07;&#xE21;&#xE35;&#xE40;&#xE2B;&#xE21;&#xE37;&#xE2D;&#xE19;&#xE40;&#xE14;&#xE34;&#xE21;&#xE19;&#xE30; &#xE02;&#xE2D;&#xE40;&#xE02;&#xE35;&#xE22;&#xE19;&#xE22;&#xE48;&#xE2D;&#xE46;&#xE01;&#xE47;&#xE1E;&#xE2D;\)](../../.gitbook/assets/image%20%28931%29.png)

จากการเปลี่ยนความสัมพันธ์ในเชิง Inheritance ให้กลายมาเป็น Composition ตามรูปด้านบน มันจะทำให้การเกิด **Combinations** ได้มากมาย และที่สำคัญคือ **เราสามารถเปลี่ยนพฤติกรรมการทำงานของ object ได้ระหว่าง Runtime** เลยนั่นเอง

```csharp
// การร้อง 2 แบบ
var quack1 = new Quack(); // ร้องแคว๊กๆ
var quack2 = new Squeak(); // ร้องเสียงแหลม

// การบิน 2 แบบ
var fly1 = new CannotFly(); // บินไม่ได้
var fly2 = new FlyWithWings(); // บินด้วยปีก

// เป็ดหัวแดงที่ร้องแคว๊กๆ และ บินไม่ได้
Duck readHead = new RedheadDuck(fly1, quack1);

// เปลี่ยนพฤติกรรมให้มันสามารถบินได้ ระหว่าง Runtime
readHead.ChangeFlyBehaviour(flt2);
```

> ใน UML ด้านบนจะเปลี่ยนไม่ได้นะขี้เกียจแก้ละ ลองทำเป็น setter method ไว้ดูเอาละกัน

## ✔️ Guideline ในการทำ Inheritance

* **อย่าใช้มันเลย**ถ้าไม่จำเป็นจริงๆ 
* ถ้าจำเป็นต้องใช้จริงๆ ให้ลองคิดในมุมของ **Composition** เสียก่อน ซึ่งถ้าใช้แทนกันได้ ขอแนะนำว่าให้ทำเป็น Composition จะดีกว่า
* ดูความถูกต้องก่อนทำ Inheritance เช่น รถตักดิน สามารถ inherit มาจาก กลุ่มของรถยนต์ ได้ เพราะมันเป็นรถยนต์ แต่ รถไฟเหาะตีลังกา มันไม่ใช่รถยนต์ ดังนั้นอย่าเอามันมา inherit เชียว เพราะมันอยู่กันคนละกลุ่มกัน
* ถ้าต้องทำจริงๆ เจ้าคลาสลูกที่กำลังจะสร้างมันจะต้อง **มีความแตกต่างจากคลาสแม่** และความแตกต่างนั้นจะต้อง **ไม่เป็นการทำลายหัวใจหลักของคลาสแม่** เด็ดขาด เช่น **กลุ่มของรถยนต์ดีเซล** เราไม่สามารถเอา **รถใช้ไฟฟ้า** มาเป็นคลาสลูกได้ เพราะมันทำลายหัวใจในการ ใช้น้ำมัน ของคลาสแม่นั่นเอง

## 🎯 บทสรุป

ขอพูดปิดท้ายแบบง่ายๆว่า **อย่าเมากาว** ตะบี้ตะบันเอาสิ่งที่ได้เรียนไปใช้มันทุกที่ จนกว่าเราจะเข้าใจมันอย่างถ่องแท้ เพราะไม่อย่างนั้นโครงสร้างของโปรเจคมันจะมั่ว พอนานวันไปถ้าจะแก้ก็จะยิ่งยาก เพราะมันผูกติดกันไปหมดตามที่เขียนไว้ด้านบนนั่นเอง

