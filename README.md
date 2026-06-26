# Open-Amblyopia-VR 

**Açık Kaynaklı, WebXR Tabanlı Göz Tembelliği (Ambliyopi) VR Rehabilitasyon Prototipi**

Bu proje, pahalı ve erişimi zor olan klinik sanal gerçeklik tedavilerini donanım bağımsız (akıllı telefon ve basit bir VRBox) hale getirerek herkes için erişilebilir kılmayı amaçlayan açık kaynaklı bir biyomedikal mühendislik girişimidir. Ticari kâr amacı gütmeyen bu sistem, klinik literatürdeki güncel dikoptik eğitim protokollerini temel alır.

---

## Projenin Amacı ve Vizyonu
Göz tembelliği tedavisinde modern nörobilim, beynin nöroplastisitesini kullanarak iki gözü birlikte çalışmaya (binoküler füzyon) zorlayan VR sistemlerinin yetişkinlerde bile etkili olduğunu kanıtlamıştır. Ancak bu yazılımlar genellikle yüksek lisans/abonelik ücretleri ve pahalı VR donanımları (Oculus vb.) gerektirir. 

**Open-Amblyopia-VR**, HTML ve A-Frame (WebXR) kullanarak tamamen tarayıcı üzerinden, harici bir kumandaya veya pahalı bir işlemciye ihtiyaç duymadan "göz takibi (gaze-based)" ile çalışan bir terapötik algoritma sunar.

## Tıbbi ve Teknik Altyapı
Sistem "yukarıdan aşağıya" (top-down) bir yaklaşımla, sadece grafik üretmek için değil, görsel korteksi spesifik olarak uyarmak için tasarlanmıştır:
* **Dikoptik İzolasyon:** Ekran donanımsal olarak ikiye bölünür. Sağlam gözün sinyali, hastanın Görme Keskinliği (Visual Acuity) değerine göre hesaplanan bir optik zayıflatıcı (attenuator filter) ile filtrelenirken; tembel göze yüksek kontrastlı ve dinamik hedefler sunulur.
* **Kalabalıklaşma Etkisi (Crowding Effect):** Asıl hedefin etrafında dönen görsel çeldiriciler (noise), beyni karmaşanın içinden asıl sinyali filtrelemeye (uzamsal dikkat) zorlar.
* **Mekansal Farkındalık (Stereopsis):** Arka planda dönen tel-kafes (wireframe) tüneller ve örtüşen (parallax) sütunlar, beynin Z eksenini (derinlik algısını) hesaplamasını kışkırtır.
* **Füzyon Kilitleri (Fusion Locks):** Çift görmeyi (diplopi) önlemek için ekran merkezinde iki gözün de eşzamanlı kilitlendiği referans çerçeveleri bulunur.

## ⚙️ Kurulum ve Kullanım
Proje tamamen statik dosyalardan oluşur ve sunucu (backend) gerektirmez. Güvenlik gereği akıllı telefon sensörlerine (jiroskop) erişim için **HTTPS** üzerinden çalıştırılmalıdır.

1. Kodları bilgisayarınıza indirin (`index.html`).
2. Dosyayı ücretsiz bir statik sunucuya (örn: Netlify Drop, GitHub Pages) yükleyin.
3. Çıkan HTTPS linkini akıllı telefonunuzda açın.
4. Ekranda çıkan **Klinik Kalibrasyon** menüsünden doktorunuzun verdiği değerleri (Tembel göz yönü, görme keskinliği, kayma durumu) girin.
5. Telefonu bir VRBox'a yerleştirin ve sistemi başlatın (2.5 dakikalık seanslar halinde çalışır).

## ÖNEMLİ GÜVENLİK VE SORUMLULUK REDDİ (DISCLAIMER)
**BU YAZILIM TIBBİ BİR CİHAZ DEĞİLDİR VE PROFESYONEL TEDAVİ YERİNE GEÇMEZ.**
* Bu algoritma, bir nöro-oftalmolog veya uzman göz hekimi gözetimi olmadan **kullanılmamalıdır.**
* Gözünde aktif kayma (şaşılık / strabismus) olan bireylerin bu sistemi doktor kontrolü dışında kullanması **kalıcı çift görme (intractable diplopia)** veya şaşılığın artması gibi ciddi riskler taşır. 
* Sistemde bir "Acil Durum Kesicisi (Kill-Switch)" bulunsa da, yazar(lar) bu kodun kullanımından doğabilecek hiçbir tıbbi veya yasal sorumluluğu kabul etmez. Kullanım riski tamamen kullanıcıya aittir.

## Katkıda Bulunma ve Akademik İşbirliği
Bu kod tabanı, üniversitelerin araştırma hastanelerinde yapılacak olan etik kurul onaylı klinik deneylerde (vaka çalışmalarında) veri toplama aracı olarak kullanılmak üzere akademisyenlere ve araştırmacılara tamamen açıktır. Sistem mimarisini geliştirmek için Pull Request gönderebilirsiniz.

## Lisans
Bu proje **GPL-3.0** lisansı altındadır. Kodlar kopyalanabilir, dağıtılabilir ve değiştirilebilir ancak elde edilen yeni yazılımların kaynak kodları da aynı özgür lisansla **açık ve ücretsiz** olarak paylaşılmak zorundadır. Kapalı kaynak ticari ürünlerde kullanılamaz.
