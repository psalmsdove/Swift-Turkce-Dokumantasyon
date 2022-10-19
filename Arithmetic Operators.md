# Aritmetik İşlemler

Swift neredeyse tüm aritmetik işlemleri destekler. +, -, *, / ve daha fazlası gibi.
Ayrıca C dilinde bulunmayan a..<b ve a...b gibi aralık operatörlerini de desteklemektedir. Bu bölümde Swift dilinde kullanılan yaygın operatörleri açıklayacağız.

## Terminoloji
3 adet operatör bulunmaktadır:

1. Unary -> Tek bir hedef üzerinde çalışırlar. (-a, !b, c! gibi)
2. Binary -> İki hedef üzerinde çalışırlar. (2 + 3 gibi)
3. Ternary -> Üç hedef üzerinde çalışırlar. C'de olduğu gibi, Swift dili sadece bir tane ternary operatörüne sahiptir (a ? b : c)

## Atama Operatörü
Atama operatörü (a = b) a'nın değerini b ile başlatır veya günceller.
```
let b = 10
var a = 5
a = b
// a değeri şu an 10
```
```
let (x, y) = (1, 2)
// x = 1 ve y = 2
```

## Aritmetik Operatörler
- Toplama (+)
- Çıkarma (-)
- Çarpma (*)
- Bölme (/)

> Toplama operatörü aynı zamanda String birleştirmesini destekler.
```
"hello, " + "world" 
// hello, world! yazdırılacaktır.
```

### Kalan Operatörü
Bölme işleminden bildiğimiz kalan terimini bulmak için Swift dilinde bu operatörü (%) kullanırız. 9 % 4'ü hesaplamak için öncelikle 9'un içine kaç tane 4'ün sığacağını bulmamız gerek. 9'un içine 2 tane 4 sığdırabiliriz ve kalan 1 olur. Yani;
```
9 % 4 //1'e eşittir
```

## Bileşik Atama Operatörleri

C'de olduğu gibi, Swift'te de bileşik atama operatörleri (=) bulunmaktadır. Bir örneği, (+=) toplama atama operatörüdür.
```
var a = 1
a += 2
// a şu an 3'e eşit
```
a += 2, a = a + 2 demektir.

## Karşılaştırma Operatörleri

a == b -> a, b'ye eşit

a != b -> a, b'ye eşit değil

a > b -> a, b'den büyük

a < b -> a, b'den küçük

a >= b -> a, b'den büyük ya da eşit

a <= b -> a, b'den küçük ya da eşit

```
let isim = "dünya"
if isim == "dünya" {
  print("hello, world")
} else {
    print("üzgünüm ama sizi tanıyamadım.")
}
//ekranda hello, world yazdırılır çünkü isim değişkeni, "dünya" kelimesine eşittir.
```

## Üçlü karşılaştırma operatörü
Üçlü koşul operatörü, soru formunu alan üç bölümden oluşan özel bir operatördür. question ? cevap1 : cevap2. Sorunun doğru mu yanlış mı olduğuna bağlı olarak iki ifadeden birini değerlendirmek için kullanılan bir kısayoldur. Eğer soru doğruysa, cevap1'i değerlendirir ve değerini döndürür; aksi takdirde, cevap2'yi değerlendirir ve değerini döndürür.

```
let contentHeight = 40
let hasHeader = true
let rowHeight = contentHeight + (hasHeader ? 50 : 20)
// rowHeight is equal to 90
```

## Aralık Operatörleri
Swift, bir dizi değeri ifade etmek için kısayollar olan birkaç aralık operatörü içerir.
### Kapalı aralık operatorü

Kapalı aralık operatörü (a...b), a'dan b'ye uzanan ve a ve b değerlerini içeren bir aralık tanımlar. a'nın değeri b'den büyük olmamalıdır.

```
for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
// Sırayla 1'den 5'e kadar olan sayıları 5 ile çarpıp ekrana yazdırır.
```
## Yarım aralık operatörü

Yarı açık aralık operatörü (a..<b), a'dan b'ye uzanan, ancak b'yi içermeyen bir aralık tanımlar. Yarı açık olduğu söylenir çünkü ilk değerini içerir, ancak nihai (son, b) değerini içermez. Kapalı aralık operatöründe olduğu gibi, a'nın değeri b'den büyük olmamalıdır. a'nın değeri b'ye eşitse, sonuç aralığı boş olacaktır.

```
let names = ["Anna", "Alex", "Brian", "Jack"]
let count = names.count
for i in 0..<count {
    print("Person \(i + 1) is called \(names[i])")
}
// Person 1 is called Anna
// Person 2 is called Alex
// Person 3 is called Brian
// Person 4 is called Jack
```

## Tek Yönlü Aralıklar

Kapalı aralık operatörü, mümkün olduğunca tek yönde devam eden aralıklar için alternatif bir biçime sahiptir; örneğin, 2'den dizinin sonuna kadar bir dizinin tüm öğelerini içeren bir aralık. Bu durumlarda, aralık operatörünün bir tarafındaki değeri atlayabilirsiniz. Bu tür bir aralığa tek yönlü aralık denir, çünkü operatör yalnızca bir tarafta bir değere sahiptir. Örneğin:

```
let names = ["Anna", "Alex", "Brian", "Jack"]
for name in names[2...] {
    print(name)
}
// Brian
// Jack

for name in names[...2] {
    print(name)
}
// Anna
// Alex
// Brian
```

## Mantıksal Operatörler

Logical NOT (!a)
Logical AND (a && b)
Logical OR (a || b)

Mantıksal NOT operatörü (!a) bir Boolean değerini ters çevirir, böylece true false olur ve false true olur.

Mantıksal NOT operatörü bir prefix operatörüdür ve üzerinde çalıştığı değerden hemen önce, boşluk olmadan görünür. Aşağıdaki örnekte görüldüğü gibi “not a” olarak okunabilir:
```
let allowedEntry = false
if !allowedEntry {
    print("ACCESS DENIED")
}
// Prints "ACCESS DENIED"
```

Mantıksal AND operatörü (a && b), genel ifadenin de doğru olması için her iki değerin de doğru olması gereken mantıksal ifadeler oluşturur.

Her iki değer de yanlışsa, genel ifade de yanlış olacaktır. Aslında, ilk değer yanlışsa, ikinci değer değerlendirilmez bile çünkü genel ifadeyi doğruya eşitleme olasılığı yoktur. Bu, kısa devre değerlendirmesi olarak bilinir.
```
let enteredDoorCode = true
let passedRetinaScan = false
if enteredDoorCode && passedRetinaScan {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Prints "ACCESS DENIED"
```
Mantıksal OR operatörü (a || b), iki bitişik kanal karakterinden oluşan bir infix operatörüdür. Bunu, genel ifadenin doğru olması için iki değerden yalnızca birinin doğru olması gereken mantıksal ifadeler oluşturmak için kullanırsınız.
```
let hasDoorKey = false
let knowsOverridePassword = true
if hasDoorKey || knowsOverridePassword {
    print("Welcome!")
} else {
    print("ACCESS DENIED")
}
// Prints "Welcome!"
```

