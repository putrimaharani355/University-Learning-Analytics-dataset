# University Learning Analytics dataset

***Source Data :*** [Open University Learning Analytics Dataset](https://www.kaggle.com/datasets/anlgrbz/student-demographics-online-education-dataoulad).

Tujuan : melakukan prediksi final result siswa 

## Integration of dataset 
Dataset yang dibuat adalah “Student Performance Dataset”. Dengan adanya prediction ini, mahasiswa akan dapat diprediksi lulus atau tidaknya hanya dengan melihat beberapa features.
Dataset tersebut merupakan gabungan dari data-data berikut.
1. Assessment

   Data Assessment berisi tentang informasi tentang penilaian dalam presentasi
modul. Biasanya setiap presentasi memiliki sejumlah penilaian yang
dilanjutkan dengan ujian akhir.
2. Student Assessment
  
   Data Student Assessment berisi tentang hasil dari assessment murid-murid.
3. Student Info

   Data Student Info berisi informasi demografis tentang siswa beserta hasilnya.

Dataset ini memuat 21 fitur. Dari data-data tersebut dapat memprediksi apakah siswa akan pass, withdrawn, fail atau distinction. Dari data yang didapat, berikut adalah visualisasi distribusi dari final result dari para siswa. 
![Image](https://github.com/user-attachments/assets/7d1001f2-ffc8-485c-beee-82c03b5270af)

## Modeling
### Preprocessing 
#### 1. Pengumpulan data 
Data dikumpulkan dengan cara melakukan integrasi pada data Assessment, Student Assessment dan Student Info.
#### 2. Pembersihan data 
Pembersihan data yang dilakukan berupa mengidentifikasikan dan menangani data yang kosong. Gambar berikut adalah gambar yang menunjukkan jumlah nilai null (missing values) dalam setiap kolom dari dataset. 
#### 3. Pemilihan features yang berkaitan
Fitur pada dataset berjumlah 21. Beberapa dari fitur tersebut tidak relevan dengan hasil final dari siswa. Maka dari itu, harus dilakukan pemilihan fitur. Fitur-fitur yang tidak relevan akan di drop. Berikut adalah fitur yang relevan dengan hasil final dari siswa. 
1. Assessment Type 
2. Score
3. Gender
4. Highest education
5. IMD band
6. Age band
7. Num of prev attempts
8. Studied credits
9. Disability
10. Final result
#### 4. Penyandian Label
Beberapa fitur dari dataset tersebut merupakan kategorial (object). Agar fitur-fitur yang memiliki data type kategorik menjadi numerik, maka dilakukan label encoder. 
#### 5. Pemisahan features dan labels 
Pemisahan kolom-kolom dataset menjadi dua bagian terpisah, yaitu features dan labels. Labels yang digunakan dalam model ini adalah “final_result”, yang merupakan variabel target yang ingin diprediksi. 
#### 6. Pembagian train set dan test set 
Selanjutnya, dilakukan pembagian dataset menjadi train set sebesar 80% dan test set sebesar 20%. Train set yang terdiri dari 80% dari keseluruhan dataset, digunakan untuk melatih model machine learning, sehingga model dapat memahami pola dan hubungan dalam data. Sedangkan data tes yang terdiri dari 20% sisa data digunakan untuk menguji kinerja model. 
#### 7. Modeling
Metode yang digunakan dalam prediction machine learning ini adalah decision tree. Dengan 4 kelas, yaitu  pass, withdrawn, fail atau distinction

### Evaluasi 
Setelah melatih model Decision Tree pada Train set, dilakukanlah prediksi pada test set. 

![Image](https://github.com/user-attachments/assets/1a7dc29f-a9b9-4446-acb2-905bec86dd2b)

Dikarenakan tingkat akurasi berada di angka 60%, maka disarankan untuk melakukan eksplorasi berbagai teknik dan model machine learning lainnya, seperti Random Forest, Support Vector Machines atau Neural Network, untuk meningkatkan akurasi prediksi. Selain itu, analisis lebih mendalam tentang fitur yang paling mempengaruhi hasil akhir siswa dapat membantu dalam peningkatan model. 

