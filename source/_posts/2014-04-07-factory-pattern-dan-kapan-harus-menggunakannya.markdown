---
layout: post
title: "Factory Pattern dan Kapan Harus Menggunakannya"
date: 2014-04-07 20:22:54 +0700
comments: true
categories: [pattern, oop, best practices]
---

Factory pattern adalah salah satu pattern yang paling sering digunakan untuk pengembangan aplikasi berbasis object. Konsepnya sangat mudah: "Instansiasi object tanpa mengkekspose cara instansiasi ke client dan object-object yang diinstansiasi memiliki interface yang sama".

Contoh: Instansiasi produk
```php
<?php

interface Product
{
    public function getId();
    public function getName();
}

class Baju implements Product
{
    //
    // ....
    //

    public function getSize()
    {
        //
    }
}

class Tas implements Product
{
    //
    // ...
    //

    public function hasLaptopContainer()
    {
        //
    }
}

class ProductFactory
{
    public function createProduct($type)
    {
       if ($type == 'baju') {
          return new Baju();
       } else if ($type == 'tas') {
          return new Tas();
       }
       throw new ProductTypeNotFoundException();
    }
}

```

Contoh diatas adalah memiliki kemudahan yaitu mudah dibuat, tetapi kekurangannya adalah jika ada produk baru kode dari ProductFactory harus diubah. Hal ini melanggar salah satu prinsip OOP yaitu Open Close Principle yang menyatakan bawah suatu class, module atau function terbuka untuk diextend tetapi tertutup untuk modifikasi.

Untuk mengatasi masalah ini terdapat implementasi lain dari Factory Pattern.

```php
<?php

interface Product
{
    //
}

class Baju
{
    static public function registerProduct()
    {
        ProductFactory.instance().registerProduct('baju', new ReflectionClass('Baju'));
    }
}

class Tas
{
    static public function registerProduct()
    {
        ProductFactory.instance().registerProduct('tas', new ReflectionClass('Tas'));
    }
}

class ProductFactory
{
    private $types = array();

    //
    // singleton code
    //

    public function registerProductType($type, ReflectionClass $product)
    {
        $this->types[$type] = $product;
    }

    public function createProduct($type)
    {
        if isset($this->types[$type]) {
            $productClass = $this->types[$type];
            return $productClass->newInstance();
        }
        throw new ProductTypeNotFoundException();
    }
}

Baju::registerProduct();
Tas::registerProduct();
```

Bisa dilihat bedanya? Untuk menambahkan Product baru, ProductFactory sama sekali tidak perlu diganggu. Hal ini berarti bahwa Open Close Principle tidak dilanggar. Tetapi implementasi seperti ini akan meningkatkan kompleksitas dari aplikasi.

Lalu kapan seharusnya aplikasi memakai Factory Pattern? Kalau saya sendiri memakainya jika ada class yang memiliki banyak subclass namun saya hanya perlu memanggil method-method dari parent class.
