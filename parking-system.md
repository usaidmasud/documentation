## Arsitektur Teknologi

Aplikasi ini dibangun dengan:

* **Backend:** Menggunakan **NestJS**.
* **Frontend:** Menggunakan **ReactJS**
* **Sistem Kontrol:**
    * **Terminal Tiket / Pintu Masuk:** Dikelola oleh **Raspberry Pi** yang berfungsi sebagai mikrokontroler utama untuk memproses tiket dan mengontrol pintu masuk.
    * **Pintu Keluar:** Dikelola oleh **ESP32**, yang berfungsi sebagai mikrokontroler terpisah untuk mengontrol mekanisme pintu keluar.

---

## Wiring


### Wiring Raspberry Pi

| Pin Raspberry Pi | Komponen | Keterangan |
| :--- | :--- | :--- |
| **GPIO 16** | RELAY CH1 (UP) | Mengontrol gerakan pintu ke atas. |
| **GPIO 20** | RELAY CH2 (DOWN) | Mengontrol gerakan pintu ke bawah. |
| **GPIO 21** | RELAY CH3 (STOP) | Mengontrol untuk menghentikan gerakan pintu. |
| **GPIO 13** | VIN Buzzer | Menghubungkan ke pin daya buzzer. |
| **GPIO 22** | PIN 1 / 2 Push Button tiket | Menghubungkan ke tombol fisik untuk fungsi tiket. |
| **GPIO 14** | OUTPUT Sensor PIR | Menerima sinyal deteksi gerakan dari sensor PIR. |

### Wiring RFID MFRC522 ke Raspberry Pi

| Pin MFRC522 | Pin Raspberry Pi | Keterangan |
| :--- | :--- | :--- |
| **VCC** | **3.3V Power** (Pin 1) | Sumber daya 3.3V. |
| **GND** | **Ground** (Pin 6) | Ground. |
| **SCK** | **GPIO 11** (Pin 23) | Serial Clock (SCLK) untuk SPI. |
| **MOSI** | **GPIO 10** (Pin 19) | Master Out Slave In (MOSI) untuk SPI. |
| **MISO** | **GPIO 9** (Pin 21) | Master In Slave Out (MISO) untuk SPI. |
| **SDA/SS** | **GPIO 8** (Pin 24) | Slave Select (SS) / Chip Enable (CE0) untuk SPI. |
| **RST** | **GPIO 25** (Pin 22) | Pin Reset modul. |

### Wiring ESP32

| Pin ESP32 | Komponen | Keterangan |
| :--- | :--- | :--- |
| **GPIO 5** | RELAY CH1 (UP) | Mengontrol gerakan pintu ke atas. |
| **GPIO 18** | RELAY CH2 (DOWN) | Mengontrol gerakan pintu ke bawah. |
| **GPIO 19** | RELAY CH3 (STOP) | Mengontrol untuk menghentikan gerakan pintu. |
| **GPIO 21** | VIN Buzzer | Menghubungkan ke pin daya buzzer. |
| **GPIO 2** | LED_PIN | Menghubungkan ke LED sebagai indikator. |

![Raspberry PI](https://cdn-ak.f.st-hatena.com/images/fotolife/B/BioErrorLog/20210821/20210821150402.png)
![ESP 32 PIN OUT](https://lastminuteengineers.com/wp-content/uploads/iot/ESP32-Pinout.png)

