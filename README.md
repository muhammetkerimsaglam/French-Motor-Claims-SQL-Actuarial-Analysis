# Fransa Motor Hasar Portföyünün SQL ile Aktüeryal Risk Analitiği

Bu proje, Fransa motorlu araç sigortası hasar kayıtlarından oluşan büyük ölçekli bir veri kümesi üzerinde yürütülen kapsamlı bir veri tabanı mühendisliği ve aktüeryal analitik çalışmasıdır. Projenin amacı; ham veri setini 3. Normal Form (3NF) ilişkisel veri tabanı yapısına dönüştürmek ve ileri düzey SQL iş zekası sorgularıyla tarife fiyatlandırması ve reasürans stratejilerine yönelik ampirik bulgular üretmektir.

---

## 📚 Veri Seti Kaynağı
Projede analiz edilen 678.013 satırlık ham veri seti Kaggle üzerinden temin edilmiştir:
👉 [Kaggle - French Motor Claims Datasets (freMTPL2freq)](https://www.kaggle.com/datasets/floser/french-motor-claims-datasets-fremtpl2freq)

---

## 🛠️ Teknolojik Altyapı
* **Veri Tabanı Yönetim Sistemi:** PostgreSQL 18 (2025)
* **Arayüz / Editör:** pgAdmin 4
* **Veri Modelleme:** 3. Normal Form (3NF) İlişkisel Veri Yapısı

---

## 📈 Öne Çıkan Aktüeryal Bulgular

* **Bonus-Malus Korelasyonu:** Beklenen aktüeryal teoriyle tam uyumlu olarak, Bonus-Malus skoru yükseldikçe hasar frekanslarının eksponansiyel arttığı kanıtlanmıştır. Yüksek riskli segment (BM: 58), taban grubuna (BM: 50) kıyasla **2.4 kat daha fazla** hasar üretmektedir.
* **Genç Sürücü Riski:** Araç yakıt türünden bağımsız olarak, 18-25 yaş arası genç sürücü segmenti **~0.176** ile portföyün en yüksek hasar frekansına sahip çekirdek risk grubunu oluşturmaktadır.
* **Coğrafi Risk Çarpanı:** Pencereli fonksiyonlarla (`SUM OVER`) yapılan analizlerde, metropol alanlarındaki hasar frekansının kırsal bölgelere göre **%48.6 daha yüksek** olduğu saptanmıştır.
* **Kuyruk Riski (Tail Risk) Analitiği:** İleri düzey pencereli yüzdelik dilim (`PERCENT_RANK`) fonksiyonu ile portföyün en uçtaki **%0.5'lik (Binde 5)** ekstrem hasar grubu izole edilmiştir. Analiz; 6-7 kademe motor gücüne sahip, 1-10 yaş arası yeni ve orta yaşlı araçların kümülatif kuyruk riskinin merkez üssü olduğunu ortaya koymuştur (*Moral Hazard* etkisi).

---

## 📂 Proje İçeriği
* `/sql_scripts`: Veri tabanı mimarisini, normalizasyon adımlarını ve 5 ana iş zekası sorgusunu içeren SQL betiği.
* `/report`: Detaylı metodoloji, ampirik tablolar, literatür taraması ve reasürans önerilerini içeren akademik rapor (PDF).

---

## 👤 Hazırlayan
**Muhammet Kerim Sağlam**  
Hacettepe Üniversitesi - Aktüerya Bilimleri
