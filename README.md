# Embedded-Systems-Development-Task
control (I/O) pin using button with arduino 
int temp_Pin = 7;                                         // the pin of temperature sensor
int temp_val;                                            // the temperature value
const int button_Pin = 2;                               // the number of the pushbutton pin
const int led_Pin = 3;                                 // the number of the LED pin
// Variables will change in process :
int led_State = HIGH;                                 // the current state of the output pin
int button_State;                                    // the current reading from the input pin
int last_Button_State = LOW;                        // the previous reading from the input pin

void setup() 
{
  Serial.begin(9600);
  pinMode(button_Pin, INPUT_PULLUP);               // declare the push button as input pullup
  pinMode(led_Pin, OUTPUT);                       // declare the led as output
  digitalWrite(led_Pin, led_State);              // set initial LED state
}

void loop() 
{
  int reading = digitalRead(button_Pin);     // reading the state of button pin
  temp_val = analogRead(temp_Pin);          // reading the state of temperature pin
// the equation of temperture value
  float mv = ( temp_val/1024.0)*5000;        // turn from voltage to the value 
  float cel = mv/10;                        // turn from voltage value to cellicus value 
 // print on screen 
 // it will be like " the temperature is = temp *c " with delay 3 seconds  
  Serial.print("TEMPRATURE = ");           
  Serial.print(cel);
  Serial.print("*C");
  Serial.println();
  delay(3000); 
// the mesurement of the state of the button : 
// check to see if you just pressed the button 
// (i.e. the input went from LOW to HIGH),  and you've waited 
// if the button state has changed:
    if (reading != button_State) 
    {
      button_State = reading;
      led_State = !led_State;
      digitalWrite(led_Pin, led_State);
     
      if (button_State == LOW) 
      {
        Serial.println("pressed");
         
      }
         
    }
 
  // save the reading.  Next time through the loop,
  // it'll be the lastButtonState:
  last_Button_State = reading;
}
