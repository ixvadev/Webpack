# Webpack haqida to'liq ma'lumot

## Webpack nima?
**Webpack** - bu ochiq kodli modul to'plovchi (bundler) bo'lib, asosan JavaScript ilovalarini yig'ish uchun ishlatiladi. Webpack kodni kichik modullarga bo'lib, ularni yagona to'plamga (bundle) birlashtirish imkonini beradi. Bu jarayon sizning ilovangizni optimallashtiradi va yuklash vaqtini qisqartiradi.

## Webpack qanday ishlaydi?
Webpack barcha kirish (entry) nuqtalarini belgilab, barcha bog'langan fayllarni (JS, CSS, tasvirlar va boshqalar) analiz qiladi. Har bir faylni o'zining modul tizimiga o'rab, bir yoki bir nechta chiqish (output) fayllariga yig'adi. Ushbu chiqish fayllar brauzer tomonidan ishlatiladi.

## Asosiy tushunchalar

### 1. Entry (Kirish nuqtasi)
Entry nuqtasi - bu Webpack'ning yig'ishni boshlaydigan fayli. Odatda, bu ilovaning bosh fayli hisoblanadi.

```javascript
module.exports = {
  entry: './src/index.js',
};
