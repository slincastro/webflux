# Creando un nuevo proyecto desde 0


Crear un directorio :

`mkdir test-bc`

* la version de gradle debe ser 6.9 or superior

Que version de gradle tengo :

`gradle -v `

si no tengo instalo gradle :

`brew install gradle`

Iniciar graddle en el proyecto:

`cd test-bc`

`gradle init`

Actualizar Gradle seteando la version del gradle wrapper :
>` ./gradlew wrapper --gradle-version=6.9`


Incluir el plugin de bancolombia :

`
echo "plugins {
    id \"co.com.bancolombia.cleanArchitecture\" version \"2.4.4\"
}" > build.gradle
`

Generate scafold : 

`gradle cleanArchitecture --package=co.com.bancolombia --name=NameProject --type=reactive --coverage=jacoco --lombok=true`

Run application :

`./gradlew bootrun`

Include new entrypoint :

`gradle generateEntryPoint --type=webflux`

Hit the endpoint :

`http://localhost:8080/api/usecase/path`

`curl --location --request GET 'http://localhost:8080/api/usecase/path'
`
