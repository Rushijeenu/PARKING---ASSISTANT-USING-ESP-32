# Parking-Assist
# **Vehicle Parking Assistant**

**Project Overview:**
Develop an application that helps users park their vehicles in a garage or tight space using an ESP32 connected to ultrasonic distance sensors. The app will provide visual feedback and guidance to ensure safe parking without collision.

**Key Features:**

- Real-time distance measurements displayed on the app.
- Graphical representation of the vehicle in relation to garage walls or obstacles.
- User authentication to access and save vehicle profiles and settings.
- Audible and visual alerts when the vehicle is too close to an object.

**Technical Specifications:**

- Utilize multiple ultrasonic sensors to provide comprehensive distance data.
- Implement WebSocket for real-time communication between the ESP32 and the Electron app.
- Data handling via SQLite to manage user and session data securely.
