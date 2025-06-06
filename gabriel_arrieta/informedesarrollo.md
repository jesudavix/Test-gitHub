# 📱 Informe de Proyecto Flutter

---

## 🧾 Sobre el proyecto

Al principio tenía la duda sobre qué hacer, ya que reconocía que para ciertos proyectos era más fácil su realización y para otros no. Al final del día, me decidí por hacer un tema de mi interés, y surgió con el gusto que me dio una serie que vi en Netflix.

Con todo esto, pensé en desarrollar una app que se adaptara a los requerimientos de hacer pedidos back-end. Con la idea reunida, surgió el plan de realizar una app que muestre información de los personajes mediante un JSON. 

Obviamente, usé como manejadores de estado tanto `Bloc` como `Equatable`, y para el pedido HTTP del JSON utilicé la librería `http`.

---

## ⚠️ Problemas encontrados

### Problema #1: Inicio del proyecto y uso de Bloc
- **Descripción:** Desde el inicio del proyecto hubo problemas, no tanto con el código, sino con imaginar cómo empezar. Cuando surgió la idea, el siguiente reto fue adaptar el uso de Bloc como manejador de estado, ya que estaba más familiarizado con `StatefulWidget`.
- **Solución:** Investigué más sobre Bloc, cómo funciona, y cómo se complementa con Equatable.

---

### Problema #2: Error `ProviderNotFoundException`
- **Descripción:** Como no entendía bien el funcionamiento de `BlocProvider`, `buildContext`, y `provider`, muchas veces al cambiar de pantalla aparecían errores en toda la app.
- **Solución:** Colocar un `BlocProvider` en el `runApp()`, que más adelante evolucionó a un `MultiBlocProvider`.

---

### Problema #3: Desorden inicial entre rutas, pantallas y lógica del BLoC
- **Descripción:** Algunas pantallas no accedían correctamente al `state`, la navegación era incompleta y había archivos desconectados.
- **Solución:** Revisé el flujo completo desde `main.dart`. Organicé la lógica: Inicio → Selección de personaje → Detalle del personaje. Se conectaron correctamente las pantallas con su respectivo BLoC y la navegación.

---

### Problema #4: Intento de usar JSON para mostrar botones
- **Descripción:** Se quiso generar botones dinámicamente desde un JSON, lo que complicó la estructura.
- **Solución:** Se simplificó la lógica creando automaticamente los botones de los personajes en la pantalla de selección.
- **Resultado:** Menos código, más control y más fácil de mantener.

---

### Problema #5: Bloqueo y desesperación por la cantidad de archivos
- **Descripción:** En momentos, el bloqueo momentáneo me hacía querer comenzar de cero, borrar todo e incluso cambiar de idea.
- **Solución:** Tomar descansos cortos y despejar la mente.

---

### Problema #6: Pensé en simplificar la lógica del Bloc
- **Descripción:** Quisimos evitar tanto Bloc y manejar todo directamente desde la pantalla.
- **Solución:** Se decidió mantener el Bloc (como pedían los requerimientos), pero simplificando al máximo los eventos y estados. Se logró una arquitectura limpia, fácil de mantener y con las pantallas desacopladas.

---

### Problema #7: El tiempo
- **Descripción:** El proyecto que tenía en mente era muy grande para el tiempo disponible. Además, los trabajos y actividades extracurriculares forzaron la reducción del alcance del proyecto.
- **Solución:** Reduje los requerimientos, conservando parte de la idea original, pero adaptándola al tiempo disponible.

---

## 🛠️ Tecnologías y Herramientas Usadas

- Flutter  
- Bloc  
- Equatable  
- http  
- GitHub  
- GitHub Desktop  
- ChatGPT  

---

## 📚 Recursos consultados

- [Flutter BLoC for Beginners – Medium](https://medium.com/flutter-community/flutter-bloc-for-beginners-839e22adb9f5)  
- [Bloc Package – pub.dev](https://pub.dev/packages/bloc)  
