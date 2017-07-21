# Branching Çalışma Şeklinizi Değiştirebilir

Bazı araçların sağladığı imkanlar günlük iş yapma şeklimizi çok derinden etkileyip, yaptığımız işe daha farklı bakabilmemizi sağlar. Git'in **branching** yaklaşımı (Türkçeye **dallanma** olarak da çevirebiliriz) da bahsettiğim bu dönüştürücü etkiye sahip araçlardan birisidir. Branching konusundaki hakimiyetimizin artması ve sağlamlaşması ile birlikte daha farklı iş yapmaya başlayıp daha iyi birer yazılım geliştirici olabilirsiniz.

Branching denilen yöntem aslında Git dışındaki diğer versiyon kontrol sistemlerinde de öteden beri kullanılmakta ve yazılım geliştiricilerin hayatını önemli derecede kolaylaştırmaktadır. Ancak, Git'deki branching yaklaşımı kullanım kolaylığı ve yüksek performansı nedeniyle kendine has olduğunu da  söylemeliyiz.

Öyleyse gelin şimdi yavaş yavaş branching'in (dallanma) ne olduğunu anlayalım.

## Birden Fazla Bağlamda Çalışmak

Daha önceki bölümün son alt başlığında (git commit) zaman zaman bireysel olarak kısa zaman dilimlerinde aynı projenin farklı özellikleri ile ilgili değişiklikler yapılması gerekebileceğinden bahsetmiştik. Büyük projelerde ise bu durum kişisel bir tercih olmaktan çıkıp iş bölümü/uzmanlık gibi kriterlere bağlı olarak proje/ürün yönetiminin önemli bir parçası halinde ele alınır. Örneğin 5 kişilik bir ekibin her bir üyesi aynı yazılımın farklı özellikleri ile ilgili çalışabilir veya iki farklı kişi aynı özelliğin farklı şekillerde nasıl geliştirilebileceği ile ilgili deneysel çalışma yapıyor olabilirler. Bahsettiğim tüm bu alternatif senaryolar aslında kendi yaşam döngüleri olabilen, çoğu zaman kısa veya uzun süreli eş zamanlı ilerleyen farklı birer **bağlama** denk gelir.

Pratikte üzerinde çalıştığınız projenin/yazılımın her zaman son stabil durumu yansıtan **ana** bir bağlamı ve X numaralı hata bildiriminin düzeltilmesi, yeni bir Y özelliği üzerinde yapılan çalışma veya deneysel bir özellik ile ilgili yapılan çalışma gibi birden fazla yan bağlamı olacaktır.

## Branching olmasa da olur mu?

Net olarak birbirinden ayrılmış farklı bağlamlar oluşturmak için branching benzeri araçlar olmasaydı aşağıdakilere benzer senaryolarda nasıl davranacağımız konusunda sıkıntılar yaşayacaktık

* Örneğin müşteriniz veya yöneticiniz iki alternatif sayfa tasarımından birincisini değil de ikincisini beğendi ve bu arada siz de sayfa tasarımı dışında birkaç tane bug fix ve birkaç tane de dokümantasyon değişikliğini farklı zamanlarda tamamladınız. Bu durumda müşterinizin beğendiği ikinci tasarımı diğer tüm düzenlemeleri kaybetmeden nasıl devreye alacaktınız?
* Üzerinde çalıştığınız alışveriş sitesi için özel olarak geliştirdiğiniz Sepet modülü yerine 3. parti bir modül kullanılması kararı alındı ve sizin de kendi modülünüzü ana yazılımdan sökmeniz istendi. Bu durumda sökmeniz gereken modül kodunu tespit edip diğer modülleri etkilemeden nasıl sökecektiniz?
* Yeni geliştirdiğiniz Beni Haberdar Et işlevi yazılımınızın geri kalan özelliklerinin bir çoğunun değiştirilmesine sebep olmuşken birden Beni Haberdar Et işlevinin saçma ve gereksiz olduğuna karar verilseydi bu işlevi aradan geçen zamanda yazılımın farklı yerlerinde yapılan diğer değişikliklerden izole ederek nasıl çöpe atacaktınız?

Birden fazla konu ile ilgili değişikliklerin tamamını tek bir bağlam ile yönetmeye çalışırsanız işler hızla sarpa saracaktır. Bu karmaşanın önüne geçmek için her bir değişiklik için projenizin tamamının farklı klasörlere kopyalamayı deneyebilirsiniz. Ancak bu durumda

* Bu klasörler versiyon kontrolünde olmadığı için ekibin geri kalanı ile iş birliği yapmanız çok zorlaşacak
* Farklı değişiklikleri entegre etmek çok zor ve hataya açık bir işlem olacak

Uzun lafın kısası projenizdeki değişiklikleri profesyonel bir yaklaşımla ele almak istiyorsanız farklı bağlamlarda çalışmak ve bu bağlamları düzgün yönetmek için bir yol bulmanız gerekiyor.

## Neyse ki branching var
Branching bir önceki bölümde değindiğimiz tüm sorunların önüne geçmek için kullanabileceğimiz bir araç ve yaklaşımdır. Branching ile farklı bağlamları birbirinde kolayca izole ederek her birini kolayca ve ayrı ayrı yönetebilirsiniz.

![Branching](01_branching.jpg "Branching")

*[Görsel : Atlassian Git Workflows sayfasından alıntı](https://www.atlassian.com/git/workflows "Git Workflows")*

Herhangi bir anda yaptığınız değişiklikler sadece aktif olarak üzerinde çalıştığınız branch'e (dal) yansıyacak diğer branch’ler bu değişikliklerden etkilenmeyecektir. Böylece aynı anda birden fazla branch üzerinde özgürce çalışabilirsiniz ve en önemlisi de bu çalışmalarınızdan bir kısmının çöpe dönmesinden çekinmeden denemelerinizi yapabilirsiniz.

<div style="padding:10px;border:1px solid #fcedd7;background-color:#fef9f1">
<p style="color:darkgray">Versiyon Kontrolünün Altın Kuralları</p>
<p style="font-weight:bold">#3 Branch'leri Bol Bol Kullanın </p>
<p>
Branch’ler git'in en güçlü özelliklerinden birisidir. Hızlı ve kullanımı kolay branching mekanizması git'in tasarımında ilk gününden itibaren ciddi bir gereksinim olarak ele alınmıştır. Branch'ler farklı bağlamlarda çalışmaktan kaynaklanabilecek karmaşanın önüne geçmek için biçilmiş kaftandır. Branch'leri bug fix'ler, yeni özellikler üzerinde çalışmak veya deneysel özellikleri geliştirmek için bol bol kullanın.
</p>
</div>
