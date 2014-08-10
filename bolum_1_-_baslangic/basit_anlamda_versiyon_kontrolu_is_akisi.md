# 1.4 Basit Anlamda Versiyon Kontrolü İş Akışı
Git'in derinliklerine dalmadan önce gelin basit bir versiyon kontrol iş akışına adım adım bir göz atalım.

Versiyon kontrolü'nin en temel bileşeni **repoistory** denilen yapıdır. Repository, dosyalarınızdaki tüm değişiklikleri ve bu değişiklikler ile ilgli ilave bilgileri (değişikliği kim, ne zaman yaptı ve değişiklik nasıl bir yorum ile tarif etti gibi) ayrı birer **versiyon** olarak kayıt altında tutulmasını sağlayan bir vertabanıdır. Git tüm bu bilgileri genellikle gizli bir klasör olarak dosya sisteminde yer alan **.git** klasörü atında yer alan bir dizi dosya olarak kayıt altında tutar.

Yukarıda bahsettiğiniz **repoistory**'nin kendi bilgisayarınızda oluşturabilmek için iki yöntem kullanabilirsiniz.

* Henüz versiyon kontrolü altına almadığınız bir projeniz varsa *git init* komutu ile projenizin (altındaki tüm klasör ve dosyalar ile birlikte) versiyon kontrolü altına alabilirsiniz
* Eğer bir proje ekibine yeni dahil oluyorsanız ve bu ekip proje dosyalarını uzaktaki veya şirket ağınızdaki bir git sunucusunda versiyon kontrolü altında tutuyorsa siz de kendi bilgisayarınıza bu projenin tüm içeriğini *git clone* komutu ile indirebilirsiniz.

Projeniz için yukarıdaki iki yöntemden biri ile *repoistory* oluşturduktan sonra aşağıdaki basit akış ile çalışmaya başlayabilirsiniz

1. Projenizin repository'sini oluşturduktan sonra dosyalarınız üzerinde istediğiniz değişiklikleri istediğiniz uygulamayı kullanarak yapmaya başlayabilirsiniz. Bu aşamada yaptığınız değişiklikleri doğrudan takip etmenize gerek yoktur.
2. Yaptığınız değişiklikler kayde değer bir noktaya ulaştığında veya bir özellik veya sorun giderme düzenlemesi ile ilgili çalışmanız tamamlandığında versiyon kontrolü bakış açısı ile değişikliklerinizi değerlendirmeniz gerekir. Bu aşamada değişikliklerinizi *commit* adını verdiğimiz anlamsal bir değişiklikler bütünü ile tarif etmelisiniz. Böylece projemizin yeni bir versiyonunu oluşturma işleminin ilk adımını yerine getirmiş olacaksınız.
3. Fakat commit'imizi oluşturmadan önce proje dosyalarınızda yaptığınız değişikliklerin bir özetini görmek isteyebilirsiniz. *git status* komutu ile hangi dosyaları değiştirdiğinizi, sildiğinizi veya yeni hangi dosyaları eklediğinizi hızlıca görebilirsiniz.
4. Bir sonraki aşamada git'e değişen dosyalarınızdan hangilerinin commit'inizde yer almasını istediğinizi söylemeniz gerekiyor. Bu işlem ile commit'inize dahil etmek istediğiniz dosyaları **staging area** denilen ara bir mantıksal alana eklemiş olacaksınız.
> Dosyaların değiştirilmiş olması, silinmesi veya eklenmesi bu dosyaların otomatik olarak bir sonraki commit'e dahil olmasını yani *staging area*'ya dahil edilmesine neden olmaz. Bu işlemi ilgilendiğiniz dosyaları seçerek ve bilrerek sizin yapmanız gerekir.
5. Dosyalarınızı *staging area* denilen alana ekledikten sonra şimdi *commit* işlemine hazırsınız. Commit işlemi ile değişikliğe dair yorumlarınızı da ekleyerek değişikliklerinizin bir versiyon olarak git veritanbanına kaydedilmesini sağlarsınız.
6. Zaman zaman, özellikle de bir ekip çalışması söz konusu ise, projenizdeki değişikliklere göz atmak isteyebilirsiniz. Projenizin versiyonlarında yapılan değşiklikleri görmek için *git log* komutunu kullanmanız gerekecek
7. Yaptığınız değişikliklerin ekibin geri kalanı tarafından da görülmesini ve kullanılmaya başlamasını sağlamak için değişikliklerinizi zaman zaman uzaktaki paylaşılan git repository'sine yüklemeniz gerekir. Bunun için *git push* komutunu kullanacaksınız.

> **Yerel & Uzak Repository'ler**
> * Yerel repository, kendi bilgisyarınızda proje klasörünüzün altında bulunan .git klasörüdür. Bu repository üzerinde sadece siz çalışabilirsiniz ve değişiklikler yerel diskinizde kayıt alttında tutulur.
> * Uzak repository'ler ise  genellikle uzaktaki bir sunucuda yer alırlar ve bu sunucudaki .git klasöründen ibarettirler. Ekip çalışması söz konusu ise ekip üyeleri değişikliklerini bu uzaktaki repository'yi kullanarak birbirleri ile paylaşırlar.


