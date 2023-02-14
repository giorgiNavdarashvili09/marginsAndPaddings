# მარჯინები და პადინგები
იმისათვის, რომ ვიჯეტები სხვა ვიჯეტებისაგან ან/და ეკრანის კიდეებისაგან დავაშოროთ შეგვიძლია გამოვიყენოთ Container ვიჯეტის margin და padding პარამეტრები

„„„
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}
class MyApp extends StatelessWidget {
  const MyApp({super.key});
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text("margins"),
        ),
        body: Container(
          child: Text("Hello World"),
        ),
      ),
    );
  }
}


„„„
