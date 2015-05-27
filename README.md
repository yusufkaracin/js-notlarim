**JAVASCRİPT NOTLARIM**

Bu döküman temel seviyede JavaScript bilgisi kazanmak amacıyla oluşturduğum notlardan oluşmaktadır. JS'ye hızlıca başlangıç yapmak isteyenler için idealdir. Temel bilgiler detaya girmeden kısa ve öz şekilde sunulmaya çalışılmıştır.
Herhangi bir programlama dilinde değişken tanımlama, döngüler, kontrol yapıları vb… gibi temel konuları bilmeniz bu dokümanı anlamanız için çok daha faydalı olacaktır. Eğer herhangi bir programlama bilginiz yoksa bu problem değil çünkü bu konular da kısa ve basit şekilde ele alındı.
Bu dokümanda aşağıdaki konular yer almaktadır:

 1. Temel JS Yazım Kuralları (Syntax)
 2. Değişkenler
 3. Local (Yerel) ve Global Değişkenler
 4. Operatörler
 5. if-else
 6. switch case
 7. Fonksiyonlar
 8. for Döngüsü
 9. while Döngüsü
 10. break ve continue
 11. for in
 12. try-catch-finally
 13. throw
 14. Diziler
 15. Nesneler (Object)
 16. DOM ve Sayfadaki Nesnelere Erişmek
 17. Olaylar ve Olay Dinleyicileri (Events & Events Listener)
 18. Arayüz Özelliklerine Müdahele
 19. JQuery

----------
**JS Hakkında**

Javascript konusunda ilk bilinmesi gereken [JAVA](https://www.java.com/tr/) programla dili ile isim dışında hiçbir alakası olmamasıdır.

>**JavaScript**, en yaygın biçiminde, JavaScript HTML dokümanlarının içinde bulunur ve web sayfalarında basit HTML ile ulaşılamayan etkileşim düzeyleri sağlar. [-java](https://java.com/tr/download/faq/java_javascript.xml)

**JS Hakkında**
Dökümanda sadece temel JavaScript bilgileri yer alacağı için bu bölümde sadece birkaç link sunuyorum:

**Faydalı Kaynaklar**

 -  [Wikipedia](http://tr.wikipedia.org/wiki/JavaScript)
 - [Codecademy ücretsiz eğitim](http://www.codecademy.com/tracks/javascript)
 - [w3schools JS eğitimi](http://www.w3schools.com/js/default.asp)
 - [codeschool teme js eğitimi](https://www.codeschool.com/courses/javascript-road-trip-part-1) (ücretsiz)
 - [MDN JS Dökümanı](https://developer.mozilla.org/en-US/docs/Web/JavaScript/About_JavaScript)
 - [jskoleji](http://www.jskoleji.com/)
 - [Ekşi Sözlük](https://eksisozluk.com/javascript--34809)
 - [Google](https://www.google.com.tr)

**Gerekli Araçlar** 

 - Güncel bir web tarayıcısı(Firefox ya da Chrome tercihen)
 - [Notepad++](https://notepad-plus-plus.org/)  (ücretsiz ve güzel özellikleri var) ya da favori editörünüz / IDEniz

----------
<h1>1-Temel JS Yazım Kuralları (Syntax)</h1>

    <html>
    <body>
    <h1>Günün Tarihi</h1>
    <p id="gununTarihi"></p>
    
    <script type="text/javascript">
        /* Birden fazla satırdan oluşan yorumlar için bu güzel.
        Lorem ipsum dolor sit amet, consectetur adipisicing elit.  */
        document.getElementById("gununTarihi").innerHTML = Date();
        
        //Tek satırlık bir not.
    </script>
    
    </body>
    </html>
Günümüzdeki modern tarayıcıların hepsi JS'i desteklemektedir.  Tarayıcı
`<script type="text/javascript"> </script>`  arasında JS kodları bekliyor. Burada `type="text/javascript"` yazmasak bile tarayıcı varsayılan olarak JS kodu beklemektedir.

JS kodlarımızı yukarıdaki örnekte olduğu gibi direkt HTML sayfası içinde yazabiliriz. Bunun yanında istersek JS kodlarımızı farklı dosyalardan da çağırabiliriz.

    <script src="dosyayolu/kodlarim.js"></script>

JS kodlarımızı HTML dosyasında herhangi bir yere yazabiliriz. `</body>` etiketinden hemen önce eklemek iyi bir tercih olacaktır. Bu sayfamızın daha hızlı yüklenmesini sağlayacaktır. 

 - JS 'case sensitive'(büyük-küçük harf duyarlı) bir dildir.
	 - <pre>var degisken;
    alert(Degisken); //hata</pre>
 - JS komutları `;` ile biter fakat bu opsiyoneldir.
	 - <pre> //; olmadan da yukarıdaki kodlar çalışır
    var degisken
    alert(degisken)</pre>
 - JS kodları içinde HTML etiketleri kullanabiliriz.
	 - <pre><code>//HTML etiketlerini de JS kodlarına gömebiliriz
document.getElementById('div').innerHTML = '&lt;h1&gt;Başlık&lt;/h1&gt;';
</code></pre>


----------
<h1>2-Değişkenler</h1>
Değişkenler verilerimizi saklamak için kullandığımız araçlardır. 

 - JS'de bir değişken tanımlayarak istediğimiz tipte veriyi saklayabiliriz.
 - Temel veri tipleri genel olarak şunlardır: Sayılar, metinler ya da doğru/yanlış (true/false) yani boolean.
 - Değişken tanımlarken rakamları, harfleri ve `_` kullanabiliriz. Fakat değişken isimleri rakamla başlayamaz.
 - Bir değişken aynı anda sadece tek değer saklayabilir. 
 - Değişkene değer ataması yapmak için `=` kullanılır. Değer atamasını değişkeni tanımladığımız anda ya da daha sonra da yapabiliriz.
<pre>
    // Değişken tanımlama
    var degisken1;
    
   // Aynı anda birden fazla değişken tanımlanabilir
    var degisken1, degisken_2;
    
   // Değişkene ilk değer ataması
    var isim = 'Asya';
    
   // Değişken tanımlama ve değer atama
    var baslangic = 78 , bitis = 90;  
    
   //Değişken tanımlama ve değerini daha sonra atama
   var dogruMu;
   dogruMu = false;
  </pre>


----------
<h1>3-Local (Yerel) ve Global Değişkenler</h1>
Bu konu ayrı bir başlık altında çünkü JS de local ve global değişkenler diğer dillere göre biraz farklı.

 - Local değişkenler sadece tanımlandıkları alan içerisinde erişilebilir.
 - Global değişkenlere ise her yerden erişilebilir.
 - Local değişkenler kod bloklarının sonunda bellekten düşer.
 - Global değişkenler tarayıcı kapandıktan sonra bellekten düşer.

JS'de fonksiyonlar içinde `var` ile yapılan değişkenler local değişkendir. Bunun haricindeki değişkenler global olacaktır. Diğer programlama dillerinde `{ }` bir scope oluşturur ve bu alan içinde tanımlanan değişkenler yerel değişkendir. Yani `{ }` dışından bu değişkenlere erişilemez ve değişkenler bu kod blokları sona erince bellekten düşer. 

    function isimGoster()
    {
	    //isim degiskeni sadece bu fonksiyon içinde erişilebilir
        var isim="Asya";
        alert(isim);
    }
    alert(isim); //değişken var ile tanımlandığı içn fonksiyon dışından erişilemez
    
    if( 15 > 10) {
	    var sayi = 17;
    }
    alert(sayi); //sayi degiskenine if bloğu dışından da erişilebilir


----------
<h1>4-Operatörler</h1>

<h2>Atama Operatörleri</h2>
Operatör | İşlev | Örnek
--- | --- | ---
= 	| Atama yapar | `x = 5;`
+=	| Ekleme yapıp atama yapar | `x+=y` ve `x=x+y` aynı
-=	| ÇIkarma yapıp atama yapar| `x-=y` ve `x=x-y` aynı
*=	| Çarp and ata | `x*=y` ve `x=x*y` aynı
/=	| Böl ve ata | `x/=y` ve `x=x/y` aynı
%=	| Mod al ve ata | `x%=y` ve `x=x%y` aynı

<h2>Karşılaştırma Operatörleri</h2>

Operatör | İşlev | Örnek
--- | --- | ---
== 	| Eşit mi | `3 == '3';`
=== | Eşit ve veri tipleri aynı mı | `3 === '5';`
!=  | Eşit değil mi | `3 != '3';`
!== | Eşit değil ve veri tipleri farklı mı | `3 !== '3';`
>	| Büyük mü | `3 > 5`
\>=	| Büyük ya da eşit mi | `3 >= 5`
<	| Küçük mü | `3 < 5`
<=	| Küçük ya da eşit mi | `3 <= 5`

<h2>Mantıksal Operatörler</h2>

Operatör | İşlev | Örnek | Açıklama
--- | --- | --- | ---
&& | ve | `(3<5) && (6>8)` | 3, 5'ten küçük mü ve 6, 8'ten büyük mü
\|\| | ya da | `(3<5) \|\| (6>8)` | 3, 5'ten küçük mü ya da 6, 8'ten büyük mü
!	| değil | `!(3<5)`| 3, 5'ten küçük mü ifadesinin tersini al


----------
<h1>5-if-else</h1>
Kodlarımızı belirlediğimiz koşullar sağlandığı zaman çalıştırmak isteyebiliriz. Bu durumda koşul ifadeleri kullanılırız. `if-else` belirttiğimiz koşulun doğru ya da yanlış olmasına göre kodlarımızı çalıştırır.

    if( 3 < 5 )
    {
	    //eğer 3, 5 ten küçükse { } arasındaki kodları çalıştır
        //başka kodlar
    }

    if ( 3 > 5)
    {
        //3, 5 ten büyükse buradaki kodları çalıştır ve else bloğuna girme
    }
    else
    {
        //yukarıdaki ifade yanlışsa bu alandaki kodları çalıştır
    }

    if ( 3 > 10)
    {
        //3, 10 dan büyükse kodları çalıştır
    }
    else if ( 10 == 20)
    {
        //eğer yukarıdaki if koşulu yanlışsa bu if koşuluna bak
        //eğer 10, 20 ye eşitse buradaki kodları çalıştır ve aşağıdaki else bloğuna girme
    }
    else
    {
        //yukarıdakilerin hiç biri doğru değilse buradaki kodları çalıştır
    }


----------
<h1>6-switch case</h1>
`switch case` ile koşula göre farklı kod bloklarını çalıştırabiliriz. Genelde menü oluşturmak ya da kullanıcı girdilerini denetlemek için kullanılan pratik bir yöntemdir.

    switch(numara)
    {
    case 1:
      //numara değişkeni 1 ise bu alandaki kodları çalış
      //break gelince bitir
      break;
    case 2:
      //numara değişkeni 2 ise bu alandaki kodları çalış
      break;
    default:
      //yukarıdakilerin hiç biri sağlanmazsa bu alandaki kodları çalıştır
    }

`switch case` ile koşulları grup halinde de yazabiliriz.

    switch (gun)
    {
    case 5,1,4:
      //kodlar
      break;
    case 1,2,6:
	    //kodlar
	    break;
    default:
      //kodlar
    }

`switch-case` break ifadesini görene kadar devam eder. Yani koşulumuz sağlandığı halde break ifadesi yoksa `switch case` break görene kadar devam edecektir.

    switch (gun)
    {
    case 1:
    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
      //gun değişkeni 1,2,3,4,5,6 durumlarında çalış
      break;
    case 0:
      //0 ise buradaki kodlar
      break;
    default:
      //hiçbiri değilse buradaki kodlar çalışsın
    }


----------


<h1>7-Fonksiyonlar</h1>
Fonksiyonlar belirli işleri yapan kod parçacıklarıdır. Belirli bir işi yapan kod için tekrar tekrar aynı kodu yazmak yerine bu kodları bir fonksiyon içinde yazabilir ve daha sonra bu fonksiyonunu ihtiyacımız olduğunda çağırarak gereksiz kod yazımından kurtulabiliriz. Ayrıca böylece kodlar üzerinde daha rahat değişiklik yapabilir, daha düzenli kod yazabiliriz.

    //fonksiyon tanımlama
    function merhaba()
    {
        alert("Hoşgeldiniz!");
    }
    //fonksiyonu çağırma
    merhaba();
JS'de fonksiyonlara parametre gönderirken dikkat edilmesi gereken bir nokta vardır. Fonksiyonun kabul ettiği parametre sayısından daha az sayıda değer gönderebiliriz. Bu durumda JS hata vermez ama program çalışırken hataya sebep olabilir.

     function topla(a,b,c)
     {
         return a+b+c;
     }
     //fonksiyonu çağırıyoruz
     topla(3,5);

Fonksiyonları kullanmadan önce tanımlamaya özen göstermeliyiz.


----------


<h1>8-for Döngüsü</h1>
Döngüler, belirtilen koşul sağlandığı sürece tekrar tekrar kodlarımızı çalıştırmaya yarar. 

    //for yapısı
    for(başlangıç değeri ; koşul ; artış miktarı)
    {
        //kodlar
    }
`for` döngüsü kodlarımızı döngüye sokmadan önce koşulu kontrol eder. Eğer koşulumuz doğru ise belirttiğimiz sayıda kodlar tekrar edilir.

    for (var i=0; i<5; i++)
    {
        console.log(i);
    }

 

 - Döngümüz çalışmaya başladığı zaman `i` değişkenine 0 değeri atanıyor.
 - Daha sonra koşul kontrol ediliyor. Yani `i`(0), 5ten küçük mü?
 - Koşul sağlandığı için döngü içine giriliyor ve kodlar çalışıyor.
 - Kodlarımızın çalışması bittiğinde yani ilk döngü sonunda, `i++` ile `i` değişkeninin değeri 1 artıyor.
 - Tekrar koşulumuz kontrol ediliyor Yani `i`(1), 5 ten küçük mü?
 - Koşulumuz sağlandığı müddetçe döngümüz devam ediyor.
 - `i = 5` değerine ulaştığı zaman, `i(5) <` 5 koşulu artık doğru olmadığı için döngümüz sona eriyor. 


----------
<h1>9-while Döngüsü</h1>

`while` döngüsü, `for` döngüsünü gibi başlangıçta koşul kontrolünü yapar ve doğru ise döngüye başlar. Fakat `for` gibi ilk değer ataması ya da artış miktarını bizim belirtmemiz gerekir.

    var i=0;
    while(i<5)
    {
        console.log(i);
        i++;
    }

 Eğer döngü içerisinde artış miktarını ayarlamazsak ya da koşulumuzu sürekli doğru olacak şekilde yazarsak sonsuz döngüye girmiş oluruz ve kodlarımız arafta sıkışır.


----------
<h1>10-do while döngüsü</h1>
`do while` döngüsü `for` ve `while` döngüsü gibi girişte koşulu kontrol etmez. Döngü sonunda koşul kontrol edilir. Yani koşulumuz doğru ya da yanlış olsa da en azından bir kez döngümüz çalışacak demektir.

    var i=1;
    do
    {
	    //kodlar
        i++;
    }while(i>1);
Yukarıda kodda koşulumuz `i`'nin 1 den büyük olduğu müddetçe döngünün çalışmasıdır. `i`'nin ilk değeri 1 olmasına rağmen öncelikle `do {}` arasındaki kodlar çalışacak daha sonra `i`'nin değeri 1 arttırılacaktır. Döngü sonunda ise koşulumuz kontrol edilecektir. Yani koşulumuz en başından yanlış olmasına rağmen döngümüz 1 kere çalışmış oldu.


----------
<h1>10-break ve continue</h1>
`break` ve `continue` ile kodlarımızın belirli parçalarını atlayabilir ya da tamamen kod bloğundan çıkabiliriz. `break`,  kod bloğundan çıkmamızı sağlarken, `continue` alt satırda kalan kod parçalarını atlayıp tekrar kod bloğunun başına dönmemizi sağlar.

    for (var i=0; i<=5; i++)
    {
        if (i==3)
        {
            continue;
        }
        console.log(i);
    }
Yukarıdaki kodda `i` değeri 3 olduğu zaman `continue` ifadesi çalışacak yani döngünün başına gidilecektir. Yani konsola 0,1,2,4,5 yazılacaktır.

    for (var i=0; i<=5; i++)
        {
            if (i==3)
            {
                break;
            }
            console.log(i);
        }
Yukarıdaki örnekte ise `i` değeri 3 olduğu zaman döngü tamamen sona erecektir. Yani konsola 0,1,2 yazılacaktır.


----------
<h1>11-for in</h1>
`for in` ile nesne içindeki özellikler kadar döngüye girilir.

    var film = {isim:"Matrix", tur:"Bilim Kurgu", yil:2500};
    var x;
    for (x in film) {
        console.log(film[x]);
    }
Yukarıdaki örnekte `film` nesnesi içindeki her bir özellik için döngü çalışacak ve konsola `Matrix, Bilim Kurgu, 2500` yazılacaktır.


----------
<h1>12-try-catch-finally</h1>
`try-catch` ile kodlarımızın çalışması sırasında oluşan hatalara karşı önlemler alabiliriz. 

 - Çalışacak kodlarımızı `try` bloğu içine yazarız. Eğer kodlarımız hata olmadan çalışırsa `catch` bloğu atlanır ve program devam eder. 
 - Eğer bir hata olursa `catch` bloğu bu hataları yakalar ve biz de hata durumunda yapılması gerekenleri belirtebiliriz.
 - `finally` bloğu ise hata olsun ya da olmasın çalışacak kodları içeren bloktur.

**try-catch**

    try
    {
        //kodlar
    }
    catch(err)
    {
        //hata olursa buradaki kodlar
        //hata mesajını yazdır
        console.log(err.message)
    }
**try-catch-finally**

    try {
        //kodlar
    }
    catch(err) {
        //hata durumunda yapılacaklar
    } 
    finally {
       //buradaki kodlar try ya da catch den sonra çalışacak
    }

----------
<h1>13-throw</h1>
`throw` ile kendimiz özel hata mesajları oluşturabilir ve bunları gösterebiliriz.

    try
    {
        if(x < 0)
        {
            throw "HataMesaji1";
        }
        else if(x > 100)
        {
            throw "HataMesaji2";
        }
    }
    catch(err)
    {
        if(err=="HataMesaji1")
        {
            console.log("Değer 0 dan küçük");
        }
        if(err=="HataMesaji2")
        {
            console.log("Değer 100 den büyük");
        }
    }
İstersek bir yeni bir `Error` nesneni oluşturarak hata mesajlarımızı daha da geliştirebiliriz.

    var HataMesaji1 = new Error();
    
    HataMesaji1.name    = 'Negatif Değer';
    HataMesaji1.message = 'Değer 0 dan büyük olmalı';
    
    throw "HataMesaji1";


----------
<h1>14-Diziler</h1>

Diziler ile bir değişken üzerinde birden çok ve farklı tipte veriyi saklayabiliriz.

    var diziAdi = ["Asya", 48, "yeni"];
Dizi elemanlarına ulaşmak istersek, index numarısını kullanabiliriz. Index numarası 0dan başlamaktadır.
`diziAdi[0]` , **Asya** değerini taşımaktadır. `diziAdi[2]` ise **yeni** değerini taşımaktadır.
Diziler aslında birer nesnedir. Aralarında fark ise dizi elemanlarına ulaşmak için index numalarını kullanırız. Nesnelerde elemanlara ulaşmak için index isimlerini kullanırız.

    var personel = {isim:"Asya", soyisim:"Yeni", yas:48};
    personel.isim; //personel nesnesinin isim özelliğine erişir

Dizileri farklı şekillerde de tanımlamak mümkündür. 

    var personel = [];
    personel["isim"] = "Asya";
    personel["soyisim"] = "Yeni";
    personel["yas"] = 48;
Yukarıdaki örnekte gibi dizi tanımlaması yapılırsa dizi elemanlarına ulaşmak için index numarası değil belirtilen anahtar kelimler kullanılmalıdır. `personel["isim"]` gibi. `personel[0]` tanımsızdır.
<h2>Diziye Yeni Eleman Eklemek</h2>
Bir diziye yeni eleman eklemenin en basit yolu `push()` fonksiyonunu kullanmaktır.

    var icecekler = ["Su", "Kola", "Ayran", "Limonata"];
    icecekler.push("Kahve"); 
<h2>Dizi Uzunluğunu Bulmak</h2>
`length` özelliği ile dizinin uzunluğunu bulabilir ve buna göre işlemler yapabiliriz. Mesela bir dizinin tüm elemanlarını yazdırmak istersek:

    var icecekler = ["Su", "Kola", "Ayran", "Limonata"];
    for	(index = 0; index < icecekler.length; index++) {
        console.log(icecekler[index]);
    }


----------
<h1>15-Nesneler (Object)</h1>
Programlama dillerinde nesneleri gerçek hayattaki gibi nesneleri oluşturmak için kullanırız. Örneğin hayvanlar, arabalar, bilgisayarlar vs... birer nesnedir. Bu nesnelerin kendine has özellikleri ve davranışları vardır.
JS'de nesneler ile dizilerde olduğu gibi birden fazla veriyi tutabiliriz. Nesneler dizilere nazaran daha komplex yapılar oluşturmamıza izin verir ve tüm programlama dillerinde önemli bir yere sahiptir.

Örnek olarak telefon nesnesini ele alalım. Bu telefonun bazı özellikleri olacaktır. Markası, modeli, işletim sistemi, rengi vb... Şimdi bu nesneyi JS'de tanımlayalım:

    var telefon = {marka:"LG", model:'G4', renk:"beyaz"}; 
Bu örnekte `marka`, `model`, `renk` nesnenin özellikleri, `LG`, `G4`, `beyaz` ise özelliklerin değeridir.
Bu özelliklere ulaşmak için `.` ya da özelliğin adını kullanabiliriz. `telefon.marka` ya da `telefon["marka"]` gibi.

Ayrıca nesnelere özellik olarak fonksiyonlarda ekleyebiliriz:

    var telefon = {
        marka:"LG",
        model:'G4',
        renk:"beyaz",
        bilgileriGetir: function(){
            return this.marka + ' ' + this.model;
        }
    };
Nesneye ait fonksiyonu şu şekilde çağırmamız gerekir: `telefon.bilgileriGetir()`. Eğer `telefon.bilgileriGetir` şeklinde çağırırsak fonksiyonu ve kodları getirir.


----------
<h1>16-DOM ve Sayfadaki Nesnelere Erişmek</h1>
DOM yani Document Object Model, bir web sayfasında bulunan tüm ögeleri bir nesne olarak kabul eder. Yani bir sayfadaki başlıklar, paragraflar, resimler vs... birer nesnedir. Böylece bu nesnelere erişebilir ve müdahele edebiliriz. HTML sayfamız içindeki nesnelere erişmek için `document` objesini kullanarak başlamamız gerek.
<h2>Sayfadaki Nesnelere Erişmek</h2>
JS ile web sayfasındaki nesnelere erişmek için birden fazla yöntem vardır. Nesnenin ID'si, etiketi ya da class (sınıf) adıyla erişebiliriz.
**getElementById**
Sayfadaki nesnenin ID'sini belirterek bu nesneye erişebiliriz.

    <html>
    <head></head>
    <body>
    <h1>Lorem</h1>
    <p id="par">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
    <p>Lorem ipsum dolor sit amet...</p>
    
    <script>
        var paragraf = document.getElementById('par');
    </script>
   
    </body>
    </html>
**getElementByTagName**
 Sayfamızdaki nesnelerin etiketlerini kullanarak bu nesnelere erişebiliriz. Eğer birden fazla ise bir dizi olarak sonuç döner. Eğer hiçbir nesne bulunamazsa elimizde boş bir nesne olacaktır.

    <html>
        <head></head>
        <body>
        <h1>Lorem</h1>
        <p id="par">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
        <p>Lorem ipsum dolor sit amet...</p>
        
        <script>
            var paragraf = document.getElementByTagName('p');
        </script>
       
        </body>
        </html>

<h2>Erişilen Nesnelere Müdahele Etmek</h2>
JS ile erişilen nesnelere müdahele ederek özelliklerini değiştirebiliriz. Bir nesnenin sahip olduğu özelliklerin değerini elde etmek için `getAttribute()`, bu özellikleri değiştirmek için `setAttribute()` kullanabiliriz.

    <html>
            <head></head>
            <body>
            <h1>Lorem</h1>
            <p id="par">Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
            <p>Lorem ipsum dolor sit amet...</p>
            
            <script>
                var paragraf = document.getElementByTagName('p');
                paragraf.setAttribute('align', 'right');
                 var baslik = document.getElementsByTagName('h1');
    baslik[0].innerHTML = 'Yeni Baslik';
            </script>
           
            </body>
            </html>
<h2>Yeni Nesne Üretmek </h2>
`createElement()` ile yeni nesnelere oluşturup sayfamıza dahil edebiliriz.

    <html>
    <head></head>
    <body>
    
    <h1>Lorem</h1>
    
    <p id="par">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ab amet beatae delectus doloremque dolores eius explicabo.</p>
    
    <script>
        var yeniParagraf = document.createElement('p');
        yeniParagraf.innerHTML = 'Bu yeni bir paragraf';
    
        document.body.appendChild(yeniParagraf);
    
    </script>
    
    </body>
    </html>
JS'de yeni bir element oluşturup sayfaya dahil etmk için farklı yöntemlerde mevcuttur.


----------
<h1>17-Olaylar ve Olay Dinleyicileri (Events & Events Listener)</h1>
HTML sayfamızda gerçekleştirdiğimiz herşey aslında bir olaydır(event). Bir butona ya da resme tıklamak, imleci hareket ettirmek, bir tuşa basmak vs... hepsi bir olaydır ve JS ile bunları takip edebilir, gerçekleştiği zaman müdahele edebiliriz.

    document.onclick = function(){
            alert('sayfada bir yere tıklandı')
        } 
Yukarıdaki basit örnekte olduğu gibi sayfamızda herhangi bir yere tıklandığı zaman bunu yakalayabilir ve istediğimiz kodları çalıştırabiliriz. Burada fonksiyonumuza bir isim vermedik çünkü dokümana tıklandığı an zaten bu fonksiyon çağrılacaktır. Bu fonksiyonu başka bir yerde kullanmayacağız.
 

    var par = document.getElementById('par');
        par.onclick = function(){
            alert('paragrafa tıklandı')
        }
Belirlediğimiz nesnelere erişip bunlar üzerindeki olayları da takip edebiliriz. 
Yukarıdaki örneklerde olduğu gibi sadece özel bir fonksiyon çağırmak yerine, farklı olaylar gerçekleştiği zaman belirlediğimiz bir fonksiyonu çağırabiliriz. Bu örnekte `addEventListener()` kullanacağız.

    document.addEventListener("click", mesajYaz);
    
        function mesajYaz() {
            document.getElementById("mesajAlani").innerHTML = "Merhaba";
        }
JS de kullanabildiğimiz olaylar sadece `click` değil tabii ki. Sayfadaki her hareketimiz bir event olduğu için JS de de birçok event bulumaktadır. 

 - [HTML üzerindeki eventlerin listesi](http://www.w3schools.com/tags/ref_eventattributes.asp)


----------
<h1>18-Arayüz Özelliklerine Müdahele</h1>
JS ile syfamızdaki nesnelere ve özelliklerine müdahele ettiğimiz gibi görünümlerine yani CSS özelliklerine de erişebilir ve müdahele edebiliriz. bunun için nesnenin `style` özelliğini kullanacağız.
CSS de özellikleri yazarken birden fazla olan kelimeleri `-` ile birleştirip yazıyoruz. JS ise `camelCase` kuralına göre bu özellikleri yazmamız gerek.

    document.getElementById("menu").style.width = "350px";
    document.getElementById("menu").style.left = "0px";
    document.getElementById("menu").style.backgroundColor = "#CCC";
Ayrıca nesnemize bir class ataması da yapabiliriz.

    document.getElementById("menu").className = "yanMenu"


----------
<h1>19-JQuery</h1>
[JQuery](https://jquery.com/) en popüler JS kütüphanesidir. JS yazmamızı daha basit ve eğlenceli hale getirir. JQuery ile daha az kod yazarak JS ile yaptığımız işlemleri gerçekleştirebiliriz. DOM'a daha rahat erişim sağlayabilir ve manipüle edebilir, uyumluluk sorunları ve cross-platform gibi detayların birçoğunu JQuery bizim için çözebilir. 

> Jquery kütüphanesi kullanılarak geliştirilen jqueryui gibi daha
> gelişmiş arayüzleri ve araçları daha kolay kullanabilmemize imkan
> veren ek kütüphanelerde mevcuttur. -[wikipedia](http://tr.wikipedia.org/wiki/JQuery)

Tek yapmamız gereken JQuery dosyasını [sayfamıza dahil etmektir](https://jquery.com/download/). 

    <script src="//code.jquery.com/jquery-1.11.3.min.js"></script>
Örnek olarak sayfamızda **menu** id'li nesneye **yanMenu** isimli yeni bir class ataması yapalım:

    $('#menu').addClass('yanMenu');
Nesnemize tıklandığı zaman başka bir nesneyi gizleyelim ve sonrasında mesaj gösterelim:

    $( "#tikla" ).click(function() {
      $( "#liste" ).hide( "slow", function() {
        alert( "Liste gizlendi" );
      });
    });
