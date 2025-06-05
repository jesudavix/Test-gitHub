# 📄 Documentación del Proyecto - *Futbol Pro*

**📅 Fecha:** Jueves 22 de mayo de 2025  
**📱 Tipo de proyecto:** Aplicación con Backend  
**🧰 Stack técnico:**  
- **Gestor de estado:** BloC  
- **Librerías:** `equatable`, `http`

---

##  ¿Qué es BloC?

**BloC** (Business Logic Component) es una arquitectura que permite separar la lógica de negocio de la interfaz de usuario.

### Funcionamiento básico:
1. El usuario genera un evento (por ejemplo, al presionar un botón).
2. El Bloc procesa ese evento y ejecuta una acción (como llamar a una API).
3. El estado cambia (por ejemplo: `Cargando`, `Éxito`, `Error`).
4. La interfaz reacciona y muestra el nuevo estado.

---

##  Librerías utilizadas

- **Equatable:**  
  Permite comparar objetos fácilmente. Es útil para que Flutter sepa cuándo debe actualizar widgets al detectar cambios en el estado. Mejora la eficiencia y evita errores.

- **http:**  
  Se usa para hacer peticiones a internet. Es como decirle al servidor:  
  “Ey, mándame esta información”. Sirve para conectar la app con una API.

---

##  Herramientas utilizadas

- **Flutter:** Framework principal para el desarrollo de la app.  
- **Mocky:** Para simular APIs durante las pruebas.  
- **DeepSeek** y **ChatGPT:** Asistentes de IA para resolver problemas, explicar conceptos y depurar código más fácilmente.

---

##  Problemas encontrados

Como usuario de GitHub, enfrenté algunos desafíos técnicos:

- **Errores en los commits:** A veces los cambios no se guardaban correctamente.
- **Dependencias conflictivas:** Algunas librerías generaban errores difíciles de entender.  
- **Bloc:** Fue complicado entender cómo fluían los eventos y estados.

---

##  Partes más difíciles

- **Implementación del BloC:** Me costó entender cómo estructurar la lógica correctamente.  
- **Errores de dependencias:** Pensaba que el problema era visual (interfaz), pero en realidad estaba en el `pubspec.yaml` y la instalación de paquetes.

---

##  Tareas pendientes

- [ ] **Modificar la pantalla de inicio a mi estilo.**  
- [ ] Agregar un **ícono personalizado** para la aplicación.
