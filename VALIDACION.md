# Validación de Cupcake

Fecha: 29 de octubre de 2026 (America/Guayaquil).

## Compilación y análisis

- JDK 21, Gradle 8.12, Android Gradle Plugin 8.8.0 y compileSdk 35.
- `assembleDebug assembleDebugAndroidTest lintDebug`: BUILD SUCCESSFUL.
- Lint: 0 errores y 18 advertencias (incluye recomendaciones de actualización y recursos del ejemplo oficial).
- APK: `app/build/outputs/apk/debug/app-debug.apk`.
- 16 pruebas de interfaz compiladas: 11 de navegación y 5 de contenido/acciones.

## Pruebas instrumentadas: ejecución parcial

Dispositivo autorizado: Redmi Note 9 Pro, Android 12, idioma es-US.
Se ejecutó `connectedDebugAndroidTest`. El progreso llegó a:

```text
Starting 16 tests on Redmi Note 9 Pro - 12
Redmi Note 9 Pro - 12 Tests 5/16 completed. (0 skipped) (0 failed)
Redmi Note 9 Pro - 12 Tests 7/16 completed. (0 skipped) (0 failed)
```

Después la ejecución dejó de avanzar. Logcat mostró `MIUILOG- Permission Denied Activity` para `com.example.cupcake/androidx.activity.ComponentActivity`, la actividad usada por las pruebas del codelab. Se interrumpió la ejecución; las 9 pruebas restantes no tienen resultado confirmado. No se afirma que la suite completa haya pasado. Se recomienda repetirla en un emulador Android sin esta restricción de MIUI.

## Verificación manual en el teléfono

- Instalación y apertura de MainActivity correctas.
- Inicio con las cantidades 1, 6 y 12 visibles.
- Pedido de 6 cupcakes, sabor Chocolate: subtotal $12.00.
- Retiro para hoy: subtotal $15.00, incluido el recargo de $3.
- Resumen con cantidad, sabor y fecha correctos.
- Apertura del selector de Android para compartir, sin enviar mensajes a otra aplicación.
- Navegación hacia atrás y cambio de fecha al día siguiente: subtotal vuelve a $12.00.
- Cancelación desde el resumen: regreso al inicio.
- Nuevo pedido de 1 cupcake: subtotal $2.00, sin el recargo del pedido anterior.
