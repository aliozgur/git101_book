# Basit Anlamda Versiyon Kontrolü İş Akışı
Git'in derinliklerine dalmadan önce gelin basit bir versiyon kontrol iş akışına adım adım göz atalım.

Versiyon kontrolü'nin en temel bileşeni **repository** denilen yapıdır. Repository, dosyalarınızdaki tüm değişiklikleri ve bu değişiklikler ile ilgli ilave bilgileri (değişikliği kim, ne zaman yaptı ve değişiklik ile ilgili girilen açıklamalar) ayrı birer **versiyon** olarak kayıt altında tutan bir vertabanıdır. Git tüm bu bilgileri genellikle gizli bir klasör olarak dosya sisteminde yer alan **.git** isimli klasör içinde bir dizi dosya olarak tutar.

Yukarıda bahsettiğiniz **repository**'yi kendi bilgisayarınızda oluşturabilmek için iki yöntem kullanabilirsiniz.

* Henüz versiyon kontrolü altına almadığınız bir projeniz varsa **git init* komutu ile projenizi altındaki tüm klasör ve dosyalar ile birlikte versiyon kontrolüne alabilirsiniz
* Projeniz uzaktaki veya şirket ağınızdaki bir Git sunucusunda versiyon kontrolü altında tutuluyorsa projeyi kendi bilgisayarınıza **git clone** komutu ile indirebilirsiniz.

Projeniz için yukarıdaki yöntemlerden biri ile *repository* oluşturduktan sonra aşağıdaki basit akışı kullanarak değişikliklerinizi yapmaya başlayabilirsiniz

1. Projenizin repository'sini oluşturduktan sonra dosyalarınız üzerinde istediğiniz değişiklikleri istediğiniz uygulamayı kullanarak yapabilirsiniz. Bu aşamada yaptığınız değişiklikleri versiyon kontrolü için birebir ve doğrudan takip etmenize gerek yoktur.
2. Yaptığınız değişiklikler istediğiniz bir noktaya ulaştığında veya bir özellik veya sorun giderme düzenlemesi ile ilgili çalışmanız tamamlandığında versiyon kontrolü bakış açısı ile değişikliklerinizi değerlendirmeniz gerekir. Bu aşamada değişikliklerinizi **commit** adını verdiğimiz bir değişiklikler bütünü şeklinde tarif etmelisiniz. Böylece projemizin yeni bir versiyonunu oluşturma işleminin ilk adımını yerine getirmiş olacaksınız.
3. Fakat commit'imizi oluşturmadan önce proje dosyalarınızda yaptığınız değişikliklerin bir özetini görmek isteyebilirsiniz. *git status* komutu ile hangi dosyaları değiştirdiğinizi, sildiğinizi veya yeni hangi dosyaları eklediğinizi hızlıca görebilirsiniz.
4. Bir sonraki aşamada değişen dosyalarınızdan hangilerinin commit'inizde yer alacağını belirlemeniz gerekiyor. Bu adımda commit'inize dahil etmek istediğiniz dosyaları **staging area** denilen ara bir alana eklersiniz.
> Dosyaların içeriğinin değiştirilmiş olması, silinmesi veya yeni dosya eklenmesi bu dosyaların otomatik olarak bir sonraki commit'e dahil olmasını yani **staging area**'ya dahil edilmesini sağlamaz. Bu işlemi ilgili dosyaları seçerek sizin yapmanız gerekir.
5. Dosyalarınızı **staging area**'ya  ekledikten sonra şimdi *commit* işlemine hazırsınız. Commit işlemi ile açıklamanızı da ekleyerek değişikliklerinizin bir versiyon olarak Git veritanbanına kaydedilmesini sağlarsınız.
6. Zaman zaman, özellikle de bir takım çalışması söz konusu ise, projenizdeki değişikliklere göz atmak isteyebilirsiniz. Projeniz için oluşturduğunuz commit'lerin tarihçesini incelemek için *git log* komutunu kullanabilirsiniz.
7. Yaptığınız değişikliklerin takımın geri kalanı tarafından da görülmesini ve kullanılmaya başlanmasını sağlamak için değişikliklerinizi zaman zaman uzaktaki Git repository'sinde yayınlamanız gerekir. Bunun için *git push* komutunu kullanacağız.

> **Local (Yerel) & Remote (Uzak) Repository'ler**
> * Local repository, kendi bilgisyarınızda proje klasörünüzün altında bulunan .git klasörüdür. Bu repository üzerinde sadece siz çalışabilirsiniz ve değişiklikler yerel diskinize kaydedilir.
> * Remote repository'ler ise  genellikle uzaktaki bir sunucuda yer alırlar ve bu sunucudaki .git klasöründen ibarettirler. Takım çalışması söz konusu ise takımdaki kişiler değişikliklerini bu uzaktaki repository üzerinden paylaşırlar.


