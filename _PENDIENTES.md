# Pendientes

## Fase 1 — Arranque personal (hazlo ahora)

- [ ] Crear el repositorio en GitHub
  - Nombre: `genealogia-historica-mexico`
  - Visibilidad: **Privado**
  - No inicializar con README (ya tenemos uno)

- [ ] Instalar Git en tu computadora si no lo tienes
  - Verificar con: `git --version`
  - Descargar en: https://git-scm.com

- [ ] Clonar el repositorio localmente
  ```bash
  git clone https://github.com/tu-usuario/genealogia-historica-mexico.git
  ```

- [ ] Subir los archivos de este ZIP al repositorio
  ```bash
  git add .
  git commit -m "estructura inicial del repositorio"
  git push
  ```

- [ ] Migrar el CSV de Naolinco al nuevo formato (plantilla_matrimonios.csv)

- [ ] Llenar el `config.yml` de Naolinco con los datos del rollo

- [ ] Empezar a capturar Izúcar de Matamoros en LibreOffice Calc

---

## Fase 2 — Cuando lleguen colaboradores externos (hazlo después)

Solo necesitas esto si alguien quiere colaborar pero no sabe usar Git.

- [ ] Crear un Google Sheet por colección con los mismos encabezados del CSV
- [ ] Crear proyecto en Google Cloud Console (https://console.cloud.google.com)
- [ ] Activar Google Sheets API y Google Drive API
- [ ] Crear cuenta de servicio y descargar credenciales JSON
- [ ] Compartir cada Sheet con el email de la cuenta de servicio
- [ ] Agregar secretos en GitHub (Settings → Secrets → Actions):
  - `GOOGLE_CREDENTIALS` — contenido del JSON de credenciales
  - `SHEET_ID_NAOLINCO` — ID del Sheet de Naolinco
  - `SHEET_ID_IZUCAR` — ID del Sheet de Izúcar
- [ ] Activar el workflow en la pestaña Actions de GitHub
- [ ] Hacer prueba manual: agregar fila en Sheet → verificar que aparece en GitHub

---

**Nota:** Cuando llegues a la Fase 2, avisa y se puede retomar paso a paso.
