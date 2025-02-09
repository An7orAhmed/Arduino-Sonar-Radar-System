Alright, let me break down how I would approach creating a README for the given project. The user wants a README for the "128. Sonar Rader" project, which includes C/C++/Arduino/Proton Basic code. They specified not to include contribution or license info, and to include a pinmap if possible, plus a note about the diagram's accuracy.

First, I need a catchy project title within 50 characters. The original name is "128. Sonar Rader" but "Rader" is likely a typo for "Radar." So correcting that to "128. Sonar Radar" makes sense, but maybe even shorter. Maybe "Arduino Sonar Radar System" fits and is descriptive.

Next, the description. It should explain what the project does. From the code, it's using an ultrasonic sensor with a servo to scan an area, measure distances, and trigger alarms with LED and buzzer. The description should mention these components and the purpose, like obstacle detection.

The code snippets show that the radar uses a servo motor moving from 15 to 165 degrees and back, using HC-SR04 ultrasonic sensor. The alarm is triggered when distance is under 8 cm. I should highlight real-time monitoring via the Serial output and Processing IDE visualization, as mentioned in the code comments.

Pin mapping is required. Looking at the code: trigPin=9, echoPin=10, servo on pin 4, LED on 2, buzzer on 3. So listing those in a table makes sense. Also, noting that the diagram (if any) may have inaccuracies.

Including a note about the accuracy of any diagrams is important to avoid confusion. The user mentioned to add that, so a section like "Important Note" about diagrams being approximate.

Additional notes might mention that the Processing code isn't included here, which the user might need elsewhere. Also, parameters like the 8 cm threshold and possible adjustments the user can make.

No need to mention contribution or license, so omit those sections.

Now, structure this all logically: Title, Description, Features, Pin Mapping, Usage, Notes. Ensure each section is concise and clear. Avoid technical jargon where possible but include necessary details for someone replicating the project.

Double-check all the components and pin numbers from the code to ensure accuracy in the pinmap. Review the description to cover all key aspects without being too verbose. Make sure the note about diagrams is placed appropriately, possibly under the pinmap or in its own section.

Lastly, make sure the README flows well, uses proper formatting for code elements (like pin names in inline code), and is free of markdown errors. That should cover everything the user requested.
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