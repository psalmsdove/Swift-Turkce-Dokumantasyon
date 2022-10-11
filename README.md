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

