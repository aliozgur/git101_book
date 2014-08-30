# Türkçe Git 101

## Önsöz

Son 4-5 yılda yazılım geliştiricilerin ve yazılım şirketlerinin vazgeçilmez araçlarından biri olan ve benim de bir yazılım geliştirici olarak çok başarılı bulduğum Git Dağıtık Versiyon Kontrol Sistemini (Distributed Version Control System) örnekler ile ele alarak size tanıtmaya çalışacağım.

## İngilizce Terimler

Yazılım Geliştirme ile ilgili çoğu konuda olduğu gibi maalesef Git ile ilgili kaynaklar da ağırlıklı olarak İngilizce. Terminoloji anlamında Türkçe bir kaynak hazırlamanın en büyük zorluğu İngilizce terimlere Türkçe uygun karşılık bulmaktır. Ancak **Git 101** kitabında İnglizce -> Türkçe geçişini birebir yapmayacağım, mümkün olduğu kadar Versiyon Kontrolü ve Git ile ilgili terimlerin İnglizcelerini kullanmaya çalışacağım.

Amacım çeviri nedeni ile terimlerin anlamını yitirmesine neden olmadan uluslar arası ekiplerde, özellikle de açık kaynak projelerde, ortak dil İnglizce olduğu için Git terminolojisi ile tanışmanızı sağlamak.

Konuların diziliminde ve içeriğin oluşturulmasında [Learn Version Control with Git](http://www.git-tower.com/learn/ebook/command-line/introduction  "Learn Version Control with Git") isimli kitapçığın online versiyonu baz alınmıştır. Belirtilen kaynaktaki başlıklara ve içeriğe ilave olarak daha ayrıntılı bir kitap olan [Pro Git](http://git-scm.com/book "Pro Git") kitabından ve online diğer kaynaklardan da faydalanılmıştır.


## Örnekler

Örneklerimizi **Terminal** (komut satırı veya command line olarak da tabir edilen) üzerinden Apple OS X işletim sistemi kullanarak oluşturacağız. Bu kaynağın oluşturulduğu anda benim bilgisayarımdaki OS X ve git versiyonları aşağıdaki gibi

* OS X versiyonu : 10.9.4 (Mavericks)
* Git versiyonu : 1.8.5.2 (Apple Git-48)

Git, OS X'in yanısıra tüm Linux dağıtımları ve Windows'da da çalışmaktadır. Git komutları kullandığınız işletim sistemine göre değişmez ancak Git kurulumu kullandığınız işletim sistemine göre değişebilir. İşletim sisteminize bağlı olarak kurulum yönergeleri için arama motorlarını kullanarak gerekli adımları öğrenebilirsiniz.

## Kaynakça ve Referanslar

1. [Git-Scm Referans Dokümanı](http://git-scm.com/docs)
2. [GitRef Referans Dokümanı](http://gitref.org/branching/)
3. [Learn Version Control with Git](http://www.git-tower.com/learn/ebook/command-line/introduction)
4. [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorial)
5. [Pro Git Book](http://git-scm.com/book)
6. [Atlassian Git Workflows](https://www.atlassian.com/git/workflows)
7. [Learn Git Branching Online Tutorial Application](http://pcottle.github.io/learnGitBranching/)
8. [Git: fetch and merge, don't pull]( http://longair.net/blog/2009/04/16/git-fetch-and-merge/ )
9. [Resolving a merge conflict from command line](https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line)
10. [Adding And Removing Remote Branches – Git Branch](http://www.gitguys.com/topics/adding-and-removing-remote-branches/)
