---
layout: post
title: "Tutorial Install Octopress dan Deploy ke Heroku"
date: 2014-02-16 11:14:23 +0700
comments: true
categories: [octopress, tutorial, heroku]
---

Setelah artikel terakhir saya yang menulis tentang [kenapa saya menggunakan Octopress](/blog/2014/02/15/ngaku-programmer-pakai-octopress-sebagai-blogging-platform-kamu/), kali ini saya akan mengajarkan bagaimana menginstall dan menggunakan Octopress kemudian mengdeploynya ke Heroku (gratis!). Sebelumnya, untuk menginstall Octopress kamu memerlukan [git](http://git-scm.com/)  dan [ruby](http://ruby-lang.org/). Jika belum ada, silahkan menginstall kedua aplikasi tersebut lebih dulu.

Pertama-tama, clone semua code untuk Octopress.
{% codeblock lang:bash %}
git clone git://github.com/imathis/octopress.git octopress
cd octopress
{% endcodeblock %}

Perintah tersebut akan mengcopy semua code Octopres kedalam folder `octopress`. Kemudian install dependencies yang diperlukan Octopress dengan perintah berikut.

<!-- more -->

{% codeblock lang:bash %}
gem install bundler
bundle install
{% endcodeblock %}

Setelah itu, install theme bawaan dengan perintah `rake install`. Selain theme bawaan kamu juga dapat menginstall [themes lainnya](https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes).

Octopress telah terinstall. Sekarang kita akan membuat postingan baru.
{% codeblock lang:bash %}
rake new_post['Blogging dengan Octopress']
{% endcodeblock %}

File markdown akan muncul di folder `source/_posts/`. File tersebut akan memiliki konten berikut.

{% codeblock %}
---
layout: post
title: "Blogging dengan Octopress"
date: 2014-02-15 13:08:20 +0700
comments: true
categories: 
---
{% endcodeblock %}

Kemudian ganti kontennya.

{% codeblock %}
---
layout: post
title: "Blogging dengan Octopress"
date: 2014-02-15 13:08:20 +0700
comments: true
categories: [blogging, octopress]
---

Lorem ipsum sit dolor amet.
{% endcodeblock %}

Kamu dapat menambahkan kategori seperti contoh diatas. Dan konten artikel yang akan kamu tulis harus berada dibawah tanda `---`.

Setelah artikel dibuat, kamu dapat melihat blog kamu dengan perintah `rake generate` dan `rake preview`. Buka `localhost:4000` dan voila! Blog kamu telah muncul. Tetapi pada saat ini jika kamu mengganti konten artikel dan merefresh browser, kamu belum akan melihat perubahan. Untuk itu kamu juga dapat menjalankan `rake watch` sehingga setiap perubahan yang kamu buat dapat segera terlihat.

Oke jadi blog kamu telah selesai dibuat. Sekarang kita akan mengdeploynya ke Heroku. Sebelumnya jika kamu belum mempunyai akunnya, daftar [disini](https://id.heroku.com/signup). Kemudian jalankan perintah `gem install heroku` untuk menginstall heroku. Lalu ganti Gemfile dengan Gemfile berikut.

{% codeblock %}
source "https://rubygems.org"

gem 'rake', '~> 0.9'
gem 'jekyll', '~> 0.12'
gem 'rdiscount', '~> 2.0.7'
gem 'RedCloth', '~> 4.2.9'
gem 'haml', '~> 3.1.7'
gem 'compass', '~> 0.12.2'
gem 'sass', '~> 3.2'
gem 'sass-globbing', '~> 1.0.0'
gem 'rubypants', '~> 0.2.0'
gem 'stringex', '~> 1.4.0'
gem 'liquid', '~> 2.3.0'
gem 'directory_watcher', '1.4.1'
gem 'pygments.rb', '~> 0.3.4'
gem 'sinatra', '~> 1.4.2'
gem 'thin'

group :development do
  gem 'rb-fsevent', '~> 0.9'
end

ruby '2.0.0'
{% endcodeblock %}

Jalankan perintah berikut untuk mengdeploy ke heroku.

{% codeblock %}
echo '' > .slugignore
heroku create --stack cedar --buildpack git://github.com/jgarber/heroku-buildpack-ruby-octopress.git
git push heroku master
{% endcodeblock %}

Jalankan perintah `heroku open` untuk membuka blog baru kamu di Heroku! Pada saat ini seharusnya blog kamu telah dapat dibuka, tetapi jika belum kamu dapat memberikan komentar dibawah atau tanya saya di [@WilHn](https://twitter.com/WilHn).
