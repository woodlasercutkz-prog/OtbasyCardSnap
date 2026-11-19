# Otbasy CardSnap (Android, Capacitor)

Фото товара → карточка (название, описание, характеристики, цена в ₸) → экспорт JSON для «Импорт из CardSnap» в Otbasy Market.
Приложение работает локально: данные хранятся на телефоне (localStorage), без своего сервера.

## Сборка APK через GitHub (без Android Studio)
1. Создайте репозиторий, загрузите все файлы из этой папки (включая `.github/`).
2. Вкладка Actions → «Build APK» → Run workflow (или просто push в `main`).
3. Через ~5–8 минут скачайте артефакт `otbasy-cardsnap-apk` → внутри `app-debug.apk`. Установите на телефон (разрешите установку из неизвестных источников).

## Сборка локально
`npm install && npx cap add android && npx cap sync android && npx cap open android` — затем Build → Build APK(s). Для камеры добавьте в AndroidManifest.xml `<uses-permission android:name="android.permission.CAMERA" />`.

## Распознавание
В «⚙ Настройки» вставьте API-ключ Anthropic. Фото отправляется в Anthropic только по кнопке «Распознать». Включённый поиск в интернете подтягивает рыночные цены (дороже и медленнее). Без ключа карточки заполняются вручную.
