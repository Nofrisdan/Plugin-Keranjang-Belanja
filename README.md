# Plugin-Keranjang-Belanja

## Tentang Plugin
Plugin Keranjang Belanja di Codeigniter 4 ini berfungsi sebagai library penyimpanan sementara produk yang telah di pilih masuk ke dalam keranjang

## Instalasi

Unduh repository ke dalam folder Codeigniter 4 menggunakan perintah `git clone`. dengan mengcopy source code dibawah ini

```
git clone https://github.com/Nofrisdan/Plugin-Keranjang-Belanja.git
```

## Konfigurasi

Tambahkan Code Di bawah ini pada folder `/App/Config/Autoload.php`. di codeigniter 4, dan cari sebuah variabel dengan nama `$psr4`.lalu copy kode berikut di dalamnya 

```
$psr4 = [

'CodeIgniterCart' => ROOTPATH . 'Plugin-Keranjang-Belanja/src'

]
```

## Load Plugin

untuk menggunakan plugin di codeigniter 4 kita harus `load`. plugin terlebih dahulu copy code dibawah ini 

```
$cart = \Config\Service::cart
```

## Cara Penggunaan

**Pastikan** Anda Sudah Meload plugin sebelum menjalankan perintah dibawah ini

### Tambahkan data ke dalam keranjang

```
$cart->insert([
    'id'      => 'sku_1234ABCD',
   'qty'     => 1,
   'price'   => '19.56',
   'name'    => 'T-Shirt',
   'options' => array('Size' => 'L', 'Color' => 'Red')

])
```
### Update Data Di Dalam keranjang

```
$cart->update([
   'rowid'   => '4166b0e7fc8446e81e16883e9a812db8',
   'id'      => 'sku_1234ABCD',
   'qty'     => 3,
   'price'   => '24.89',
   'name'    => 'T-Shirt',
   'options' => array('Size' => 'L', 'Color' => 'Red')

])
```

### Mengambil jumlah belanja di dalam keranjang

```
$cart->totalItems();
```

### Mengambil keseluruhan belanja di dalam keranjang
Data yang akan dikembalikan berupa array 

```
$cart->contents();
```



### Menghapus satu item di dalam keranjang

Isiikan Parameter dengan `rowid`.

```
$cart->remove('4166b0e7fc8446e81e16883e9a812db8');
```

### Menghapus seluruh data di dalam keranjang

```
$cart->destroy()
```
