# PrepIA (InterviewPrep AI) — Android (Kotlin + Jetpack Compose)

Simulador de entrevistas técnicas y blandas con IA. Programación para Dispositivos Nativos · Universidad de Cundinamarca.

## Abrir y correr
1. Android Studio (Koala o superior) → **Open** → carpeta `PrepIA`.
2. Espera el **Gradle Sync** y pulsa **Run ▶** (Android 7.0+ / API 24+).

## Activar la IA (Gemini)
1. Consigue una API key en https://aistudio.google.com/apikey
2. En la app: **Perfil → Inteligencia artificial** → pega la key → *Guardar configuración*.
3. Modelo por defecto: `gemini-3.5-flash-lite` (editable en el mismo formulario).

Si no hay key, no hay internet o la API falla, la app usa automáticamente el **evaluador local** (`Evaluator.kt`) y lo avisa en pantalla.

## Funcionalidades
| Funcionalidad | Dónde |
|---|---|
| Registro / login (SQLite, hash SHA-256) | `AuthScreen`, `Db.kt` |
| Perfil técnico + tipo de entrevista | `HomeScreen` |
| Entrevista tipo chat: pregunta por voz (TTS), respuesta por voz o texto | `InterviewScreen` |
| Evaluación con IA real (puntaje, fortalezas, mejoras, respuesta modelo, pregunta de seguimiento) | `Ai.kt` |
| Evaluación local de respaldo (offline) | `Evaluator.kt` |
| Reporte final con anillo de puntaje y detalle por pregunta | `ReportScreen` |
| Historial y gráfico de evolución | `HistoryScreen` |
| Guía offline: conceptos, preguntas por perfil, guardadas | `GuideScreen` |
| Notificación diaria "pregunta del día" (WorkManager) | `Notifs.kt` |
| Tema claro/oscuro automático | `Theme.kt` |

## Nota de seguridad
La API key se guarda en el dispositivo (SharedPreferences) y nunca va en el código ni en el repositorio.
