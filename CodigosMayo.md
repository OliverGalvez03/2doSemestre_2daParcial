# Codigos Mayo
### 19 Abril
~~~ dart
void main() {
  var e1 = Estudiante();
  Estudiante e2 = Estudiante();
  print(e1);
  print(e2);
  e1.nombre = "Juan";
  e1.aNacimiento = 1990;
  e2.nombre = "Pedro";
  e2.aNacimiento = 1991;
  ~~~
  ~~~ dart
  void main(List<String> args) {
  Animal gato = Animal();
  gato.nombre = "Garfield";
  gato.sonido = "Miau";
  Animal pato = Animal();
  pato.nombre = "Pato Donald";
  pato.sonido = "Cuac";

}

class Animal {
  String nombre = "";
  String sonido = "";

}

void reporte(Animal) {
  print("Nombre: ${a.nombre}");
  print("Sonido: ${a.sonido}");
}
~~~

~~~ dart
void main(List<String> args) {
  Animal gato = Animal();
  gato.nombre = "Garfield";
  gato.sonido = "Miau";
  gato.Reporte();
  Animal pato = Animal();
  pato.nombre = "Pato Donald";
  pato.sonido = "Cuac";
  pato.Reporte();
}

class Animal {
  String nombre = "";
  String sonido = "";

  void Reporte() {
    print("Nombre: $nombre");
    print("Sonido: $sonido");
  }
}

void reporte(Animal) {
  print("Nombre: ${a.nombre}");
  print("Sonido: ${a.sonido}");
}
~~~

### 26 Abril
~~~ dart 
/*
Escriba un programa que tenga una clase figurra
que tenga dos propiedades: base, altura
y dos metdos que calculen el area y el perimetro
de un rectangulo
*/

import '2604figura.dart';

void main(List<String> args) {
  print('Base: ${f1.base}');
  print('Altura: ${f1.altura}');
  print('Area: ${f1.areaRectangulo(5, 4)}');
  print('Base: ${f1.base}');
  print('Altura: ${f1.altura}');
}
~~~

### 27 Abril
~~~ dart
import 'vehiculo.dart';

void main(List<String> args) {
  Vehicle v1 = Vehicle(
    'Toyota',
    'Corolla',
    'Rojo',
    'Automatico',
  );

  Vehicle v2 = Vehicle(
    'Honda',
    'Civic',
    'Azul',
    'Manual',
  );

  List<Vehicle> vehicles = [v1, v2];

  vehicles.forEach((vehicle) => vehicle.showVehicle());
}

class Vehicle {
  String _brand;
  String _name;
  String _color;
  String _transmittion;

  Vehicle(
    this._brand,
    this._name,
    this._color,
    this._transmittion,
  );

  void set brand(String brand) => this._brand = brand;
  void set name(String name) => this._name = name;
  void set color(String color) => this._color = color;
  void set transmittion(String transmittion) =>
      this._transmittion = transmittion;

  String get brand => this._brand;
  String get name => this._name;
  String get color => this._color;
  String get transmittion => this._transmittion;

  void showVehicle() {
    print('''\n
      Marca: ${this.brand}
      Nombre: ${this.name}
      Color: ${this.color}
      Transmittion ${this.transmittion}
      ''');
  }
}
~~~

~~~ dart
import 'shape.dart';

void main(List<String> args) {
  Shape f1 = Shape(10, 5);
  print(f1.getArea());
  f1.base = 15;
  f1.altura = 10;
  print(f1.getArea());
  print('''El area del rectangulo con base ${f1.base} 
      y altura ${f1.altura} es ${f1.getArea()}''');
}

class Shape {
  int? _base;
  int? _altura;

  Shape(this._base, this._altura);

  int getArea() {
    return _calcularArea();
  }

  int _calcularArea() {
    return _base! * _altura!;
  }

  /* void set base(int base) {
    _base = base;
  } */

// setters
  void set base(int? base) => _base = base;
  void set altura(int? altura) => _altura = altura;

  //getters
  int? get base => _base;
  int? get altura => _altura;
}

~~~
