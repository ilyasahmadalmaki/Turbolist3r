##Penerjemah bahasa indonesia 
IlYas Ahmad almaki / Monkey D_Oon

##Tools ini juga sangat cocok buat para GRETONGER INDONESIA / PEMBURU INTERNET GRATIS :)

## Turbolist3r

Turbolist3r is a fork of the [sublist3r](https://github.com/aboul3la/sublist3r) subdomain discovery tool. In addition to the original OSINT capabilties of sublist3r, turbolist3r automates some analysis of the results, with a focus on subdomain takeover.

Turbolist3r queries public DNS servers for each discovered subdomain. If the subdomain exists (i.e. the resolver replied with an address), the answer is categorized as CNAME or A record. By examining A records, it is possible to discover potential penetration testing targets for a given domain. Likewise, the process of looking for subdomain takeovers is simple; view the discovered CNAME records and investigate any that point to applicable cloud services.

Please do not use for illegal purposes.

## Screenshots

![Screenshot 1](https://cp270.files.wordpress.com/2019/01/turbo-lister.png)

![Screenshot 2](https://cp270.files.wordpress.com/2018/01/turbo_analysis.png)

## Cara penggunaan dan keterangan

Singkatan     |  Kepanjangan  | Deskripsi
------------- | ------------- |-------------
-d            | --domain      | Nama domain untuk menghitung subdomain
-b            | --bruteforce  | Aktifkan modul bruteforce subbrute
-p            | --ports       | Pindai subdomain yang ditemukan terhadap port tcp tertentu
-v            | --verbose     | Aktifkan mode verbose dan tampilkan hasil secara realtime
-t            | --threads     | Jumlah waktu yang digunakan untuk subbrute bruteforce
-e            | --engines     | Tentukan daftar mesin pencari dan pisahkan dengan koma
-o            | --output      | Simpan semua domain yang ditemukan ke dalam file teks yang ditentukan
-h            | --help        | untuk melihat penggunaan dan module
-a            | --analyze     | Mengulamg DNS analysis dan hasil output
(none)        | --saverdns    | Simpan reverse DNS analysis kedalam file yang ditentukan
(none)        | --inputfile   | Baca domain dari file yang ditentukan, dan gunakan untuk analisis
(none)        | --debug       | Cetak informasi debug selama modul analisis (-a). Mencetak sebagian besar data DNS mentah, dibarengi dengan utilitas DIG Linux DNS dan outputnya sangat membantu untuk menafsirkan output debug
-r            | --resolvers   | File dengan server DNS untuk diisi sebagai resolvers. File harus hanya memiliki satu alamat IP server per baris dan hanya alamat IP yang diterima

### Contoh :

###keterangan : jika anda menggunakan termux,saya sarankan menggunakan python2

* Untuk melihat semua opsi,gunakan input -h :

```python turbolist3r.py -h```

* Untuk menghitung subdomain dari domain tertentu, melakukan analisis lanjutan, dan menyimpan analisis ke file:

``python turbolist3r.py -d contohsitus.com -a --saverdns analysis_file.txt``

* Baca subdomain dari file dan lakukan analisis lanjutan pada mereka:

``python turbolist3r.py -d contohsitus.com -a --inputfile subdomains.txt``

* Gunakan -r untuk mengisi resolver DNS dari file (resolver digunakan dengan -a modul analisis):

``python turbolist3r.py -d example.com -a --inputfile subdomains.txt -r dns_servers.txt``

* Untuk menghitung subdomain dari domain tertentu:

``python turbolist3r.py -d example.com``

* Untuk menghitung subdomain dari domain tertentu dan menyimpan subdomain yang ditemukan ke dalam file:

``python turbolist3r.py -d example.com -o hasil.txt``

* Untuk menghitung subdomain dari domain tertentu dan menunjukkan hasil real-time:

``python turbolist3r.py -v -d example.com``

* Untuk menghitung subdomain dan mengaktifkan modul bruteforce:

``python turbolist3r.py -b -d example.com``

* Untuk menghitung subdomain dan menggunakan mesin penelusuran khusus seperti Google, Bing, Yahoo dll.

``python turbolist3r.py -e google,yahoo,virustotal -d example.com``


## Definisi

Perhatikan bahwa turbolist3r belum diuji pada Windows. 
Turbolist3r tergantung pada modul `` dnslib`, `request`,` dnspython`, dan `argparse` python.

#### Modul dnslib 
Modul dnslib dapat diunduh dari [https://bitbucket.org/paulc/dnslib/[(https://bitbucket.org/paulc/dnslib/) 
atau diinstal  menggunakan python-pip

``pip install dnslib``

#### Modul request

-install untuk android/termux:
```pip2 install requests```

- Install untuk Ubuntu/Debian:
```sudo apt-get install python-requests```

- Install untuk Centos/Redhat:
```sudo yum install python-requests```

- Install using pip on Linux:
```sudo pip install requests```

#### Modul dnspython  (http://www.dnspython.org/)

- Install untuk Ubuntu/Debian:
```sudo apt-get install python-dnspython```

- Install using pip:
```sudo pip install dnspython```

#### Modul argparse 

- Install untuk Ubuntu/Debian:
```sudo apt-get install python-argparse```

- Install untuk Centos/Redhat:
```sudo yum install python-argparse``` 

- Install menggunakan pip:
```sudo pip install argparse```

## License

Turbolist3r is licensed under the GNU GPL license. take a look at the [LICENSE](https://github.com/fleetcaptain/Turbolist3r/blob/master/LICENSE) for more information.

Respect legal restrictions and only conduct testing against infrastructure that you have permission to target.

## Credits

* [aboul3la](https://github.com/aboul3la/sublist3r) - The creator of **Sublist3r**; turbolist3r adds some features but is otherwise a near clone of sublist3r. 
* [TheRook](https://github.com/TheRook/) - The bruteforce module was based on his script **subbrute**.
* [bitquark](https://github.com/bitquark) - The Subbrute's wordlist was based on his research **dnspop**.

## Thanks

* Thank you to [aboul3la](https://github.com/aboul3la/) for releasing sublist3r, an incredible subdomain discovery tool!
