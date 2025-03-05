# 📌 Retrieval Ensemble Projesi

Bu proje, **metin tabanlı sorgu-cevap eşleştirme süreçlerini iyileştirmek için farklı embedding yöntemleri ve ensemble tekniklerini incelemektedir**. Projede, çeşitli gömme modelleri kullanılarak sorgu ve cevapların anlam benzerlikleri hesaplanmış ve kararların birleştirilmesiyle doğruluk oranları artırılmıştır.

## 📖 Proje Açıklaması

Metin gömme yöntemlerinin doğruluğunu artırmak için farklı embedding modelleriyle **cosine similarity** hesaplanmış, ardından **average ensemble, weighted average ensemble ve max voting** teknikleri kullanılarak sonuçlar birleştirilmiştir.

En iyi bireysel embedding modeli **jina-embeddings-v3** olurken, **weighted average ensemble yöntemi en yüksek başarıyı sağlamıştır**.

## 📊 Kullanılan Veri Kümesi

- **51.563 satır ve 4 sütun** içeren veri seti kullanılmıştır.
- "Talimat" ve "Giriş" sütunları birleştirilerek sadeleştirilmiş ve analiz için yeni bir yapı oluşturulmuştur.
- 2.000 satır örnek seçilerek **%80 eğitim - %20 test** olarak ayrılmıştır.

## 🔍 Kullanılan Temsil Yöntemleri (Embeddings)

- `all-MiniLM-L12-v2`
- `multilingual-e5-large-instruct`
- `gte-large`
- `bert-base-turkish-uncased`
- `jina-embeddings-v3`

Bu yöntemler, **sorgu ve cevaplar için benzerlik matrisi oluşturmak amacıyla kullanılmıştır**.

## 🏆 Kullanılan Ensemble Yöntemleri

- **Average Ensemble:** Modellerin skorlarının ortalaması alınarak karar verilir.
- **Weighted Average Ensemble:** Daha yüksek performanslı modellere daha fazla ağırlık verilerek ortalama hesaplanır.
- **Max Voting:** Her sorgu için en yüksek benzerlik skorunu veren model seçilir.

## 📊 Deneysel Sonuçlar

- **Bireysel embedding başarısı:**  
  - En iyi sonuç: `jina-embeddings-v3`  
  - İkinci en iyi yöntem: `multilingual-e5-large-instruct`  
  - En düşük başarı: `bert-base-turkish-uncased`  

- **Ensemble yöntemlerinin başarısı:**  
  - **Weighted Average Ensemble** en iyi sonucu vermiştir.  
  - **Max Voting** yöntemi en düşük başarıyı göstermiştir.  
  - **Average Ensemble**, dengeli bir sonuç üretmiş ve Top5 başarısı açısından güçlü bulunmuştur.  

Detaylı sonuçlar için **[📄 Proje Raporu](rapor/Kolektif Öğrenme Rapor 3.pdf)** dosyasını inceleyebilirsiniz.

