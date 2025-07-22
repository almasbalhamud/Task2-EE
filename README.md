# 🔧 التحكم في 6 محركات سيرفو باستخدام الأردوينو
##هذا المشروع يوضح طريقة التحكم المتزامن في 6 محركات سيرفو باستخدام لوحة أردوينو. تقوم المحركات بالحركة ذهابًا وإيابًا بين الزاويتين 0° و180° لمدة ثانيتين فقط، ثم تتوقف عند الزاوية 90° وتظل ثابتة

# � الأدوات المستخدمة في المحاكي
•	لوحة Arduino UNO
•عدد 6 محركات سيرفو
•أسلاك توصيل
 # 💻 الكود 
 #include <Servo.h>
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;
Servo servo5;
Servo servo6;

int pos = 0;
unsigned long startTime;

void setup() {
  servo1.attach(3);
  servo2.attach(4);
  servo3.attach(5);
  servo4.attach(6);
  servo5.attach(7);
  servo6.attach(8);
  startTime = millis();
}

void loop() {
  if (millis() - startTime <= 2000) {
    for (pos = 0; pos <= 180; pos++) {
      servo1.write(pos);
      servo2.write(pos);
      servo3.write(pos);
      servo4.write(pos);
      servo5.write(pos);
      servo6.write(pos);
      delay(5);
    }
    for (pos = 180; pos >= 0; pos--) {
      servo1.write(pos);
      servo2.write(pos);
      servo3.write(pos);
      servo4.write(pos);
      servo5.write(pos);
      servo6.write(pos);
      delay(5);
    }
  } else {
    servo1.write(90);
    servo2.write(90);
    servo3.write(90);
    servo4.write(90);
    servo5.write(90);
    servo6.write(90);
    while (true);
  }
}
# 🔌 طريقة التوصيل
<img width="723" height="637" alt="image" src="https://github.com/user-attachments/assets/7f07301b-ef3c-4873-8aae-fe095200f60f" />
# ✅ النتائج المتوقعة
عند تشغيل المحاكاة:
	1.	تبدأ محركات السيرفو الستة بالحركة بشكل متزامن من الزاوية 0° إلى 180°.
	2.	بعد الوصول إلى 180°، تعود المحركات تدريجيًا إلى 0°.
	3.	تستمر هذه الحركة ذهابًا وإيابًا لمدة ثانيتين فقط.
	4.	بعد مرور الثانيتين، تتوقف كل المحركات تلقائيًا وتثبت عند الزاوية 90° .
	5.	يتوقف البرنامج عن تنفيذ أي أوامر إضافية، وتظل المحركات ثابتة .
