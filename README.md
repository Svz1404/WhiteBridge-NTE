# WhiteBridge Dapp Bot

Script Node.js untuk generate wallet Ethereum (via `ethers.js`), melakukan proses nonce → sign → signin → claim referral, serta menyimpan wallet ke file `wallets.json`.
Output diformat dengan **cfonts** dan **ora** agar lebih rapi.

---

## 🚀 Fitur

* Generate wallet baru secara otomatis (alamat, private key, mnemonic).
* Simpan semua wallet ke file `wallets.json`.
* Flow otomatis:

  1. Request nonce.
  2. Sign message.
  3. Signin ke API.
  4. Claim referral code.
* CLI interaktif: input jumlah loop & referral code.
* Tampilan CLI lebih cantik (spinner + font banner).

---

## 📦 Installation

### 1. Clone project

```bash
git clone https://github.com/Svz1404/WhiteBridge-NTE.git
cd WhiteBridge-NTE
```

### 2. Install dependencies

Gunakan versi **stabil** dari library:

```bash
npm install ethers@5.7.2 node-fetch@2 ora@5.4.1 cfonts
```

Kenapa versi ini?

* `ethers@5.7.2` → stabil, CommonJS.
* `node-fetch@2` → masih mendukung `require()`.
* `ora@5.4.1` → versi terakhir yang mendukung `require()`.
* `cfonts` → untuk banner teks di CLI.

---

## ▶️ Usage

Jalankan script dengan:

```bash
node index.js
```

Kemudian input:

* **How many loop?** → jumlah wallet yang ingin digenerate.
* **Referral code** → masukkan referral code (default: `SecNsrxX`).

---

## 📂 Output

* Semua wallet yang dibuat akan tersimpan di file:

  ```
  wallets.json
  ```

Format contoh:

```json
[
  {
    "address": "0x1234abcd...",
    "privateKey": "0xabc123...",
    "mnemonic": "seed phrase here",
    "createdAt": "2025-10-05T09:00:00.000Z"
  }
]
```

---

## ⚠️ Notes

* Gunakan Node.js versi **≥16** (direkomendasikan v18 atau v20).
* Jika ada error `ERR_REQUIRE_ESM` pada `ora`, pastikan install `ora@5.4.1`.
* Jangan share `wallets.json` ke orang lain, karena berisi private key.

---

## 📜 License

MIT License. Bebas digunakan untuk belajar & eksperimen.
