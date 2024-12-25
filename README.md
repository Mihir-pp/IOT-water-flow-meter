# IoT-Based Water Flow Meter

## Overview

This project is an IoT-based water flow meter that monitors and tracks water usage in real time. It measures the flow rate of water and calculates the total volume used, displaying the data on an OLED screen. The data is also sent to a cloud server (ThingSpeak) for remote monitoring and analysis.

## Features

- Real-time measurement of water flow rate and total volume.
- Display of current flow rate and cumulative water usage on an OLED screen.
- Sends data to the ThingSpeak cloud platform for remote monitoring.
- Low-cost and efficient solution for monitoring water consumption.

## Components Required

1. **ESP8266 WiFi Module**
2. **Water Flow Sensor**
3. **OLED Display (128x64)**
4. **Resistors and Wires**
5. **Breadboard**
6. **Power Supply**

## Libraries Used

- `ESP8266WiFi.h`: For Wi-Fi connectivity.
- `Adafruit_GFX.h` and `Adafruit_SSD1306.h`: For controlling the OLED display.

## Circuit Connections

1. **ESP8266 to Water Flow Sensor**:

   - Sensor Signal Pin -> GPIO2
   - Sensor Power (VCC) -> 5V
   - Sensor Ground (GND) -> GND

2. **ESP8266 to OLED Display**:

   - OLED SCL -> D1 (GPIO5)
   - OLED SDA -> D2 (GPIO4)
   - OLED VCC -> 3.3V
   - OLED GND -> GND

## Software Setup

1. **Install Arduino IDE**: Ensure you have the latest Arduino IDE installed.
2. **Install Required Libraries**: Install the following libraries via Arduino Library Manager:
   - Adafruit GFX Library
   - Adafruit SSD1306 Library
3. **ThingSpeak Setup**:
   - Create a ThingSpeak account.
   - Create a new channel and note down the Write API Key.

## Configuration

1. Replace the placeholders for `ssid` and `pass` with your Wi-Fi credentials.
2. Replace the `apiKey` with the Write API Key from your ThingSpeak channel.

## How It Works

1. The water flow sensor generates pulses based on the flow of water.
2. The ESP8266 reads the pulses and calculates the flow rate using a calibration factor.
3. The calculated flow rate and total volume are displayed on the OLED screen.
4. The data is periodically sent to the ThingSpeak server for remote monitoring.

## Code Explanation

- **Interrupts**: Used to count the pulses from the flow sensor.
- **Wi-Fi Connection**: The ESP8266 connects to the Wi-Fi network for internet access.
- **ThingSpeak Integration**: Sends flow rate and total volume data to the cloud.
- **OLED Display**: Displays the flow rate (L/min) and total volume (L) locally.

## Example Output

### Serial Monitor:

```
Flow rate: 2.5L/min	
Output Liquid Quantity: 1500mL / 1.5L
```

### OLED Display:

```
Water Flow Meter
R: 2.5 L/M
V: 1.5 L
```

## Usage Instructions

1. Assemble the circuit as per the connections mentioned above.
2. Upload the provided code to the ESP8266 using the Arduino IDE.
3. Open the serial monitor to verify data output.
4. Monitor water flow data on the OLED display and ThingSpeak dashboard.

## Troubleshooting

- **No Wi-Fi Connection**:

  - Ensure correct SSID and password.
  - Check if the Wi-Fi network is active.

- **Incorrect Flow Readings**:

  - Adjust the calibration factor to match your flow sensor specifications.

- **Data Not Sent to ThingSpeak**:

  - Verify the Write API Key.
  - Check internet connectivity.

## Images





## Author

[Your Name]

## License

This project is open-source and available under the MIT License.





