---
title:  "Cara Install ZeroTier di OpenWRT"
categories: openwrt
permalink: cara-install-zerotier-di-openwrt.html
tags: [zerotier]
sidebar: kategori-artikel
toc: true
---

## Pendahuluan

 Artikel ini akan membahas langkah-langkah untuk menginstal `ZeroTier` di `OpenWRT`, sebuah sistem operasi berbasis `Linux` yang dirancang untuk router.

## Persiapan

Sebelum memulai instalasi, pastikan Anda memiliki akses ke router `OpenWRT` Anda dan koneksi internet yang stabil. Anda juga perlu memiliki akun di situs web `ZeroTier` untuk membuat jaringan virtual.

## Langkah-langkah Instalasi

1. Update dan Instalasi Paket
Pertama, Anda perlu memperbarui daftar paket di `OpenWRT` dan menginstal paket `ZeroTier`. Buka terminal SSH dan masukkan perintah berikut:

<pre><code class="language-bash">opkg update && opkg install zerotier</code></pre>

Perintah ini akan memperbarui daftar paket dan menginstal `ZeroTier` di router Anda.

2. Konfigurasi ZeroTier

Setelah instalasi selesai, Anda perlu mengaktifkan dan mengonfigurasi `ZeroTier`. Masukkan perintah berikut untuk mengaktifkan ZeroTier:

<pre><code class="language-bash">uci set zerotier.global.enabled='1'
uci commit zerotier
/etc/init.d/zerotier start
</code></pre>

Perintah ini akan mengaktifkan `ZeroTier` dan memulai layanan.

3. Membuat Jaringan di ZeroTier

Selanjutnya, buka situs web `ZeroTier` dan masuk ke akun Anda. Buat jaringan baru dan catat `Network ID` yang diberikan. `Network ID` ini akan digunakan untuk menghubungkan perangkat ke jaringan `virtual` Anda.

4. Menghubungkan Router ke Jaringan ZeroTier

Kembali ke `terminal SSH` dan masukkan perintah berikut untuk menghubungkan router ke jaringan ZeroTier:

<pre><code class="language-bash">zerotier-cli join <Network ID></code></pre>

Gantilah `<Network ID>` dengan Network ID yang Anda dapatkan dari situs web `ZeroTier`. Perintah ini akan menghubungkan router Anda ke jaringan `virtual`.

5. Verifikasi Koneksi

Untuk memastikan bahwa router Anda telah terhubung ke jaringan `ZeroTier`, masukkan perintah berikut:

<pre><code class="language-bash">zerotier-cli listnetworks</code></pre>

Anda akan melihat daftar jaringan yang terhubung, termasuk jaringan `ZeroTier` yang baru saja Anda tambahkan.

## Menghubungkan Perangkat Lain

Setelah router Anda terhubung ke jaringan `ZeroTier`, Anda dapat menghubungkan perangkat lain seperti komputer, smartphone, atau perangkat IoT. Instal aplikasi `ZeroTier` di perangkat tersebut dan gunakan `Network ID` yang sama untuk bergabung ke jaringan.

## Keuntungan Menggunakan ZeroTier di OpenWRT

Menggunakan `ZeroTier` di `OpenWRT` memiliki beberapa keuntungan, antara lain:

- `Keamanan`: ZeroTier menggunakan enkripsi end-to-end untuk melindungi data Anda.
- `Kemudahan Akses`: Anda dapat mengakses perangkat di jaringan ZeroTier dari mana saja, selama Anda memiliki koneksi internet.
- `Fleksibilitas`: ZeroTier mendukung berbagai platform, termasuk Windows, macOS, Linux, Android, dan iOS.

{% include links.html %}