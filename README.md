# Deteksi Warna - Hijau
Deskripsi
Program ini mendeteksi warna hijau secara real-time menggunakan OpenCV. Kode ini akan menangkap video dari webcam, memproses setiap frame untuk mengidentifikasi objek berwarna hijau, dan menyorotnya dengan kotak pembatas.
# Fitur
•	Menangkap video menggunakan OpenCV
•	Mengonversi frame ke ruang warna HSV untuk deteksi warna yang lebih akurat
•	Menerapkan Gaussian Blur untuk mengurangi noise
•	Menggunakan deteksi kontur untuk mengidentifikasi objek hijau
•	Menampilkan frame asli dan hasil mask dengan area yang terdeteksi
# Cara Kerja
•	Skrip menangkap frame dari webcam.
•	Frame diberi efek blur menggunakan Gaussian Blur untuk mengurangi noise.
•	Frame dikonversi dari BGR ke HSV.
•	Mask dibuat menggunakan rentang HSV yang telah ditentukan untuk warna hijau.
•	Kontur objek hijau yang terdeteksi diidentifikasi dan diberi kotak pembatas.
•	Hasilnya ditampilkan dalam dua jendela: frame asli dengan objek yang terdeteksi dan mask.
# Penjelasan Fungsi
1.	cv2.VideoCapture(0)
Mengaktifkan webcam untuk menangkap video secara real-time.
2.	cv2.GaussianBlur(frame, (5, 5), 0)
Menghaluskan gambar dengan Gaussian Blur untuk mengurangi noise sebelum diproses lebih lanjut.
3.	cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)
Mengonversi frame dari format BGR ke HSV agar lebih mudah mendeteksi warna tertentu.
4.	cv2.inRange(hsv, lower_green, upper_green)
Membuat mask yang hanya menampilkan area dengan warna hijau dalam rentang HSV yang ditentukan.
5.	cv2.findContours(mask, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)
Menemukan kontur dalam mask untuk mengidentifikasi objek yang memiliki warna hijau.
6.	cv2.contourArea(contour)
Menghitung luas area kontur untuk memastikan hanya objek berukuran tertentu yang diproses.
7.	cv2.boundingRect(contour)
Menghitung koordinat kotak pembatas yang mengelilingi objek berwarna hijau.
8.	cv2.rectangle(frame, (x, y), (x + w, y + h), (0, 255, 0), 2)
Menggambar kotak berwarna hijau di sekitar objek yang terdeteksi.
9.	cv2.putText(frame, "Green", (x, y - 10), cv2.FONT_HERSHEY_SIMPLEX, 0.6, (0, 255, 0), 2)
Menambahkan teks "Green" di atas kotak pembatas untuk menandai objek yang terdeteksi.
10.	cv2.imshow("Frame", frame)
Menampilkan frame asli dengan objek yang terdeteksi.
11.	cv2.imshow("Mask", mask)
Menampilkan mask hasil deteksi warna hijau.
12.	cv2.waitKey(1) & 0xFF == ord('q')
Menutup program saat tombol 'q' ditekan.
13.	cap.release()
Melepaskan akses ke kamera setelah program selesai dijalankan.
14.	cv2.destroyAllWindows()
Menutup semua jendela tampilan yang dibuat oleh OpenCV.
