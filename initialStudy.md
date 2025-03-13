# Pesquisa sobre ROS2

-Tópico <br>
-Publisher <br>
-Subscriber <br>
-Nós <br>
-Serviços e Cliente <br>


### Tópico:

O tópico é como se fosse uma interface que é usada pra compartilhamento de data contínuo, tipo ler os dados de um sensor, o estado de alguma coisa e etc. ELe usa o modelo publish-subscribe, e a sua comunicação é **assíncrona** e baseada em mensagens.

### Publisher:

Os publisher's podem ser vistos como "produtores" de dados, que serão posteriormente consumidos pelos Subscriber's. Ao criar um Publisher, nós atribuimos uma String à ele que seria como o "nome" do tópico.
Uma vez que os dados são publicados, todos os subscriber's que pertence ao mesmo tópico vão receber os dados. 
É importante dizer que podem haver mais de um Publisher publicando no mesmo tópico, e ele(s) não dependem do Subscriber ler a mensagem para continuar publicando, isso é feito de forma assíncrona.

### Subscriber:

Os Subscriber's podem ser vistos como "consumidores" de dados gerados pelos Publisher's. Ao criar um Subscriber nós também atribuimos à ele uma String que seria o "nome" do tópico, e ele receberá dados somente desse tópico.
Assim como no Publisher, podem haver mais de um Subscriber "consumindo" os dados de um mesmo tópico, e eles só consumirão esses dados caso haja um Publisher publicando algo.

### Nós:

Os nós são grafos em que cada aresta executa uma tarefa diferente, e a comunicação entre esses nós que é feita com a ROS2 pode ser com nós do mesmo processo, de diferentes processos ou até mesmo de outra máquina. Além disso, eles aparentemente podem receber parâmetros que permitem que mudem o seu comportamento em tempo de execução. Os nós também podem publicar em alguns tópicos para transmitir dados para outros nós, ou até mesmo se comportar como os subscribers pra poder obter esses dados.

### Serviços e Cliente:

A definição de serviço no ROS2 pode ser entendida como uma chamada procedural remota, ou seja, um nó pode fazer uma chamada procedural remota pra outro nó que vai fazer um processamento e retornar um resultado.
No ROS2,é esperado que os serviços retornem sempre rápido, pois na maioria das vezes o cliente vai estar esperando pelo resultado. Por esse motivo, o serviço nunca deve ser usado pra fazer um processe muito longo.
Os serviços são identificados por um nome de serviço, parecido com os nomes dos tópicos, e eles contem duas partes: service server e service client.

Obs: diferentemente dos tópicos, a comunicação entre os serviços é síncrona, ou seja, uma vez enviada uma requisição ele ficará esperando pela resposta. Por esse motivo os serviços podem ser usados para tarefas menos frequentes e menores, enquanto os tópicos são melhores para dados contínuos.

Service Server: é uma entidade que aceida uma requisição procedural remota e vai executar algum processamento com base nisso.

Service Client: é uma entidade que vai requisitar um service server remoto pra performar alguma coisa no nome dele. 

Exemplo:

```
uint32 a
uint32 b
uint32 sum
```
Nesse caso, o Service client que "cria' essa mensagem inicial contendo a e b, e espera o Service server processar a soma e retornar o resultado.


### Fontes:

- https://docs.ros.org/en/jazzy/Concepts/Basic/About-Topics.html
- https://docs.ros.org/en/jazzy/Concepts/Basic.html
- https://docs.ros.org/en/jazzy/Concepts/Basic/About-Nodes.html
- https://docs.ros.org/en/jazzy/Concepts/Basic/About-Services.html
