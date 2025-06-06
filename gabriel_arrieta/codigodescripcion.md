# 🧱 Código principal del proyecto Flutter con Bloc

A continuación se muestra el código `main.dart` del proyecto **Arcane App**, el cual utiliza el patrón Bloc para el manejo del estado.  
Este fragmento es el punto de entrada de la app, y registra dos BLoCs usando `MultiBlocProvider`.

---

## 📌 Explicación breve

- Se importan los paquetes necesarios (`flutter_bloc`, archivos locales y pantallas).
- Se usan dos `BlocProvider`:
  - `AudioBloc`: para controlar el audio del juego.
  - `CharacterblocBloc`: para manejar los datos de los personajes.
- Se construye la app con `MyApp`, y la pantalla inicial es `Inicio`.

---

## 🔢 Código Dart:

```dart
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';
import 'bloc/audio_bloc.dart';
import 'package:arcane_characters/bloc/characterbloc_bloc.dart'; 
import 'package:arcane_characters/ventanas/inicio.dart';

void main() {
  runApp(
    MultiBlocProvider(
      providers: [
        BlocProvider<AudioBloc>(
          create: (_) => AudioBloc(),
        ),
        BlocProvider<CharacterblocBloc>(
          create: (_) => CharacterblocBloc(),
        ),
      ],
      child: MyApp(),
    ),
  );
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Arcane App',
      home: Inicio(),
      debugShowCheckedModeBanner: false,
    );
  }
}
