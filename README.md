# proxys4yall

¡Bienvenido al repositorio **proxys4yall**! Este proyecto mantiene una lista pública de proxys HTTP(S) y SOCKS5 que se renueva automáticamente en GitHub. Úsalo para pruebas, desarrollo u otras herramientas de red.

---

## 📋 Contenido

1. [Descripción](#descripción)
2. [Cómo usar](#cómo-usar)
3. [Formato de la lista](#formato-de-la-lista)
4. [Actualización automática](#actualización-automática)
5. [Contribuciones](#contribuciones)
6. [Historial de cambios](#historial-de-cambios)
7. [Licencia](#licencia)
8. [Contacto](#contacto)

---

## 📝 Descripción

El repositorio **proxys4yall** contiene una colección de proxys públicos (HTTP, HTTPS y SOCKS5) que se validan y renuevan cada cierto tiempo. El objetivo es ofrecer una fuente centralizada y siempre actualizada para desarrolladores, testers y entusiastas de la seguridad.

---

## 📂 Cómo usar

1. **Clona el repositorio**:
   ```bash
   git clone https://github.com/alucinacion/proxys4yall.git
   cd proxys4yall
   ```

2. **Descarga la lista raw**:
   ```bash
   curl -s https://raw.githubusercontent.com/alucinacion/proxys4yall/main/proxys.txt -o proxys.txt
   ```

3. **Integrar en tu script**:
   ```bash
   # Ejemplo en Bash
   while read proxy; do
     curl -x "$proxy" https://example.com
   done < proxys.txt
   ```

4. **Filtrar por tipo** (HTTP, HTTPS, SOCKS5):
   ```bash
   grep "^HTTP" proxys.txt     # Sólo proxys HTTP
   grep "SOCKS5" proxys.txt    # Sólo proxys SOCKS5
   ```

---

## 🔧 Formato de la lista

Cada línea de `proxys.txt` sigue el formato:

```
<TIPO>://<IP>:<PUERTO>
```

- **TIPO**: HTTP, HTTPS o SOCKS5
- **IP**: Dirección IPv4 o IPv6
- **PUERTO**: Puerto de conexión

**Ejemplo**:
```
HTTP://203.0.113.45:8080
HTTPS://198.51.100.23:443
SOCKS5://192.0.2.10:1080
```

---

## ⏱️ Actualización automática

La lista se renueva cada 6 horas mediante un **GitHub Actions** que:

1. Descarga proxies desde varias fuentes públicas.
2. Valida la disponibilidad de cada proxy.
3. Genera un nuevo archivo `proxys.txt`.
4. Abre un pull request automático si hay cambios.
5. Fusiona el PR tras pasar las comprobaciones.

Revisa el flujo de trabajo en `.github/workflows/update.yml`.

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Puedes:

- **Reportar** proxys que fallen o enlaces rotos (abre un issue).
- **Sugerir** nuevas fuentes de proxys en un issue.
- **Enviar PR** con mejoras en el script o filtros.

Al enviar un PR, asegúrate de:

- Seguir el formato de `proxys.txt`.
- Añadir tu nombre y perfil si realizas contribuciones significativas.

---


## 📬 Contacto

- **Autor**: alucinacion ([@alucinacion](https://github.com/alucinacion))

¡Gracias por usar **proxys4yall**! 🚀
