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
El dataset está compuesto por \<10\> columnas, con la siguiente descripción:

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
Un tipo que implemento en este proyecto se llama Asset y lo he creado con una clase
### Tipo Base: Asset
Descripción breve del tipo Asset.

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
- valorRango, de tipo \<Double\>, consultable.
**Constructores**: 

- Asset(Integer id, String description): Crea un objeto de tipo Asset con el identificador, una descripción con 
  las otras propiedades en 0 o null y una Arraylist nueva para el atributo locations.
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
### Assets_lector
Es una clase que implento para comprobar todos los métodos que he creado y que lea el csv correctamente.
Por una parte, recorro el datatset por el método creaAssetsDeFichero de la clase FactoriaAsset y por otra parte uso  el método leerAssets para usar los Streams
### TestAsset
En esta clase compruebo los métodos getters del tipo Asset y sus constructores
### Ficheros
Contiene un método:
- leeFichero(String path): devuelva una lista de tipos String que se usa para leer el archivo csv.

#### Tipos auxiliares
Descripción de los tipos auxiliares que sean necesarios añadir al proyecto.
  underlyingAsset de tipo enum que puede tener los valores:
  bank_account, none, bank_account_license_deal, residential_real_estate,
	land, bank_account_management_co, bank_account_management_deal;
  CalcRango que tiene un método getRangoVal que devuelva la diferencia entre el valor 
  maximo de 2016 y el valor minimo.


### Factoría
Se llama FactoriaAsset la clase y se usa para crear tipos Asset de distintas formas
o una lista de tipos Asset
- _creaAsset(Integer id, Integer page, String description, underlyingAsset underlyingAssets, String location, String eif,
			Integer attachedSchedule, Double valueMin2016, Double valueMax2016, String incomeType)_: recibe todos los parámetros para llamar 
			al constructor del tipo Asset para crear un objeto
-	_creaAssetStr(String s)_: recibe un tipo String y lo trocea adecuadamente y hace una conversión de tipos necesarios para poder llamar al método anterior y crear un tipo Asset
-	_creaAssetsDeFichero(String titulo, String fichero)_: recibe un titulo y la ruta del fichero y crea una ArrayList para poder meter todos los tipos Asset que se van creando línea a línea desde el fichero, saltando la cabecera.
-	_leerAssets(String ruta)_: recibe la ruta de tipo String y crea un Tipo Stream<Asset> a partir de ello. Luego crea un tipo Assets<Stream<Asset>> a partir del anterior. Si la ruta es vacía, salta la excepción "Fichero no encontrado"
-	_parseaUnderlyingAsset(String s)_: recibe un String y lo convierta en un tipo underlyingAsset según el String de parámetro
### Tipo Contenedor

Descripción breve del tipo Assets.
  Assets es un tipo que se usa para guradar los tipos Asset leídos del fichero

**Propiedades**:

- _nombre_, de tipo \<String\>, consultable y modificable
- _codigo_, de tipo \<Integer\>, consultable y modificable. 
- _assets_, de tipo \<List<Asset>\>, consultable y modificable.
- 
**Constructores**: 

- Assets(): pone el nombre y el codigo a null y crea una nueva ArrayList<Asset> para assets.
- Assets(String nombre, List<Asset> assets): recibe el nombre y una lista para assets pero pone codigo a null.
- Assets(Stream<Asset> assets): recibe assets de tipo Stream<Asset> y pone el nombre y codigo a null. Además, usa un Collector para converir el Stream de entrada a una List<Asset>

**Restricciones**:
 Hasta ahora no ha requerido restricciones
- R1: Descripción de la restricción 1.
- R2: Descripción de la restricción 2.
- ...
- 
**Criterio de igualdad**: Tiene hashCode() y equals(Object obj) que se generan a partir del assets, nombre y codigo

**Criterio de ordenación**: Describir el criterio de ordenación (si lo hay).

**Otras operaciones**:
- 	_getNombre()_: devuelve el nombre.
-	_setNombre(String nombre)_: Pone la propiedad nombre a nombre.
-	_getCodigo()_: devuelve el codigo.
-	_setCodigo(Integer codigo)_: Pone la propiedad codigo a codigo.
-	_getAssets()_: devuelve la propiedad assets.
-	_calcularNumeroAssets()_: Recorre assets y cuenta el número de tipo Asset hay.
-	_añadirAsset(Asset a)_: Añade un tipo Asset a assets
-	_añadirAssets(Collection<Asset> c)_: Añade una colección de Asset a assets.
-	_eliminarAsset(int index)_: Elimina un tipo Asset de assets según su índice
-	_existeId(Integer id)_: Recorre assets para ver si exista un tipo Asset con atributo id igual al parámetro pasado
-	_existeId2(Integer id)_: devuelve un Boolean que depende de si el parametro id existe en uno de los tipos Asset dentro de la propiedad assets.
-	_sumaValueMin2016()_: Recorre assets y suma todos los atributos valueMin2016 de cada Asset
-	_sumaValueMin2016II()_: implementa el método stream para sumar todas las propiedades valueMin2016 de cada tipo Asset dentro de assets
-	_getAssetsLand()_: Recorre assets y si su atributo underlyingAsset es land, se añade ese asset a una nueva lista y la devuelva.
-	_getAssetsLand2_: usa el metodo stream para devolver todos los tipos Asset que tengan la propiedad underlyingAssets de tipo land dentro de assets
-	_assetPorUnderlyingAsset()_: Recorre assets y devuelva una map con las claves siendo el atributo underlyingAsset de los asset, y los valores una lista de los asset con dicho atributo
-	_conteoUbicaciones()_: Recorre assets y devuelve una map con las claves siendo el atributo location de los asset u los valores siendo el número de veces que aparezca ese location.
-	_assetsMasTiempoHorario(String incomeType_: Método que recibe una ubicación, y devuelve el Asset con su propiedad location igual con el mayor AttachedSchedule
-	_assetsBankAccountOrdenadoPorAS()_: metodo que devuelva una lista de los assets con la propiedad underlyingAssets de tipo BankAccount y ordenado por la propiedad attachedSchedule de mayor a menor
-	_toString()_: Devuelve un String con todos los atributos.
