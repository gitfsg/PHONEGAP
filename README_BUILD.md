# Guía de Compilación para Play Store - Lectura Productos

Ya he corregido y validado los archivos de tu proyecto ("HealthScan - Lectura Productos"). 

Debido a que para generar un archivo `.apk` o `.aab` (el formato que pide Google Play ahora) se requiere tener instalado **Java JDK 17+** y el **Android SDK**, aquí tienes los pasos finales para terminar el proceso en tu equipo:

## 1. Requisitos previos
Asegúrate de tener instalados:
- **Node.js y npm**
- **Java JDK 17** (o superior)
- **Android Studio** (con el SDK Command-line Tools instalado)

## 2. Comandos para generar el APK
Abre una terminal en la carpeta del proyecto y ejecuta:

```powershell
# 1. Instalar cordova si no lo tienes
npm install -g cordova

# 2. Añadir la plataforma android (ya lo he preparado, pero si falla haz esto)
cordova platform remove android
cordova platform add android

# 3. Compilar para producción (genera un .aab o .apk sin firmar)
cordova build android --release
```

## 3. Ubicación del archivo generado
Una vez ejecutado el comando `build`, encontrarás tu archivo en:
`platforms/android/app/build/outputs/bundle/release/app-release.aab`
(Este es el archivo que se sube a Google Play Console).

## 4. Firma de la App (Obligatorio para el Play Store)
Google requiere que la app esté firmada. Si es la primera vez que la subes, Google Play Console te guiará para usar su sistema de "Play App Signing".

---
He validado:
- [x] **Config.xml:** Nombre e ID de la app corregidos (`com.calidadproducto.lectura`).
- [x] **Manifest.json:** Movido a la carpeta correcta.
- [x] **Permisos:** Cámara y escritura añadidos para Android.
- [x] **Estructura:** Archivos de lógica (`app.js`, `camera.js`) revisados.

¡Tu proyecto está listo para ser compilado y subido!
