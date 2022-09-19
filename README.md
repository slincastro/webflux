# Creando un nuevo proyecto con webflux en 10 pasos desde 0

[Referencia](https://github.com/bancolombia/scaffold-clean-architecture)

1) Crear un directorio :

`mkdir test-bc`

> la version de gradle debe ser 6.9 or superior

2) Que version de gradle tengo :

`gradle -v `

 si no tengo instalo gradle :

`brew install gradle`

4) Iniciar graddle en el proyecto:

`cd test-bc`

`gradle init`

5) Actualizar Gradle seteando la version del gradle wrapper :

` ./gradlew wrapper --gradle-version=6.9`

6) Incluir el plugin de bancolombia :

`
echo "plugins {
    id \"co.com.bancolombia.cleanArchitecture\" version \"2.4.4\"
}" > build.gradle
`

7) Generar el scafold : 

`gradle cleanArchitecture --package=co.com.bancolombia --name=NameProject --type=reactive --coverage=jacoco --lombok=true`

8) correr la application :

`./gradlew bootrun`

9) Incluir el nuevo entrypoint :

`gradle generateEntryPoint --type=webflux`

10) Consumir el endpoint :

`http://localhost:8080/api/usecase/path`

`curl --location --request GET 'http://localhost:8080/api/usecase/path`
`
