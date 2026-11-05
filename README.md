# Kompas Belajar

Aplikasi web untuk memperkirakan **nilai ujian siswa** dari kebiasaan harian, sebagai alat bantu pendampingan belajar.
Dibuat sebagai produk Rencana Tindak Lanjut (RTL) Pelatihan Data Science (skema Associate Data Scientist, SKKNI 299-2020).

## Fitur
- Input nama, kelas, dan empat kebiasaan siswa: jam belajar, skor kesehatan mental, olahraga per minggu, dan jam tidur
- Perkiraan nilai (0 sampai 100), kategori, dan kisaran wajar
- Kontribusi tiap kebiasaan dan saran "tuas terbesar" untuk menaikkan nilai
- Riwayat prediksi dan tombol **Simpan ke Excel (.xlsx)**
- Mode terang dan gelap

## Cara memakai
Buka `index.html` di browser (atau melalui tautan GitHub Pages), isi data siswa, lalu tekan **Prediksi Nilai**.
Tidak perlu instalasi. Tidak ada data yang dikirim ke server: riwayat tersimpan di browser perangkat masing-masing.

## Model
- Regresi Linear (scikit-learn) pada dataset `student_habits_performance.csv` (1.000 siswa)
- Pembagian data 80:20 (800 latih, 200 uji), cross validation 5-fold
- Hasil pada model 5 fitur (termasuk kehadiran): R² data uji 0,834; MAE 5,27 poin; RMSE 6,52 poin
- **Catatan:** versi aplikasi ini memakai 4 fitur (tanpa kehadiran), sehingga metrik perlu dihitung ulang setelah model dilatih ulang
- Pemetaan quantile dan intersep di aplikasi merupakan rekonstruksi dari ringkasan data, jadi hasilnya adalah estimasi

## Catatan etika
Hasil prediksi bersifat statistik dan menunjukkan hubungan, bukan sebab-akibat. Gunakan sebagai alat bantu pendampingan,
bukan sebagai keputusan akhir atau label untuk siswa. Jangan memasukkan nama asli siswa pada uji coba publik.

## Penyusun
Mohamad Irfan, S.Tr.T., M.M., Gr. — Peserta Pelatihan, LKP Bina Teknologi
