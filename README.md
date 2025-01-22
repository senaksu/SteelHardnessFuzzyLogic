# Çelik Sertliği Modeli için Bulanık Mantık Uygulaması

Bu proje, çelik sertliğini belirlemek amacıyla bulanık mantık tabanlı bir model geliştirmektedir. Model, çelik sertliğini soğuma hızı ve suda bekletme süresi gibi fiziksel parametrelere bağlı olarak tahmin etmektedir. Bu proje, geleneksel sertlik tahmini yöntemlerinden daha hızlı ve etkili bir alternatif sunmayı amaçlamaktadır.

## Proje Özeti

Bulanık mantık yaklaşımı kullanılarak, çelik sertliği tahmini için bir sistem geliştirilmiştir. Bu sistemde, soğuma hızı ve suda bekletme süresi girdileri ile çelik sertliği (Vickers Hardness) çıktısı hesaplanmaktadır. jFuzzyLogic kütüphanesi kullanılarak FCL (Fuzzy Control Language) dosyası oluşturulmuş ve modelleme işlemi gerçekleştirilmiştir.

Model, kullanıcıdan alınan soğuma hızı ve suda bekletme süresi girdilerini işleyerek çelik sertliğini hesaplamakta ve sonuçları COG (Merkez Ağırlık Yöntemi) gibi durulama yöntemleriyle elde etmektedir.

## Kullanılan Teknolojiler

- **Java**: Proje geliştirme dili.
- **jFuzzyLogic**: Bulanık mantık hesaplamalarını yapmak için kullanılan kütüphane.
- **FCL (Fuzzy Control Language)**: Modelin tanımlanması için kullanılan dil.

## Değişkenler ve Aralıklar

### Girdiler

1. **Soğuma Hızı (Δ°C/sn)**: 0 - 120
    - Düşük (0 - 60)
    - Orta (30 - 90)
    - Yüksek (60 - 120)

2. **Suda Bekletme Süresi (sn)**: 0 - 60
    - Kısa (0 - 30)
    - Orta (15 - 45)
    - Uzun (30 - 60)

### Çıktı

1. **Çelik Sertliği (Vickers Hardness)**: 200 - 800
    - Çok Yumuşak (200 - 300)
    - Yumuşak (250 - 400)
    - Orta (300 - 500)
    - Sert (400 - 700)
    - Çok Sert (600 - 800)

## Proje Dosya Yapısı

- **CelikSertligi.java**: Çelik sertliğini hesaplayan sınıf. Fuzzy Logic modelini çalıştırır ve FCL dosyasını yükler.
- **test.java**: Ana çalışma dosyası. Kullanıcıdan veri alır ve `CelikSertligi` sınıfını kullanarak sertlik hesaplamalarını yapar.
- **CelikSertligiModel.fcl**: Fuzzy Logic modelinin kuralları ve üyelik fonksiyonlarını tanımlar.

## Kurallar

Proje kapsamında tanımlanan bazı örnek kurallar:

1. **Kural 1**: Soğuma hızı düşük ve suda bekleme süresi kısa ise çelik çok yumuşaktır.
2. **Kural 2**: Soğuma hızı düşük ve suda bekleme süresi orta ise çelik yumuşaktır.
3. **Kural 3**: Soğuma hızı düşük ve suda bekleme süresi uzun ise çelik yumuşaktır.
4. **Kural 4**: Soğuma hızı orta ve suda bekleme süresi kısa ise çelik yumuşaktır.
5. **Kural 5**: Soğuma hızı orta ve suda bekleme süresi orta ise çelik orta sertliktedir.
6. **Kural 6**: Soğuma hızı orta ve suda bekleme süresi uzun ise çelik serttir.
7. **Kural 7**: Soğuma hızı yüksek ve suda bekleme süresi kısa ise çelik serttir.
8. **Kural 8**: Soğuma hızı yüksek ve suda bekleme süresi orta ise çelik çok serttir.
9. **Kural 9**: Soğuma hızı yüksek ve suda bekleme süresi uzun ise çelik çok serttir.
