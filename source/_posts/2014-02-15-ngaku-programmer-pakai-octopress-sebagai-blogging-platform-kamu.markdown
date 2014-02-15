---
layout: post
title: "Ngaku Programmer? Pakai Octopress Sebagai Blogging Platform Kamu"
date: 2014-02-15 13:08:20 +0700
comments: true
categories: [blogging, octopress, jekyll]
---

Sebagai permulaan, apakah blog ini memakai Octopress? Jelas! Kalau tidak saya tidak akan menulis artikel ini. Saya sebelumnya memakai [tumblr](http://praxmatig.tumblr.com) untuk blogging dan meskipun overall tumblr merupakan platform blogging yang cukup bagus, tapi SEOnya jelek! Pernah melihat postingan tumblr yang ada di page 1 google? Saya belum. Oleh karena itu, saya mencari platform blogging lain untuk memuat tulisan-tulisan saya tentang software development. Tetapi untuk curhatan dan hal pribadi lainnya saya tetap memakai tumblr.

Okay. Jadi kriteria saya untuk blogging platform yang akan saya pakai itu simple. Enak nulis, punya tema yang minimalis dan yang penting mudah untuk nulis code. Seperti biasanya, jika kata blog terucap yang pertama kali terlintas di kepala itu pasti [Wordpress](http://wordpress.org) dan [Blogger](http://blogger.com). Tetapi sayang sekali, kedua platform tadi tidak memenuhi kriteria #3. Yup! Nulis code di Wordpress dan Blogspot itu kurang mudah. Atau mungkin bisa juga dibilang susah. Setelah itu saya melirik platform lain yaitu [Squarespace](http://squarespace.com), [Typepad](http://typepad.com), [Posthaven](http://posthaven.com) dan juga [Ghost](http://ghost.org). Ke 4 platform tersebut mempunyai 1 kesamaan yang cukup menyebalkan. Layanan yang ditawarkan berbayar! Seperti kebanyakan orang Indonesia lainnya, tentu saja saya lebih suka barang gratisan. Tetapi dari ke 4 platform tersebut, jika suatu hari nanti saya sudah kembali ke jalan yang benar (mau membayar), saya akan memilih Ghost. Kenapa? Karena Ghost memenuhi ke 3 kriteria saya dengan sangat baik.

Setelah perjuangan yang berat tersebut, saya mencoba melihat kembali platform blogging yang pernah saya pakai sebelumnya. [Octopress](http://octopress.org). Sebelum tertipu oleh tumblr, saya telah memakai Octopress untuk blogging. Dan jujur saja, saya sangat suka menulis dengan Octopress yang memenuhi 3 kriteria tersebut. Apa hebatnya Octopress ini? Sebelum saya menjelaskan tentang Octopress, mari kita membahas Jekyll terlebih dahulu.

<!-- more -->

# Jekyll
{% blockquote Jekyll http://jekyllrb.com/docs/home/ %}
Jekyll is a simple, blog-aware, static site generator. It takes a template directory containing raw text files in various formats, runs it through Markdown (or Textile) and Liquid converters, and spits out a complete, ready-to-publish static website suitable for serving with your favorite web server. Jekyll also happens to be the engine behind GitHub Pages, which means you can use Jekyll to host your project’s page, blog, or website from GitHub’s servers for free.
{% endblockquote %}

Ngerti? Jadi intinya kamu hanya perlu menulis di file teks dengan format [Markdown](daringfireball.net/projects/markdown/) atau [Textile](http://textile.sitemonks.com/), lalu Jekyll akan menggenerate website kamu. Website yang dihasilkan hanya berupa website statis yang berisi hanya html, css dan javascript. Tidak ada database, tidak ada code apapun. Sudah kelihatan bagusnya dimana? Belum? Oke, akan saya jelaskan.

*   Cepat

    Performa sebuah website biasanya paling ditentukan oleh waktu yang diperlukan untuk melakukan query ke database dan juga overhead dari code kamu. Tetapi Jekyll agan menggenerate website statis untuk kamu yang tidak ada query database atau code apapun. Artinya? Betul sekali. Website kamu akan menjadi super cepat! Belum lagi jika kamu melakukan caching secara agressive, pembaca pasti akan sangat senang membaca blog kamu (tentunya jika artikel kamu semenarik artikel ini).

*   Mudah

    Sudah pernah pakai Markdown? Kalau sudah silahkan skip ke point selanjutnya. Jika belum silahkan baca tentang [Markdown](http://daringfireball.net/projects/markdown). Intinya Markdown adalah tool untuk konversi text-to-HTML. Tetapi teks yang kamu tulis harus mengikuti [syntax](http://daringfireball.net/projects/markdown/syntax) Markdown. Jangan khawatir, syntaxnya sangat mudah sekali. Cukup luangkan waktu setengah jam saja untuk menguasainya.

*   Pakai teks editor kesayangan kamu

    Secara pribadi, saya kurang menyukai editor Wordpress, Blogger dan beberapa platform lainnya. Apakah kamu sependapat dengan saya? Jika ya, bagus sekali karena dengan Jekyll kamu dapat menulis postingan kamu dengan editor kesayangan kamu. Saya sendiri menulis postingan ini menggunakan [Vim](http://vim.org).

Keren bukan? Kamu dapat membacanya secara lebih lengkap di situs [Jekyll](http://jekyllrb.com/). Sekarang saya akan menjelaskan tentang Octopress.


# Octopress

{% blockquote Octopress http://octopress.org/ %}
Octopress is a framework designed by Brandon Mathis for Jekyll, the blog aware static site generator powering Github Pages. To start blogging with Jekyll, you have to write your own HTML templates, CSS, Javascripts and set up your configuration. But with Octopress All of that is already taken care of. Simply clone or fork Octopress, install dependencies and the theme, and you're set.
{% endblockquote %}

Singkatnya Octopress hampir menyerupai Jekyll. Tetapi di Octopress kamu telah diberikan theme/template dasar. Selain template dasar, juga tersedia themes lain seperti yang dapat dilihat di [opthemes.com](http://opthemes.com/), [octopressthemes.com](http://octopressthemes.com/) dan [octopress wiki](https://github.com/imathis/octopress/wiki/3rd-Party-Octopress-Themes). Octopress juga menyediakan plugin-plugin seperti code snippets, video tag, github gists, jsFiddle, syntax highlight dan plugin lainnya.

Gimana? Tertarik untuk mencobanya? Saya akan menulis tentang cara menginstall dan menggunakannya di post berikutnya. Namun, sesuai dengan konsep Octopress "A blogging framework for hackers", kamu harusnya dapat melakukannya sendiri jika kamu merasa cukup pantas untuk dipanggil `hacker`

Dan yang terakhir, kamu dapat melihat code blog ini di [github](https://github.com/wlzch/kulicoding) dan teks untuk artikel ini [disini](https://raw2.github.com/wlzch/kulicoding/master/source/_posts/2014-02-15-ngaku-programmer-pakai-octopress-sebagai-blogging-platform-kamu.markdown)
