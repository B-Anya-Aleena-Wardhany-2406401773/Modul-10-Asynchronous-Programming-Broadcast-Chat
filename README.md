# Reflection

Anya Aleena Wardhany

2406401773

## Experiment 2.1: Original Code, and How It Run

![Experiment 2.1](images/01.png)

### Cara menjalankan

Buka 4 terminal terpisah, lalu jalankan:

Term 1:

```
cargo run --bin server
```

Term 2, 3, 4:

```
cargo run --bin client
```


Ketika satu client mengetik pesan, server menerima pesan tersebut lalu mem-broadcast ke semua client yang sedang terhubung. Terlihat pada screenshot, ketika client pertama mengetik "anya", pesan tersebut diterima oleh semua client lain dalam format
`127.0.0.1:56950: anya` yaitu IP:Port pengirim diikuti isi pesannya.


Server menggunakan `tokio::broadcast channel` untuk mendistribusikan pesan ke semuasubscriber. Setiap client yang connect akan subscribe ke channel yang sama, sehingga setiap pesan yang masuk akan diterima oleh semua client secara asynchronous.