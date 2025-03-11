# Pesquisa sobre ROS2

-Tópico <br>
-Publisher <br>
-Subscriber <br>
-Nós <br>
-Serviços e Cliente <br>


### Tópico:

Permite o contato entre Publisher's e Subscriber's.

### Publisher:

Os publisher's podem ser vistos como "produtores" de dados, que serão posteriormente consumidos pelos Subscriber's. Ao criar um Publisher, nós atribuimos uma String à ele que seria como o "nome" do tópico.
Uma vez que os dados são publicados, todos os subscriber's que pertence ao mesmo tópico vão receber os dados. 
É importante dizer que podem haver mais de um Publisher publicando no mesmo tópico, e ele(s) não dependem do Subscriber ler a mensagem para continuar publicando, isso é feito de forma assíncrona.

### Subscriber:

Os Subscriber's podem ser vistos como "consumidores" de dados gerados pelos Publisher's. Ao criar um Subscriber nós também atribuimos à ele uma String que seria o "nome" do tópico, e ele receberá dados somente desse tópico.
Assim como no Publisher, podem haver mais de um Subscriber "consumindo" os dados de um mesmo tópico, e eles só consumirão esses dados caso haja um Publisher publicando algo.

### Nós:

### Serviços e Cliente:



### Fontes:

- https://docs.ros.org/en/jazzy/Concepts/Basic/About-Topics.html
- https://docs.ros.org/en/jazzy/Concepts/Basic.html
- https://docs.ros.org/en/jazzy/Concepts/Basic/About-Nodes.html
- https://docs.ros.org/en/jazzy/Concepts/Basic/About-Services.html
