# Swift-Turkce-Dokumantasyon
Bu repo, Swift dilinin Türkçe dökümantasyonunu kullanıcılar ve dili yeni öğrenmek isteyenler için hazırlanmıştır.

Swift, iOS, macOS, watchOS ve tvOS uygulamaları yapmak için kullanılan bir programlama dilidir. Swift geliştirirken C ve Objective-C dilinden bir sürü ortak şey olduğunu göreceksiniz. Int, Double, Float, Bool ve String verilerini içerir. Swift'de ayrıca Array, Set ve Dictionary gibi özellikler de bulunur. Bunlara ileride daha detaylıda değineceğiz.

C'de olduğu gibi, Swift dilinde de değişkenler bir isme atanır. Ayrıca değişmeyecek değerler için farklı bir kullanıma sahiptir. Bunlara constants denir ve C'deki constants özelliğinden çok çok daha güçlüdür. Kodu daha güvenli ve temiz yapmak için kullanılırlar. Swift ayrıca optional özelliğini bulundurur. Bu şu anlama gelir; "bir değer var, ve bu x'e eşit" ya da "herhangi bir değer yok". Optionals kullanmak Objective-C'de nil kullanmaya benzer ama tüm tipler için geçerlidir, sadece sınıflar için değil. 

## Sabitleri ve Değişkenleri Tanımlama
Sabitler ve değişkenler kullanılmadan önce tanımlanmalıdır. Sabitler "let", değişkenler ise "var" kelimesi ile tanımlanırlar. Örnek kullanım:
> let maxLoginAttempt = 10

> var currentLoginAttempt = 0

İlk kodumuzda let anahtar kelimesini kullandık çünkü bu değerimiz ne olursa olsun değişmeyecek, maksimum giriş yapma hakkı her zaman 10 olarak kalacak. Ama diğer değerimiz giriş yaptıkça artacağı için, "var" anahtar kelimesi kullanıldı.

## Tip Açıklamaları
Bir sabit veya değişken tanımladığınızda bunun hangi türe ait olduğunu açıklamak için bir tip açıklaması verebilirsiniz. Bunun için değişken adından sonra iki nokta, sonra boşluk ve hangi tipe tanımlayacaksanız onu yazarak tanımlayabilirsiniz.
> var welcomeMessage: String

Tek satırda birden fazla aynı türde değeri aralarında virgülle ayırarak tanımlayabilirsiniz. 
> var red, green, blue: Double

## Değişkenleri ve Sabitleri İsimlendirme
Değişkenler ve sabitler herhangi bir karakteri içerebilir, buna Unicode karakterler dahil. 
>     let π = 3.14159
>     let 你好 = "你好世界"
>     let 🐶🐮 = "dogcow"

Bir değşiken veya sabit tanımladıktan sonra bunu aynı tipteyse değiştirmek mümkündür.

> var friendlyWelcome = "Hello"

> friendlyWelcome = "Bonjour"

> şu an değişkenimiz Bonjour.

## Sabitleri ve değişkenleri yazdırma

print() fonksiyonunu kullanarak bir sabitin veya değişkenin değerini yazdırabiliriz.

> print("The current value of friendlyWelcome is \(friendlyWelcome)")

> Ekranda "The current value of friendlyWelcome is Bonjour" yazacaktır.

### Yorumlar
Satırların başına // koyarak yorum satırı haline getirebiliriz. Yorum satırını xcode programı çalıştırmaz ve yoksayar. Kodunuzu inceleyen başka mühendisler kodunuzun ne işe yaradığını anlamak için bu yorum satırları çok işlevsel olabilir.

> Diğer dillerin aksine, Swift dilinde ; bulunmaz. Ancak isterseniz kullanabilirsiniz.

## Tam Sayılar

Swift işareti olmayan ve işaretli 8, 16, 32 ve 64 bit formlarında tam sayılar sağlar. 
