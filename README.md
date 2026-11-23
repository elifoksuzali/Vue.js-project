# Vue Axios — HTTP İstek Örnekleri

**Vue.js 2** ve **Axios** kullanarak farklı HTTP istek yöntemlerini (GET / POST, `then/catch`
ve `async/await`, global axios örneği) uygulamalı gösteren bir öğrenme / staj projesidir.
Proje **Vue CLI** ile oluşturulmuştur ve sayfalar arası geçiş için **Vue Router** kullanır.

---

## 🎯 Amaç

Axios ile bir REST API'ye nasıl istek atılacağını farklı yaklaşımlarla göstermek:

- `GET` ile veri çekme (ülke listesi)
- `POST` ile veri gönderme
- `Promise` (`.then/.catch`) ve `async/await` sözdizimlerinin karşılaştırılması
- Tüm uygulamada ortak kullanılan **global axios örneği** (`baseURL`, interceptor'lar)

Kullanılan açık demo API'ler:
- `https://restcountries.eu/rest/v2/all` — ülke bilgileri
- `https://jsonplaceholder.typicode.com` — örnek gönderi (post) verisi

---

## 🧩 Ekranlar (Router)

| Yol (route) | Bileşen | Açıklama |
|-------------|---------|----------|
| `/axios-get` | `AxiosGet.vue` | GET + `then/catch` ile ülke tablosu |
| `/axios-get-async-await` | `AxiosGetAsyncAwait.vue` | Aynı GET isteği `async/await` ile |
| `/axios-post` | `AxiosPost.vue` | POST + `then/catch` ile yeni kayıt |
| `/axios-post-async-await` | `AxiosPostAsyncAwait.vue` | POST isteği `async/await` ile |
| `/axios-global` | `AxiosGlobal.vue` | Global axios örneği (`this.$axios`) ile GET |

---

## 📁 Proje Yapısı

```
.
├── public/
│   ├── index.html        # HTML şablonu (Bootstrap + #app)
│   ├── bootstrap.css
│   └── favicon.ico
├── src/
│   ├── main.js           # Uygulama girişi; global axios örneği + interceptor
│   ├── App.vue           # Ana düzen + router menüsü
│   ├── router/
│   │   └── index.js       # Vue Router tanımları
│   ├── views/            # Her route'a karşılık gelen sayfalar
│   │   ├── AxiosGet.vue
│   │   ├── AxiosGetAsyncAwait.vue
│   │   ├── AxiosPost.vue
│   │   ├── AxiosPostAsyncAwait.vue
│   │   └── AxiosGlobal.vue
│   ├── components/
│   │   └── Home.vue       # Varsayılan karşılama bileşeni
│   └── assets/
│       └── logo.png
├── package.json
├── babel.config.js
├── .eslintrc.js
├── .gitignore
└── README.md
```

---

## 🛠️ Gereksinimler

- **Node.js** (14+ önerilir) ve **npm**
- Global bir Vue CLI kurulumu gerekmez; komutlar `package.json` scriptleri üzerinden çalışır.

---

## 🚀 Kurulum ve Çalıştırma

```bash
# 1) Bağımlılıkları yükle
npm install

# 2) Geliştirme sunucusunu başlat (hot-reload)
npm run serve

# 3) Üretim için derle
npm run build

# 4) Kod denetimi (lint)
npm run lint
```

`npm run serve` sonrası uygulama genellikle `http://localhost:8080` adresinde açılır.
