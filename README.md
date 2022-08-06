## JVM nedir,ne işe yarar?
JVM (Java Virtual Machine) derlenmiş java kodlarının çalışmasını sağlayan soyut bir makinedir. </br>
En önemli özelliği, bir kere yaz her yerde çalıştır mantığıdır.</br>
Esas olarak üç faaliyetten sorumludur:
* Kodu yükler </br>
* Kodu doğrular 
* Kodu yürütür 

## JDK nedir,ne işe yarar?
JDK, java uygulamaları geliştirmek için gerekli araçlar ve kitaplıklar koleksiyonu sunan bir yazılım geliştirme ortamıdır.Bu paket Java ile geliştirme yapmak için bütün araçları içerir bu sayede bir java uygulaması geliştirmek için JDK yüklememiz yeterlidir.


![](https://www.simplilearn.com/ice9/free_resources_article_thumb/JDK-in-Java-The-architecture-of-JDK-in-Java.png)

## Garbage Collector görevi nedir? Nasıl çalışır?
Garbage Collector'ın temel amacı,erişilemeyen nesneleri yok ederek yığın belleği boşaltmaktır.Öncelikle yığın belleğe bakar ve hangi neslerin kullanılıp hangilerinin kullanımda olmadığını tespit eder ve boşa yer kaplamaması için kullanılmayan nesneleri siler.


## .jar formatı nedir?
Java dilini kullanarak oluşturulan dosyaların arşiv dosyası, .jar uzantılı JAR dosyalarıdır.İçinde pek çok farklı dosya barındırdığı için ZIP formatındadır

## Javada .class ve .java formatının farkı nedir?
* .class, java derleyicisi tarafından oluşturulan derlenmiş bir dosyadır.
* .java, java dilinde yazılmış kaynak kodları saklar.

## Abstract class nedir, nasıl çalışır, ne işe yarar?
Java dilinde,ortak özellikleri olan nesneleri modellemek için abstract(soyut) class kullanılır.Kalıtım özelliği kullanılabilerek kod tekrarı azaltılır.
* Abstract class kullanılarak, bu sınıflardan bir nesne oluşturulmaz.
* Soyut sınıflar ancak kendilerinden bir alt sınıf türetmek için kullanılan sınıflardır. Bir nevi şablon yada taslak gibi düşünülebilir.
* Soyut metotların bir gövdesi yoktur ve alt sınıfta override edilir.

```
public abstract class Kisi {

  String adSoyad;

  String dogumTarihi;


  public Kisi(String adSoyad, String dogumtarihi) {

  this.adSoyad=adSoyad;

  this.dogumTarihi=dogumtarihi;

  }

  public String getAdSoyad() {

  return adSoyad;

  }

  public void setAdSoyad(String adSoyad) {

  this.adSoyad=adSoyad;

  }


  public abstract void kisiBilgileri();

}
```

```
public class Ogrenci extends Kisi {

 int ogrNo;


 public Ogrenci(String adSoyad, String dtarih, int ogrNo,) {

   super(adSoyad,dtarih);

   this.ogrNo=ogrNo;


 }

 @Override

 public void kisiBilgileri() {

   System.out.println("Kisi adı Soyadı:"+getAdSoyad());

   System.out.println("Öğrenci Numarası:"+ogrNo);

   System.out.println("Doğum tarihi:"+ super.dogumTarihi);

 }

 public static void main(String[] args) {

   Ogrenci ogr=new Ogrenci("Işınnur Günay", "19/07/2003", 21253041);

   ogr.kisiBilgileri();

 }

}
```

