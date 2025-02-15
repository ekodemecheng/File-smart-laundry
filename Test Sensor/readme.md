Penjelasan Sensor & Koneksi dengan Arduino dalam Smart Laundry
Dalam sistem Smart Laundry, tiga sensor utama digunakan untuk mendeteksi status mesin cuci, yaitu 
- MPU6050 (Accelerometer & Gyroscope), 
- Hall Effect Sensor, dan
- Gravity Motor Vibration Sensor.
Masing-masing sensor memiliki peran yang berbeda dalam memantau kinerja mesin cuci.

Penjelasan Sensor & Koneksi dengan ESP32 dalam Smart Laundry
Pada sistem Smart Laundry, ESP32 digunakan sebagai mikrokontroler utama karena memiliki WiFi & Bluetooth 
untuk mengirim data ke Firebase dan aplikasi mobile. Sensor yang digunakan untuk memonitor mesin cuci adalah:

- MPU6050 (Accelerometer & Gyroscope) → Mendeteksi getaran dan kemiringan mesin.
- Hall Effect Sensor → Mendeteksi putaran drum mesin cuci.
- Gravity Motor Vibration Sensor → Mendeteksi getaran motor mesin cuci

1. MPU6050 (Accelerometer & Gyroscope)
Fungsi dalam Smart Laundry
- Memonitor getaran untuk menentukan apakah mesin sedang mencuci atau berhenti.
- Jika tidak ada perubahan akselerasi, artinya mesin selesai mencuci.
- Bisa juga digunakan untuk mendeteksi mesin miring atau tidak stabil, yang penting untuk menghindari kerusakan mekanik.

Koneksi MPU6050 dengan ESP32
MPU6050 menggunakan komunikasi I2C, sehingga hanya memerlukan dua pin pada ESP32.

MPU6050 Pin	to ESP32 Pin
VCC -->	3.3V;

GND -->	GND;

SDA	--> GPIO21;

SCL	--> GPIO22;

INT	--> Tidak digunakan (Opsional);

2. Hall Effect Sensor
Fungsi dalam Smart Laundry
- Digunakan untuk mendeteksi rotasi drum dengan menghitung jumlah pulsa medan magnet.
- Jika jumlah pulsa berhenti meningkat, artinya mesin selesai mencuci.
- Jika drum berputar tidak normal, sistem dapat mengeluarkan peringatan kesalahan.

Koneksi Hall Effect Sensor dengan ESP32
Hall Effect Pin	ESP32 Pin
VCC --->	3.3V;
GND --->	GND;
OUT	---> GPIO23;

