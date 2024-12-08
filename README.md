# Hotel Booking Cancellation Tendency
### Created By : Ivanka Larasati Kusumadewi

**Context**  
Data ini berasal dari sistem manajemen pemesanan hotel dan mencakup berbagai fitur yang dapat memberikan wawasan tentang perilaku pelanggan dan pengelolaan pemesanan hotel. Setiap baris data mencerminkan sebuah pemesanan dengan informasi terkait pelanggan, tipe kamar yang dipesan, jenis permintaan khusus, status pembatalan, serta perubahan yang dilakukan pada pemesanan. Data ini bertujuan untuk menganalisis faktor-faktor yang mempengaruhi pembatalan pemesanan dan mengidentifikasi pola-pola yang dapat digunakan untuk memprediksi kemungkinan pembatalan di masa depan.

**Target**
- 0 : Tidak mencari cancel booking
- 1 : Cancel booking

**Problem Statement**
- Pembatalan pemesanan hotel menyebabkan kerugian finansial signifikan karena opportunity cost, yaitu pendapatan yang hilang akibat kamar yang kosong. Ketika sebuah pemesanan dibatalkan, hotel kehilangan kesempatan untuk mengisi kamar tersebut dengan pelanggan lain yang mungkin tidak hanya menginap, tetapi juga membeli layanan tambahan seperti sarapan, spa, atau layanan lainnya.

**Goals**
- Untuk mengurangi kerugian akibat opportunity cost dengan memprediksi pembatalan pemesanan, sehingga hotel dapat mengoptimalkan alokasi sumber daya seperti staf dan fasilitas. Selain itu, analisis ini bertujuan untuk mengidentifikasi faktor-faktor utama yang mempengaruhi pembatalan, sehingga hotel dapat meningkatkan perencanaan operasional dan stabilitas pendapatan, serta meningkatkan kepuasan pelanggan dengan mengurangi ketidakpastian dalam proses pemesanan.

**Analytic Approach**
- Analisis ini akan menggunakan algoritma klasifikasi untuk memprediksi pembatalan pemesanan berdasarkan fitur-fitur seperti tipe pelanggan dan perubahan pemesanan. Tujuannya adalah untuk mengidentifikasi faktor-faktor utama yang mempengaruhi pembatalan dan memberikan wawasan bagi hotel dalam mengoptimalkan sumber daya dan mengurangi kerugian.


**Matric Evaluation**

**Type 1 error : False Positive**

**Deskripsi :** Ketika kita memprediksi bahwa pelanggan akan membatalkan pemesanan, tetapi kenyataannya pelanggan tidak jadi membatalkan.

**Konsekuensi:**
Hotel akan mengalokasikan sumber daya (seperti staf atau fasilitas) untuk pemesanan yang akhirnya tidak dibatalkan, yang menyebabkan pemborosan waktu dan biaya operasional. Ini juga bisa mengganggu perencanaan kapasitas hotel karena mereka bersiap untuk pembatalan yang tidak terjadi

**Type 2 error : False Negative**  

**Deskripsi :** Ketika kita memprediksi bahwa pelanggan tidak akan membatalkan pemesanan, tetapi ternyata pelanggan membatalkan pemesanan tersebut.

**Konsekuensi :**
Hotel kehilangan kesempatan untuk mengelola pemesanan yang dibatalkan, seperti mengisi kembali kamar yang kosong atau merencanakan sumber daya secara lebih efisien. Hal ini menyebabkan kerugian finansial karena kamar tidak dapat dijual kembali, yang berujung pada opportunity cost.

Untuk problem ini, metric utama yang akan digunakan adalah Mmatrix recall

## Data Understanding

### Attribute Information

| **Attribute**                    | **Data Type, Length** | **Description** |
| --------------------------------- | --------------------- | --------------- |
| **country**                       | Text                  | Country of origin of the customer. |
| **market_segment**                | Text                  | Market segment designation (e.g., online travel agents, corporate, etc.). |
| **previous_cancellations**        | Integer               | Number of previous bookings cancelled by the customer. |
| **booking_changes**               | Integer               | Number of changes/amendments made to the booking after it was entered. |
| **deposit_type**                  | Text                  | Indicates whether the customer made a deposit to guarantee the booking (e.g., no deposit, non-refundable, refundable). |
| **days_in_waiting_list**          | Integer               | Number of days the booking was on the waiting list before it was confirmed. |
| **customer_type**                 | Text                  | Type of booking (e.g., transient, contract, group). |
| **reserved_room_type**            | Text                  | Code for the reserved room type (anonymized). |
| **required_car_parking_space**   | Integer               | Number of car parking spaces required by the customer. |
| **total_of_special_request**     | Integer               | Number of special requests made by the customer (e.g., twin bed, high floor). |
| **is_canceled**                   | Integer               | Whether the booking was canceled (1 for canceled, 0 for not canceled). |
