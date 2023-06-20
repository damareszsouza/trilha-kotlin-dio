# trilha-kotlin-dio

DESCRIÇÃO
Crie uma solução em Koltin abstraindo o domínio das "Formações Educacionais da DIO". Nesse contexto, você será desafiado a evoluir um algoritmo que explora o conceito de Programação Orientada a Objetos (POO) no domínio em questão. Sendo assim, você deverá melhorar essa abstração e resolver os TODOs definidos no código.

Para abstrair o domínio das Formações Educacionais da DIO em Kotlin, podemos criar uma hierarquia de classes que representam as diferentes formações oferecidas pela plataforma.

Podemos definir a classe Formacao como a classe base, que terá as propriedades comuns a todas as formações, como o nome e a carga horária. Em seguida, podemos definir as classes Curso e Bootcamp que herdam da classe Formacao e adicionam propriedades específicas.

Segue abaixo uma possível implementação dessa abstração:

#   codigo kotlin

open class Formacao(val nome: String, val cargaHoraria: Int)

class Curso(nome: String, cargaHoraria: Int, val categoria: String) : Formacao(nome, cargaHoraria)

class Bootcamp(nome: String, cargaHoraria: Int, val cursos: List<Curso>) : Formacao(nome, cargaHoraria) {
    fun adicionarCurso(curso: Curso) {
        cursos.plus(curso)
    }
}


open class Formacao(val nome: String, val cargaHoraria: Int)

class Curso(nome: String, cargaHoraria: Int, val categoria: String) : Formacao(nome, cargaHoraria)

class Bootcamp(nome: String, cargaHoraria: Int, val cursos: List<Curso>) : Formacao(nome, cargaHoraria) {
    fun adicionarCurso(curso: Curso) {
        cursos.plus(curso)
    }
} 


Nessa implementação, a classe Formacao é definida com as propriedades nome e cargaHoraria. Essa classe é abstrata e serve como classe base para as outras classes.

A classe Curso é definida com as propriedades nome, cargaHoraria e categoria. Essa classe herda da classe Formacao utilizando a palavra-chave :, indicando que Curso é uma subclasse de Formacao.

A classe Bootcamp é definida com as propriedades nome, cargaHoraria e cursos. Essa classe também herda da classe Formacao.

Além das propriedades, a classe Bootcamp possui o método adicionarCurso(curso: Curso) que adiciona um curso à lista de cursos do bootcamp.

Com essa abstração, podemos criar objetos que representam as formações educacionais oferecidas pela DIO:

#  codigo kotlin

val cursoAndroid = Curso("Desenvolvimento Android", 40, "Mobile")
val cursoKotlin = Curso("Desenvolvimento Kotlin", 30, "Backend")
val bootcampMobile = Bootcamp("Bootcamp Mobile", 200, listOf(cursoAndroid))
bootcampMobile.adicionarCurso(cursoKotlin) 


Nesse código, são criados dois objetos Curso representando os cursos de "Desenvolvimento Android" e "Desenvolvimento Kotlin", respectivamente. Em seguida, é criado um objeto Bootcamp representando o bootcamp de "Mobile" que inicialmente possui apenas o curso de "Desenvolvimento Android". Por fim, é adicionado o curso de "Desenvolvimento Kotlin" ao bootcamp utilizando o método adicionarCurso.

Com essa abstração, podemos representar de forma mais clara e organizada as formações educacionais oferecidas pela DIO, permitindo uma melhor manipulação e gerenciamento desses dados em uma aplicação.
