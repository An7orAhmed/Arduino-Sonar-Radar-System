# Arduino Sonar Radar System  

## Description  
A portable radar system using an HC-SR04 ultrasonic sensor and servo motor to detect nearby obstacles within an 8 cm range. The device scans 15°–165° in real-time, triggering an LED and buzzer alarm on detection. Distance data is serialized for visualization (e.g., Processing IDE). Ideal for small-scale obstacle avoidance or proximity sensing applications.  

## Features  
- **Ultrasonic Detection**: Measures distances up to 400 cm (calibrated for 8 cm alerts).  
- **Panning Radar**: Servo motor sweeps 150° range (15°–165°).  
- **Visual/Audio Alerts**: Red LED and buzzer activate when obstacles are detected.  
- **Serial Data Output**: Compatible with real-time visualization tools.  

## Pin Mapping  
| Component       | Arduino Pin |  
|-----------------|-------------|  
| Ultrasonic Trig | 9           |  
| Ultrasonic Echo | 10          |  
| Servo Motor     | 4           |  
| LED             | 2           |  
| Buzzer          | 3           |  

**Note**: Circuit diagrams (if referenced) may not be fully accurate. Adjust wiring as needed.  

## Usage  
1. Upload `RaderArduino.ino` to your Arduino board.  
2. Open the Serial Monitor (`9600 baud`) to view distance-angle pairs in the format:  
   ```angle,distance.```  
3. Use Processing or similar tools to plot a real-time radar display (code not included).  

## Notes  
- Detection threshold: 8 cm (adjust `distance < 8` in `alarm()` for custom ranges).  
- Servo delay: 30 ms per angle step (modify `delay(30)` for faster/slower scanning).
