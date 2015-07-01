# Türkçe Git 101

## Önsöz 

Son 4-5 yılda yazılım geliştiricilerin ve yazılım şirketlerinin vazgeçilmez araçlarından biri olan ve benim de bir yazılım geliştirici olarak çok başarılı bulduğum Git Dağıtık Versiyon Kontrol Sistemini (Distributed Version Control System) örnekler ile ele alarak size tanıtmaya çalışacağım.

## İngilizce Terimler

Yazılım Geliştirme ile ilgili çoğu konuda olduğu gibi maalesef Git ile ilgili kaynaklar da ağırlıklı olarak İngilizce. Terminoloji anlamında Türkçe bir kaynak hazırlamanın en büyük zorluğu İngilizce terimlere Türkçe uygun karşılık bulmaktır. Ancak **Git 101** kitabında İnglizce -> Türkçe geçişini birebir yapmayacağım, mümkün olduğu kadar Versiyon Kontrolü ve Git ile ilgili terimlerin İnglizce hallerini kullanmaya çalışacağım.

Konuların diziliminde ve içeriğin oluşturulmasında [Learn Version Control with Git](http://www.git-tower.com/learn/ebook/command-line/introduction  "Learn Version Control with Git") isimli kitapçığın online versiyonu baz alınmıştır. Belirtilen kaynaktaki başlıklara ve içeriğe ilave olarak daha ayrıntılı bir kitap olan [Pro Git](http://git-scm.com/book "Pro Git") kitabından ve son bölümde linklerini paylaştığım online diğer kaynaklardan da faydalanılmıştır.


## Örnekler

Örneklerimizi **Terminal** (komut satırı veya command line olarak da tabir edilen) üzerinden Apple Mac OS X işletim sistemi kullanarak oluşturacağız. Bu kaynağın oluşturulduğu anda benim bilgisayarımdaki Apple Mac OS X ve git versiyonları aşağıdaki gibi

* OS X versiyonu : 10.9.4 (Mavericks)
* Git versiyonu : 1.8.5.2 (Apple Git-48)

Git, OS X'in yanısıra tüm Linux dağıtımları ve Windows'da da çalışmaktadır. Git komutları kullandığınız işletim sistemine göre değişmez ancak Git kurulumu kullandığınız işletim sistemine göre değişebilir. İşletim sisteminize bağlı olarak kurulum yönergeleri için arama motorlarını kullanarak gerekli adımları öğrenebilirsiniz.

