Muhammad Rizky Febrianto | 2409116045
# Web Portofolio
Website dirancang dengan konsep modern minimal portfolio, responsif pada perangkat Desktop maupun Mobile, serta menggunakan pendekatan component-based dengan Vue JS.

## **Tampilan** dan **penjelasan kode** setiap section
### Navbar & Hero Section
<table>
  <tr>
    <th>Tampilan Desktop</th>
    <th>Tampilan Mobile</th>
  </tr>
  <tr>
    <td><img width="1895" height="884" alt="image" src="https://github.com/user-attachments/assets/82024fac-7077-42dd-bed8-f2261a9eb376" /></td>
    <td>
      <img width="347" height="327" alt="image" src="https://github.com/user-attachments/assets/0031d029-8e49-4eec-822e-e572a397caa1" />
      <img width="348" height="325" alt="image" src="https://github.com/user-attachments/assets/cbb5b8f2-f80a-4437-be99-1e0915177d7e" />
    </td>
  </tr>
</table>

**1. Navbar**

Navbar berada pada bagian atas website dan bersifat sticky sehingga tetap terlihat saat halaman di-scroll.

Fitur:
- Logo brand KYFE
- Navigasi ke:
  - Home
  - About Me
  - Certificates
- Hamburger menu untuk tampilan mobile
- Dropdown navigation pada perangkat kecil

Navbar dibuat menggunakan kombinasi:
- HTML Flexbox Layout
- CSS Fixed Position
- JavaScript Event Listener

Konsep utama:
`<nav class="sticky-nav">`
Navbar menggunakan:
```
position: fixed;
top: 0;
```
Agar selalu berada di atas halaman. Hamburger menu dikontrol menggunakan: `navDropdown.classList.toggle('open');`

---

**2. Hero**

Hero section merupakan tampilan pertama yang dilihat pengguna.
Elemen utama:
- Nama lengkap pengguna
- Judul besar PORTFOLIO
- Foto profil di tengah (overlapping layout)
- Background pattern grayscale
- Tombol Get Started
- Subtitle profesi

Hero menggunakan struktur layered layout:
- Background Layer
- Typography Layer
- Image Overlay
- Action Button
Foto profil diposisikan menggunakan:
```
position: absolute;
transform: translateX(-50%);
```
Sehingga foto dapat overlap dengan teks PORTFOLIO.

Vue digunakan untuk data dinamis: `{{ subLabel }}`

---

### About Me Section

<table>
  <tr>
    <th>Tampilan Desktop</th>
    <th>Tampilan Mobile</th>
  </tr>
  <tr>
    <td>
      <img width="1891" height="881" alt="image" src="https://github.com/user-attachments/assets/b53f948d-c393-4edf-9e3a-14101da16c87" />
      <img width="1898" height="883" alt="image" src="https://github.com/user-attachments/assets/fad0f995-5176-48e7-84fc-07cd1a3dc316" />
    </td>
    <td>
      <img width="350" height="665" alt="image" src="https://github.com/user-attachments/assets/1e8b82cf-50cd-4bb0-ab77-2fc672e2eb43" />
      <img width="349" height="675" alt="image" src="https://github.com/user-attachments/assets/8ab25108-551b-4f94-b062-bb5d0f7e09c1" />
      <img width="347" height="672" alt="image" src="https://github.com/user-attachments/assets/24624d3b-c886-4a12-b270-79577045ac96" />
    </td>
  </tr>
</table>

**3. About Me**

Section ini menampilkan informasi pribadi serta latar belakang pengguna.
Isi utama:
- Foto profil
- Deskripsi singkat mahasiswa
- Daftar pengalaman organisasi & kepanitiaan
- Progress bar kemampuan (Skills)

Fitur visual:
- Timeline experience
- Animated skill bar
- Dark theme section

Section ini menggunakan sistem Bootstrap Grid: `<div class="row">`

**Experience**

- Data pengalaman berasal dari Vue data: `experiences: []`
- Kemudian ditampilkan menggunakan: `v-for="exp in experiences"`

**Skills**

- Progress bar dibuat dinamis: `:style="{ width: skill.pct + '%' }"`
- Nilai persentase langsung mengatur panjang bar skill.

---

### Certificates & Footer Section

<table>
  <tr>
    <th>Tampilan Desktop</th>
    <th>Tampilan Mobile</th>
  </tr>
  <tr>
    <td>
      <img width="1896" height="891" alt="image" src="https://github.com/user-attachments/assets/8615f3ec-b517-46a4-8b2a-82cd1232116f" />
      <img width="1898" height="884" alt="image" src="https://github.com/user-attachments/assets/1d40941c-4a20-49e3-8dcc-e8344fe32770" />
    </td>
    <td>
      <img width="347" height="679" alt="image" src="https://github.com/user-attachments/assets/df19880c-d46d-4663-991f-f578338b079c" />
      <img width="349" height="672" alt="image" src="https://github.com/user-attachments/assets/d764c757-9eed-4c6a-9aa3-4286d49fb8e3" />
    </td>
  </tr>
</table>

**5. Certificates**

Section untuk menampilkan sertifikat yang telah diperoleh.

Fitur:
- Card layout sertifikat
- Hover overlay
- Tombol preview sertifikat
- Grid responsive (Desktop & Mobile)
- Pengguna dapat membuka sertifikat secara langsung melalui tombol Lihat →.

Pada section ini card sertifikat dibuat secara reusable menggunakan Vue Loop:

```v-for="cert in certificates"```

Lalu dilengkapi juga dengan Hover effect menggunakan:
```
.cert-overlay {
  opacity: 0;
}
.cert-card:hover .cert-overlay {
  opacity: 1;
}
```
Sehingga tombol muncul saat hover.

---

**6. Footer**

Bagian akhir website yang berisi:
- Brand website
- Copyright otomatis
- Teknologi yang digunakan

Footer menggunakan data Vue untuk tahun otomatis:
```currentYear: new Date().getFullYear()```

Sehingga tidak perlu update manual setiap tahun.

## Teknologi yang digunakan
- `HTML5` = Struktur halaman website
- `CSS3` =	Styling & Layout
- `Bootstrap 5` =	Grid system & responsive layout
- `Vue JS 3`	= Reactive data & rendering
- `JavaScript`	= Interaksi UI
- `Google Fonts` =	Typography
- `Responsive Design` =	Tampilan multi-device
