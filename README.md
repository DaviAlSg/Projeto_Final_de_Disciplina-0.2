# Projeto_Final_de_Disciplina-0.2
# Sobre o projeto:
Este projeto utiliza um LDR para detectar a intensidade da luz no ambiente.
Quando o LDR percebe que está claro, o LED permanece apagado. Se o ambiente escurece,
o LED acende automaticamente.
-
![Editing Components (5)](https://github.com/user-attachments/assets/d251a4d8-96d5-4a81-b2b7-9fc3378847a8)

# Como montar o circuito:
 Para montar o circuito, conecte uma extremidade do LDR ao pino de 5V do Arduino e a outra à entrada A0 e a um resistor de 10kΩ ligado ao GND.
 Conecte o anodo do LED à porta digital D9 e o catodo, através de um resistor de 220Ω, ao GND.
 Finalize ligando os pinos de 5V e GND do Arduino à protoboard para alimentar o circuito.
-
# Materiais
1 Fotorresistor
1 Fio de 10 k ohm
1 fio de 220 k ohm
1 Led
1 Protobord
# Código
#define ldr A0  // Define o pino do LDR 
#define led 8   // Define o pino do LED
int vldr = 0;  // Variável para armazenar a leitura do LDR

void setup() {
  pinMode(ldr, INPUT);  // LDR é um sensor, deve ser apenas INPUT
  pinMode(led, OUTPUT); // LED como saída
  Serial.begin(9600);   // Inicia a comunicação serial
}

void loop() {
  vldr = analogRead(ldr); // Lê o valor do LDR
  
  if (vldr > 120) {       // Se a leitura for maior que 900 (ambiente claro)
    digitalWrite(led, LOW);  // Apaga o LED
  } else {               // Se estiver escuro
    digitalWrite(led, HIGH); // Acende o LED
  }

  Serial.println(vldr);  // Exibe o valor lido no monitor serial
  delay(100);            // Pequena pausa para estabilizar a leitura
}
