# Pastillero de Mascotas

Medicamentos de tus mascotas: recordatorios, stock y consejos.

## Descargar

- **Android:** en la pestaña **Releases** de este repositorio, bajá `Pastillero.apk` y abrilo en el teléfono. Si Android lo pide, permití instalar apps de esta fuente.
- **iPhone:** abrí la dirección de GitHub Pages del repositorio en **Safari**, tocá **Compartir → Agregar a pantalla de inicio**.

Cada vez que se sube un cambio a `main`, GitHub compila un APK nuevo y actualiza la versión web.

## Estructura

- `www/` — la app (un solo HTML), el manifiesto y el modo sin conexión.
- `android-res/` — íconos de la app y de las notificaciones para Android.
- `capacitor.config.json` — configuración de Capacitor (`py.oddone.pastillero`).
- `.github/workflows/android.yml` — compila el APK y lo publica en Releases.
- `.github/workflows/web.yml` — publica `www/` en GitHub Pages.

## Alarmas

En Android las alarmas se programan en el teléfono con `@capacitor/local-notifications`: suenan con la app cerrada y sin internet, tienen los botones “Ya se la di” y “+15 min”, y repiten a los 30 minutos si la toma sigue pendiente. En iPhone (versión web) los avisos no suenan con la app cerrada.

## Desarrollo local

```bash
npm ci
npx cap add android
npx cap sync android
npx cap open android
```
