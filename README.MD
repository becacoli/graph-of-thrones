# Graph of Thrones :crown:

Produzido por: Rebeca Queiroz e Wemilly Souza.

## Sumário

1. [Introdução](#introdução)
2. [Modelagem](#modelagem)
3. [Instalação](#instalação)
4. [Uso](#uso)

### Introdução
    Nesse projeto, usaremos um banco de dados baseado em grafos usando [Neo4j](https://neo4j.com/) e Docker para armazenar dados dos personagens da série chamada Game of Thrones.

    A linguagem utilizada para interagir com os dados se chama (https://neo4j.com/developer/cypher/). Ela é usada pelo Neo4j como linguagem de query. Sendo assim, é com ela que faremos algumas consultas nesse tutorial.

    Os dados foram inseridos de forma manual para explicar a relação entre eles. 

### Modelagem
   A modelagem de dados no Neo4j é realizada por meio de grafos, onde os nós representam as entidades e os relacionamentos entre eles representam as relações entre as entidades.

    Neste modelo, cada personagem é representado como um nó com duas propriedades: nome e casa à qual pertence. Os relacionamentos entre eles são modelados como arestas direcionadas com rótulos que indicam a relação parental entre eles, como "FATHER" ou "MOTHER".

    Essa abordagem permite representar relações complexas de forma clara e eficiente. Além disso, o uso de grafos permite consultas e análises rápidas e flexíveis, que podem ser utilizadas para obter insights valiosos em dados complexos.


