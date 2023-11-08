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
* TAHMİN

  %90 tahmin aralığını hesaplayacağız
  
 ```python
forecasts = sf.predict(h=24)
forecasts['MSTL-lo-90'] = forecasts['MSTL'] - (1.645 * forecasts['MSTL'].std())
forecasts['MSTL-hi-90'] = forecasts['MSTL'] + (1.645 * forecasts['MSTL'].std())
print(forecasts[['ds', 'MSTL', 'MSTL-lo-90', 'MSTL-hi-90',]].head())
```

<img width="684" alt="Screen Shot 2023-11-06 at 22 46 34" src="https://github.com/safakulgun/MSTL/assets/108941899/88d60728-2b8c-4545-82da-5d7dbd2fa4d9">


 ```python
_, ax = plt.subplots(1, 1, figsize = (20, 7))
df_plot = pd.concat([df, forecasts]).set_index('ds').tail(24 * 7)
df_plot[['y', 'MSTL']].plot(ax=ax, linewidth=2)
ax.fill_between(df_plot.index,
                df_plot['MSTL-lo-90'],
                df_plot['MSTL-hi-90'],
                alpha=.35,
                color='orange',
                label='MSTL-level-90')
ax.set_title('PJM Load Hourly', fontsize=22)
ax.set_ylabel('Electricity Load', fontsize=20)
ax.set_xlabel('Timestamp [t]', fontsize=20)
ax.legend(prop={'size': 15})
ax.grid()
```
![predict](https://github.com/safakulgun/MSTL/assets/108941899/2eb8fbd3-d568-4af1-b264-956c68166980)

# MSTL MODELİNİN PERFORMANSI

* Test\Train Set

  ```python
df_test = df.tail(24)
df_train = df.drop(df_test.index)
```
* MSTL modeli

  ```python
sf = StatsForecast(
    models=[mstl, SeasonalNaive(season_length=24)], # add SeasonalNaive model to the list
    freq='H'
)
from time import time
sf = sf.fit(df=df_train)
forecasts_test = sf.predict(h=len(df_test))
init = time()
sf = sf.fit(df=df_train)
forecasts_test = sf.predict(h=len(df_test))
end = time()
forecasts_test.head()
```

<img width="577" alt="Screen Shot 2023-11-08 at 22 15 58" src="https://github.com/safakulgun/MSTL/assets/108941899/af58ed07-16b3-4c63-9477-b7b3dcd95ef3">

```python
time_mstl = (end - init) / 60
print(f'MSTL Time: {time_mstl:.2f} minutes')
```
MSTL Time: 0.22 minutes

```python
plot_forecasts(df_train, df_test, forecasts_test, models=['MSTL', 'SeasonalNaive'])
```
![Figure_1](https://github.com/safakulgun/MSTL/assets/108941899/d80dd276-5002-4832-b860-a34b519f04dc)

MSTL Zaman serisinin davranışını takip eden çok doğru tahminler ürettiğini görüyoruz. Şimdi modelin doğruluğunu sayısal olarak inceleyelim.

```python
def evaluate_performace(y_hist, y_true, y_pred, models):
    y_true = y_true.merge(y_pred, how='left', on=['unique_id', 'ds'])
    evaluation = {}
    for model in models:
        evaluation[model] = {}
        for metric in [mase, mae, mape, rmse, smape]:
            metric_name = metric.__name__
            if metric_name == 'mase':
                evaluation[model][metric_name] = metric(y_true['y'].values, 
                                                 y_true[model].values, 
                                                 y_hist['y'].values, seasonality=24)
            else:
                evaluation[model][metric_name] = metric(y_true['y'].values, y_true[model].values)
    return pd.DataFrame(evaluation).T
```
```python
evaluate_performace(df_train, df_test, forecasts_test, models=['MSTL', 'SeasonalNaive'])
```
<img width="577" alt="Screen Shot 2023-11-08 at 22 43 43" src="https://github.com/safakulgun/MSTL/assets/108941899/9fddf30a-737f-4518-adbc-292e039be0d8">

Verilere bakıldığında MSTL modeli, SeasonalNaive modeline göre daha iyi performans sergiliyor gibi gözükmektedir.

# PROPHET İLE KARŞILAŞTIRMA

Zaman serisi tahmini için en yaygın kullanılan modellerden biridir. Tatil günleri, mevsimsel etkiler ve özel olaylar gibi zaman serisi verilerinin özelliklerini otomatik olarak ele alabilen güçlü ve esnek bir modele sahiptir. Verilerin trendlerini ve mevsimsel desenlerini modellemek için parametrik bir yaklaşım kullanır ve belirli bir veri setine uyarlanabilir. Ayrıca tatil günleri gibi özel olayları da kolayca ekleyebilirsiniz.

```python
from prophet import Prophet

# create prophet model
prophet = Prophet(interval_width=0.9)
init = time()
prophet.fit(df_train)
# produce forecasts
future = prophet.make_future_dataframe(periods=len(df_test), freq='H', include_history=False)
forecast_prophet = prophet.predict(future)
end = time()
# data wrangling
forecast_prophet = forecast_prophet[['ds', 'yhat', 'yhat_lower', 'yhat_upper']]
forecast_prophet.columns = ['ds', 'Prophet', 'Prophet-lo-90', 'Prophet-hi-90']
forecast_prophet.insert(0, 'unique_id', 'PJM_Load_hourly')
forecast_prophet.head()
```
<img width="597" alt="Screen Shot 2023-11-08 at 23 09 40" src="https://github.com/safakulgun/MSTL/assets/108941899/f569a4ff-5fc7-461e-a3b3-3c3e5e73a7d5">

```python
time_prophet = (end - init) / 60
print(f'Prophet Time: {time_prophet:.2f} minutes')
```
Prophet Time: 0.45 minutes

```python
times = pd.DataFrame({'model': ['MSTL', 'Prophet'], 'time (mins)': [time_mstl, time_prophet]})
times
```
<img width="238" alt="Screen Shot 2023-11-08 at 23 18 00" src="https://github.com/safakulgun/MSTL/assets/108941899/c201e1b0-23b5-43ce-b314-284101c5d733">

```python
forecasts_test = forecasts_test.merge(forecast_prophet, how='left', on=['unique_id', 'ds'])
plot_forecasts(df_train, df_test, forecasts_test, models=['MSTL', 'SeasonalNaive', 'Prophet'])
```
![Figure_1](https://github.com/safakulgun/MSTL/assets/108941899/e8a4992f-81c1-47e6-ab31-7cda5e170ce3)

Prophet'ın zaman serisinde genel davranışları yakaladığını söyleyebiliriz fakat bazı durumlarda gerçek değerin oldukça altında tahminler üretir.

```python
evaluate_performace(df_train, df_test, forecasts_test, models=['MSTL', 'Prophet', 'SeasonalNaive'])
```
<img width="576" alt="Screen Shot 2023-11-08 at 23 32 38" src="https://github.com/safakulgun/MSTL/assets/108941899/56ad5949-1a09-4b85-ae2f-8fd5da4607f2">

# NEURAlPROPHET İLE KARŞILAŞTIRMA
```python
from neuralprophet import NeuralProphet

neuralprophet = NeuralProphet(quantiles=[0.05, 0.95])
init = time()
neuralprophet.fit(df_train.drop(columns='unique_id'))
future = neuralprophet.make_future_dataframe(df=df_train.drop(columns='unique_id'), periods=len(df_test))
forecast_np = neuralprophet.predict(future)
end = time()
forecast_np = forecast_np[['ds', 'yhat1', 'yhat1 5.0%', 'yhat1 95.0%']]
forecast_np.columns = ['ds', 'NeuralProphet', 'NeuralProphet-lo-90', 'NeuralProphet-hi-90']
forecast_np.insert(0, 'unique_id', 'PJM_Load_hourly')
forecast_np.head()
```
<img width="428" alt="Screen Shot 2023-11-08 at 23 46 08" src="https://github.com/safakulgun/MSTL/assets/108941899/85d62431-d4d0-402d-9202-38a66bf5c462">


```python
time_np = (end - init) / 60
print(f'Prophet Time: {time_np:.2f} minutes')
```
Prophet Time: 4.21 minutes

```python
times = times.append({'model': 'NeuralProphet', 'time (mins)': time_np}, ignore_index=True)
times
```
<img width="322" alt="Screen Shot 2023-11-08 at 23 48 37" src="https://github.com/safakulgun/MSTL/assets/108941899/693d41e7-4b9b-43a4-a4b7-4518f66b30f4">

```python
forecasts_test = forecasts_test.merge(forecast_np, how='left', on=['unique_id', 'ds'])
plot_forecasts(df_train, df_test, forecasts_test, models=['MSTL', 'NeuralProphet', 'Prophet'])
```
![Figure_1](https://github.com/safakulgun/MSTL/assets/108941899/a8127624-293a-47ca-8abd-96127d78ec79)

```pythonevaluate_performace(df_train, df_test, forecasts_test, models=['MSTL', 'NeuralProphet', 'Prophet', 'SeasonalNaive'])
```
<img width="595" alt="Screen Shot 2023-11-08 at 23 53 45" src="https://github.com/safakulgun/MSTL/assets/108941899/2c7bf2fe-4a54-4994-937b-cf2535d835c7">

Sonuçlara baktığımız zaman  MSTL ve SeasonalNaive modelleri, NeuralProphet ve Prophet modellerine göre daha iyi tahmin performansı sergiliyor.
