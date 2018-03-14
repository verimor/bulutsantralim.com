**Rehberde yeni grup oluşturmak, güncellemek veya silmek için api.bulutsantralim.com adresi aşağıdaki örneklerdeki gibi çağrılır.**

**GRUP OLUŞTURMA ÖRNEĞİ**
```json
POST http://api.bulutsantralim.com/contact_groups
Host: api.bulutsantralim.com
Content-Type: application/json
Accept: */*

{
 "key" : "K12345678-1234-5678-4321-123456789012",
 "name" : "Müşteriler"
}
```
**BAŞARILI CEVAP**

```json
HTTP/1.1 200 OK
20212
```

**BAŞARISIZ CEVAP**

```json
HTTP/1.1 400 Bad Request
name can't be blank
```

**GRUP GÜNCELLEME ÖRNEĞİ**
```json
PATCH http://api.bulutsantralim.com/contact_groups/20212
Host: api.bulutsantralim.com
Content-Type: application/json
Accept: */*

{
 "key" : "K12345678-1234-5678-4321-123456789012",
 "name" : "Arkadaşlarım"
}
```
**BAŞARILI CEVAP**

```json
HTTP/1.1 200 OK
OK
```

**BAŞARISIZ CEVAP**

```json
HTTP/1.1 400 Bad Request
cannot find group with id: 20212
```

**GRUP SİLME ÖRNEĞİ**
```json
DELETE http://api.bulutsantralim.com/contact_groups/20212
Host: api.bulutsantralim.com
Content-Type: application/json
Accept: */*

{
 "key" : "K12345678-1234-5678-4321-123456789012"
}
```
**BAŞARILI CEVAP**

```json
HTTP/1.1 200 OK
OK
```

**BAŞARISIZ CEVAP**

```json
HTTP/1.1 400 Bad Request
cannot find group with id: 20212
```

**Rehbere yeni kişi eklemek, güncellemek veya silmek için api.bulutsantralim.com adresi aşağıdaki örneklerdeki gibi çağrılır.**

**KİŞİ EKLEME ÖRNEĞİ**
```json
POST http://api.bulutsantralim.com/contacts
Host: api.bulutsantralim.com
Content-Type: application/json
Accept: */*

{
 "key" : "K12345678-1234-5678-4321-123456789012",
 "name" : "Verimor",
 "surname" : "Telekomünikasyon",
 "tckn" : "12345678910",
 "description" : "A.Ş.",
 "phone" : "08505320000",
 "email" : "info@verimor.com.tr",
 "title" : "Sabit Telefon Operatörü",
 "phone2" : "02123205062",
 "fax" : "02123205072",
 "gender" : "m",
 "birthday" : "01.01.1990",
 "birthday_sms" : "true",
 "weddingday" : "01.01.2018",
 "weddingday_sms" : "true",
 "note1" : "",
 "note2" : "",
 "note3" : "",
 "note4" : "",
 "monthly_sms_day" : "9",
 "monthly_sms_message" : "Bu gün ayın dokuzu",
 "group_ids:[]" : "20212",
 "group_ids:[]" : "20213",
}
```
**BAŞARILI CEVAP**

```json
HTTP/1.1 200 OK
10203
```

**BAŞARISIZ CEVAP**

```json
HTTP/1.1 400 Bad Request
name can't be blank
```

**PARAMETRELER** <br/>
Kullanılacak parametreler aşağıdakilerdir. **Zorunlu** olanlar koyu olarak belirtilmiştir.

* **key** = Size özel oluşturulmuş API anahtarınızdır. https://oim.verimor.com.tr/switch/domain/edit adresinden görebilir/üretebilirsiniz.
* **name:** Ad
* surname: Soyad
* tckn: TC kimlik numarası
* description: Açıklama
* **phone:** Telefon numarası
* email: E-posta adresi
* title: Unvan
* phone2: Ek telefon numarası
* fax: Fax numarası
* gender: Cinsiyet (Erkek: 'm', Kadın: 'f' olarak gönderilmeli)
* **birthday:** Doğum günü (dd.mm.yyyy formatında olmalı, birthday_sms parametresi 'true' olarak gönderildiği zaman zorunludur)
* birthday_sms: Doğum gününde otomatik mesaj gönderimi ('true' veya 'false' olarak girilmeli)
* **weddingday:** Evlilik günü (dd.mm.yyyy formatında olmalı, weddingday_sms parametresi 'true' olarak gönderildiği zaman zorunludur)
* weddingday_sms: Evlilik gününde otomatik mesaj gönderimi ('true' veya 'false' olarak girilmeli)
* note1: Kişiyle ilgili notlar
* note2:
* note3:
* note4:
* monthly_sms_day: Kişiye aylık otomatik SMS gönderilmesini istiyorsanız gönderilecek günü giriniz (1-31 arası).
* monthly_sms_message: Aylık SMS mesajı
* group_ids:[]: Kişinin eklenmesini istediğiniz grubun id değeri

**Doğum günü, Evlilik günü ve Aylık SMS gönderimi özelliklerinin kullanılabilmesi için [Rehber Ayarlarım](https://oim.verimor.com.tr/contact/settings/edit) sayfasından "Özel Gün Mesajları" özelliği aktif edilmelidir**

**KİŞİ GÜNCELLEME ÖRNEĞİ**

Kişi eklerken kullanabileceğiniz tüm parametreler güncelleme için de geçerlidir.

```json
PATCH http://api.bulutsantralim.com/contacts/10203
Host: api.bulutsantralim.com
Content-Type: application/json
Accept: */*

{
 "key" : "K12345678-1234-5678-4321-123456789012",
 "name" : "Bulutsantralim"
}
```
**BAŞARILI CEVAP**

```json
HTTP/1.1 200 OK
OK
```

**BAŞARISIZ CEVAP**

```json
HTTP/1.1 400 Bad Request
cannot find group with id: 10203
```

**KİŞİ SİLME ÖRNEĞİ**
```json
DELETE http://api.bulutsantralim.com/contacts/10203
Host: api.bulutsantralim.com
Content-Type: application/json
Accept: */*

{
 "key" : "K12345678-1234-5678-4321-123456789012"
}
```
**BAŞARILI CEVAP**

```json
HTTP/1.1 200 OK
OK
```

**BAŞARISIZ CEVAP**

```json
HTTP/1.1 400 Bad Request
cannot find group with id: 10203
```
