# ![EduPay](https://user-images.githubusercontent.com/61607058/201572233-c22a4876-725a-44c5-aca2-668238f56862.png)

Plataforma de pagos en linea para institución de educación superior.

![Landingpage](https://user-images.githubusercontent.com/61607058/201576500-f502950a-5c80-4d31-a044-244e7ca2cd23.png)

## Construcción
```mermaid
graph TD
A(Instalar MySql) -->B(Usar usuario: root y constraseña: root)
    B --> C(Montar las bases de datos - Repositorio: DataBases - EduPay)
    C --> D(Descargar todos los repositorios de APIs en una misma carpeta)
    D --> E(Descargar las dependencias en cada carpeta usando: npm install)
    E --> F(Tomar los archivos de To_Build y sacarlos a la carpeta padre)
```
<h3 align="center"> Tu carpeta debería verse así </h3>
<div align="center">
  
![Screenshot 2022-11-13 231357](https://user-images.githubusercontent.com/61607058/201573894-4e5d5d17-1f04-4fd2-ac9a-527af7ef3beb.png)

</div>
  
```mermaid
graph TD
A(Doble clic en el archivo run.cmd) -->B(fa:fa-spinner Esperar un minuto a que todo esté listo)
B --> C(Ir a la consola pertenciente al proyecto en React - Tiene Vite de titulo)
C --> D(Poner el url en el navegador)
D --> E(("¡Todo listo!"))
```

## Requisitos 📅

- [ ] Debe disponer de una pantalla para capturar los datos de la transacción a efectuar.

- [ ] Se debe validar saldos.

- [ ] Se debe validar tipos de tarjetas de crédito (solo Visa, Mastercard y American Express). Para el caso del trabajo un cliente solo podrá tener tarjetas de dos bancos: el East Bank y el Western Bank.

- [ ] Posibilidad de pagar con tarjeta debido y o crédito. Cuando se refieran al pago con tarjeta débito se referirán al pago con PSE.

- [ ] Cuando el cliente no tenga el medio de pago activo, se debe informar y no permitir la transacción. 

- [ ] Los medios de pago deben existir para quien intenta comprar. Es decir, las tarjetas de crédito o medios de pagos deben existir.

- [ ] Validar que la transacción de descuento se efectué así la aplicación base no esté disponible. Webhook.

- [ ] Validar que el valor a pagar sea mayor que cero.

- [ ] La solución debe contar con alta disponibilidad, para que, si un nodo no está disponible, otro pueda responder.

- [ ] Implementar consulta de saldo en el medio de pago. Antes de comprar existirá una opción para que el cliente pueda consultar el saldo de todas sus tarjetas débito o crédito (Composición). Esta opción podrá deshabilitarse en algún momento y aun así podrá realizarse una transacción de pago.

- [ ] Los datos básicos a capturar son: nombre completo, email e identificación del comprador, concepto de pago, sede, monto a comprar, medio de pago, incluido franquicia, nro de cuotas cuando aplica. La fecha, hora y número de transacción son generados por el sistema.

- [ ] El sistema debe mostrar la cliente el resultado de la transacción sea exitoso o no.

- [ ] Se debe contar con un registro de transacciones exitosas o no.

- [ ] La solución debe manejar la disponibilidad del servicio de consulta o compra, es decir debe mostrar mensajes controlados si estos servicios no están disponibles. 
(Circuit Breaker)

- [ ] Se debe aplicar el mejor estilo arquitectural que permita: cohesión, encapsulamiento, bajo acoplamiento, interdependencia al máximo nivel posible.

- [ ] Es un mismo momento es posible que uno de los bancos no tenga activos los servicios de consulta y/o compra o retiro, esto debe validarse.

- [ ] La interfaz de las tablas de parámetros no es necesario que se construyan, los datos de parámetros se pueden ingresar por base de datos, pero sí se deben elaborar los bocetos de estas interfaces.

- [ ] La solución debe contar con ayudas para orientar el usuario en caso de dudas.


## Arquitectura 🌐

![Diagrama de despliegue - Página 1](https://user-images.githubusercontent.com/61607058/201572704-8441ee21-7604-4ed8-af1c-35bb828ee010.png)

## Base de datos (Sistema institucional) 🏫

![sistemainst](https://user-images.githubusercontent.com/61607058/201577941-17f26371-b71c-4f97-bfaf-62927aa9508f.png)

## Base de datos (Sistema de bancos) 🏦

![sistemabanc](https://user-images.githubusercontent.com/61607058/201578060-f189e396-9bbc-41ec-b34d-715b14b12fc0.png)

## API Gateway 🚚

### Registry json

En este json se registra la cantidad de instancias por servicios que se tienen activas y si estas están activas o inactivas

```json

{
  "services": {
    "auth": {
      "loadBalancerStrategy": "ROUND_ROBIN",
      "index": 0,
      "instances": []
    },
    "query": {
      "loadBalancerStrategy": "ROUND_ROBIN",
      "index": 0,
      "instances": []
    },
    "account": {
      "loadBalancerStrategy": "ROUND_ROBIN",
      "index": 0,
      "instances": []
    },
    "balance": {
      "loadBalancerStrategy": "ROUND_ROBIN",
      "index": 0,
      "instances": []
    },
    "pay": {
      "loadBalancerStrategy": "ROUND_ROBIN",
      "index": 0,
      "instances": []
    }
  }
}

```

## Servicio de consultas ❔

## Servicos de cuentas 🧑

## Servicio de pago 💵

## Servicio de autorización 🔒

## Servicio de consulta de saldos 💸

---

### **Consultar credito de tarjeta**
* **URL**

  _/credito-tarjeta-:numero_

* **Method:**
  `GET`
  
*  **URL Params**

   **Required:**
 
   `numero=[integer]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ credito : 50000 }`
  * **Code:** 200 <br />
    **Content:** `Consultas deshabilitadas`
 
* **Error Response:**
  * **Code:** 
    **Content:** `{ error : ... }`
---

---

### **Consultar saldo de cuenta**
* **URL**

  _/saldo-cuenta-:numero_

* **Method:**
  `GET`
  
*  **URL Params**

   **Required:**
 
   `numero=[integer]`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `{ credito : 50000 }`
  * **Code:** 200 <br />
    **Content:** `Consultas deshabilitadas`
 
* **Error Response:**
  * **Code:** 
    **Content:** `{ error : ... }`
---

## API de bancos 🏧




<!--
![Enunciado_page-0001](https://user-images.githubusercontent.com/61607058/198183272-3ffca75a-092b-435e-8a41-9ffed67ee677.jpg)
![Enunciado_page-0002](https://user-images.githubusercontent.com/61607058/198183275-1211345f-e1fb-4cd5-b022-a772d4bf83f0.jpg)
![Enunciado_page-0003](https://user-images.githubusercontent.com/61607058/198183277-a968c48e-8cf4-4a20-8fe3-600c362c4fb6.jpg)
![Enunciado_page-0004](https://user-images.githubusercontent.com/61607058/198183263-c2388e2e-2193-48a8-8178-f124f5756906.jpg)
![Enunciado_page-0005](https://user-images.githubusercontent.com/61607058/198183266-548ca9f9-25b4-4431-98e1-7bb2cf22de18.jpg)
![Enunciado_page-0006](https://user-images.githubusercontent.com/61607058/198183269-9a68e6e7-6af0-4009-a950-e67de03ce011.jpg)
-->

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
