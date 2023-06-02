#  Codigo Proyecto
### Proyecto
~~~ dart
import 'dart:io';
import 'ClassAlumno.dart';
import 'ClassProfesor.dart';

void main(List<String> args) {
  var ban = true;
  while (ban == true) {
    print("*Base de datos i.c.i**");
    print("Seleccione una de las siguiente opciones para continuar... ");
    print("--------------------------------------------------");
    print("1. Agregar nuevo alumno");
    print("2. Agregar nuevo profesor");
    print("3. Buscar estudiante");
    print("4. Buscar profesor");
    print("5. Editar estudiante");
    print("6. Editar profesor");
    print("7. Eliminar estudiante");
    print("8. Eliminar profesor");
    print("--------------------------------------------------");
    print("0. Salir");

    var num = stdin.readLineSync();

    switch (num) {
      case '1':
        //Agregar alumno

        List<Alumno> listaAlumnos = [];

        stdout.write('Ingrese el nombre del alumno');
        String? nombre = stdin.readLineSync();

        stdout.write('Ingrese el apellido del alumno: ');
        String? apellido = stdin.readLineSync();

        stdout.write('Ingrese la edad del alumno: ');
        int edad = int.parse(stdin.readLineSync());

        Alumno nuevoAlumno = Alumno(nombre!, apellido!, edad);
        listaAlumnos.add(nuevoAlumno);

        print("-Alumno agregado-");
        break;

      case '2':
        //Agregar profesor
        List<Profesor> listaProfesor = [];

        stdout.write('Ingrese el nombre del profesor');
        String? nombre = stdin.readLineSync();

        stdout.write('Ingrese el apellido del profesor: ');
        String? apellido = stdin.readLineSync();

        stdout.write('Ingrese la edad del profesor: ');
        int edad = int.parse(stdin.readLineSync());

        Profesor nuevoProfesor = Profesor(nombre!, apellido!, edad);
        listaProfesor.add(nuevoProfesor);

        print("-Profesor agregado-");

        break;

      case '3':
        // Búsqueda de alumno
        List<Alumno> listaAlumnos = [];

        print('--- Búsqueda de Alumno ---');

        if (listaAlumnos.isEmpty) {
          print('No hay alumnos en la lista.');
        } else {
          stdout.write('Ingrese el nombre del alumno a buscar: ');
          String? searchName = stdin.readLineSync();

          Alumno buscarAlumno = listaAlumnos.firstWhere(
            (alumno) => alumno.name == searchName,
            orElse: () => null,
          );

          if (buscarAlumno != null) {
            print('Alumno encontrado:');
            print(buscarAlumno.toString());
          } else {
            print('No se encontró ningún alumno con el nombre "$searchName".');
          }
        }
        break;

      case '4':
        //Buscar profesor
        List<Profesor> listaProfesor = [];

        print('--- Búsqueda de Profesor ---');

        if (listaProfesor.isEmpty) {
          print('No hay profesores en la lista.');
        } else {
          stdout.write('Ingrese el nombre del profesor a buscar: ');
          String? searchName = stdin.readLineSync();

          Profesor buscarProfesor = listaProfesor.firstWhere(
            (profesor) => profesor.name == searchName,
            orElse: () => null,
          );

          if (buscarProfesor != null) {
            print('Alumno encontrado:');
            print(buscarProfesor.toString());
          } else {
            print('No se encontró ningún alumno con el nombre "$searchName".');
          }
        }
        break;

      case '5':
        //Editar alumno
        List<Alumno> listaAlumnos = [];

        print('Alumnos disponibles:');
        for (int i = 0; i < listaAlumnos.length; i++) {
          print('$i. ${listaAlumnos[i].toString()}');

          stdout.write('Ingrese el índice del alumno a editar: ');
          int indice = int.parse(stdin.readLineSync());

          if (indice >= 0 && indice < listaAlumnos.length) {
            Alumno alumnoEditar = listaAlumnos[indice];

            stdout.write('Ingrese el nuevo nombre: ');
            String? nuevoNombre = stdin.readLineSync();
            alumnoEditar.name = nuevoNombre!;

            stdout.write('Ingrese el nuevo apellido: ');
            String? nuevoApellido = stdin.readLineSync();
            alumnoEditar.apellido = nuevoApellido!;

            stdout.write('Ingrese la nueva edad: ');
            int nuevaEdad = int.parse(stdin.readLineSync());
            alumnoEditar.edad = nuevaEdad;

            print('Alumno editado correctamente:');
            print(alumnoEditar.toString());
          } else {
            print('El índice ingresado no es válido.');
          }
        }
        break;

      case '6':
        //Editar profesor
        List<Profesor> listaProfesor = [];

        print('Profesores disponibles:');
        for (int i = 0; i < listaProfesor.length; i++) {
          print('$i. ${listaProfesor[i].toString()}');

          stdout.write('Ingrese el índice del profesor a editar: ');
          int indice = int.parse(stdin.readLineSync());

          if (indice >= 0 && indice < listaProfesor.length) {
            Profesor profesorEditar = listaProfesor[indice];

            stdout.write('Ingrese el nuevo nombre: ');
            String? nuevoNombre = stdin.readLineSync();
            profesorEditar.name = nuevoNombre!;

            stdout.write('Ingrese el nuevo apellido: ');
            String? nuevoApellido = stdin.readLineSync();
            profesorEditar.apellido = nuevoApellido!;

            stdout.write('Ingrese la nueva edad: ');
            int nuevaEdad = int.parse(stdin.readLineSync());
            profesorEditar.edad = nuevaEdad;

            print('Profesor editado correctamente:');
            print(profesorEditar.toString());
          } else {
            print('El índice ingresado no es válido.');
          }
        }
        break;

      case '7':
        //Eliminar alumno
        List<Alumno> listaAlumnos = [];

        for (int i = 0; i < listaAlumnos.length; i++) {
          print('$i. ${listaAlumnos[i].toString()}');

          stdout.write('Ingrese el índice del alumno a eliminar: ');
          int indice = int.parse(stdin.readLineSync());

          if (indice >= 0 && indice < listaAlumnos.length) {
            Alumno alumnoEliminar = listaAlumnos[indice];
            listaAlumnos.removeAt(indice);

            print('Alumno eliminado correctamente:');
            print(alumnoEliminar.toString());
          } else {
            print('El índice ingresado no es válido.');
          }

          print('Alumnos restantes:');
          for (Alumno alumno in listaAlumnos) {
            print(alumno.toString());
          }
        }
        break;

      case '6':
        // Eliminar profesor
        List<Profesor> listaProfesor = [];

        for (int i = 0; i < listaProfesor.length; i++) {
          print('$i. ${listaProfesor[i].toString()}');

          stdout.write('Ingrese el índice del profesor a eliminar: ');
          int indice = int.parse(stdin.readLineSync());

          if (indice >= 0 && indice < listaProfesor.length) {
            Profesor profesorEliminar = listaProfesor[indice];
            listaProfesor.removeAt(indice);

            print('Profesor eliminado correctamente:');
            print(profesorEliminar.toString());
          } else {
            print('El índice ingresado no es válido.');
          }

          print('Profesores restantes:');
          for (Profesor profesor in listaProfesor) {
            print(profesor.toString());
          }
        }
        break;
    }
  }
}
----------------------------------------------------------------
class Alumno {
  String name;
  String apellido;
  int edad;

  Alumno(this.name, this.apellido, this.edad);

  @override
  String toString() {
    return 'Nombre: $name, Apellido: $apellido, Edad: $edad';
  }
}
----------------------------------------------------------------
class Profesor {
  String name;
  String apellido;
  int edad;

  Profesor(this.name, this.apellido, this.edad);

  @override
  String toString() {
    return 'Nombre: $name, Apellido: $apellido, Edad: $edad';
  }
}
~~~
