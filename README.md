<img class="logo" src="https://webpack.js.org/site-logo.c0e60df418e04f58.svg" alt="webpack logo" width="300" height="200">

# Webpack haqida to'liq ma'lumot

## Webpack nima?
**Webpack** - bu ochiq kodli modul to'plovchi (bundler) bo'lib, asosan JavaScript ilovalarini yig'ish uchun ishlatiladi. Webpack kodni kichik modullarga bo'lib, ularni yagona to'plamga (bundle) birlashtirish imkonini beradi. Bu jarayon sizning ilovangizni optimallashtiradi va yuklash vaqtini qisqartiradi.

## Webpack qanday ishlaydi?
Webpack barcha kirish (entry) nuqtalarini belgilab, barcha bog'langan fayllarni (JS, CSS, tasvirlar va boshqalar) analiz qiladi. Har bir faylni o'zining modul tizimiga o'rab, bir yoki bir nechta chiqish (output) fayllariga yig'adi. Ushbu chiqish fayllar brauzer tomonidan ishlatiladi.

## Asosiy tushunchalar

### 1. Entry (Kirish nuqtasi)
Entry nuqtasi - bu Webpack'ning yig'ishni boshlaydigan fayli. Odatda, bu ilovaning bosh fayli hisoblanadi.

    module.exports = {
      entry: './src/index.js',
    };

### 2. Output (Chiqish)
Output - bu Webpack tomonidan yaratilgan to'plamning qayerga yozilishini belgilaydi. Odatda dist katalogiga yoziladi.

    module.exports = {
      entry: './src/index.js',
      output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist'),
      },
    };
### 3. Loaders (Yuklovchilar)
Loaders Webpack'ga JavaScript bo'lmagan fayllarni (masalan, CSS, tasvirlar) ishlash imkonini beradi. Ular fayllarni o'zgartirib, ularni Webpack'ning modul tizimiga kiritadi.

    module.exports = {
      module: {
        rules: [
          {
            test: /\.css$/,
            use: ['style-loader', 'css-loader'],
          },
        ],
      },
    };


### 4. Plugins (Plaginlar)
Plaginlar Webpack'ning imkoniyatlarini kengaytiradi va yig'ish jarayonining turli bosqichlarida qo'shimcha vazifalarni bajaradi. Masalan, fayllarni minifikatsiya qilish yoki o'zgarishlarni avtomatik aniqlash (HMR).

    const HtmlWebpackPlugin = require('html-webpack-plugin');
    module.exports = {
      plugins: [
        new HtmlWebpackPlugin({
          template: './src/index.html',
        }),
      ],
    };

### 5. Mode (Rejim)
Webpack ikkita asosiy rejimga ega: development va production. Har bir rejim ma'lum konfiguratsiyalarga ega, masalan, production rejimi optimallashtirishni o'z ichiga oladi.
    
    module.exports = {
      mode: 'development',
    };

### Webpack konfiguratsiyasi
Webpack odatda webpack.config.js fayli orqali konfiguratsiya qilinadi. Bu fayl Webpack'ga qanday kirish nuqtalarini ishlatish, qanday yuklovchilar va plaginlar qo'llash kerakligini aytadi.

    const path = require('path');
    const HtmlWebpackPlugin = require('html-webpack-plugin');
    
    module.exports = {
      mode: 'development',
      entry: './src/index.js',
      output: {
        filename: 'bundle.js',
        path: path.resolve(__dirname, 'dist'),
      },
      module: {
        rules: [
          {
            test: /\.css$/,
            use: ['style-loader', 'css-loader'],
          },
        ],
      },
      plugins: [
        new HtmlWebpackPlugin({
          template: './src/index.html',
        }),
      ],
    };




