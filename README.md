# SwiftProtocolKonuAnlatimi
Swift programlama dilinde "protocol," nesnelerin belirli bir davranışı veya özelliği uygulamalarını sağlayan bir yapılardır. 
Protocol'ler, Swift'te kullanılan birçok türdeki nesneler arasında iletişim kurmayı ve kodunuzu daha modüler ve esnek hale
getirmeyi mümkün kılar. Protocol'leri, belirli bir sınıf veya tür hiyerarşisine bağlı olmaksızın uygulanabilirler.

Bir protocol tanımlarken şu unsurları içerebilirsiniz:

Method Requirements (Yöntem Gereksinimleri): Bir protocol, belirli bir metodu veya metotları uygulamanın gerektiğini belirtebilir.
Protocol'deki bu yöntemlerin adını, parametrelerini ve dönüş değerini tanımlarsınız, ancak bu metotların içeriğini sağlamazsınız.
İlgili sınıflar veya yapılar bu metotları kendi ihtiyaçlarına göre uygularlar.

protocol Konusabilen {
    func selamVer()
}

Property Requirements (Özellik Gereksinimleri): Bir protocol, belirli bir özelliği uygulamanın gerektiğini de belirtebilir.
Bu özelliklerin adını ve veri türünü tanımlarsınız, ancak başlangıç değerlerini belirtmezsiniz. İlgili sınıflar veya yapılar 
bu özellikleri kendi ihtiyaçlarına göre uygularlar.

protocol AdliGorev {
    var kimlikNumarasi: String { get }
}

Initializer Requirements (Başlatıcı Gereksinimleri): Bir protocol, belirli bir başlatıcıyı (initializer) uygulamanın gerektiğini
de belirtebilir. Bu, ilgili sınıfların belirli bir başlatıcıyı tanımlamalarını ve bu başlatıcıyı uygulamalarını zorunlu kılar.

protocol Kisi {
    init(isim: String)
}

Bir sınıf veya yapı, bir protocol'ü uyguladığında, o protocol'ün gerektirdiği metotları, özellikleri veya başlatıcıları uygulamak 
zorundadır. Örneğin:

class Ogrenci: Konusabilen {
    func selamVer() {
        print("Merhaba!")
    }
}

struct Calisan: AdliGorev {
    var kimlikNumarasi: String
}

class Insan: Kisi {
    var isim: String
    
    required init(isim: String) {
        self.isim = isim
    }
}

Yukarıdaki örneklerde, Ogrenci sınıfı Konusabilen protocol'ünü uyguluyor ve bu nedenle selamVer metodunu uygulamak zorunda. 
Calisan yapısı AdliGorev protocol'ünü uyguluyor ve bu nedenle kimlikNumarasi özelliğini sağlamak zorunda. Insan sınıfı ise Kisi 
protocol'ünü uyguluyor ve bu nedenle init(isim:) başlatıcısını sağlamak zorunda, bu aynı zamanda "required" bir başlatıcıdır.

Protocol'ler, kodunuzu daha modüler hale getirir, çünkü farklı sınıf ve yapılar arasında aynı davranışı veya özelliği paylaşmanızı 
sağlar. Bu, kodunuzun daha anlaşılır, bakımı daha kolay ve daha genişletilebilir olmasına yardımcı olur.

