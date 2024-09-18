# Projeto_Final_de_Disciplina-0.2
-
-
![Editing Components (5)](https://github.com/user-attachments/assets/d251a4d8-96d5-4a81-b2b7-9fc3378847a8)
-
-
# Materiais
-
-
1 Fotorresistor
1 Fio de 10 k ohm
1 fio de 220 k ohm
1 Led
1 Protobord
-
-
# Código
-
-
int LED = 8;
void setup() {
  Serial.begin(9600);
  pinMode(LED, OUTPUT);
}
void loop() {
  int LDR = analogRead (A0);
  Serial.println(LDR);

  if(LDR<500)
   digitalWrite(LED, HIGH);
   else
     digitalWrite(LED,LOW);

   delay(500);
}
