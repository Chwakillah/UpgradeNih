# Sistem Rekomendasi Training dan Certification untuk Pekerjaan Anda!

## Deskripsi Proyek

Sistem ini dikembangkan untuk merekomendasikan kursus Coursera berdasarkan pilihan pekerjaan impian pengguna. Dengan memilih pekerjaan, sistem akan menampilkan daftar kursus yang relevan untuk membantu pengguna membangun keterampilan menuju karir tersebut.

Pendekatan yang digunakan adalah content-based recommendation system dengan vektorisasi teks dan cosine similarity.

---

## Pendekatan Sistem

Sistem ini menggunakan pendekatan sebagai berikut:

* Vektorisasi teks menggunakan metode TF-IDF (Term Frequency-Inverse Document Frequency).
* Cosine Similarity digunakan untuk mengukur kemiripan antara deskripsi pekerjaan dengan tags kursus.
* Pendekatan ini dipilih karena cocok untuk dataset kecil sampai menengah, tidak terlalu berat, mudah, dan memanfaatkan kekuatan teks pendek.

---

## Proses Pembangunan Sistem

1. **Vektorisasi Teks**

   * Dataset pekerjaan dan kursus diproses melalui tahapan prepocessing terlebih dahulu:

     * Lowercasing.
     * Menghapus karakter tidak penting.
     * Stemming (mengembalikan kata ke bentuk dasar).
    * Selanjutnya dilakukan Feature Selection untuk memfokuskan area kolom yang relevan dengan sistem yang akan dibuat:

        * Kolom yang dipilih di file worklist (Semua kolom)
        * Kolom yang dipilih di file course (Kursus, Link Courses, Skills)
   * Selanjutnya, deskripsi pekerjaan dan tags kursus diubah menjadi vektor numerik menggunakan TF-IDF.

2. **Labelling dan Similarity Mapping**

   * Deskripsi pekerjaan dijadikan label query.
   * Setiap deskripsi pekerjaan dibandingkan dengan seluruh kursus menggunakan cosine similarity.
   * Dibentuk similarity matrix yang menunjukkan seberapa relevan setiap kursus terhadap suatu pekerjaan.

3. **Modelling Rekomendasi**

   * Sistem akan mengembalikan N kursus dengan nilai similarity tertinggi terhadap deskripsi pekerjaan yang dipilih pengguna.
   * Model ini bersifat content-based, fokus pada kemiripan isi.

---

## File Output

* File hasil vektorisasi disimpan dalam format `.json` atau `.csv`.
* File similarity matrix disimpan dalam format `.csv`.

---

## Contoh Hasil Rekomendasi

### Pekerjaan: UI/UX Designer

* UX/UI Design Fundamentals: Usability and Visual Principles
  [https://www.coursera.org/learn/uxui-design-fundamentals-usability-and-visual-principles](https://www.coursera.org/learn/uxui-design-fundamentals-usability-and-visual-principles)

* IBM UI/UX Designer
  [https://www.coursera.org/professional-certificates/ibm-ui-ux-designer](https://www.coursera.org/professional-certificates/ibm-ui-ux-designer)

* Principles of UX/UI Design
  [https://www.coursera.org/learn/principles-of-ux-ui-design](https://www.coursera.org/learn/principles-of-ux-ui-design)

* UI/UX Wireframing and Prototyping with Figma
  [https://www.coursera.org/learn/uiux-wireframing-and-prototyping-with-figma](https://www.coursera.org/learn/uiux-wireframing-and-prototyping-with-figma)

* Fundamentals of UI/UX Design
  [https://www.coursera.org/learn/fundamentals-of-uiux-design](https://www.coursera.org/learn/fundamentals-of-uiux-design)

### Pekerjaan: Computer Support Specialist

* Technical Support Fundamentals
  [https://www.coursera.org/learn/technical-support-fundamentals](https://www.coursera.org/learn/technical-support-fundamentals)

* Microsoft IT Support Specialist
  [https://www.coursera.org/professional-certificates/microsoft-it-support-specialist](https://www.coursera.org/professional-certificates/microsoft-it-support-specialist)

* GenAI for Computer Support Specialists (IT Support)
  [https://www.coursera.org/learn/genai-for-computer-support-specialists-it-support](https://www.coursera.org/learn/genai-for-computer-support-specialists-it-support)

* Dell Technologies Technical Support for Hardware
  [https://www.coursera.org/learn/dell-hardware-tech-support](https://www.coursera.org/learn/dell-hardware-tech-support)

* Google IT 지원 수료증 이수 과정
  [https://www.coursera.org/professional-certificates/google-it-support-korean](https://www.coursera.org/professional-certificates/google-it-support-korean)

---

## Refleksi Pengembangan

* Kendala:

  * Saya masih awam terkait sistem ini, alhasil saya agak lama memikirkan cara membangun modelnya
  * Entah tadi ada kendala ketika saya mengunduh file tfidf dan similarity di google colab.

* Solusi:

  * Saya banyak menonton pembahasan terkait model recomendation untuk lebih memfamiliarkan diri dengan sistem yang dibuat
  * Memindahkan folder ini dari google colab ke lokal komputer saya

---
