# digital-sensor

تصميم دائرة كهربائية لـ push buttom

اول خطوة سنقوم بفتح موقع tinkercad

ثاني خطوة نبحث عن القطع المطلوبة ( pushbutton - مقاومة 220 اوم - مقاومة 10 كيلو اوم - led - اردوينو مع بورد  ) 

نضع pushbutton في منتصف البورد و نضع led  في مكان اخر من البورد 

نقوم بتوصيل الطرف السالب من led بالجزء السالب من البورد و الجزء الموجب نوصله مع مقاومة 220 اوم مع D13 من الاردوينو 

اما بالنسبة للpushbutton نوصل terminal 1a مع الجزء الموجب من البورد و نوصل terminal 2a مع مقاومة 10 كيلو اوم و ايضا نوصله مع D2 من الاردوينو  
( الطرف الاخر من المقاومة 10 كيلو يكون موصل مع الطرف السالب من البورد ) 

<img src=https://user-images.githubusercontent.com/108413904/181605396-bed1fdb4-83ed-4465-8860-352fb2408cc5.png >

الان بعد التوصيل نضيف الكود لتشغيل الدائرة 

void setup()
{

  pinMode(2, INPUT);
  
  pinMode(13, OUTPUT);
  
}

void loop()

{

  if (digitalRead(2) == HIGH) {
  
    digitalWrite(13, HIGH);
    
  } else {
  
    digitalWrite(13, LOW);
    
  }
  
  delay(10); // Delay a little bit to improve simulation performance
  
}

