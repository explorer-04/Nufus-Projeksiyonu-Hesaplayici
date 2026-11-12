# 📊 Nüfus Projeksiyonu Hesaplayıcı ve Analiz Aracı

Şehir ve Bölge Planlama çalışmalarında, demografik analizlerde ve mekansal strateji hazırlıklarında kullanılmak üzere geliştirilmiş, web tabanlı **Nüfus Projeksiyonu Hesaplama ve Raporlama** uygulamasıdır. 

Kurulum gerektirmeden doğrudan tarayıcı üzerinden çalışır; Excel/CSV veri entegrasyonu, otomatik veri doğrulama, karşılaştırmalı grafik üretimi ve doğrudan PDF raporlama yeteneklerine sahiptir.

---

## ✨ Temel Özellikler

* **5 Farklı Projeksiyon Yöntemi:** Aynı veri seti üzerinden Aritmetik, Geometrik, Bileşik Faiz, Üstel (Eksponansiyel) ve En Küçük Kareler (Doğrusal Regresyon) yöntemleriyle eşzamanlı projeksiyon hesabı ve **Ortalama** değer üretimi.
* **Gelişmiş Veri Entegrasyon Sihirbazı (Excel / CSV):** `.xlsx`, `.xls` ve `.csv` formatındaki verileri içe aktarma. **TÜİK ayracı (`|`)**, noktalı virgül (`;`) ve virgül (`,`) desteği ile hem dikey hem de yatay tablo okuma.
* **Akıllı Veri Temizleme ve Sıralama:** Tabloya girilen düzensiz yılları küçükten büyüğe otomatik sıralama, boş satırları temizleme, mükerrer yıl girişlerini ve eşit olmayan sayım periyotlarını tespit ederek kullanıcıyı uyarma.
* **Dinamik Raporlama ve Grafik:** `Chart.js` tabanlı etkileşimli projeksiyon grafiği, hedef yıl vurgulama ve rapor başlangıç yılını anlık değiştirerek tabloyu güncelleme.
* **Baskı ve PDF Optimizasyonu:** Tek tıkla gereksiz arayüz elemanlarını gizleyerek A4 dikey formatta, doğrudan çıktıya veya PDF kaydetmeye hazır analiz raporu oluşturma.
* **Mobil Uyumlu (Responsive):** Bilgisayar, tablet ve mobil cihazlarla tam uyumlu arayüz.

---

## 🧮 Kullanılan Matematiksel Yöntemler ve Formüller

Sistem, girilen tarihsel nüfus verilerini ($P_{ilk}, P_{son}$) ve zaman aralıklarını analiz ederek aşağıdaki 5 yöntemle hedef yıl ($t$) projeksiyonunu hesaplar:

1. **Aritmetik Yöntem:** Doğrusal artış varsayımına dayanır.

$$P_n = P_{son} + (K_a \times t) \quad \text{—} \quad K_a = \frac{P_{son} - P_{ilk}}{\Delta t_{toplam}}$$

2. **Geometrik Yöntem:** Logaritmik artış eğimini baz alır.

$$\log(P_n) = \log(P_{son}) + (K_g \times t) \quad \text{—} \quad K_g = \frac{\log(P_{son}) - \log(P_{ilk})}{\Delta t_{toplam}}$$

3. **Bileşik Faiz Yöntemi:** Sayım dönemleri arasındaki artış hızlarının ortalamasını ($r_{ort}$) kullanır.

$$P_n = P_{son} \times (1 + r_{ort})^t \quad \text{—} \quad r_{ort} = \text{Ortalama}\left[\left(\frac{P_{i+1}}{P_i}\right)^{\frac{1}{\Delta t_i}} - 1\right]$$

4. **Üstel (Eksponansiyel) Yöntem:** Sürekli büyüme modelini doğal logaritma ($\ln$) üzerinden parçalı ortalamayla hesaplar.

$$P_n = P_{son} \times e^{(r_{exp} \times t)} \quad \text{—} \quad r_{exp} = \text{Ortalama}\left[\frac{\ln(P_{i+1} / P_i)}{\Delta t_i}\right]$$

5. **En Küçük Kareler Yöntemi (Regresyon):** Tüm sayım yıllarının eğilim çizgisini oluşturur.

$$y = a + (b \times x)$$

---

## 🚀 Kullanım

Uygulama tamamen istemci taraflı (client-side) çalışmaktadır. Herhangi bir sunucu veya kütüphane kurulumuna gerek yoktur:

1. Depodaki `Nufus_Projeksiyonu.html` dosyasını bilgisayarınıza indirin ve herhangi bir web tarayıcısında açın.
2. **Veri Girişi:**
   * **Manuel Giriş:** Sayım periyodu, başlangıç yılı ve hedef yılı belirleyip *"1. Adım: Manuel Tablo Oluştur"* butonuna tıklayın ve nüfus verilerini girin.
   * **Dosyadan Aktarım:** Sağ üstteki *"Excel / CSV Veri Çek"* butonunu kullanarak TÜİK'ten veya kendi arşivinizden aldığınız tabloyu seçin, okuma yönünü (Dikey/Yatay) belirleyip tabloya aktarın.
3. *"2. Adım: ANALİZİ BAŞLAT"* butonuna tıklayarak tüm yöntemlerin sonuçlarını, karşılaştırma tablosunu ve grafiği görüntüleyin.
4. *"Raporu Yazdır / PDF Olarak Kaydet"* butonu ile çıktınızı alın.

---

## 🛠️ Teknik Altyapı

* **HTML5 / CSS3 / Vanilla JavaScript**
* **Chart.js:** Çoklu veri seti ve projeksiyon grafiği çizimi.
* **SheetJS (xlsx):** İstemci taraflı Excel ve CSV dosya okuma/ayrıştırma.

---

## 👨‍💻 Geliştirici ve Teşekkür

Bu çalışma **Mehmet Ali SÖKMEN** tarafından hazırlanmıştır.

Değerli katkı ve desteklerinden dolayı **Prof. Dr. Barış ERGEN** ve **Arş. Gör. Dr. Merve KOÇAK GÜNGÖR** hocalarıma teşekkür ederim.

* **GitHub:** [@explorer-04](https://github.com/explorer-04)
* **İletişim:** ali438mehmet@gmail.com
