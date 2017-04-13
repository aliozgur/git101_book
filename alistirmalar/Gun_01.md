# 1.Gün: İstemci Kurulumları

* Putty (Bu kurulum opsiyonel), Putty Git tarafından depolara  SSH ile erişmek için kullanılır. 2. adımda kuracağınız Git for Windows SSH için OpenSSH mı yoksa Putty/Plink mi kurmak istediğinizi soracak
* Git for Windows, Git'in Windows'da çalışması için kullanılan paket.
* Görsel istemciler. Aşağıdaki iki istemciden en az bir tanesini kurabilirsiniz.
  * Atlassian SourceTree (Önerilen)
  * CollabNet GitEye

## Alıştırma-1: Git kurulumunun doğru yapıldığının test edilmesi

Windows > Start > Git Bash isimli uygulama gelmeli

Git Bash'i çalıştırıp aşağıdaki komutu yazalım

``` bash
git --version
```

Bu komut çalıştığında aşağıdakine bezer bir versiyon bilgisi görmelisiniz.

```bash
git version 2.9.2.windows.1
```

> Alıştırmaları OS X veya Linux işletim sistemlerinde yapıyorsanız komut satırında git --version komutunu  çalıştırabilirsiniz.

## Alıştırma-2: Git konfigürasyonunun yapılması

Bu alıştırmayı yapmadan önce
* Kitabın 1. bölümündeki Git Konfigürasyonu başlığına tekrara göz atabilirsiniz
* Git servislerinden Github, Gitlab veya Bitbucket üzerinde bir hesap oluşturmalısınız

Git'in global konfigürasyonuna kullanıcı adınızı ve e-posta adresinizi git config  komutu ile tanımlayın.

```bash
git config --global user.name ali.ozgur
git config --global user.email ali.ozgur@xyz.com.tr
git config --global core.eol native
git config --global core.autocrlf true
```

> **İPUCU**: core.eol ve core.autocrlf değerleri Windows platformu için  önerilen değerler. Git’in windows’da End-Of-Line karaketerlerini (Windows EOL için CRLF kullanıyor, Linux, Unix ve OSX ise LF kullanıyor) düzgün çalışması için global git konfigürasyonunuzda core.eol ve core.autocrlf ayarlarının yapılması gerekiyor. Ancak, proje depolarınızda .gitattributes dosyasının ilk satırında text=auto değerini girerseniz bu ayar yukarıda yapılan core.eol ve core.autocrlf ayarlarını ezecektir.


## Alıştırma-3: Uzak deponun bilgisayarınıza klonlanması

Önceki alıştırmada oluşturduğunuz Github, Gitlab veya Bitbucket hesabınız için ilgili servis sağlayıcısının sayfalarını kullanarak uzak sunucuda boş bir proje deposu oluşturun. Örneğin, Git101 isimli boş bir depo oluşturabilirsiniz. Daha sonra da  SourceTree veya GitEye uzak depoyu bilgisayarınıza kopyalayın.

Kopyalama işlemini alternatif olarak git clone komutu ile komut satırı ara yüzünden (Git Bash veya Terminal) de yapabilirsiniz. Clone komutu kullanmak isteyenler 

* Kullanıcı adı ve şifre bilgisinin bu komutta nasıl geçileceğini
* Klonlama sırasında karşılaşabileceğiniz fatal: index-pack failed şeklindeki hatayı gidermek için ne yapılması gerektiğini araştırabilir

[İleri >>](Gun_02.md)
