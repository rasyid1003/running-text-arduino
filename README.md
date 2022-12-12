# running-text-arduino
## Authors

- [Faris Rasyid](http://farisrasyid.my.id)


## Diagram
Codingan Yg Berfungsi Untuk Membuat Running Text Sederhana Dengan Board Arduino
![image](https://user-images.githubusercontent.com/85282829/207043395-fa96f813-8adf-47fc-b796-c799b72568d0.png)
## Codingan

#include <LiquidCrystal_I2C.h>

int totalColumns = 16;
int totalRows = 2;

LiquidCrystal_I2C lcd(0x27, totalColumns, totalRows);  

String staticMessage = "Faris Rasyid";
String scrollingMessage = "Selamat Datang.";

void scrollMessage(int row, String message, int delayTime, int totalColumns) {
  for (int i=0; i < totalColumns; i++) {
    message = " " + message;  
  } 
  message = message + " "; 
  for (int position = 0; position < message.length(); position++) {
    lcd.setCursor(0, row);
    lcd.print(message.substring(position, position + totalColumns));
    delay(delayTime);
  }
}

void setup(){
  lcd.init();                    
  lcd.backlight();
}

void loop(){
  lcd.setCursor(0, 0);
  lcd.print(staticMessage);
  scrollMessage(1, scrollingMessage, 250, totalColumns);
}


## Feedback

Follow Saya Di Instagram ❤️[Faris_Rasyid❤️](https://www.instagram.com/_farisrasyid_/)

## License

Copyright (c) [2022] [Faris Rasyid]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

