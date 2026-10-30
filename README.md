# Anima VTT

Mesa de juego virtual en el navegador para el juego de rol *Anima: Beyond Fantasy*. El Game Master (GM) y los jugadores comparten una sesión en tiempo real: mapa con tokens, dados con las reglas de Anima, fichas de personaje, combate por turnos y diario de campaña. Los jugadores no instalan nada.

<!-- ![Captura](docs/screenshot.png) -->

## Funcionalidades

- Mapa en canvas con cuadrícula, zoom, arrastre de tokens y niebla de guerra
- Dados abiertos de Anima (`/roll d100`, `/roll 2d6+3`, `/roll init`) y chat en vivo
- Fichas de personaje, combate con iniciativa y orden de turnos
- Varias escenas con fondo propio y diario con entradas privadas o públicas
- Permisos por rol (GM / jugador) y persistencia completa en SQLite

## Tecnologías

Java 17+ · Spring Boot 3 · WebSocket · SQLite · React 19 · TypeScript · Zustand · Vite · Tailwind CSS 4 · pnpm · Docker · Tauri

## Instalación

### Con Docker

```bash
docker compose up --build -d
```

Abre `http://localhost:1000`. Los datos y las imágenes subidas se guardan en volúmenes y persisten entre reinicios.

### En desarrollo

```bash
# Servidor (desde server/)
./mvnw spring-boot:run        # puerto 1000

# Cliente web (desde client/)
pnpm install
pnpm web                      # puerto 5173
```

Al primer arranque se crean datos de ejemplo. Usuarios de prueba: `gm / gm123` y `player1 / player123`.

### Jugar por internet (Windows)

Ejecuta `setup-tailscale.ps1` una vez como administrador y, en cada sesión, `start-gm.bat`. Genera una URL HTTPS estable con Tailscale Funnel para compartir con los jugadores.

## Documentación

La arquitectura, el protocolo WebSocket, el esquema de base de datos y las decisiones técnicas están en [`MEMOIRE_TECHNIQUE.md`](MEMOIRE_TECHNIQUE.md).

## Autor

Gonzalo Sanmar
