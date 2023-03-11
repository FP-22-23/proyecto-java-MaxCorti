# proyecto-java-MaxCorti
proyecto-java-MaxCorti created by GitHub Classroom
# Proyecto del Segundo Cuatrimestre Fundamentos de Programación (Curso  \<22\>/\<23\>)
Autor/a: \<Max Corti\>   uvus:\<nrf5668\>

Aquí debes añadir la descripción del dataset y un enunciado del dominio del proyecto.
El dataset resume los bienes del ex-presidente de EE.UU y el proyecto embarca en trabajar sobre los datos y presentarlos de una forma más comprensible.

## Estructura de las carpetas del proyecto

* **/src**: Contiene los diferentes archivos que forman parte del proyecto. Debe estar estructurado en los siguentes paquetes
  * **fp.\<assets\>**: Paquete que contiene los tipos del proyecto.
  * **fp.\<assets\>.test**: Paquete que contiene las clases de test del proyecto.
  * **fp.common**: Paquete que contiene los tipos auxiliares del proyecto
  * **fp.utiles**:  Paquete que contiene las clases de utilidad. 
* **/data**: Contiene el dataset o datasets del proyecto
    * **\<2016 Part II Assets No Longer Listed .csv\>**: Parte de los bienes de Donald Trump en 2016.
    * **\<Part I- Positions.csv\>**: Una lista descriptiva de los posiciones que tiene Donal Trump.
    
## Estructura del *2016 Part II Assets No Longer Listed.csv*

Aquí debes describir la estructura del dataset explicando qué representan los datos que contiene y la descripción de cada una de las columnas. Incluye también la URL del dataset original.
Los datos representan unos de los bienes que poseó Trump en 2016
El dataset está compuesto por \<N\> columnas, con la siguiente descripción:

* **\<columna 1>**: de tipo \<Integer\>, representa el identificador del bien en el artículo
* **\<columna 2>**: de tipo \<Integer\>, representa la página en la que está el bien en el artículo
* **\<columna 3>**: de tipo \<String\>, es la descripción o el nombre del bien
* **\<columna 4>**: de tipo \<underlyingAsset\>, indica el tipo del bien
* **\<columna 5>**: de tipo \<String\>, representa el lugar del bien
* **\<columna 6>**: de tipo \<String\>, representa el fondo de inversión exceptuado
* **\<columna 7>**: de tipo \<Integer\>, representa el horario del bien
* **\<columna 8>**: de tipo \<Double\>, representa el valor mínimo que podía tener en 2016
* **\<columna 9>**: de tipo \<Double\>, representa el valor máximo que podía tener en 2016
* **\<columna 10>**: de tipo \<String\>, representa el tipo del ingreso
....

## Tipos implementados

Describe aquí los tipos que usas en tu proyecto.
El tipo que implemento en este proyecto se llama Asset y lo he creado con una clase
### Tipo Base
Descripción breve del tipo base.

**Propiedades**:

- id, de tipo \<Integer\>, consultable. 
- page, de tipo \<Integer\>, consultable.
- description, de tipo \<String\>, consultable. 
- underlyingAssets, de tipo \<underlyingAsset\>, consultable. 
- location, de tipo \<String\>, consultable. 
- eif, de tipo \<String\>, consultable. 
- attachedSchedule, de tipo \<Integer\>, consultable. 
- valueMin2016, de tipo \<Double\>, consultable. 
- valueMax2016, de tipo \<Double\>, consultable. 
- incomeType, de tipo \<String\>, consultable.
- locations, de tipo \<List<String>\>, consultable.  
**Constructores**: 

- Asset(Integer id, String description): Crea un objeto de tipo Asset con el identificador y una descripción con 
  las otras propiedades en 0 o null.
- Asset(Integer id, Integer page, String description, underlyingAsset underlyingAssets, String location, String eif,
			Integer attachedSchedule, Double valueMin2016, Double valueMax2016, String incomeType): 
  Crea un objeto de tipo Asset donde hay que intoducir todas las propiedades como parametros.
- ...

**Restricciones**:
 
Usando los checkers del paquete fp.utiles, implemento un checker para que el identifcador sea siempre mayor que 0 y 
  otro que comprueba que la descripción no sea null
- 
- 
**Criterio de igualdad**: Describir el criterio de igualdad
  El criterio de igualdad dice que dos objetos son iguales si los atributos description,
  id y page son los mismos

**Criterio de ordenación**: Describir el criterio de ordenación (si lo hay).
  El criterio de ordenación que implemento, "compareTo" compara el id primero y si 
  ese atributo coincide, compara el atributo page

**Otras operaciones**:
 
-	formatoCorto que es un método que imprima la página y el identificador 
- toString que representa el tipo con todos sus atributos 
- ...

#### Tipos auxiliares
Descripción de los tipos auxiliares que sean necesarios añadir al proyecto.
  underlyingAsset de tipo enum que puede tener los valores:
  bank_account, none, bank_account_license_deal, residential_real_estate,
	land, bank_account_management_co, bank_account_management_deal;


### Factoría
Descripción breve de la factoría.

- _método 1_: Descripción del método 1.
-	_método 2_: Descripción del método 2.

### Tipo Contenedor

Descripción breve del tipo contenedor.
  Implemento una lista "locations" como atributo pero aún no realizo operaciones sobre ella

**Propiedades**:

- _propiedad1_, de tipo \<Tipo1\>, consultable. 
- _propiedad2_, de tipo \<Tipo2\>, consultable y modificable. 
- ...
- 
**Constructores**: 

- C1: Descripción del constructor 1.
- C2: Descripción del constructor 2.
- ...

**Restricciones**:
 
- R1: Descripción de la restricción 1.
- R2: Descripción de la restricción 2.
- ...
- 
**Criterio de igualdad**: Describir el criterio de igualdad

**Criterio de ordenación**: Describir el criterio de ordenación (si lo hay).

**Otras operaciones**:
 
-	_método 1_: Descripción del método 1.
- ...
