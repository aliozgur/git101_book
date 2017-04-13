# 2.Gün: Yerel Depo Oluşturma

Git ile çalışabilmek için illa bir sunucu kurulumuna veya bir Git servis sağlayıcısına ihtiyaç duyulmaz. Git kurulumumuzu tamamladığımıza göre artık kendi bilgisayarımızda da bir depo oluşturup denemelerimizi yapabiliriz.

Bilgi Kutusu (NOT) : Git'in push, pull gibi birkaç komutu dışındaki tüm komutlar kendi bilgisayarınızda çalıştırdığınız komutlardır.

Git'de boş bir repository oluşturmak için git init komutunu kullanırız. Init komutunun genel şablonu ve komut ile ilgili yardım almak için kullanabileceğiniz Git komutu aşağıdaki gibidir.

```bash
git help <komut_adı>
git help init
```

## Alıştırma-1
Git Bash veya Terminal komut satırını ara yüzünü açarak herhangi bir parametre kullanmadan aşağıdaki komutları sırası ile çalıştırın

```bash
Diskinizin C bölümüne konumlanın
cd C:/

# pg_00 isimli boş bir klasör oluşturun. Bu projenizi temsil eden kök klasördür
mkdir pg_00

# pg_00 isimli klasöre konumlanın
cd pg_00

# pg_00 proje klasörünüzü Git deposu haline getirin
git init
```

## Alıştırma-2

```bash

# Diskinizin C bölümüne konumlanın
cd C:/
	
# pg_00 isimli klasörü silin
rm -r pg_00
	
# pg_00 proje klasörünü oluşturup Git deposu haline getirin
git init pg_00
```

## Alıştırma-3
Bu alıştırmaya başlamadan önce kitabın 3. Bölümünde yer alan “Tek Dallı Akış” başlığı altındaki Yalın Depolar ile ilgili açıklamaları tekrar okuyun. 

Aşağıdaki komutları sırası ile çalıştırın ve en son komutun verdiği bilgi mesajını bir yere not edin.  

```bash
cd C:/

rm -r pg_00

git init --bare pg_00.git

cd pg_00.git

git status
```

[<< Geri](Gun_01.md) | [İleri >>](Gun_03.md)