# analog-sensor
في هذه المهمة سنقوم بتصميم دائرة كهربائية لحساس الحراره lm35 

اول خطوة سنقوم بفتح موقع tinkercad 

ثانيا نبحث عن القطع المطلوبه لتنفيذ الدائرة ( الاردوينو مع البورد - حساس TMP)

الان سنبدء علمية التوصيل مع الاردوينو ، نضع حساس الحراره في منتصف البورد و نقوم بتوصيل Power مع الجزء الموجب من البورد و GND مع الجزء السالب من البورد و Vout مع A0 من الاردوينو   

<img src=https://user-images.githubusercontent.com/108413904/181600029-c04a86d1-2a20-48ff-90a5-ebce06f9f3dd.png >

بعد ذلك نقوم باضافة الكود لتشغيل الدائرة 

int sensorPin = 0;
 
void setup()
{
  Serial.begin(9600);
}
 
void loop()
{
 
 int reading = analogRead(sensorPin);
 // measure the 5v with a meter for an accurate value
 //In particular if your Arduino is USB powered
 float voltage = reading * 4.68;
 voltage /= 1024.0;
 
 // now print out the temperature
 float temperatureC = (voltage - 0.5) * 100;
 Serial.print(temperatureC);
 Serial.println(" degrees C");
 
 delay(1000);
}
