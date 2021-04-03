---
description: Ali Özgür
---

# Remote  bir proje oluşturmak

Versiyon kontrolü Git ile yapılan bir projede yer alıyorsanız _remote repository_'lerinizi nasıl yöneteceğinizi de öğrenmeniz gerekir. Remote repository'leri projelerinizi internette veya sınırlı erişime izin verilen şirket ağında yer alan versiyonları olarak düşünebilirsiniz.

Diğer ekip üyeleri ile birlikte verimli çalışabilmek, onların yaptığı değişiklikleri kendi yerel çalışma alanınıza almak, kendi yaptığınız değişiklikleri onlar ile paylaşabilmek için remote repository'lerinizi doğru ve etkin bir şekilde yönetmelisiniz.

Git ile versiyon kontrolü yapılan bir projeye dahil olduğunuzda size verilecek ilk bilgiler projenin Git adresi \(URL\) ve projeye erişim için kullanacağınız kullanıcı adı ve şifrenizdir. Uzaktaki bir repository'nin \(URL\) adresi aşağıdaki formatlardan birinde olacaktır

* ssh://user@server/git-repo.git
* kullanıcıadı@sunucuadı:git-repo.git
* [http://example.com/git-repo.git](http://example.com/git-repo.git)
* [https://example.com/git-repo.git](https://example.com/git-repo.git)
* git://example.com/git-repo.git

Bu adres formatlarından ilk iki tanesi [SSH](http://en.wikipedia.org/wiki/Secure_Shell) \(Secure Shell\) protokolüne karşılık gelir. http:// ve https:// protokolleri ise normal internet erişimi için de kullanılan protokollerdir. Son format ise git'in kendi protokolüne karşılık gelir.

Remote repository'nizin adresini ve erişim için gerekli kullanıcı adınızı ve şifrenizi öğrendikten sonra yapmanız gereken tek şey bu adresten projenizin dosyalarını yerel diskinize klonlamak. Bunun için öncelikle yerel diskinizde projenizi indireceğiniz bir klasör oluşturmanız ve Terminal'den bu klasöre gitmeniz gerekiyor. Sırasıyla aşağıdaki komutları Terminal'de yazınız

![Bo&#x15F; Klas&#xF6;r Olu&#x15F;turma](../.gitbook/assets/01_emptyprojectdir.jpg)

Yukarıdaki ekran görüntüsünde yer alan ilk **cd** komutu ile proje klasörümün içinde yer alacağı ana klasör olan **Projects** klasörüne konumlanıyoruz. İkinci komut olan **mkdir** ile proje klasörümüz olan **git101\_kitap** klasörünü oluşturuyoruz. Üçüncü komutumuz ile de yeni oluşturduğumuz **git101\_kitap** klasörüne konumlanıyoruz.

Yerel diskimizde boş proje klasörümüzü oluşturduğumuza göre şimdi remote repository'mizi yerel klasörümüze **git clone** komutu ile indirebiliriz.

!\[Remote repository'yi klonlama\]\(02\_cloneremote.jpg "Remote repository'yi klonlama"\)

> Kullanıcı adınızı ve şifrenizi vererek remote repository'yi klonlamak için aşağıdaki **git clone** komutuna bu bilgileri aşağıdaki formatta vermeniz gerekiyor
>
> git clone [https://kullanıcıadı:şifre@github.com/username/repository.git](https://kullanıcıadı:şifre@github.com/username/repository.git)

