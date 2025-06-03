# Informe de Desarrollo de la Aplicación Pokédex en Flutter

## 📱 Introducción

Este informe describe el proceso de desarrollo de una aplicación tipo Pokédex desarrollada con Flutter, cuyo propósito es permitir al usuario explorar una lista de Pokémon obtenida desde la [PokeAPI](https://pokeapi.co). La app incluye funcionalidades como la visualización de datos, búsqueda dinámica, manejo de estados con BLoC y una interfaz de usuario amigable e interactiva. Este documento también detalla las tecnologías empleadas, las dificultades encontradas, cómo fueron resueltas y el rol que desempeñó la inteligencia artificial (ChatGPT) como herramienta de apoyo.

---

## 🔧 Tecnologías Utilizadas

Durante el desarrollo de la app se utilizaron las siguientes tecnologías:

- **Flutter**: Framework de desarrollo multiplataforma basado en Dart.
- **Dart**: Lenguaje de programación utilizado por Flutter.
- **PokeAPI**: API REST gratuita para obtener datos de Pokémon.
- **HTTP**: Paquete para hacer peticiones a la API.
- **BLoC** (`flutter_bloc`, `bloc`): Patrón para el manejo del estado de la aplicación.
- **Equatable**: Paquete que facilita la comparación entre estados.
- **ChatGPT (IA)**: Herramienta de apoyo para resolver dudas técnicas y estructurar la lógica del código.

---

## ⚙️ Funcionalidades Implementadas

- **Listado de Pokémon**: Visualización de tarjetas (cards) que muestran imagen, nombre y tipo de cada Pokémon.
- **Filtro por nombre**: Funcionalidad de búsqueda en tiempo real para filtrar Pokémon por nombre.
- **Manejo de estados con BLoC**: Uso de eventos y estados para representar el flujo lógico de datos.
- **Cambio dinámico del AppBar**: Transición del `AppBar` entre un título ("Pokédex") y un campo de búsqueda interactivo.
- **Indicador de carga (`loading`)**: Mientras se obtienen los datos de la API, se muestra un spinner de carga.
- **Diseño responsive y temático**: Uso de colores basados en los tipos de Pokémon.

---

## ⚠️ Dificultades Encontradas

### 1. Aprendizaje del patrón BLoC

El principal reto fue entender e implementar correctamente el patrón BLoC. Fue necesario comprender cómo:

- Separar los eventos que lanza la UI.
- Escuchar estos eventos en el BLoC.
- Emitir estados según la lógica de negocio.
- Actualizar la interfaz en función del estado actual.

### 2. Búsqueda en tiempo real

Implementar la búsqueda dinámica no fue trivial. Fue necesario:

- Guardar una copia local de todos los Pokémon (`_todosLosPokemones`) para filtrar sin necesidad de repetir llamadas a la API.
- Manejar el evento `onChanged` del campo de texto para lanzar un evento `BuscarPokemonPorNombre` en el BLoC.
- Filtrar en tiempo real los resultados y actualizar la UI sin afectar el rendimiento.

### 3. Alternancia entre modos del AppBar

Implementar el comportamiento dinámico del AppBar también fue un desafío, especialmente al coordinar dos BLoC distintos:

- `PokemonBloc`: Para manejar la lógica de búsqueda.
- `SearchBloc`: Para alternar entre los modos del AppBar (con campo de búsqueda o con título).

---

## ✅ Solución a los Problemas

Con el apoyo de documentación oficial y el uso de ChatGPT para comprender la arquitectura BLoC, logré:

- Organizar los BLoC por funcionalidad (uno para los Pokémon y otro para la barra de búsqueda).
- Separar claramente los eventos y los estados.
- Usar `Equatable` para comparar correctamente los estados y evitar renderizados innecesarios.
- Implementar `SearchBloc` de esta forma:

```dart
on<MostrarBarraBuscador>((event, emit) {
  emit(BarraBuscadorVisible());
});

on<OcultarBarraBuscador>((event, emit) {
  emit(BarraBuscadorOculta());
});
```

Así, cuando se lanza el evento MostrarBarraBuscador, se emite el estado que hace visible la barra de búsqueda (TextField), permitiendo escribir el nombre del Pokémon a buscar. Por el contrario, al lanzar el evento OcultarBarraBuscador, se oculta la barra de búsqueda.

---

## 🎨 Diseño de la Interfaz

- **Tarjetas con imagen y tipo**: Cada tarjeta muestra un Pokémon con su imagen cargada desde la API, su nombre y tipo(s).
- **Colores temáticos**: Las tarjetas cambian de color según el tipo del Pokémon, haciendo la UI más atractiva.

---

## 📌 Conclusion 
El desarrollo de esta Pokédex en Flutter fue una experiencia enriquecedora que me permitió mejorar mis habilidades en programación móvil, arquitecturas limpias y consumo de APIs. A pesar de los retos, especialmente con BLoC, logré implementar una aplicación funcional, visualmente atractiva y con un código bien organizado.