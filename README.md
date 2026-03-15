## CRYPDOLFIN — Portfolio & Growth Studio

Tek sayfalık, servis odaklı bir portföy sitesi.  
Stack:

- HTML + CSS (custom tasarım, neon/glassmorphism)
- Vanilla JS (`script.js`) ile etkileşimler
- Firebase Web SDK ile Analytics + (isteğe göre) Hosting

### Geliştirme

Projeyi yerelde açmak için:

```bash
git clone https://github.com/dolphinay1/crypdolfin.git
cd crypdolfin
# Basitçe bir static server ile çalıştırabilirsiniz
npx serve .
```

Ana dosyalar:

- `index.html` – sayfa iskeleti ve Firebase init script'i
- `styles.css` – tema, bento grid, istatistikler, responsive kurallar
- `script.js` – animasyonlar, modallar, ROI hesaplayıcı, etkileşimler

### Firebase Analytics & Event Tracking

`index.html` altında Firebase Web SDK yüklü ve Analytics başlatılmıştır.  
`script.js` içerisindeki event handler'lar, global `window.crypLogEvent` fonksiyonu üzerinden aşağıdaki gibi log atar:

- Hero CTA tıklamaları (paketler / iletişim)
- WhatsApp FAB tıklaması
- İletişim kartları (Mail, X, Telegram, Instagram)

### Firebase Hosting ile Yayınlama

1. Firebase CLI yükle:

```bash
npm install -g firebase-tools
firebase login
```

2. Proje klasörü içinde Hosting'i başlat:

```bash
cd crypdolfin
firebase init hosting
```

- **Use an existing project?**: `crypdolfin-59d35`
- **Public directory**: `.` (tek sayfa kök dizinde)
- **Configure as a single-page app (rewrite all urls to /index.html)?**: `Yes`
- **Set up automatic builds and deploys with GitHub?**: İstersen sonra

3. Deploy:

```bash
firebase deploy --only hosting
```

Komut tamamlandığında Firebase sana canlı bir URL verecektir; istersen kendi domain'ini de Firebase Hosting'e bağlayabilirsin.

