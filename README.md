# Dengesiz Veri Setinde Kredi Kartı Dolandırıcılığı Tespiti

Bu proje, dengesiz veri seti üzerinde kredi kartı dolandırıcılığı tespitini amaçlamaktadır. Makine öğrenmesi algoritmaları kullanılarak veri üzerinde analizler yapılmış ve farklı modelleme yöntemleri denenmiştir.

## 🔍 Veri Seti

Kullandığımız veri seti, yüksek boyutlu olduğu için doğrudan GitHub'a yüklenememektedir. Ancak aşağıdaki bağlantıdan indirilebilir:

🔗 [Kaggle - Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud/)

Veri seti, Avrupa'da gerçekleşen kredi kartı işlemlerine aittir ve yalnızca sayısal veriler içermektedir. Toplamda **284,807** işlem bulunmaktadır.

### 📊 Veri Dengesizliği

Veri setinde ciddi bir dengesizlik söz konusudur:

- Normal İşlemler: 284,315
- Dolandırıcılık İşlemleri: 492

---

## ⚙️ Kullanılan Algoritmalar

Veri ön işleme ve temizleme işlemleri tamamlandıktan sonra aşağıdaki makine öğrenmesi algoritmaları kullanılarak modellemeler yapılmıştır:

- Lojistik Regresyon
- Karar Ağacı
- Rastgele Orman

---

## 📈 Lojistik Regresyon Sonuçları

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 53804    | 1234 |
| 1     | 9    | 86 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9998    | 0.9776 | 0.9886   | 55038   |
| 1     | 0.0652    | 0.9053 | 0.1216   | 95      |

- **Accuracy:** 0.9775  
- **Macro Average F1-Score:** 0.5551  
- **Weighted Average F1-Score:** 0.9871  

## 📈 Karar Ağacı Sonuçları

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 55010    | 28 |
| 1     | 37| 58 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9993    | 0.9995 | 0.9994   | 55038   |
| 1     | 0.6744    | 0.6105 | 0.6409   | 95      |

- **Accuracy:** 0.9988  
- **Macro Average F1-Score:** 0.8201
- **Weighted Average F1-Score:** 0.9988

## 📈 Rastgele Orman

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 55032    | 6 |
| 1     | 29| 66 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9995    | 0.9999 | 0.9997   | 55038   |
| 1     | 0.9167    | 0.6947 | 0.7904   | 95      |

- **Accuracy:** 0.9994  
- **Macro Average F1-Score:** 0.8951
- **Weighted Average F1-Score:** 0.9993

# Undersampling(Alt Örnekleme)

Bu sonuçlardan sonra verimizin dengesizliğinden kurtulmak için undersampling uyguladık. 473 normal işleme karşılık 473 dolandırıcılık işlemi oldu bu şekilde.

## 📈 Lojistik Regresyon Sonuçları

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 94    | 1 |
| 1     | 9    | 86 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9126    | 0.9895 | 0.9495   | 95   |
| 1     | 0.9885    | 0.9053 | 0.9451   | 95      |

- **Accuracy:** 0.9474
- **Macro Average F1-Score:** 0.9473
- **Weighted Average F1-Score:** 0.9473  

## 📈 Karar Ağacı Sonuçları

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 88    | 7 |
| 1     | 6| 89 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9362    | 0.9263 | 0.9312   | 95   |
| 1     | 0.9271    | 0.9368 | 0.9319   | 95      |

- **Accuracy:** 0.9316
- **Macro Average F1-Score:** 0.9316
- **Weighted Average F1-Score:** 0.9316

## 📈 Rastgele Orman

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 94 | 1 |
| 1     | 9| 86 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9126   | 0.9895 | 0.9495   | 95   |
| 1     | 0.9885    | 0.9053 | 0.9451   | 95  |

- **Accuracy:** 0.9474
- **Macro Average F1-Score:** 0.9473
- **Weighted Average F1-Score:** 0.9473


# Oversampling (Aşırı Örnekleme)

Undersamplingden sonra Oversamplingide deneye karar verdik. Oversamplingde ise 473 olan dolandırıcılık işlemi sayısını çokça arttırarak makine öğrenmesine yardımcı olmasını bekliyoruz.

## 📈 Lojistik Regresyon Sonuçları

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 53804    | 1234 |
| 1     | 9    | 86 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9998    | 0.9776 | 0.9886   | 55038   |
| 1     | 0.0652    | 0.9053 | 0.1216   | 95      |

- **Accuracy:** 0.9775
- **Macro Average F1-Score:** 0.5551
- **Weighted Average F1-Score:** 0.9871  

## 📈 Karar Ağacı Sonuçları

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 55010    | 28 |
| 1     | 37 | 58 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9993    | 0.9995 | 0.9994   | 55038   |
| 1     | 0.6744    | 0.6105 | 0.6409   | 95      |

- **Accuracy:** 0.9988
- **Macro Average F1-Score:** 0.8201
- **Weighted Average F1-Score:** 0.9988

## 📈 Rastgele Orman

### Confusion Matrix:

|  | 0 | 1 |
|-------|-----------|--------|
| 0     | 55032 | 6 |
| 1     | 29| 66 |

### Classification Report:

| Sınıf | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.9995   | 0.9999 | 0.9997   | 55038   |
| 1     | 0.9167    | 0.6947 | 0.7904   | 95  |

- **Accuracy:** 0.9994
- **Macro Average F1-Score:** 0.8951
- **Weighted Average F1-Score:** 0.9993
## Ekler

Herhangi bir ek bilgi buraya gelir

  