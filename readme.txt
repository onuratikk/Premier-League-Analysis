# Premier League 2024/25 Sezonu İstatistiksel Analiz Raporu

## Proje Tanımı

Bu proje, 2024/25 Premier League sezonuna ait futbol istatistiklerini kullanarak kapsamlı bir oyuncu performans analizi sunmayı amaçlamaktadır. Proje, farklı mevkilerdeki oyuncuların performanslarını değerlendirmek, ligdeki öne çıkan isimleri belirlemek ve bu verileri derinlemesine yorumlayarak futbol analizi meraklıları için değerli bilgiler sağlamak üzere tasarlanmıştır.

## Amaç

*   Premier League oyuncularının çeşitli istatistiksel metrikler üzerinden performanslarını analiz etmek.
*   Mevki bazında (Forvet, Orta Saha, Defans, Kaleci) ve genel olarak ligin en değerli oyuncularını (MVP) belirlemek.
*   Elde edilen verileri ve analiz sonuçlarını detaylı grafikler ve yorumlarla destekleyerek profesyonel bir rapor sunmak.
*   Veriye dayalı futbol analizi için bir referans noktası oluşturmak.

## Veri Kaynakları

Analizde kullanılan veriler, Premier League 2024/25 sezonuna ait çeşitli istatistiksel kategorileri kapsayan CSV dosyalarından elde edilmiştir. Bu veri setleri şunları içermektedir:

*   `accurate_passes_stats.csv`: İsabetli pas istatistikleri.
*   `assists.csv`: Asist istatistikleri.
*   `big_chances_created_stats.csv`: Yaratılan büyük şans istatistikleri.
*   `clean_sheets_stats.csv`: Kalecilerin gol yemeyen maç istatistikleri.
*   `expected_goals_stats.csv`: Beklenen gol (xG) istatistikleri.
*   `goals.csv`: Gol istatistikleri.
*   `goals_per_90_stats.csv`: 90 dakika başına gol istatistikleri.
*   `interceptions_stats.csv`: Top kapma istatistikleri.
*   `save_percentage_stats.csv`: Kaleci kurtarış yüzdesi istatistikleri.
*   `total_scoring_attempts_stats.csv`: Toplam şut denemesi istatistikleri.
*   `won_contests_stats.csv`: Kazanılan ikili mücadele istatistikleri.
*   `won_tackles_stats_fixed.csv`: Kazanılan top kapma istatistikleri.

## Metodoloji

Oyuncu performanslarını değerlendirmek amacıyla, her bir istatistik `sklearn.preprocessing.MinMaxScaler` kullanılarak 0 ile 100 arasında normalize edilmiştir. Bu normalleştirme, farklı ölçeklerdeki verilerin karşılaştırılabilirliğini sağlamıştır. Normalize edilmiş değerler, her mevki için belirlenen özel ağırlıklandırma faktörleri ile çarpılarak nihai 'Rating' skorları elde edilmiştir. Bu sayede, her mevkinin kendine özgü gereksinimleri doğrultusunda adil ve anlamlı bir değerlendirme yapılmıştır.

**MVP Hesaplama Ağırlıkları:**

*   **Forvet:** Goller (0.30), 90 Dakika Başına Gol (0.25), Asistler (0.20), Yaratılan Büyük Şanslar (0.15), Toplam Şut Denemeleri (0.10).
*   **Orta Saha:** Asistler (0.30), İsabetli Paslar (0.25), Yaratılan Büyük Şanslar (0.20), Kazanılan İkili Mücadeleler (0.15), Goller (0.10).
*   **Defans:** Top Kapmalar (0.40), Kazanılan Top Kapmalar (0.35), İsabetli Paslar (0.25).
*   **Kaleci:** Kurtarış Yüzdesi (0.50), Gol Yenmeyen Maçlar (0.50).

Genel MVP ise, tüm mevkilerden en iyi oyuncuların bir araya getirilmesi ve tüm istatistiksel kategorilerdeki performanslarının eşit ağırlıklandırılarak normalize edilmesiyle belirlenmiştir.

## Analiz Sonuçları

Proje kapsamında yapılan analizler sonucunda, mevki bazında ve genel olarak ligin en değerli oyuncuları belirlenmiştir. Detaylı analiz sonuçları, MVP sıralamaları, grafik yorumları ve metodoloji açıklamaları `rapor.docx` dosyasında bulunmaktadır.

## Nasıl Kullanılır / Tekrar Üretilir

Bu analizi kendi ortamınızda çalıştırmak ve sonuçları tekrar üretmek için aşağıdaki adımları takip edebilirsiniz:

1.  Tüm CSV veri dosyalarını ve `run_analysis.py` Python betiğini aynı dizine indirin.
2.  Gerekli Python kütüphanelerini (Pandas, Scikit-learn) yükleyin:
    ```bash
    pip install pandas scikit-learn
    ```
3.  `run_analysis.py` betiğini çalıştırın:
    ```bash
    python run_analysis.py
    ```
    Bu betik, analizleri gerçekleştirecek ve sonuçları `analysis_results.txt` dosyasına yazacaktır.
4.  `rapor.md` dosyasını bir Markdown okuyucu ile görüntüleyebilir veya Pandoc gibi bir araçla PDF/Word formatına dönüştürebilirsiniz.


Yazar : Onur ATİK


