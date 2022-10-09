# Swift Türkçe Dokümantasyon
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

Swift işareti olmayan ve işaretli 8, 16, 32 ve 64 bit formlarında tam sayılar sağlar. Tam sayılar 42, -23 gibi kesirli bileşen içermeyen sayılardır.

### Tam Sayı Sınırları

Her tam sayı tipi için minimum ve maksimum değerlerine min ve max özellikleriyle ulaşabilirsiniz.

> let minValue = UInt8.min //minValue değeri 0'a eşit, tipi ise UInt8

> let maxValue = UInt8.max //maxValue değeri 255'e eşit, tipi ise UInt8

## Floating-Point Sayılar

Floating sayılar, kesirli bileşen içeren 3.14159, 0.1 ve -273.15 gibi sayılardır. Tam sayılara göre daha geniş bir aralığı temsil ederler ve Int ile saklanabilen sayılardan çok daha büyük ve küçük sayıları saklayabilirler. 

- Double 64 biti,
- Float ise 32 biti temsil eder.

## Sayısal Tip Dönüşümü

Negatif olmadıkları bilinse bile, kodunuzdaki tüm genel amaçlı tam sayı sabitleri ve değişkenler için Int türünü kullanın. Günlük durumlarda varsayılan tam sayı türünü kullanmak, tam sayı sabitlerinin ve değişkenlerin kodunuzda hemen birlikte çalışabileceği ve tamsayı değişmez değerleri için çıkarılan türle eşleşeceği anlamına gelir. 

Diğer tamsayı türlerini, performans, bellek kullanımı veya diğer gerekli optimizasyon için yalnızca özel olarak gerektiğinde kullanın. Bu durumlarda açıkça boyutlandırılmış türleri kullanmak, herhangi bir kaza sonucu oluşan değer taşmalarını yakalamaya yardımcı olur ve kullanılan verilerin doğasını dolaylı olarak belgeler.

### Tam Sayı Dönüşümü

Bir tamsayı sabitinde veya değişkeninde saklanabilecek sayı aralığı, her sayısal tür için farklıdır. Bir Int8 sabiti veya değişkeni -128 ile 127 arasındaki sayıları saklayabilirken, bir UInt8 sabiti veya değişkeni 0 ile 255 arasındaki sayıları saklayabilir. Bu değerler dışındaki bir değeri değişkeninize atarsanız bir hata ile karşılaşacaksınız: 

> let cannotBeNegative: UInt8 = -1 //UInt8 negatif sayıları saklayamaz

> let tooBig: Int8 = Int8.max + 1 //Int8 maksimum değerinden daha büyük bir değeri saklayamaz

Her sayısal tür, farklı bir değer aralığı depolayabildiğinden, duruma göre sayısal tür dönüştürmeyi seçmelisiniz. Bu yaklaşım, dönüştürme hatalarını önler.

Belirli bir sayı türünü diğerine dönüştürmek için, mevcut değerle istenen türden yeni bir sayı başlatırsınız. Örneği inceleyin:

```
let twoThousand: UInt16 = 2_000
let one: UInt8 = 1
let twoThousandAndOne = twoThousand + UInt16(one)
```

### Tam Sayı ve Floating-Point Dönüşümü

```
let three = 3
let pointOneFourOneFiveNine = 0.14159
let pi = Double(three) + pointOneFourOneFiveNine
//pi 3.14159'a eşittir ve Double tipindendir

```
Görmüş olduğunuz üzere, 'three' değişkenimizin başına Double ekleyip parantez içine alarak değişkenimizi Double tipine dönüştürdük.

```
let integerPi = Int(pi)
// burada değerimiz tam sayı değerine dönüştü, yani 3.
```

## Type Alias

Tür takma adları, mevcut bir tür için alternatif bir ad tanımlar. typealias anahtar sözcüğüyle tür takma adları tanımlarsınız.

```
typealias AudioSample = UInt16
var maxAmplitudeFound = AudioSample.min
// maxAmplitudeFound değerimiz şu an 0.
```
## Booleans

Swift dili basit bir Boolean tipine sahiptir. Sadece doğru veya yanlış olabilirler.

```
let portakallarTuruncudur = true
let muzMavidir = false
```

Doğru kullanılırlarsa boolean değerleri çok kullanışlı olabilir.

```
if portakallarTuruncudur {
    print("Evet doğru!")
} else {
    print("Hayır, değil.")
}
// ilk seçenek yazdırılacak.
```

## Tuples

Tuples, birden çok değeri tek bir bileşik değerde gruplandırır. Bir tanımlama grubu içindeki değerler herhangi bir türden olabilir ve birbirleriyle aynı türden olmaları gerekmez. Bu örnekte (404, "Not Found"), bir HTTP durum kodunu tanımlayan bir tanımlama grubudur. HTTP durum kodu, bir web sayfası talep ettiğinizde bir web sunucusu tarafından döndürülen özel bir değerdir. Mevcut olmayan bir web sayfası talep ettiğinizde 404 Not Found durum kodu döndürülür.

```
let http404Error = (404, "Not Found")
```

Gördüğünüz gibi Int ve String bir değeri virgülle ayırarak tanımladık. İstediğiniz tipte ve istediğiniz kadar farklı şekilde tuple tanımlayabilirsiniz

## Optionals

Swift dilinde bir değişkenin değerinin olmaması nil değeri alabilmesi için o değişkenin optional olarak tanımlanmış olması gerekir. Bir değişken nil değeri alabiliyor ise o değişken optional bir değişkendir yani değer almasa da olur. Yani değişkenin bir değeri olabilir, ya da olmayabilir demektir.
> Kaynak: https://www.mobilhanem.com/swift-optional/

Bir değişken veya sabit tanımlanırken, değişken tipinin sonuna ! veya ? ekleyerek optional yapabiliriz. Örneğin Int ile Int? ayrı tiplerdir. Eğer bir değişkenin kesinlikle değer içerdiği biliniyorsa, optional kullanılmaz, bilinmiyorsa optional kullanılır.

## Hata Yakalama

Programın çalıştırılması sırasında karşılaşılabilecek bir hata durumunda cevap verilmesi için hata yakalama kullanılır. 
```
func hataFirlatabilir() throws {
    //hata olabilir ya da olmayabilir, koda bağlı
    }
```
throws kelimesini kullanarak bir fonksiyonun hata fırlatabileceğini belirtiriz. Hata fırlatabilecek bir fonksiyonu çağırdığınızda, try anahtar kelimesini kullanırsınız.
```
    do {
        try canThrowAnError()
        // hata fırlatılmadı
    } catch {
        // hata fırlatıldı
    }
```
