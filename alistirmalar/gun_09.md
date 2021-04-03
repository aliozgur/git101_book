---
description: Ali Özgür
---

# 9.Gün : Değişiklikleri Birleştirme \(Merge\)

Oluşturduğumuz dallardaki değişiklikleri master dalına veya master dalındaki değişiklikleri üzerinde çalıştığınız başka bir dala entegre işlemine birleştirme \(merge\) denir.

Alıştırmalarımıza geçmeden önce aşağıdaki komutları kullanarak git log komutu için bir alias \(kısaltma\) oluşturalım.

```bash
git config --global alias.hist = "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
```

## Alıştırma-1

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Yeni bir dal oluşturalım
git checkout -b <dalınızın adı>

# Yeni bir dosya oluşturalım
touch dosya1.txt
# Oluşturduğunuz dosyayı commit edin
git add -A .
git commit -m “Dosya 1 eklendi”

# Yeni bir dosya daha oluşturalım
touch dosya2.txt
# Oluşturduğunuz dosyayı commit edin
git add -A .
git commit -m “Dosya 2 eklendi”

# Yeni bir dosya daha oluşturalım
touch dosya3.txt
# Oluşturduğunuz dosyayı commit edin
git add -A .
git commit -m “Dosya 3 eklendi”
```

## Alıştırma-2

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# master dalını aktif hale getirelim
$ git checkout master 

# Proje klasörünüzün içeriğini listeleyin
ls -lah

# Yeni bir dosya oluşturalım
touch ornek1.txt

# Oluşturduğunuz dosyayı commit edin
git add -A .
git commit -m “Örnek 1 eklendi”
```

**Soru-1:** git hist --all komutu çalıştırdığınızda iki alıştırmada yaptığınız işlemleri görüyor musunuz? Çıktıyı nasıl yorumlarsınız?

## Alıştırma-3

**master** dalındaki değişiklikleri oluşturduğunuz dal’a entegre edelim. Bu durumda birleştirme işlemi için master kaynak oluşturduğunuz diğer dal da hedeftir.

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Oluşturduğunuz dalı aktif hale getirin
git checkout <dalınızın adı> 

# master dalındaki değişiklikleri birleştirin
git merge master 

git hist --all
```

## Alıştırma-4

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# master dalını aktif hale getirelim
git checkout master 

# Eklediğiniz  ornek1.txt dosyasını metin editörünüz ile açıp içine adınızı ve soyadınızı yazın
# Değişikliklerinizi commit edin
git add -A .
git commit -m “Ad ve soyad eklendi” 

# Oluşturulan dalı aktif hale getirelim
git checkout <dalınızın adı> 

# ornek1.txt dosyasını metin editörünüz ile açıp içine Deneme yazın
# Değişikliklerinizi commit edin
git add -A .
git commit -m “Ad soyad bilgisi Deneme olarak değiştirildi”

git hist --all
git merge master
```

**Soru-1:** Çakışma oluşan dosyayı açın ve çakışma olan satırların nasıl gösterildiğini inceleyip gösterimde kullanılan notasyonu yorumlayın.

**Soru-2:** git mergetool komutunu çalıştırın ve bu komutun ne işe yaradığını yorumlayın.

**Soru-3:** merge/diff işlemlerinde Windows üzerinde WinMerge uygulamasının kullanılması için Git’de nasıl bir konfigürasyon yapmanız gerektiğini araştırın. \(OSX kullanıyorsanız SourceGear DiffMerge, Linux kullanıyorsanız da KDiff3 için araştırmanızı yapabilirsiniz\)

[&lt;&lt; Geri](gun_08.md) \| [İleri &gt;&gt;](gun_10.md)

