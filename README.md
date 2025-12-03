# 🔹 graph-metrics-computation

Bu çalışma, InputFileNodes ve InputFileEdges dosyaları kullanılarak bir medya ağı üzerinde kapsamlı bir **karmaşık ağ analizi** yapılmasını amaçlamaktadır. Çalışmada hem yönsüz (G) hem yönlü (G_directed) networkler oluşturulmuş, çeşitli merkezilik ölçütleri hesaplanmış ve ağ yapısının yapısal özellikleri incelenmiştir.

---

##  1. Veri Seti Açıklaması

### **InputFileNodes.csv**
Bu dosyada her bir medya kaynağına ait düğüm bilgileri bulunmaktadır:
- `ID` – Düğüm adı (benzersiz kimlik)
- `media` – Medya adı
- `media.type` – Medya türü
- `type.label` – İçerik türü
- `audience.size` – İzleyici / takipçi büyüklüğü

### **InputFileEdges.csv**
Bu dosyada düğümler arasındaki bağlantılar yer almaktadır:
- `from` – Kaynak düğüm
- `to` – Hedef düğüm
- `weight` – Bağlantı ağırlığı
- `type` – Bağlantı türü

---

##  2. Yapılan İşlemler

Aşağıdaki adımlar Python kullanılarak gerçekleştirilmiştir:

### ✔ 1) Düğümler InputFileNodes dosyasından yüklendi  
### ✔ 2) Kenarlar InputFileEdges dosyasından okundu  
### ✔ 3) Tekrar eden kenarlar birleştirildi (ağırlıklar toplandı)  
### ✔ 4) Yönsüz ağ (G) oluşturuldu ve çizildi  
### ✔ 5) Yönlü ağ (G_directed) oluşturuldu ve çizildi  
### ✔ 6) G ağı için tüm düğümlerin derece değerleri listelendi  
### ✔ 7) Ortalama derece hesaplandı  
### ✔ 8) Derece histogramı çizdirildi  
### ✔ 9) Degree Centrality hesaplandı  
### ✔ 10) Closeness Centrality hesaplandı  
### ✔ 11) Betweenness Centrality hesaplandı  
### ✔ 12) Eigenvector Centrality hesaplandı  
### ✔ 13) Katz Centrality hesaplandı  
### ✔ 14) PageRank değerleri hesaplandı  
### ✔ 15) Modularity değeri hesaplandı  
### ✔ 16) Ağ yoğunluğu (density) hesaplandı  
### ✔ 17) Ortalama kümeleşme katsayısı (average clustering) hesaplandı  
### ✔ 18) Çap (diameter) hesaplandı  
### ✔ 19) G ağı için derece dağılımı çıkartıldı ve grafiği çizildi  
### ✔ 20) Tüm metrikler yorumlandı  
### ✔ 21) G ağı için en kritik 5 “köprü düğüm” hesaplandı (betweenness)  
### ✔ 22) G ağı için en kritik 5 “lider düğüm” hesaplandı (eigenvector)  
### ✔ 23) G_directed ağı için in-degree & out-degree dağılımları hesaplandı ve çizildi  
### ✔ 24) G ağındaki en güçlü 3 düğüm kaldırılarak ağ yeniden çizildi ve yapısal değişim yorumlandı  

---

##  3. Kullanılan Merkezilik Ölçütleri

### **• Degree Centrality**
Bir düğümün kaç komşusu olduğunu gösterir. Yerel önem derecesini ölçer.

### **• Closeness Centrality**
Bir düğümün diğer düğümlere ortalama uzaklığını ölçer.  
Düşük mesafe → daha merkezi düğüm.

### **• Betweenness Centrality**
Düğümlerin “köprü” olma derecesini gösterir.  
Topluluklar arası geçişlerin yoğunlaştığı kritik düğümler bu metrikle belirlenir.

### **• Eigenvector Centrality**
Önemli düğümlere bağlı düğümlerin daha değerli sayılmasını sağlar.  
Ağın “liderlerini” belirlemek için kullanılır.

### **• Katz Centrality**
Hem doğrudan hem dolaylı bağlantıları değerlendirir.

### **• PageRank**
Google’ın sayfa sıralama mantığına benzer.  
Ağın en prestijli düğümlerini gösterir.

---

##  4. Ağ Yapısı Analizi

Çalışmada elde edilen bulgulara göre:

- Ağ orta yoğunlukta olup belirgin **topluluk yapıları (modularity yüksek)** gözlenmiştir.  
- Bazı düğümlerin hem derece hem merkezilik ölçümlerinde çok baskın olduğu görülmüş, bu düğümlerin ağın **omurgasını** oluşturduğu tespit edilmiştir.
- Köprü düğümlerin kaldırılması durumunda ağın parçalandığı, bağlı bileşen sayısının arttığı ve bilgi akışının önemli ölçüde zayıfladığı gözlemlenmiştir.

---

##  5. Kritik Düğümler

### 🔵 **En Kritik 5 Köprü Düğümü**
(Betweenness Centrality’ye göre)
Bu düğümler ağdaki akışın en önemli aracılarındandır.

### 🔴 **En Kritik 5 Lider Düğümü**
(Eigenvector Centrality’ye göre)
Ağın etki merkezlerini oluşturur.

---

## 🛠️ 6. Kullanılan Kütüphaneler

- `pandas`
- `networkx`
- `matplotlib`
- `collections`
- `warnings`

---


