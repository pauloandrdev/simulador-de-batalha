# 🧙‍♂️ Simulador de Batalha de Fantasia Medieval

Um simulador de batalhas entre personagens por turnos ambientado em um rico mundo de fantasia medieval. Este projeto demonstra princípios abrangentes da programação orientada a objetos, proporcionando uma experiência envolvente de simulação de batalhas.

## 📌 Visão Geral do Projeto

Este simulador de batalha permite que os jogadores criem e personalizem personagens de diferentes classes (Guerreiro, Mago, Arqueiro), equipem-nos com diversos itens e participem de batalhas por turnos. O projeto exibe conceitos de programação orientada a objetos, incluindo herança, polimorfismo, mixins, composição e associação.

## 🌍 Universo & Contexto

O simulador se passa no reino de Eldoria, um mundo de fantasia medieval onde magia e habilidades marciais coexistem. Diversas classes de personagens utilizam diferentes poderes:

- **Guerreiros**: Mestres do combate físico com força superior e alta capacidade defensiva  
- **Magos**: Usuários de magia arcana com feitiços poderosos, mas defesa física limitada  
- **Arqueiros**: Especialistas em combate à distância com alta precisão e chance de golpe crítico  

## 📝 Casos de Uso

### Criando um Personagem
1. O usuário seleciona uma classe (Guerreiro, Mago, Arqueiro)  
2. O usuário personaliza os atributos (nome, aparência, estatísticas)  
3. O usuário atribui o equipamento inicial  
4. O sistema salva o personagem  

### Iniciando uma Batalha
1. O usuário seleciona dois personagens para batalhar  
2. O sistema inicializa a arena de batalha  
3. A batalha ocorre em turnos  
4. O sistema registra e exibe as ações do combate  
5. Um vencedor é determinado quando a vida de um personagem chega a zero  

### Gerenciando o Inventário do Personagem
1. O usuário seleciona um personagem  
2. O usuário adiciona, remove ou equipa itens  
3. O sistema atualiza os atributos com base nos equipamentos  
4. As alterações são salvas  

### Salvando/Carregando Progresso
1. O usuário seleciona a opção de salvar  
2. O sistema serializa os dados do personagem  
3. Os dados são armazenados de forma persistente  
4. O usuário pode carregar os personagens salvos posteriormente  

## 📊 Diagrama de Classes

```
+-------------------+       +-------------------+       +-------------------+
|    Personagem     |<------|     Combate       |       |   Habilidade      |
+-------------------+       +-------------------+       +-------------------+
| - nome            |       | - personagem1     |       | - nome            |
| - nivel           |       | - personagem2     |       | - descricao       |
| - vida            |       | - turno_atual     |       | - custo           |
| - forca           |       | - log_combate     |       | - efeito          |
| # habilidades     |       +-------------------+       +-------------------+
| # inventario      |       | + iniciar()       |               ▲
+-------------------+       | + proximo_turno() |               |
| + atacar()        |       | + finalizar()     |    +---------+---------+
| + defender()      |       +-------------------+    |                   |
| + usar_habilidade()|                               |                   |
+-------------------+                          +-------------+   +-------------+
         ▲                                     | Magica      |   | Fisica      |
         |                                     +-------------+   +-------------+
+--------+--------+                            | - mana      |   | - stamina   |
|                 |                            +-------------+   +-------------+
|                 |
+--------+--------+--------+
|        |        |        |
+--------+  +-----+  +-----+
| Guerreiro | Mago  | Arqueiro |
+--------+  +-----+  +-----+
| + furia   | + mana | + precisao|
+---------+ +------+ +-------+
```

## 🛠️ Tecnologias Utilizadas

- **Python 3.10+**: Lógica principal e implementação POO  
- **Flask**: Servidor web para o frontend  
- **HTML/CSS**: Design da interface do usuário  
- **Pickle/JSON**: Serialização de dados para salvar/carregar estado  

## 🚀 Primeiros Passos

1. Clone o repositório  
2. Instale as dependências: `pip install -r requirements.txt`  
3. Execute a aplicação: `python main.py`  
4. Acesse a interface web em `http://localhost:5000`  

## 🔄 Estrutura do Projeto

```
simulador_batalha/
├── README.md
├── main.py
├── requirements.txt
├── package/
│   ├── personagens/
│   │   ├── base.py
│   │   ├── guerreiro.py
│   │   ├── mago.py
│   │   ├── arqueiro.py
│   │   ├── mixins.py
│   ├── combate.py
│   ├── habilidades.py
│   ├── inventario.py
│   ├── banco.py
├── templates/
│   ├── index.html
│   ├── create.html
│   ├── battle.html
│   ├── inventory.html
├── static/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── main.js
│   ├── images/
```

## 📈 Critérios de Avaliação

- Funcionalidade do programa com todos os recursos requeridos (6 pts)  
- Modelagem POO com herança, polimorfismo, mixins, composição, associação (6 pts)  
- Serialização de objetos para salvar estado dos personagens (6 pts)  
- Interface gráfica funcional e clara (2 pts) 
