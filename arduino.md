int V;
void setup() {
  Serial.begin(9600);
}

void loop(){
  int V=analogRead(A0)/4;
//  Serial.write(V);
//  Serial.print(V);
   if(V>189&&V<193){Serial.write(1);}
  if(V>125&&V<129){Serial.write(2);}
  if(V>61&&V<65){Serial.write(3);}

  delay(200);
 }
