String, "merhaba, dünya" veya "albatros" gibi bir dizi karakterdir. Swift dizeleri, String türü ile temsil edilir. Bir String'in içeriğine, bir Karakter değerleri koleksiyonu dahil olmak üzere çeşitli şekillerde erişilebilir.

Swift'in String ve Karakter türleri, kodunuzdaki metinle çalışmak için hızlı, Unicode uyumlu bir yol sağlar. String oluşturma ve işleme sözdizimi, C'ye benzer bir dize değişmez sözdizimi ile hafif ve okunabilirdir. String birleştirme, iki stringi + operatörüyle birleştirmek kadar basittir ve string değişebilirliği, bir sabit veya bir değişken arasında seçim yapılarak yönetilir, tıpkı Swift'deki diğer değerler gibi. Swift enterpolasyonu olarak bilinen bir işlemde, daha uzun dizelere sabitler, değişkenler, değişmez değerler ve ifadeler eklemek için dizeleri de kullanabilirsiniz. Bu, görüntüleme, depolama ve yazdırma için özel dize değerleri oluşturmayı kolaylaştırır.

Swift'de önceden tanımlanmış String değerlerini kullanabilirsiniz.
```
let someString = "Some string literal value"
```
## çok satırlı stringler
Birkaç satırdan oluşan bir string tanımlamak istiyorsanız, çok satırlı string özelliğini kullanmanız gerekir. Bunun için 3 tane tırnak işareti koyarsınız.
```
let quotation = """
the white rabbit put on his spectacles.
where shall i begin?

"begin at the beginning", the king said.
"""
```
3 tırnak işareti arasındaki her şey sizin yazdığınız gibi ekrana yazdırılır, yani çoklu satır şeklinde.
### boş string tanımlama

Daha uzun bir string oluşturmak için başlangıç noktası olarak boş bir string değeri oluşturmak için, bir değişkene boş bir değişmeyen string değeri atayın veya başlatıcı sözdizimi ile yeni bir String örneğini başlatın:
```
var emptyString = ""
var anotherEmptyString = String()
```
Yukarıdaki örnekte iki String de boştur.
### string değişebilirliği
Belirli bir String'in değiştirilip değiştirilemeyeceğini onu bir değişkene (bu durumda değiştirilebilir) veya bir sabite (bu durumda değiştirilemez) atayarak belirtirsiniz:
```
1. var variableString = "Horse"
2. variableString += " and carriage"
3. let constantString = "Highlander"
4. constantString += " and another Highlander
```
## characters ile çalışma

