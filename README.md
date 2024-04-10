void setup() {
  //Bus de control
  pinMode(10,INPUT); //Entrada X
  pinMode(11,INPUT); //Entrada Y
  pinMode(12,INPUT); //Entrada Z

  pinMode(2, OUTPUT); //Signo
  pinMode(3, OUTPUT); //OP3
  pinMode(4, OUTPUT); //OP2
  pinMode(5, OUTPUT); //OP1
  pinMode(6, OUTPUT); //OP0
  pinMode(7, OUTPUT); //Residuo1
  pinMode(8, OUTPUT); //Residuo0
  pinMode(9, OUTPUT); //Error

  pinMode(A1, INPUT); 
  pinMode(A2, INPUT); 
  pinMode(A3, INPUT); 
  pinMode(A4, INPUT); 

  void loop() {
  Operacion();
  OFF();
}

void Operacion(){
  //Suma
  if (!digitalRead(10)&&!digitalRead(11)&&!digitalRead(12)){
    Suma();
    //Resta
  }else if(!digitalRead(10)&&!digitalRead(11)&&digitalRead(12)){
    Resta();
  }else if(!digitalRead(10)&&digitalRead(11)&&!digitalRead(12)){
    Multiplicacion();
  }else if(!digitalRead(10)&&digitalRead(11)&&digitalRead(12)){
    Division(); /*
  }else if(digitalRead(10)&&!digitalRead(11)&&!digitalRead(12)){
    And();
  }else if (digitalRead(10)&&!digitalRead(11)&&digitalRead(12)){
    Or();
  }else if (digitalRead(10)&&digitalRead(11)&&!digitalRead(12)){
    Xor();
  }else if (digitalRead(10)&&digitalRead(11)&&digitalRead(12)){
    Not();*/
  }
}

void Suma(){
  
  if (!digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)){
    Imprimir0();
  }

  if (!digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4) || digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)) {
    Imprimir1();
  }
 
  if ((!digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)) || (!digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4))) {
    Imprimir2();
  }
  
  if ((!digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)) || (!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && !digitalRead(A4))) {
    Imprimir3();
  }
  
  if ((!digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4))) {
    Imprimir4();
  }
  
  if ((!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4))) {
    Imprimir5();
  }
 
  if(digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4)){
    Imprimir6();
  }
}

void Resta(){
 
  if ((!digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)) || (!digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4))) {
    Imprimir0();
  }
 
  if ((!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4))) {
    Imprimir1();
  }
  
  if ((!digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4))) {
    Imprimir2();
  }
 
  if (digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)){
    Imprimir3();
  }
 
  if ((!digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)) || (!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && digitalRead(A4))) {
  Imprimir_1();
  }

  if ((!digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && digitalRead(A4))) {
  Imprimir_2();
  }
  
  if (!digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)){
    Imprimir_3();
  }

}

void Multiplicacion(){
  
  if ((!digitalRead(A1) && !digitalRead(A3)) || (!digitalRead(A2) && !digitalRead(A4))) {
    Imprimir0();
  }
  
  if (digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)){
    Imprimir1();
  }
  
  if ((!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && digitalRead(A4))) {
    Imprimir2();
  }
  
  if ((digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4))) {
    Imprimir3();
  }
 
  if (!digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4)){
    Imprimir4();
  }

  if (digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4)){
    Imprimir9();
  }
 
  if ((!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4))) {
    Imprimir6();
  }

}

void Division(){
 
  if ((!digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && !digitalRead(A2) && !digitalRead(A4))) {
    ImprimirINF();
  }
  
  if (!digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)){
    ImprimirIND();
  }

  if ((!digitalRead(A1) && !digitalRead(A3) && digitalRead(A4)) || (!digitalRead(A1) && digitalRead(A2) && !digitalRead(A3))) {
    Imprimir0();
  }
 
  if ((!digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && !digitalRead(A4)) || (digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4))) {
    Imprimir1();
  }
 
  if (!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)){
    Imprimir2();
  }
 
  if (digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && !digitalRead(A4)){
    Imprimir3();
  }

  if (!digitalRead(A1) && digitalRead(A2) && digitalRead(A3) && digitalRead(A4)){
    Imprimir0_6();
  }

  if (digitalRead(A1) && !digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)){
    Imprimir0_5();
  }
 
  if (digitalRead(A1) && !digitalRead(A2) && digitalRead(A3) && digitalRead(A4)){
    Imprimir1_5();
  }
  //0.3 1/3
  if (digitalRead(A1) && digitalRead(A2) && !digitalRead(A3) && digitalRead(A4)){
    Imprimir0_3();
  }

}



void Imprimir0(){
  OFF();
}

void Imprimir1(){
  digitalWrite(6, HIGH);
}

void Imprimir2(){
  digitalWrite(5, HIGH);
}

void Imprimir3(){
  digitalWrite(5, HIGH);
  digitalWrite(6, HIGH);
}

void Imprimir4(){
  digitalWrite(4, HIGH);
}

void Imprimir5(){
  digitalWrite(4, HIGH);
  digitalWrite(6, HIGH);
}

void Imprimir6(){
  digitalWrite(4, HIGH);
  digitalWrite(5, HIGH);
}

void Imprimir9(){
  digitalWrite(3, HIGH);
  digitalWrite(6, HIGH);
}

void Imprimir_1(){
  digitalWrite(2, HIGH);
  digitalWrite(6, HIGH);
}

void Imprimir_2(){
  digitalWrite(2, HIGH);
  digitalWrite(5, HIGH);
}

void Imprimir_3(){
  digitalWrite(2, LOW);
  digitalWrite(5, HIGH);
  digitalWrite(6, LOW);
}

void ImprimirIND(){
  digitalWrite(9, HIGH);
}

void ImprimirINF(){
  digitalWrite(9, HIGH);
}

void Imprimir0_6(){
  digitalWrite(7, HIGH);
}

void Imprimir0_5(){
  digitalWrite(8, HIGH);
}

void Imprimir1_5(){
  digitalWrite(6, HIGH);
  digitalWrite(8, HIGH);
}

void Imprimir0_3(){
  digitalWrite(6, HIGH);
}

void OFF(){
  digitalWrite(2, LOW);
  digitalWrite(3, LOW);
  digitalWrite(4, LOW);
  digitalWrite(5, LOW);
  digitalWrite(6, LOW);
  digitalWrite(7, LOW);
  digitalWrite(8, LOW);
  digitalWrite(9, LOW);
}
