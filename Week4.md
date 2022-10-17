## Writing Test Week 4 



Nama : Muhammad Arya Wirawan
Track : Front End Web Development
Group Track : 2
Mentor : Thoriq Nur Faizal


### Asynschronous - Fetch & Async Await
- API merupakan perantara antara aplikasi front-end dengan server. Untuk dapat berinteraksi dengan server, aplikasi front end memerlukan pelayan/perantara yaitu API.
- Data yang sering kita kirim/terima dengan API biasanya dalam bentuk JSON
- JSON (Javascript Object Notation) bentuknya mirip seperti object, tapi tiap propertinya menggunakan tanda kutip
```
//JSON 
{
    "name" : "arya"
    "age" : 20
}
```
- Async Await
  Async await merupakan salah satu cara untuk menangkap object promise.
  Cara mendeklarasikan Async Await
  ```
  //1
  async function nonton () {
    //code
  }
  //2
  let nonton = async ()=> {
    //code
  }
  ```
  - Error Handler pada Async Await
    ```
    async function nonton() {
        try {
            //code
        } catch {
            ///code
        }
    }
    ```
- Fetch merupakan object promise yang sudah disediakan oleh Javascript. Seperti pada object promise lain, Fetch dapat ditangkap menggunakan then & catch atau async await.  
```
// contoh fetch API menggunakan then
fetch (url)
.then (result => {
    return result.json() // unboxing data // membutuhkan waktu
})
.then (result => {
    console.log(result) // menampilkan data yang sudah diunboxing
})

// Contoh fetch API menggunakan async await
let getDataMovie = async (url) => {
  let response = await fetch(url); // menangkap object promise
  let movies = await response.json(); // unboxing data
  let data = movies.results; // menampilkan hasil
  // console.log(data);
  showData(data);
};
```
- json() merupakan method yang dimiliki oleh objek fetch
### Git & Github Lanjutan
Untuk dapat berkolaborasi dengan anggota kelompok menggunakan github, dapat dilakukan dengan cara:

1. Create organization repository di github
Jika ingin repository dapat diakses oleh tim, kita dapat memberikan akses kepada tim kita sehingga tim kita dapat melakukan push ke repository tersebut
2. Repository dibuat publik dan ceklis Readme
3. Buat branch bernama dev
   Dev sebagai branch development yang akan menyimpan setiap progress pada tahap development.
Setelah itu, masuk ke tahap collaborasi
4. Setiap anggota tim, melakukan clone terhadap repository
```
git clone (url)
```
5. Kemudian, tim membagi tugas kepada setiap anggota tim
6. Langkah selanjutnya, anggota tim membuat branch dari dev. nama branch disesuaikan. bisa menggunakan nama fitur ataupun yang lain
```
git switch dev
```
git switch digunakan untuk berpindah branch
setelah itu, buat branch di branch dev
```
git branch login
```
setelah itu, pindah branch lagi ke branch login
```
git switch login
```
7. Lakukan pengerjaan pada branch yang sudah dibuat
8. Jika sudah selesai, lakukan git commit
```
git add . 
git commit -m "message"
```
9. Sebelum di push, lakukan git merge dev untuk menghindari konflik 
10. jika aman, push branch ke github
```
git push -u origin (nama branch)
```
11. Lakukan pull request untuk merge ke branch dev
    Pull request adalah permintaan untuk menggabungkan antara branch yang sudah kita buat dengan branch yang lain

- Cara Update Repository di github ke local
  ```
  git pull
  ```
- Menggabungkan branch
    ```
    git merge (nama branch)
    ```
- Konflik
  Lebih dari 1 orang mengedit file yang sama
### Responsive Web Design
- Definisi
  Responsive Web Design membuat desain website kita dapat diakses pada device apapun
- Tools
- Viewport
  Viewport merupakan area website yang dapat diakses oleh user
  Cara menambahkan viewport di HTML
  ```
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```
  Viewport berguna untuk memberitahu browser untuk mengatur skala dan dimensi website
- Relative CSS Unit
  Menggunakan CSS unit / satuan ukur yang responsif karena ukurannya dapat berubah relatif terhadap parent atau layar
  ```
  em = relative terhadap ukuran font (2 em berarti 2x ukuran font yang telah dipakai)
  rem = relative terhadap ukuran font root element
  vw = relative terhadap 1% width dari viewport (100 vw = 100% width viewport)
  vh = relative terhadap 1% height dari viewport (100vh = 100% height viewport)
  % = relative terhadap parent element
  ```
  ```
  max-width:100%; // ukuran elemen 100% dari layar
  ```
- Media Query
  Media query digunakan untuk membuat beberapa style tergantung jenis device tertentu
  ```
  @media (max-width:500px) {
    // styling here
  }
  ```
- Flexbox & Grid
  CSS yang digunakan untuk membuat layouting website menjadi responsive.
   - Flexbox 
    Digunakan untuk layouting secara horizontal (baris)
    - Digunakan untuk layouting secara horizontal dan vertikal (baris dan kolom)
### Bootstrap 5
- Definisi
  Bootstrap merupakan framework CSS yang dapat membuat website dengan cepat dan juga sudah responsive. Selain bootstrap, terdapat framework lain seperti tailwind css.
- Install bootstrap with CDN
  ```
    // styling, diletakkan pada element head HTML
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Zenh87qX5JnK2Jl0vWa8Ck2rdkQ2Bzep5IDxbcnCeuOxjzrPF/et3URy9Bv1WTRi" crossorigin="anonymous">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-OERcA2EqjJCMA+/3y+gxIOqMEjwtxJY7qPCqsdltbNJuaOe923+mo//f6V8Qbsw3" crossorigin="anonymous"></script> 

    // Javascript
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.11.6/dist/umd/popper.min.js" integrity="sha384-oBqDVmMz9ATKxIep9tiCxS/Z9fNfEXiDAYTujMAeBAsjFuCZSmKbSSUnQlmh/jp3" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.min.js" integrity="sha384-IDwe1+LCz02ROU9k972gdyvl+AESN10+x7tBKgc9I5HFtuNz0wWnPclzo6p9vxnk" crossorigin="anonymous"></script>
  ```
- How to use Bootstrap
    Setelah kita menginstall bootstrap pada HTML kita, kita dapat menggunakan component serta content yang telah disediakan bootstrap. kita dapat menyalin source code yang telah disediakan ke file HTML kita.
- Grid System Bootstrap
  Digunakan untuk mengatur layout pada halaman web menggunakan bootstrap
  ```
     <section class="row">
        <div class="col">hello</div>
        <div class="col">hello</div>
        <div class="col">hello</div>
    </section>
        /// Output section akan terbagi menjadi 3 kolom
  ```
- Breakpoints
  Mengatur dimensi agar layout halaman kita responsive di berbagai tipe device
  ```
  sm : >=576px
  md : ≥768px
  lg : ≥992px
  xl : ≥1200px
  xxl : ≥1400px
  ```
- Contoh Website yang menggunakan bootstrap
  Website use Bootstrap [Lihat di sini](https://nonton-lah.netlify.app/)
