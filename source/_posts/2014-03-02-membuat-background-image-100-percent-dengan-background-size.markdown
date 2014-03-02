---
layout: post
title: "Membuat Background Image 100% dengan background-size"
date: 2014-03-02 10:58:35 +0700
comments: true
categories: [css3, css, tricks, tutorial]
---

Pernah melihat halaman dimana background imagenya itu 100% dan jika diresize pun hasilnya tetap bagus? Coba lihat [Medium](https://medium.com/) dan lakukan resize sesukamu. Background image akan menyesuaikan dengan width dari browser. Berbeda jika kamu hanya memberikan 100% pada image dan melakukan resize, hasilnya pasti proporsi image menjadi tidak bagus. Lalu bagaimana cara melakukannya?

Siapkan image dengan ukuran yang cukup besar (height dari gambar original melebihi height bagian dari image yang akan ditampilkan). Misalnya Medium menggunakan image berikut.
{% img center https://d262ilb51hltx0.cloudfront.net/fit/c/1400/1120/gradv/29/81/60/darken/25/1*jdRb-HndWS3PrA9acE9laA.jpeg Medium %}

Dapat kita lihat bahwa image original memiliki height yang cukup besar dan bagian yang ingin ditampilkan berada di tengah gambar.

Kamu dapat mencoba hasilnya terlebih dahulu di [cssdeck](http://cssdesk.com/GFUmR) sebelum saya menjelaskannya. Kamu juga dapat mengganti-ganti cssnya.

Yang pertama yang harus dilihat adalah wrapper mempunyai height 450px yang artinya background yang akan diambil hanya 450px secara vertikal. Setelah itu definisikan background-image ke url dari image yang akan digunakan. Setelah itu gunakan css background-position untuk menampilkan hanya bagian tengah dari gambar jika height dari gambar terlalu besar sehingga sisanya akan di crop. Dan yang paling penting adalah css `background-size: cover` dimana image akan discaling sehingga menempati containernya (dalam hal ini #wrapper) tetapi jika rasionya berbeda, image akan di crop. Jangan lupa gunakan prefix -moz dan -webkit untuk support browser yang lebih bagus.

Begitu saja. Mudah bukan? Kamu dapat mencoba mengganti background-position menjadi bottom atau top. Background-size juga memiliki beberapa nilai yang dapat digunakan (selengkapnya dapat dilihat di [sitepoint](http://www.sitepoint.com/css3-background-size-property/)). Silahkan mencoba.
