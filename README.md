# 🔧 Sistema de Préstamo de Herramientas Comunitario

Aplicación de consola en **Python** para que la junta comunal de un barrio controle las herramientas que los vecinos se prestan entre sí: qué herramientas hay, quién las tiene, cuándo deben devolverse y cuáles se piden más.

La información se guarda en archivos **JSON**, y cada evento importante (préstamos, errores, cambios) queda registrado en un archivo de logs.

---

## ✨ Funcionalidades

**Roles con permisos distintos**

| Rol | Qué puede hacer |
|---|---|
| **Residente** | Ver herramientas disponibles, solicitar una herramienta y devolverla |
| **Administrador** | Gestionar usuarios y herramientas (CRUD), aprobar préstamos pendientes, ver reportes y logs |

**Gestión de préstamos**
- Verifica la disponibilidad antes de prestar y descuenta del stock.
- Al devolver la herramienta, actualiza el estado del préstamo y restaura la cantidad.
- Las solicitudes quedan en espera hasta que el administrador las aprueba.

**Reportes**
- Herramientas con stock bajo
- Préstamos activos y vencidos
- Historial de préstamos de un usuario
- Herramientas más solicitadas
- Usuarios más activos

**Registro de eventos**: cada acción y cada error (por ejemplo, pedir más unidades de las disponibles) se guarda con fecha y hora en `eventos.txt`.

---

## 🧱 Estructura

```
├── menu.py            Punto de entrada: inicio de sesión y menús por rol
├── usuarios.py        CRUD de usuarios
├── herramientas.py    CRUD de herramientas, solicitud y devolución
├── datos.py           Préstamos pendientes, reportes y logs
├── reportes.py        Consultas estadísticas
├── gestion.py         Carga y guardado de archivos JSON
├── usuarios.json      ┐
├── herramientas.json  ├ Persistencia
├── prestamos.json     ┘
├── eventos.txt        Log de eventos
└── proyecto.txt       Enunciado original del proyecto
```

---

## 🚀 Cómo ejecutarlo

Requiere **Python 3.10 o superior** y no necesita librerías externas.

```bash
git clone https://github.com/250930/prestamo-herramientas-python.git
cd prestamo-herramientas-python
python menu.py
```

Para entrar, usa el nombre y el ID de un usuario registrado en `usuarios.json`. Según su `tipo_usuario`, verás el menú de **residente** o el de **administrador**.

---

## 🧠 Conceptos aplicados

Modularización · Listas y diccionarios · Serialización JSON (`json.load` / `json.dump`) · Manejo de fechas con `datetime` · Control de flujo · Manejo de errores · Registro de logs

---

## 👤 Autor

**Jaime Naranjo**, desarrollador en formación en Campuslands.
GitHub: [@250930](https://github.com/250930)
