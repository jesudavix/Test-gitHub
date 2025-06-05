# Documentación de la Aplicación Móvil - Rick and Morty

## Índice

1. [Descripción general](#descripción-general)
2. [Características principales](#características-principales)
3. [Arquitectura del proyecto](#arquitectura-del-proyecto)
4. [Dependencias](#dependencias)
5. [Estados de la app](#estados-de-la-app)
6. [Consumo de API](#consumo-de-api)
7. [Futuras mejoras](#futuras-mejoras)
8. [Herramientas usadas](#herramientas-usadas)
9. [Partes más difíciles del proyecto](#partes-más-difíciles-del-proyecto)

---

## Descripción General

Aplicación móvil desarrollada con **Flutter** que permite al usuario explorar información de personajes mediante el consumo de una **API externa**.  
La interfaz cambia entre estados de carga, éxito y error según la respuesta del servidor.

---

## Características Principales

- Consumo de API REST
- Gestión de estados con **Bloc**
- Navegación entre vistas
- Manejo de errores y estados vacíos
- UI responsiva y moderna

---

## Arquitectura del Proyecto

- **Framework:** Flutter
- **Manejo de estado:** Bloc + Equatable
- **API HTTP:** Librería `http`
- **Modelo de datos:** `CharactersModel`, `Info`, `Results`, `Origin`

---

## Dependencias

```yaml
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.8
  flutter_bloc: ^9.1.1
  equatable: ^2.0.7
  http: ^1.4.0
  lottie: ^3.3.1
```
