# ![EduPay](https://user-images.githubusercontent.com/61607058/201572233-c22a4876-725a-44c5-aca2-668238f56862.png)

Plataforma de pagos en linea para institución de educación superior.

![Landingpage](https://user-images.githubusercontent.com/61607058/201576500-f502950a-5c80-4d31-a044-244e7ca2cd23.png)

## Construcción
```mermaid
graph TD
A(Instalar MySql) -->B(Usar usuario: root y constraseña: root)
    B --> C(Montar las bases de datos - Repositorio: DataBases - EduPay)
    C --> D(Descargar todos los repositorios de APIs en una misma carpeta)
    D --> E(Tomar los archivos de To_Build y sacarlos a la carpeta padre)
    E --> F(Descargar las dependencias en cada carpeta usando el ejecutable npm_install.cmd)
    F --> G(Poner tus credenciales de la base de datos en db_credentials.js)
```
<h3 align="center"> Tu carpeta debería verse así </h3>
<div align="center">
  
![image](https://user-images.githubusercontent.com/61607058/203145131-634c558d-ef94-499f-9ba7-daeb772ec609.png)

</div>
  
```mermaid
graph TD
A(Doble clic en el archivo run.cmd) -->B(fa:fa-spinner Esperar un minuto a que todo esté listo)
B --> C(Ir a la consola pertenciente al proyecto en React - Tiene Vite de titulo)
C --> D(Poner el url en el navegador)
D --> E(("¡Todo listo!"))
```

## Arquitectura 🌐

![Diagrama de despliegue - Página 1](https://user-images.githubusercontent.com/61607058/201572704-8441ee21-7604-4ed8-af1c-35bb828ee010.png)

## Base de datos (Sistema institucional) 🏫

![sistemainst](https://user-images.githubusercontent.com/61607058/201577941-17f26371-b71c-4f97-bfaf-62927aa9508f.png)

## Base de datos (Sistema de bancos) 🏦

![sistemabanc](https://user-images.githubusercontent.com/61607058/201578060-f189e396-9bbc-41ec-b34d-715b14b12fc0.png)

## API Gateway 🚚 ([Documentación](https://github.com/Diseno-de-Software-2/API-Gateway-EduPay#readme))

## Servicio de consultas ❔

## Servicos de cuentas 🧑

## Servicio de pago 💵

## Servicio de autorización 🔒

## Servicio de consulta de saldos 💸  ([Documentación](https://github.com/Diseno-de-Software-2/Balance-API-EduPay#readme))

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
