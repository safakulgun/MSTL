# MSTL
MSTL ile Elektrik Yükü Tahmini
MSTL modeli, zaman serilerini mevsimsel, trend ve artık bilesenlere ayırmak için kullanılan bir yöntemdir. Bu yaklaşım, zaman serilerinin bileşenlerini tahmin etmek için LOESS (Yerel Regresyon Düzeltme) yöntemini kullanır.

MSTL ayrıştırması, klasik mevsimsel-trend ayrıştırma yöntemlerinin (örneğin Holt-Winters ayrıştırma) bir gelişmesi olarak tasarlanmıştır. Bu yöntem, özellikle zaman serilerinin birden fazla mevsimsel model içerdiği durumları ele almak için kullanışlıdır. Örneğin, bir zaman serisi hem günlük, hem haftalık, hem de yıllık mevsimsel desenler gösteriyorsa MSTL ayrıştırma bu karmaşıklığı ele alabilir.

MSTL ayrıştırma işlemi şu adımları içerir:

1. Trend Tahmini: LOESS, zaman serisinin trend bileşenini tahmin etmek için kullanılır. LOESS, verilere yerel olarak uyar ve karmaşık trend modellerini yakalayabilir.

2. Mevsimsel Bileşenlerin Tahmini: Verilerde farklı mevsimsel desenleri tanımak ve modellemek için mevsimsel ayrıştırma teknikleri kullanılır. Bu, günlük, haftalık veya yıllık mevsimsel bileşenlerin çıkarılmasını ve modellemesini içerir.

3. Artık Bileşenlerin Tahmini: Artık bileşenler, orijinal zaman serisi ile trend ve mevsimsel bileşen tahminlerinin farkı olarak hesaplanır. Artıklar, trend ve mevsimsel desenlerle açıklanmayan varyasyonları temsil eder ve ek bilgi veya gürültü içerebilir.

MSTL ayrıştırması, bir zaman serisinin farklı bileşenlerini ayrıntılı bir şekilde analiz etme ve anlama olanağı sunar. Bu, zaman serisindeki desenleri veya anormallikleri tahmin etmeyi ve tespit etmeyi kolaylaştırabilir. Ayrıca LOESS'in kullanımı, farklı trend ve mevsimsel desenlere esnek bir şekilde uyum sağlar.

Unutmayın ki MSTL modeli, zaman serisi ayrıştırması için yalnızca bir yöntemdir ve kullanılacak yöntem, verilerin özelliklerine ve uygulama bağlamına bağlı olarak değişebilir.
LOESS (Yerel Regresyon Düzeltme)
LOESS, verilerdeki düzgün bir işlevi tahmin etmek için kullanılan parametrik olmayan bir yumuşatma tekniğidir. Bu yöntem, zaman serisindeki her bir nokta için yerel olarak uyan bir regresyon yapar.

LOESS hesaplaması şu adımları içerir:

Herhangi bir t zamanındaki verileri ele alalım. Bu noktanın etrafında, t zamanındaki en yakın komşu noktalar bir pencere içinde toplanır.

Bu komşulara, t zamanındaki noktaya olan uzaklıklarına bağlı olarak ağırlıklar atanır. Bu ağırlıklar genellikle bir Gauss çekirdeği gibi bir ağırlıklandırma fonksiyonu kullanılarak hesaplanır. Bu, yakın komşulara daha fazla ağırlık verirken uzak komşulara daha az ağırlık verir.

Ağırlıklı regresyon, bu komşular ve ağırlıklar kullanılarak gerçekleştirilir. Bu regresyon, t zamanındaki değerin tahmin edilmesinde kullanılır.

Bu işlem, zaman serisindeki her bir t zamanı için tekrarlanır. Böylece, her zaman noktası için yerel bir tahmin elde edilir ve bu tahminler bir düzgünleştirme işlemi sonucu trendi oluşturur.

LOESS, verilerin yerel özelliklerini vurgulayarak karmaşık trendlerin ve desenlerin daha iyi yakalanmasını sağlar. Bu yöntem, zaman serisi analizi, veri görselleştirmesi ve tahminleme gibi birçok alanda kullanılır.

MSTL Özellikleri

1. Çoklu Mevsimsel Bileşenlerin Ayrıştırılması: MSTL modeli, aynı anda birden fazla mevsimsel desene sahip zaman serilerini ele alabilir. Farklı mevsimsel bileşenleri etkili bir şekilde tanımlayabilir ve modelleyebilir.

2. Karmaşık Trendlere Esneklik: LOESS kullanımı, MSTL modelinin karmaşık trend modellerini anlamasını sağlar. Bu, doğrusal olmayan eğilimleri ve ani değişiklikleri içerir.

3. Farklı Mevsimsel Frekanslara Uyarlanabilirlik: MSTL modeli, günlük, haftalık, aylık veya yıllık mevsimsel döngüler gibi farklı mevsimsel frekanslara sahip verileri işleyebilir. Bu, farklı döngü uzunluklarındaki mevsimsel desenleri tanımlamanıza olanak tanır.

4. Gürültüyü ve Aykırı Değerleri Düzeltme Yeteneği: LOESS'in yumuşatma işlemi, zaman serisindeki gürültünün ve aykırı değerlerin etkisini azaltır. Bu, altta yatan modellerin daha iyi tespit edilmesine ve trend ile mevsimselliklerin daha iyi analiz edilmesine yardımcı olur.

5. Geliştirilmiş Tahmin: MSTL modeli, zaman serilerini mevsimsel, trend ve artık bileşenlere ayırarak daha doğru tahminler sunar. Bu, gelecekteki trend ve mevsimsel desenlerin daha iyi tahmin edilmesini sağlar.

6. Daha Ayrıntılı Analiz İmkanı: MSTL ayrıştırması, zaman serisini daha detaylı bir şekilde analiz etmenizi sağlar. Bu, mevsimsel kalıpları, trenddeki değişiklikleri tanımlamanıza ve kalan değişkenliği değerlendirmenize yardımcı olur.

7. Verimli Uygulama: MSTL modeli, uygun algoritmalar kullanıldığında verimli bir şekilde hesaplanabilir ve birçok farklı uygulama için kullanılabilir.

Bu özellikler, MSTL modelini karmaşık zaman serileriyle çalışırken keşif amaçlı analiz, tahmin ve modelleme için etkili bir araç haline getirir.

# UYGULAMA

* Veri Seti Hikayesi
  
  PJM Interconnection LLC (PJM), Amerika Birleşik Devletleri'nde bölgesel bir iletim organizasyonudur (RTO). Delaware, Illinois, Indiana, Kentucky, Maryland, Michigan, New Jersey, North Carolina, Ohio, Pennsylvania, Tennessee, Virginia, West Virginia ve District of Columbia'nın tamamına veya bir kısmına hizmet veren bir elektrik iletim sistemi işleten Eastern Interconnection şebekesinin bir parçasıdır. Saatlik güç tüketimi verileri PJM'nin web sitesinden alınmıştır ve megawatt (MW) cinsindendir.

```python
import matplotlib.pyplot as plt

import numpy as np

import pandas as pd

from statsforecast import StatsForecast

from statsforecast.models import MSTL, AutoARIMA, SeasonalNaive

from statsforecast.utils import AirPassengers as ap

df = pd.read_csv('PJM_Load_hourly.csv')

df.head
 ```
<img width="573" alt="Screen Shot 2023-11-04 at 17 05 17" src="https://github.com/safakulgun/MSTL/assets/108941899/eb6a34f7-8f43-43bc-9764-911a4b8e5ce5">

```python
df.types
```
Datetime        object

PJM_Load_MW    float64

```python
df.isnull().sum()
```
unique_id    0

Datehours    0

Load         0

dtype: int64

```python
df.columns = ['Datehours', 'Load']
df.insert(0, 'unique_id', 'PJM_Load_hourly')
df['Datehours'] = pd.to_datetime(df['Datehours'])
df = df.sort_values(['unique_id', 'Datehours']).reset_index(drop=True)

df.tail()
```
<img width="469" alt="Screen Shot 2023-11-04 at 18 27 22" src="https://github.com/safakulgun/MSTL/assets/108941899/c92f4af0-13c5-4ffd-bedc-23ed018c47ef">

```python
df.plot(x='Datehours', y='Load')
```
![Figure_1](https://github.com/safakulgun/MSTL/assets/108941899/950efc14-aa2b-4be6-b697-116fbfe69eaa)

Zaman serisinin mevsimsel davranış sergideğini görüyoruz. Burada 32.896 gözlem olduğundan üretimde görüntülemek adına hesaplama bakımından verimli yöntemler kullanmak gereklidir.

# MSTL MODEL

Elektrik yükü 24 saatte bir (Saatlik) ve 24*7 (Günlük) saatte bir mevsimsellik göstermektedir. [24, 24 * 7]Dolayısıyla MSTL modelinin aldığı mevsimsellikleri kullanacağız . Aynı zamanda trendin nasıl tahmin edileceğini de belirtmeliyiz. Bu durumda  AutoARIMA modelini kullanacağız.

```python
#StatsForecast nesnesinin giriş veri çerçevesinde
# "unique_id", "ds" ve "y" sütunlarını bekler.
df.columns = ['ds', 'y']
df.insert(0, 'unique_id', 'PJM_Load_hourly')
df['ds'] = pd.to_datetime(df['ds'])
df = df.sort_values(['unique_id', 'ds']).reset_index(drop=True)
mstl = MSTL(
    season_length=[24, 24 * 7],
    trend_forecaster=AutoARIMA()
)
sf = StatsForecast(
    models=[mstl],
    freq='H',
)
sf = sf.fit(df=df)

```
* Zaman serilerini birden fazla mevsimselliğe göre ayrıştırma

```python
sf.fitted_[0, 0].model_
```
<img width="532" alt="Screen Shot 2023-11-04 at 20 08 12" src="https://github.com/safakulgun/MSTL/assets/108941899/e728a69b-c0a2-456d-b809-c45957a45fb3">

Bileşenlerine grafiksel olarak bakalım.

```python
sf.fitted_[0, 0].model_.tail(24 * 28).plot(subplots=True, grid=True)
plt.tight_layout()
plt.show()
```
![Figure_1](https://github.com/safakulgun/MSTL/assets/108941899/36d45822-fe36-4057-957a-6e38a56c5acf)

Burada trend çizgisinin yukarı yönde artan olduğunu görmekteyiz. Dolayısıyla AutoARIMA modelini kullanabiliriz ayrıca  iki bileşen  SeasonalNaiveBu modeli kullanılarak ayrı ayrı tahmin edilecektir.




