<<<<<<< HEAD
# Proyecto final programación backend
## Coderhouse - 32190
### Candela Dominguez Barco 

Mi repositorio es del proyecto final del curso backend realizado en coderhouse de la carrera de Desarrollo FullStack. Es sobre un API REST en JavaScript para un ecommerce. 

### Url del proyecto: 

### Url del proyecto en Glitch: 

### Metodos 
| Metodos | Routes                                          | Descripción                                                              			|
| :---    |     :---                                        | :---                                                                			|
| GET     | /api/productos                                  | Devuelve todos los productos                                       			|
| GET     | /api/productos/:id 		                    | Devuelve un producto según su id                            	 			|
| POST    | /api/productos                                  | Recibe y agrega un producto, y lo devuelve con su id asignado	 			|
| PUT     | /api/productos/:id       		            | Recibe y actualiza un producto según su id		         			|
| DELETE  | /api/productos/:id 		                    | Elimina un producto según su id		                         			|
| GET     | /api/carrito/		    		    | Devuelve todos los carritos					 			|
| POST    | /api/carrito/		    		    | Crea un carrito y devuelve su id					 			|
| DELETE  | /api/carrito/:id		                    | Vacía un carrito y lo elimina	                                 			|
| GET     | /api/carrito/:id/productos    		    | Permite listar todos los productos guardados en el carrito por su id  	 		|
| POST    | /api/carrito/:id1/productos/:id2   		    | Para incorporar productos a un carrito id1 = id carrito, id2 = id producto 		|
| DELETE  | /api/carrito/:id1/productos/:id_prod	    | Eliminar un producto del carrito por su id (id1) de carrito y de producto (id_prod) 	|
| POST	  | /api/login					    | Para iniciar sesión con un usuario registrado					 	|
| POST	  | /api/register				    | Para registrar un usuario nuevo							 	|
| GET	  | /api/fail-login				    | Se obtiene al ingresar credenciales no válidas en el POST de loggin		 	|
| GET	  | /api/fail-register				    | Se obtiene al no poder concretar el registro de un nuevo usuario			 	|
| GET	  | /api/home					    | Se obtiene al realizar un loggin exitoso, o se puede acceder para ver el de la sesion	|
| GET	  | /api/succesfull-register			    | Se obtiene al realizar un registro de nuevo usuario exitoso		 		|
| GET	  | /api/logout					    | Permite cerrar una sesion activa						 		|
| POST	  | /api/pedido					    | Continua el proceso de confirmar la compra del carrito de la sesion activa		|

<br>

## REQUESTS/RESPONSES

<details>
<summary>GET <b>/api/productos</b></summary> 

```js
GET http://localhost:8080/api/productos
```

### Respuestas

```json
[
	{"id":1,
	"timestamp":1670096837624,
	"nombre":"Cafe",
	"descripcion":"Cafe",
	"código":"Cafe",
	"foto":"https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
	"precio":800,"stock":10
	},
	{"id":2,
	"timestamp":1670096837624,
	"nombre":"Capuchino",
	"descripcion":"Capuchino",
	"código":"Capuchino",
	"foto":"https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-03-512.png",
	"precio":1000,"stock":15
	}
]
```
</details>
<br>
<details>
<summary>GET <b>/api/productos/:id</b></summary> 

```js
GET http://localhost:8080/api/productos/1
```
### Solicitud

```json
{
	"código":"Cafe",
	"foto":"https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
	"stock": 10,
	"descripcion": "Cafe",
	"precio": 800,
	"timestamp": 1670096837624,
	"idStore": 1,
	"nombre": "Cafe"
}
```
### Respuesta
```json
{
	"codigo": "Cafe",
	"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
	"stock": 10,
	"descripcion": "Cafe",
	"precio": 800,
	"idStore": 4,
	"nombre": "Cafe",
	"timestamp": 1678033395055,
	"id": 4
}
```
</details>
<br>


<details>
<summary>PUT <b>/api/productos/:id</b></summary> 

```js
PUT http://localhost:8080/api/productos/4
```

### Solicitud
```json
{
	"codigo": "Cafe",
	"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
	"stock": 6,
	"descripcion": "Cafe",
	"precio": 1000,
	"idStore": 4,
	"nombre": "Cafe"
}
```
### Respuesta

```json
{
	"ok": "Producto actualizado"
}
```
</details>
<br>


<details>
<summary>DELETE <b>/api/productos/:id</b></summary> 

```js
DELETE http://localhost:8080/api/productos/4
```
### Respuesta
```json
{
	"ok": "Producto eliminado"
}
```
</details>
<br>

<details>
<summary>GET <b>/api/carrito/</b></summary> 

```js
GET http://localhost:8080/api/carrito/
```
### Respuesta
```json
[
	{
		"_id": "63acb3f740a3d442f972f4c1",
		"timestamp": 1672262647281,
		"productos": [
			{
				"idStore": 1,
				"timestamp": 1670096837624,
				"nombre": "Cafe",
				"descripcion": "Cafe",
				"codigo": "Cafe",
				"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
				"precio": 800,
				"stock": 10,
				"_id": "63acb41840a3d442f972f4c9"
			},
			{
				"idStore": 2,
				"timestamp": 1670096837624,
				"nombre": "Capuchino",
				"descripcion": "Capuchino",
				"codigo": "Capuchino",
				"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-03-512.png",
				"precio": 1000,
				"stock": 15,
				"_id": "63acb41e40a3d442f972f4d3"
			}
		],
		"__v": 0
	},
	{
		"_id": "640241997d58d47da33ddf90",
		"timestamp": 1677869465621,
		"productos": [],
		"__v": 0
	},
	{
		"_id": "640241de63d5e918cbdb83bc",
		"timestamp": 1677869534518,
		"productos": [],
		"__v": 0
	}	
]
```
</details>
<br>


<details>
<summary>POST <b>/api/carrito/</b></summary> 

```js
POST http://localhost:8080/api/carrito/
```
### Respuesta

```json
{
	"id del carrito nuevo": "6404c4361a63250879cf654f9"
}
```
</details>
<br>

<details>
<summary>DELETE <b>/api/carrito/:id</b></summary> 

```js
DELETE http://localhost:8080/api/carrito/6404c4361a63250879cf654f9
```

### Respuesta


```json
{
	"ok": "Carrito eliminado"
}
```
</details>
<br>

<details>
<summary>GET <b>/api/carrito/:id/productos</b></summary> 

```js
GET http://localhost:8080/api/carrito/63acb3f740a3d442f972f4c1/productos
```
### Respuesta
```json
[
	{
		"idStore": 1,
		"timestamp": 1670096837624,
		"nombre": "Cafe",
		"descripcion": "Cafe",
		"codigo": "Cafe",
		"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
		"precio": 800,
		"stock": 10,
		"_id": "63acb41840a3d442f972f4c9"
	},
	{
		"idStore": 2,
		"timestamp": 1670096837624,
		"nombre": "Capuchino",
		"descripcion": "Capuchino",
		"codigo": "Capuchino",
		"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-03-512.png",
		"precio": 1000,
		"stock": 15,
		"_id": "63acb41e40a3d442f972f4d3"
	}
]
```
</details>
<br>

<details>
<summary>POST <b>/api/carrito/:id1/productos/:id2 </b></summary> 

```js
POST http://localhost:8080/api/carrito/640241de63d5e918cbdb83bc/productos/1
```
### Respuesta

```json
{
	"ok": "Se agrego el producto al carrito"
}
```
</details>
<br>



<details>
<summary>DELETE <b>/api/carrito/:id1/productos/:id_prod </b></summary> 

```js
DELETE http://localhost:8080/api/carrito/640241de63d5e918cbdb83bc/productos/1
```

### Respuesta

```json
{
	"ok": "El producto fue eliminado del carrito"
}
```
</details>
<br>


<details>
<summary>POST <b>/api/login </b></summary> 

```js
POST http://localhost:8080/api/login
```
### Solicitud

```json
{	
	"username": "candela@candela.com",
	"password": "candela-password"
}
```
	
### Respuesta

```json
{
	"ok": "Se inicio sesion correctamente",
	"productos disponibles": {
		"0": {
			"idStore": 3,
			"descripcion": "Capuchino",
			"timestamp": 1670096837624,
			"nombre": "Capuchino",
			"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-03-512.png",
			"stock": "15",
			"precio": "1000",
			"codigo": "Capuchino"
		},
		"1": {
			"codigo": "Capuchino",
			"precio": 1000,
			"timestamp": 1670096837624,
			"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-03-512.png",
			"nombre": "Capuchino",
			"descripcion": "Capuchino",
			"stock": 15,
			"idStore": 2
		},
		"2": {
			"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
			"codigo": "Cafe",
			"idStore": 1,
			"stock": 10,
			"timestamp": 1670096837624,
			"precio": 800,
			"descripcion": "Cafe",
			"nombre": "Cafe"
		}
	},
	"su carrito": {
		"_id": "640271314e5af1b4ad62c59f",
		"timestamp": 1677881649798,
		"productos": [],
		"__v": 0
	}
}
```
</details>
<br>


<details>
<summary>POST <b>/api/register </b></summary> 

```js
POST http://localhost:8080/api/register
```
### Solicitud

```json
{
	"username": "candela@candela.com",
	"password": "candela-password",
	"nombre": "candela",
	"direccion": "Calle falsa 123",
	"edad": 22,
	"telefono": 1155550000,
	"avatar": "https://cdn4.iconfinder.com/data/icons/avatars-xmas-giveaway/128/avocado_scream_avatar_food-512.png"
}
```
	
### Respuesta

```json
{
	"ok": "Usuario registrado correctamente"
}
```
</details>
<br>

<details>
<summary>GET <b>/api/fail-login </b></summary> 

```js
POST http://localhost:8080/api/login
```
### Solicitud

```json
{	
	"username": "usuario-incorrecto",
	"password": "contraseña-incorrecta"
}
```
	
### Respuesta

```json
{
	"error": "Usuario y contraseña incorrectos"
}
```
</details>
<br>

<details>
<summary>GET <b>/api/fail-register </b></summary> 

```js
POST http://localhost:8080/api/register
```
### Solicitud

```json
{
	"username": "usuario-en-uso",
	"password": "password",
	"nombre": "Candela",
	"direccion": "Calle falsa 123",
	"edad": 22,
	"telefono": 1155550000,
	"avatar": "https://cdn4.iconfinder.com/data/icons/avatars-xmas-giveaway/128/avocado_scream_avatar_food-512.png"
}
```
	
### Respuesta

```json
{
	"error": "El usuario esta en sesion"
}
```
</details>
<br>

<details>
<summary>GET <b>/api/home </b></summary> 

```js
GET http://localhost:8080/api/home
```
	
### Respuesta

```json
{
	"ok": "Inicio de sesion",
	"productos disponibles": {
		"0": {
			"stock": "15",
			"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-03-512.png",
			"timestamp": 1670096837624,
			"descripcion": "Capuchino",
			"nombre": "Capuchino",
			"codigo": "Capuchino",
			"idStore": 3,
			"precio": "1000"
		},
		"1": {
			"codigo": "Capuchino",
			"nombre": "Capuchino",
			"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-03-512.png",
			"descripcion": "Capuchino",
			"timestamp": 1670096837624,
			"stock": 15,
			"idStore": 2,
			"precio": 1000
		},
		"2": {
			"foto": "https://cdn2.iconfinder.com/data/icons/coffee-store/64/coffee-04-512.png",
			"codigo": "Cafe",
			"descripcion": "Cafe",
			"timestamp": 1670096837624,
			"idStore": 1,
			"precio": 800,
			"stock": 10,
			"nombre": "Cafe"
		}
	},
	"su carrito": {
		"_id": "640271314e5af1b4ad62c59f",
		"timestamp": 1677881649798,
		"productos": [],
		"__v": 0
	}
}
```
</details>
<br>

<details>
<summary>GET <b>/api/succesfull-register </b></summary> 

```js
POST http://localhost:8080/api/register
```
### Solicitud

```json
{
	"username": "candela@candela.com",
	"password": "candela-password",
	"nombre": "candela",
	"direccion": "calle falsa 123",
	"edad": 22,
	"telefono": 1122333445,
	"avatar": "https://cdn4.iconfinder.com/data/icons/avatars-xmas-giveaway/128/avocado_scream_avatar_food-512.png"
}
```
	
### Respuesta

```json
{
	"ok": "Usuario registrado correctamente"
}
```
</details>


<details>
<summary>GET <b>/api/logout </b></summary> 

```js
GET http://localhost:8080/api/logout
```
	
### Respuesta

```json
{
	"ok": "Se cerro la sesion correctamente"
}
```
</details>


<details>
<summary>POST <b>/api/pedido </b></summary> 

```js
POST http://localhost:8080/api/pedido
```
	
### Respuesta

```json
{
	"ok": "Se confirmo su compra con el codigo: 6404c8f71a63250879cf2a23"
}
```
</details>






















=======
# ProyectoFinalBackend
Proyecto final de backend Candela Dominguez Barco
>>>>>>> 02c151287135d41b1c8c5cef96d8454baf63091a
