![Ironhack logo](https://i.imgur.com/1QgrNNw.png) 

# Proyecto Kaggle Machine Learning

<p align="center"> <img src="https://www.unthinkable.fm/wp-content/uploads/2021/07/m1.jpg" width="700" height="350">  </p>

# 📈OBJETIVO

- Preparar los datos para los diversos modelos (proceso empírico) 
- Entrenar y Testear modelos de Machine Learning
- Subir el mejor modelo entrenado de Machine Learning

---

## 📚RECURSOS

- Salaries_data.csv (Datos para trabajar)
- Testeo.csv (Datos para predecir)
- Muestra.csv (Ejemplo de resultados que deben subir a Kaggle)

## 🔍INFO DE COLUMNAS 
- *work_year:* The year the salary was paid.
- *experience_level:* The experience level in the job during the year
- *employment_type:* The type of employment for the role
- *job_title:* The role worked in during the year.
- *salary:* The total gross salary amount paid.
- *salary_currency:* The currency of the salary paid as an ISO 4217 currency code.
- *salaryinusd:* The salary in USD
- *employee_residence:* Employee's primary country of residence in during the work year as an ISO 3166 country code.
- *remote_ratio:* The overall amount of work done remotely
- *company_location:* The country of the employer's main office or contracting branch
- *company_size:* The median number of people that worked for the company during the year

---

# PROCEDIMIENTO Y CONCLUSIÓN

En primer lugar, hemos cargado los archivos con los cuales realizaremos la mejor predicción salarial.

Hemos empezado analizando cada columna y decidimos eliminar las columnas:'salary','salary_currency','employee_residence', porque no aportan información importante para la prediccion que queremos hacer. Además, contamos con otra columna 'salary_in_usd' que esa será nuestra variable 'y' y nos proporciona datos mas detallados que las columnas que acabamos de eliminar.

Posteriormente, despues de haber limpiado y modificado columnas de diferentes formas y de haber usado diferentes modelos de predicción, vemos que la siguiente limpieza es la que más se acerca a nuestro objetivo, es decir la que menos error muestral tiene:

 - Modificamos la columna 'job_title' y nos quedamos con solamente estas 4 variables:

    ==> Machine Learning
    ==> Data Engineer
    ==> Data Analyst
    ==> Data Scientist

 - Reemplazamos, en la columna 'employment_type',  los valores CT y FL por PT y FT respectivamente para quedarnos con esas 2 variables únicamente para tener una mejor predicción en el modelo.

    Posteriormente, creamos una funcion para asignar una escala numerica a esas dos variables, PT y FT. Siendo 1 y 0.5 respectivamente

 - En la columna 'experience_level' asignamos un número en función de la categoria/experiencia que tenga el empleado. A mayor experiencia, asignaremos un número más alto.

 - Observamos que la columna 'company_location', contiene diez paises qlos cuales más se repiten. Nos quedamos con esos paises y el resto lo agrupamos en 'Other'

A continuación, con el método one-hot encoding, utilizaremos la función get_dummies para evitar la colinealidad. Transformaremos los datos a 0 o 1.

Una vez que importamos los modelos, los iniciamos y entrenamos. 
A la hora de la predicción y evaluación podemos observar que los modelos Ridge y PoissonRegressor nos muestran los errores más bajos con un r2 en torno al 60%. 





 