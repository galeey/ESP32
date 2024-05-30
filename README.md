Kode ini adalah program yang membaca tegangan baterai LiPo 18650 menggunakan pin ADC pada mikrokontroler ESP32, 
mengonversi tegangan tersebut menjadi persentase baterai, dan menampilkan kedua nilai tersebut melalui komunikasi Serial.

**Struktur Kode**
1. Konstanta dan Variabel Global:
    BATTERY_PIN: Pin ADC yang digunakan untuk membaca tegangan baterai.
    ADC_MAX: Nilai maksimum dari ADC (4095 untuk ADC 12-bit).
    V_REF: Tegangan referensi ADC dalam Volt (3.3V pada ESP32).
    VOLTAGE_DIVIDER_RATIO: Rasio pembagi tegangan yang digunakan untuk menurunkan tegangan baterai agar sesuai dengan tegangan referensi ADC.
    Fungsi Setup Awal (setup()):

2. Menginisialisasi komunikasi Serial dengan baud rate 9600.
    Mengatur resolusi pembacaan ADC menjadi 12 bit.
    Fungsi Membaca Nilai Mentah ADC (readADCRaw()):

3. Membaca nilai mentah dari pin ADC yang telah ditentukan (BATTERY_PIN).
    Fungsi Mengkonversi Nilai ADC ke Tegangan (getBatteryVoltage()):

4. Memanggil fungsi readADCRaw() untuk membaca nilai ADC.
    Mengkonversi nilai ADC menjadi tegangan dengan memperhitungkan rasio pembagi tegangan dan tegangan referensi ADC.

5. Fungsi Mendapatkan Persentase Baterai (getBatteryPercentage()):
  Mengambil nilai tegangan sebagai parameter.
  Menghitung persentase baterai berdasarkan tegangan, dengan memperhitungkan rentang tegangan baterai LiPo 18650 (3.0V hingga 4.2V).

6. Fungsi Loop Utama (loop()):
  Memanggil fungsi getBatteryVoltage() untuk mendapatkan tegangan baterai.
  Memanggil fungsi getBatteryPercentage() untuk mendapatkan persentase baterai berdasarkan tegangan.
  Menampilkan tegangan baterai dan persentase baterai ke Serial Monitor setiap detik.
  Menunggu selama 1 detik sebelum membaca kembali.

**Logika dan Algoritma Kunci**
1. Membaca nilai ADC dari pin yang ditentukan.
2. Mengkonversi nilai ADC menjadi tegangan baterai dengan memperhitungkan rasio pembagi tegangan dan tegangan referensi ADC.
3. Menghitung persentase baterai berdasarkan tegangan yang diukur, dengan memperhitungkan rentang tegangan baterai LiPo 18650.
4. Menampilkan nilai tegangan baterai dan persentase baterai ke Serial Monitor.
