---
description: Ali Özgür
---

# 8. Gün: Dal Oluşturmak

Projelerimizde önemli ve göreceli olarak uzun sürebilecek değişikliklere başlamadan önce yerel deponuzda bir dal \(branch\) oluşturup değişiklikleri bu dal üzerinde yapmanızı öneriyorum. Bu öneri aslında Konu Dalları Akışı adı verilen ve kitabımızın 3. Bölümünde ele aldığımız Git iş akışlarından bir tanesini tanımlar.

Oluşturduğunuz yerel dal üzerinden çalışmalarımızı yapmaya devam ederken herhangi bir anda, örneğin acil bir hata durumunu gidermek için master \(master olmak zorunda değil başka herhangi bir dal de olabilir\) dalı aktif hale getirip oradaki düzenlememizi yaparak tekrar önceki dal’a geri dönebiliriz. Bu geçişler sırasında dallarda yaptığınız değişiklikler korunur.

Git'de dal oluşturmak için iki yöntemden birini kullanabilirsiniz

**Yöntem-1,** branch komutu

```bash
git branch <dalınızın adı>
```

Branch komutu ile dalınızı oluşturduktan sonra yeni dalda çalışmaya başlayabilmek için `git checkout <dalınızın adı>` komutu ile dalınızı aktif hale getirmeniz lazım.

**Yöntem-2,** checkout komutu

```bash
git checkout -b <dalınızın adı>
```

Bu komut ile yeni bir dal oluşturulur ve otomatik olarak yeni dal için checkout işlemi yapılır.

> **DİKKAT:** Yeni dal oluşturma komutlarını yazdığınız sırada hangi dalın aktif olduğu önemlidir. Her iki komut da yeni dalı o sırada aktif olan dalı referans alarak aktif dalın bir kopyasını oluşturur.

## Dal İşlemleri

```bash
# Tüm dalları listele
git branch

# Bir dalı silme 
git branch -d <dalınızın adı> 

# Dalın adını değiştir
git branch -m
```

> **İPUCU:** git status komutunu çalıştırdığınızda aktif olan dalın adını da görebilirsiniz

## Alıştırma-1

```bash
# yöntem 1
git branch <dalınızın adı>
git branch -d <dalınızın adı>

$ # yöntem 2
$ git checkout -b <adiniz>
$ git branch -d <adiniz>
```

**Soru-1:** Yukarıdaki alıştırmada kullandığımız git branch komutlarının çıktıları arasında nasıl bir fark var?

**Soru-2:** 2. yöntem ile oluşturduğunuz dalı nasıl silersiniz?

## Alıştırma-2

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Yeni bir dal oluşturun
git checkout -b <dalınızın adı>
# Proje klasörünüze yeni bir dosya ekleyin
# Eklediğiniz dosyayı commit edin

# master dalını aktif hale getirin
git checkout master 

# Dalı silin
git branch -d <dalınızın adı>
```

## Alıştırma-3

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Yeni bir dal oluşturun
git checkout -b <dalınızın adı>
# Proje klasörünüze yeni bir dosya ekleyin

# master dalını aktif hale getirin
git checkout master 

# Dalı silin
git branch -d <dalınızın adı>

# Deponuzun durumunu inceleyin
git status
```

**Soru-1:** En son çalıştırdığınız git status komutu eklediğiniz dosyayı neden listeliyor?

## Alıştırma-4

```bash
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

# Yeni bir dosya oluşturun
touch <dosyanızın adı>.txt

# Yeni bir dosya oluşturun
git add -A .
git commit -m “8.gün 4. alıştırma”

# Yeni dosyanızın içeriğini metin editörü ile değiştirin ve sonra aşağıdaki komutu çalıştırın

git stash

# Yeni dosyanızın metin editörü ile açıp içeriğini kontrol edin
```

**Soru-1:** stash komutunu çalıştırmadan önceki dosya içeriğinizi nasıl geri getirebilirsiniz?

[&lt;&lt; Geri](gun_07.md) \| [İleri &gt;&gt;](gun_09.md)

