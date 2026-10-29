# Laboratorio Paradigmas (UNA Chat)

Last updated: 2026-10-28

## Clone

- Path: `Repos/Laboratorio_Paradigmas/` (gitignored by workspace; own Git remote `origin`).
- Remote: https://github.com/DavidMA17-04/Laboratorio_Paradigmas

## Layout

- `antes/` — baseline UNA Chat (Lab 5 reference).
- `despues/` — evolved app with tests and OpenSpec.

## OpenSpec

- Root: `Repos/Laboratorio_Paradigmas/despues/openspec/`
- Use `/opsx-propose` and `/opsx-apply` for functional changes in `despues/`.

## Lab 6 constraints (course)

- Software-factory **harness (consigna punto 3)** omitted by instructor — not configured in this workspace.
- Do not modify UNA Chat or install dependencies unless a later lab step asks for it.

## Auth0 (implementado, 2026-10-28)

- Change OpenSpec: `integracion-auth0` (apply completado).
- JWT: `express-oauth2-jwt-bearer` en handshake Socket.IO; `nombre` desde claims (`name` → `nickname` → `sub`).
- Cliente: Auth0 SPA SDK; `/auth-config`; e2e usa `/?testAuth=1` + tokens RS256 de prueba (`NODE_ENV=test`).
- Pruebas: `npm test` 31 OK; `npm run test:integration` 7 OK; Playwright 4 OK.
- Login real: crear `.env` con `AUTH0_CLIENT_ID` del dashboard UNA-chat.
- Fix 2026-10-28: el CDN `cdn.auth0.com` no cargaba el SDK (403) → `auth0 is not defined`. SDK servido desde `@auth0/auth0-spa-js` en `/vendor/auth0/auth0-spa-js.production.js`.
- Fix post-login: `getTokenSilently()` debe pedir `audience` de la API; sin access token válido el socket falla JWT y la UI mostraba «No autenticado». Logout unificado con botón «Cerrar sesión».
- Fix socket: `express-oauth2-jwt-bearer` en Socket.IO necesita `socket.request` (Host válido); stub mínimo → `Invalid Host header` → `connect_error`.
