import 'package:flutter/material.dart';

void main() {
  runApp(app());
}

class app extends StatelessWidget {
  app({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: "app",
      home: Home(),
    );
  }
}

class Home extends StatelessWidget {
  Home({super.key});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      
    );
  }
}
