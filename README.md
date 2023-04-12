### Doğal Dil İşleme Yöntemiyle Aşağılayıcı Söylem Tespiti 
## Teknofest 2023
$${\color{blue}TrendMiner Takımı }$$

Modeli Kullanmak Yüklenmesi Gereken Bağımlılıklar
pip install gradio
!pip install transformers
 pip install simpletransformers
 pip install zemberek-python
 !pip install git+https://github.com/emres/turkish-deasciifier. git
 !pip install TurkishStemmer
 Hugginface bağlantısı için 
 Install Hugging Face Hub
 !python -m pip install huggingface_hub
 !python -m pip install evaluate
 from fast_ml.model_development import train_valid_test_split
 
 ### Model Oluşturma
 
 

 <img src="https://github.com/HuseyinAts/Acikhack2023_TrendMiner/blob/main/short%20text%20represantion%20taxonomies.jpg" width="auto">
 
 
 ## Veri Setinin Ön İşleme Basamakları
 
 
 <img src="https://github.com/HuseyinAts/Acikhack2023_TrendMiner/blob/main/text%20mining%20grafik.jpg" width="auto">
 
 
 # Veri Seti incelendi. Kısa metinlerden oluştuğu gözlemlendi.
# Kısa metin clustering üzerine bilimsel makaleler tarandı.
# Yayınlanan makalede Short Text Clustering modellerinin performans verileri incelendi.
# Kısa metinlerde performansı en yüksek olan Soft Cluster Assignment for Text Clustering - Auto Encoder yöntemi üzerine modelimizi kurup performans verilerini kaydettik.

# Yine performansı yüksek olan Bert üzerine modelimizi kurup performans verilerini kaydettik.

# Türkçe metinler üzerinde fine-tune edilmiş Bert modelinin daha yüksek performans gösterdiği için modelimizi Bert üzerine kurduk.

# Kısa metinler üzerinde clustering işlemi için güncel bilimsel makaleleri taradığımızda öne çıkan yaklaşımları temel alarak modellerimizi kurup performanslarını kıyasladık.

# En başarılı yöntem olarak geçen Soft Cluster Assignment for Text Clustering - Auto Encoder yönteminden istediğimiz performansı alamadık.

# Bunda Türkçe’nin sondan eklemeli bir dil oluşunun , alfabede ki bazı harflerin İngilizce de olmamasının , veri setinin az olmasının ve bazı deyim ve atasözlerinin model tarafından algılanamamasından kaynaklandığını düşünüyoruz.

# Diğerlerine göre daha iyi performans gösteren  https://huggingface.co/dbmdz/bert-base-turkish-cased modelini veri setimizle fine-tune edip hazırladık.

#  Veri setimizle fine tüne ettiğimiz modelin hugginface modelinden daha iyi performans sağladığını gözlemledik

## Proje İş Akışı 

![image](https://user-images.githubusercontent.com/72999029/231423545-5a6247b3-de5a-4c5e-88d8-f86d371f3715.png)


![image](https://user-images.githubusercontent.com/72999029/231423292-67c983c1-9eb4-48c6-839a-41213a4ab4c7.png)


![image](https://user-images.githubusercontent.com/72999029/231423078-095e9b76-9adb-470d-b206-d4dde278d50b.png)

 
 <img src="https://github.com/HuseyinAts/Acikhack2023_TrendMiner/blob/main/pre%20processing.jpg" width="auto">
 
 ## Çalışma Basamaklarının Açıklaması 
 
# Dijital ortamda yazıların genelde resmi yazı formuna uymadığı için önce cümleler ve kelimeler için normal formuna getirme olan normalizasyon yaptık.

# Bu kelimeler sayısal değerlere çevrilme olan tokenizasyonu Bert Model yapılıyor.

# Çıkarıldığı zaman anlam bütünlüğünü bozmayan dolgu kelimeleri (stop words)’ler çıkarılır.

# Kelimelerin köklerinin bulunması (lematization)

# Feature Selection (Özellik belirleme)’de text değerleri ve etiket değerleri (INSULT,PROFANITY VB) seçilir

# Oluşturduğumuz model aracılığıyla önce önce classification(sınıflandırma) daha sonra clustering yapılır.
![image](https://user-images.githubusercontent.com/72999029/231423900-0b4f7844-18d4-4896-897c-8f323e58e466.png)

 
 
