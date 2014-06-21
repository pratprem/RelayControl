RelayControl
============

(#define START1 7

(#define START2 8

//remove parentheses

char input;

void setup() {

  pinMode(START1, OUTPUT);
  
  digitalWrite(START1, HIGH);
  
  pinMode(START2, OUTPUT);
  
  digitalWrite(START2, HIGH);
  
  Serial.begin(9600);
}

void loop() {

  if (Serial.available()) {
  
    input = Serial.read();
    
    switch(input) {  
    
      case '1':
      
        Serial.println("Relay 1&2");
        
        digitalWrite(START1, LOW);
        
        break;
        
      case '2':
      
        Serial.println("Stop Relay 1&2");
        
        digitalWrite(START1, HIGH);
        
        break;
        
      case '3':
      
        Serial.println("Relay 3&4");
        
        digitalWrite(START2, LOW);
        
        break;
        
      case '4':
      
        Serial.println("Stop Relay 3&4");
        
        digitalWrite(START2, HIGH);
        
        break;
        
      default:
      
        break;
        
    }
    
  }
  
}
