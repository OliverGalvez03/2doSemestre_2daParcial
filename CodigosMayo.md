# Codigos Mayo
### 3 Mayo
~~~ dart
void main(List<String> args) {
  Mueble m1 = Mueble();
  m1.ShowCounter();
  print('Propiedad de clase Mueble: ${Mueble.counterStatic}');
  print("-" * 28);
  Mueble m2 = Mueble();
  m2.ShowCounter();
  print('Propiedad de clase MMuevle: ${Mueble.counterStatic}');
}

class Mueble {
  //Propiedad de instancia
  int counter = 0;

  //Propiedad de clase
  static int? counterStatic = 0;

  Mueble() {
    counter++;
    counterStatic++;
  }
  //Metedo de instancia
  void ShowCounter() {
    print('Propiedad de instancia: $counter');
  }

  static void showCounterStatic() {
    print("Propiedad de clase: $counterStatic");
  }
}
~~~

~~~ dart
import 'animal.dart';
import 'pato.dart';
import 'caballo.dart';
import 'vaca.dart';

void main(List<String> args) {
  Pato pato1 = Pato();
  pato1.breed = 'Pekines';
  pato1.quantity = 10;
  pato1.tipo_pico = 'Curvo';
  pato1.showProperties();
  print("_" * 28);
  Animal a1 = Animal();
  a1.breed = 'Animal';
  a1.quantity = 100;
  a1.showProperties();
  print("_" * 28);
  Caballo c1 = Caballo();
  c1.breed = 'Azteca';
  c1.quantity = 50;
  c1.color_crin = 'Cafe';
  c1.showProperties();
  print("_" * 28);
  Vaca v1 = Vaca();
  v1.breed = 'Holstein';
  v1.quantity = 30;
  v1.color_manchas = 'Negras';
  v1.showProperties();
}
------------------------------------------
class Animal {
  String? breed;
  int? quantity;

  void showProperties() {
    print('Breed: $breed');
    print('Quantity: $quantity');
  }
}
------------------------------------------
import 'animal.dart';

class Pato extends Animal {
  String? tipo_pico;

  Pato(this.tipo_pico);

  @override
  void showProperties() {
    super.showProperties();
    print('Tipo de pico: $tipo_pico');
  }
}
------------------------------------------
import 'animal.dart';

class Caballo extends Animal {
  String? color_crin;

  Caballo(this.color_crin);
}
------------------------------------------
import 'animal.dart';

class Vaca extends Animal {
  String? color_manchas;

  @override
  void showProperties() {
    super.showProperties();
    print('Color de manchas: $color_manchas');
  }
}
~~~
