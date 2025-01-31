## Smart 3D Printer Safety and Readiness System
This project involves The **Smart 3D Printer Safety and Readiness System** ensures secure and reliable 3D printing by monitoring **temperature** and **vibrations** using an **STM32F446ZE microcontroller**. It prevents printing if the **temperature is below 20°C** and alerts users to excessive vibrations, reducing errors and protecting hardware. Real-time status is displayed on an **LCD**, with a buzzer providing safety alerts, making 3D printing more efficient and stable.
## Components Required
- **STM32F446ZE Microcontroller**
- **I2C LCD (16x2) Display**
- **DHT11 Temperature Sensor**
- **SW-18010 Vibration Sensor**
- **HW-508 Buzzer**
- **Jumper wires and Breadboard**
## Connection Details
| **Device**         | **Pin Name**    | **Connection** |
|--------------------|-----------------|----------------|
| **I2C LCD**        | VCC             | 5V             |
|                    | GND             | GND            |
|                    | SDA             | Pin D14        |
|                    | SCL             | Pin D15        |
| **DHT11 Sensor**   | VCC             | 5V             |
|                    | GND             | GND            |
|                    | OUT             | Pin D32        |
|**Vibration Sensor**| VCC             | 3.3V           |
|                    | GND             | GND            |
|                    | D0              | Pin A1         |
|   **Buzzer**       | VCC             | 5V             |
|                    | GND             | GND            |
|                    | S               | Pin A0         |
  
## Working Principle
1. **Initialization:**
   - Upon powering up the system, the STM32 Microcontroller initializes the **I2C LCD**, the **Temperature Sensor**, the **Vibration Sensor**,and the **Buzzer**. The LCD displays a default message".
2. **Temperature Monitoring:**
   - The DHT11 temperature sensor measures ambient temperature.If the temperature is ≥ 20°C, the system displays **Ready for Printing** on the 16x2 LCD and enables printing.If the temperature is below 20°C, the LCD displays **Not Ready for Printing**, and printing remains disabled
3. **Vibration Detection:**
   - The SW-18010 vibration sensor detects excessive vibrations during printing.If vibrations exceed a predefined threshold, the buzzer activates, and the LCD displays a **Vibration Alert** to warn the user.
4. **Real time Monitoring and Control:**
   - The firmware, developed using STM32CubeIDE, utilizes GPIO, ADC, and timers for real-time data processing and hardware control.The system continuously monitors and updates the status based on sensor inputs, ensuring safe and stable 3D printing.

## Applications
- **Enhanced 3D Printing Safety**:Prevents printing under inadequate temperature conditions, reducing material waste and print failures.Detects vibrations during operation, preventing misalignments and hardware damage
- **Industrial & Manufacturing Use**:Ensures consistent print quality in automated production environments.Reduces downtime by
  alerting users to operational instabilities.
## How to Use
1. Connect the components as shown in the **Connections** section.
2. Upload the code to your **STM32F446ZE Microcontroller Board**.
3. Upon powering the system, the **LCD** will show a default message.
4. The **Temperature Sensor** will going to measure the tempearture of the Printer machine and it will Display the diiferent values in the LCD Screen.
5. The **Vibration Sensor** will going to give an **Buzzer** alarm whenever the printer machine vibrates.
