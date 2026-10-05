# 智慧魚缸水質監測系統 (Smart Aquarium System)

本系統為結合物聯網（IoT）技術的智慧魚缸水質監測與自動控制系統，採用標準 IoT 三層架構設計。

---

## 1. 系統架構 (System Architecture)

* 3. Application Layer: Blynk App / Smartphone UI
* 2. Network Layer: ESP32 Wi-Fi <--> Wi-Fi Router (Wi-Fi / MQTT Protocol)
* 1. Perception Layer: 
  - Sensors: DS18B20 (Water Temp), pH Sensor
  - MCU: ESP32
  - Actuators: Relay Module --> Cooling Fan / Heating Rod

---

## 2. 硬體元件 (Components)

- ESP32: 主控板，負責讀取感測器資料與 Wi-Fi 連線[cite: 3]。
- DS18B20: 防水型溫度感測器，監測魚缸水溫[cite: 3]。
- pH Sensor: 水質 pH 值檢測模組[cite: 3]。
- Relay Module (繼電器模組): 開關控制致動器[cite: 3]。
- Cooling Fan (散熱風扇): 水溫過高時自動降溫[cite: 3]。
- Heating Rod (水族加熱棒): 水溫過低時自動加熱[cite: 3]。

---

## 3. 控制邏輯與運作流程 (Control Logic)

| 檢測項目 | 測量數值 | 系統狀態 | 系統動作 |
| :--- | :--- | :--- | :--- |
| 水溫 (Temp) | < 25°C | 過低 | 啟動 Relay -> 啟動加熱棒[cite: 3] |
| 水溫 (Temp) | 25°C - 28°C | 正常 | 保持 OFF[cite: 3] |
| 水溫 (Temp) | > 28°C | 過高 | 啟動 Relay -> 啟動風扇 + 手機警報[cite: 3] |
| pH 值 | 超出設定範圍 | 異常 | 發送警報通知至 Blynk App[cite: 3] |

---

## 4. 專案進度 (Project Status)

- [x] 硬體電路接線與測試[cite: 3]
- [x] ESP32 程式碼撰寫與 MQTT 連線[cite: 3]
- [x] Blynk App 介面設定[cite: 3]
- [ ] 系統整體整合與簡報製作[cite: 3]
