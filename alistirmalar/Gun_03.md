# 3.Gün: Klonlama

Klonlama işlemi ile uzakta bulunan bir Git deposunu kendi bilgisayarımıza indiriyoruz. Uzak depoyu klonlandıktan sonraki tüm değişiklikler artık bilgisayarımızdaki klon Git deposunda kayıt altına alınacak, ta ki git push komutu ile değişikliklerimizi uzaktaki depoya geri yazana kadar.

## Kolonlama Hazırlık

* **Adım-1,** 1. Gün, 3. Alıştırmada Github, Gitlab veya Bitbucket üzerinde oluşturduğunuz projenin HTTP depo adresini öğrenmemiz gerekiyor. Bunun için kullandığınız Git servisinin sayfasına girip deponuzun ana sayfasındaki “Clone” linkini kullanabilirsiniz.

* **Adım-2,** Aşağıdaki iki komutu çalıştırarak Git'in uzak deponuza HTTP üzerinden bağlanırken kullanacağı kullanıcı adını ve şifremizi geçici bir süre için kaydedeceği store bilgisini tanımlamalıyız

```bash
# Windows üzerinde şifre'nin cacheleneceği store, wincred
git config --global credential.helper wincred 

# Uzak depo servis sağlayıcısı depoları için kullanılacak olan kullanıcı adı
git config --global credential.https://<github.com|gitlab.com|bitbucket.com> <kullanıcı_adınız>
```

Wincred ve kullanıcı adımızı tanımladıktan sonra git clone komutu ile Git Bash'den \(veya Terminal\) klonlama işlemi yapıldığında Git size şifrenizi soracak ve şifre girildikten sonra klonlama işlemi gerçekleştirilecek.

> **DİKKAT:** Klonlama işlemi SourceTree veya Git Eye ile değil Git Bash veya Terminal ile komut satırından yapılacak. clone komutu ile ilgili yardım almak için git help clone komutunu kullanabilirsiniz.

## Alıştırma-1

Uzak depodaki projenizi Git Bash \(Terminal\) kullanarak Git'in komut satırı komutları ile kendi bilgisayarınıza klonlayın ve sonrasında aşağıdaki komutları çalıştırın

```baseh
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

git status
git log -n 5
```

## Alıştırma-2

```baseh
# Proje klasörünüze konumlanın
cd <proje_kök_klasörü_yolu>

mkdir src
touch <adınız>.txt

# Aşağıdaki komutları çalıştırmadan önce <adınız>.txt dosyasını açıp içine herhangi bir metin yazın
git status
git log -n 5
```

## Sorular

**Soru-1:** `git status` komutunun çıktısında verilen bilgiyi nasıl yorumlamamız lazım?  
**Soru-2:** `git log` komutunun çıktısında eklediğiniz dosyaya ilişkin herhangi bir bilgi görüyor musunuz?

[&lt;&lt; Geri](Gun_02.md) \| [İleri &gt;&gt;](Gun_04.md)

