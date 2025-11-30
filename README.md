# Crypto App - Tugas 3 Pemrograman Berbasis Perangkat Bergerak

## Deskripsi

Crypto App adalah aplikasi sederhana untuk menampilkan harga cryptocurrency secara real-time menggunakan **framework Ionic dengan Vue.js**.
Aplikasi ini memanfaatkan **API Coinlore** untuk menampilkan data cryptocurrency populer termasuk **nama, rank, dan harga dalam USD**.

---

## Fitur

* Menampilkan 7 cryptocurrency teratas.
* Refresh data dengan tombol.
* Menampilkan loading spinner saat data sedang diambil.
* Tampilan responsif untuk perangkat mobile.

---

## Screenshot

<img width="1919" height="1079" alt="Screenshot 2025-11-30 224432" src="https://github.com/user-attachments/assets/bd991c15-1e7f-4df5-a666-1c7e8b592e6b" />


---

## Teknologi yang Digunakan

* **Framework:** Ionic Vue
* **Bahasa Pemrograman:** JavaScript, HTML, CSS
* **API:** [Coinlore API](https://www.coinlore.com/cryptocurrency-data-api)
* **State Management:** Vue Ref & Composition API

---

## Cara Menjalankan Aplikasi

1. **Clone repository**

```bash
git clone https://github.com/username/crypto-app.git
cd crypto-app
```

2. **Install dependencies**

```bash
npm install
```

3. **Jalankan aplikasi di browser**

```bash
ionic serve
```

4. **Build aplikasi (opsional)**

```bash
ionic build
```

---

## Struktur Project

```
crypto-app/
│
├─ src/
│  ├─ components/       # Komponen Vue
│  ├─ views/            # Halaman utama
│  ├─ App.vue
│  └─ main.js
│
├─ public/
├─ package.json
└─ README.md
```

---

## Cara Menggunakan

1. Buka aplikasi di browser / perangkat mobile.
2. Klik tombol **Refresh** untuk mengambil data terbaru.
3. Lihat daftar cryptocurrency dengan **rank, nama, dan harga USD**.

---

## Referensi

* [Ionic Vue Documentation](https://ionicframework.com/docs/vue/overview)
* [Coinlore API](https://www.coinlore.com/cryptocurrency-data-api)


