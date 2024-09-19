# Projeto_Final_de_Disciplina-0.2
-
-
![Editing Components (5)](https://github.com/user-attachments/assets/d251a4d8-96d5-4a81-b2b7-9fc3378847a8)

 -Para montar o circuito, conecte uma extremidade do LDR ao pino de 5V do Arduino e a outra à entrada A0 e a um resistor de 10kΩ ligado ao GND.
 Conecte o anodo do LED à porta digital D9 e o catodo, através de um resistor de 220Ω, ao GND.
 Finalize ligando os pinos de 5V e GND do Arduino à protoboard para alimentar o circuito.
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
