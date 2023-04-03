# Graph of Thrones :crown:

Produzido por: Rebeca Queiroz e Wemilly Souza.

## Sumário

1. [Introdução](#introdução)
2. [Modelagem](#modelagem)
3. [Instalação](#instalação)
4. [Consultas](#consultas)

### Introdução
Nesse projeto, usaremos um banco de dados baseado em grafos usando [Neo4j](https://neo4j.com/) e Docker para armazenar dados dos personagens da série chamada Game of Thrones.

A linguagem utilizada para interagir com os dados se chama (https://neo4j.com/developer/cypher/). Ela é usada pelo Neo4j como linguagem de query. Sendo assim, é com ela que faremos algumas consultas nesse tutorial.

Os dados foram inseridos de forma manual para explicar a relação entre eles. 

### Modelagem
A modelagem de dados no Neo4j é realizada por meio de grafos, onde os nós representam as entidades e os relacionamentos entre eles representam as relações entre as entidades.

Neste modelo, cada personagem é representado como um nó com duas propriedades: nome e casa à qual pertence. Os relacionamentos entre eles são modelados como arestas direcionadas com rótulos que indicam a relação parental entre eles, como "FATHER" ou "MOTHER".

Essa abordagem permite representar relações complexas de forma clara e eficiente. Além disso, o uso de grafos permite consultas e análises rápidas e flexíveis, que podem ser utilizadas para obter insights valiosos em dados complexos.

### Instalação

### Consultas

    Para realizar as consultas, após adicionar os dados, usaremos alguns comandos Cypher.


1. **Para selecionar todos os nós e relacionamentos**

   ```cypher
   MATCH (n) RETURN n;
   ```
2. **Para selecionar os nós conectados por meio da relação "MOTHER" com o nó do nome da mãe**

    ```cypher 
    MATCH (c:Character {name: 'Cersei Lannister'})-[:MOTHER]->(child:Character) RETURN child.name
    ```

     ```cypher 
    MATCH (c:Character {name: 'Catelyn Stark'})-[:MOTHER]->(child:Character)
    RETURN child.name
    ```

3. **Para selecionar o nome de todos os personagens que pertencem à casa Lannister**

    ```cypher 
    MATCH (c:Character {house: 'Lannister'})
    RETURN c.name
    ```
4. **Para selecionar o nome de todos os personagens que não contêm a letra a no nome**
    ```cypher 
    MATCH (character:Character)
    WHERE NOT character.name CONTAINS 'a'
    RETURN character
    ```

5. **Para selecionar o nome de todos os personagens que não contêm a letra a no nome**
    ```cypher 
    MATCH (character:Character)
    WHERE character.name CONTAINS 'a'
    RETURN character
    ```
5. **Para selecionar o nome de todos os personagens do gênero feminino**

    ```cypher
    MATCH (character:Character)
    WHERE character.gender = 'masculine'
    RETURN character
    ```

    
