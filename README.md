# IOT_Lab1
# LAB1 — ESP32 Temperature Sensor with Relay Control (Telegram)

## 🔧 Configuration Steps
1. **Set up Wi-Fi**  
   Edit the top of `main.py`:
   ```python
   WIFI_SSID     = "YourWiFiName"
   WIFI_PASSWORD = "YourWiFiPassword"
   ```

2. **Create a Telegram Bot**  
   - In Telegram, open **@Bot**.  
   - Run `/newbot` and follow prompts.  
   - Copy the generated **BOT_TOKEN** and paste it:
     ```python
     BOT_TOKEN = "123456789:ABC-YourBotToken"
     ```

3. **Get Your Chat ID**  
   - Start a chat with your bot and send a message.  
   - Either check your program logs or type `/whoami`.  
   - Use the ID returned and add it to:
     ```python
     ALLOWED_CHAT_IDS = {-123456789}  # replace with your chat/group id
     ```

---

## 💡 Usage Instructions
- **/status** → Shows current relay state + temperature & humidity.  
- **/on** → Turns the relay ON.  
- **/off** → Turns the relay OFF.  
- **/whoami** → Returns your chat id.  
- **/help** → Lists available commands.  

### Alert Behavior
- If **T ≥ 30 °C** and relay is **OFF** → bot sends alerts every 5 seconds until `/on` is sent.  
- If relay is turned **ON**, alerts stop.  
- Once **T < 30 °C**, relay turns **OFF automatically** and bot sends a one-time auto-OFF notice.  

---

