---
layout: post
title: "Buat Aplikasi Mobile Tanpa Code Server dengan Parse.com"
date: 2014-03-02 19:51:33 +0700
comments: true
categories: [parse, mobile, android]
---

{% img center http://blogparsecom.c.presscdn.com/wp-content/uploads/2013/04/Parse_Hosting.jpg Parse %}

Pengen buat aplikasi mobile tapi tidak bisa atau malas code server/backendnya? Kalau betul [Parse](http://www.parse.com) sangat cocok dengan kamu. Kok bisa?

{% blockquote Parse https://parse.com/about %}
With Parse, you can add a scalable and powerful backend in minutes and launch a full-featured app in record time without ever worrying about server management. We offer push notifications, social integration, data storage, and the ability to add rich custom logic to your app’s backend with Cloud Code.
{% endblockquote %}

Artinya dengan menggunakan Parse, kamu hanya perlu fokus ke pembuatan aplikasi mobile tanpa perlu menyentuh code server sedikitpun. Parse menyediakan push notifications (misalnya untuk notifikasi pertemanan), integrasi sosial (misalnya login facebook/twitter) dan yang paling penting data storage (penyimpanan data).

Langsung lihat contoh code untuk Android SDKnya aja biar lebih ngerti.

``` java

ParseObject restaurant = new ParseObject("restaurant");
restaurant.put("name", "Awesome Restaurant");
restaurant.put("address", "Jalan jalan no 142, Medan");

ParseObject owner = new ParseObject("user");
owner.put("name", "Eric Ries");

restaurant.put("owner", owner);

restaurant.saveInBackground(new SaveCallback() {

    public void done(ParseException e) {
        // do something
    }
});

```

Simpel kan? Jadi kamu tidak perlu mendefinisikan tabel restaurant dan user, juga field-field yang ada pada kedua tabel tersebut, semua serba dinamis dan cepat! Lalu dimana data tersebut tersimpan? Tentu saja di servernya Parse. Kamu juga bisa melihat data-datanya melalui data browser jika sudah login di Parse.com.

Kebayang kelebihannya dimana? Pastinya code akan lebih cepat karena tidak perlu ribet dengan segala code server, autentikasi dan segala macam hal rumit lainnya. Kamu hanya perlu fokus membuat aplikasi mobile yang keren! Selain Android, Parse juga memiliki SDK untuk iOS, Windows 8, Windows Phone 8, OS X, Xamarin, Unity dan Javascript. Dan yang kerennya lagi? Kamu bisa mencobanya GRATIS dengan batasan yang cukup banyak: 1 juta request/bulan dan 1 juta push notification/bulan. Untuk ukuran startup saya rasa sudah sangat cukup.

Tertarik? Langsung menuju ke tkp aja kalau gitu. [Parse](https://parse.com/).
