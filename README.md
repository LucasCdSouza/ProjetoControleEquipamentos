# Sistema de Controle Patrimonial de equipamentos de TI na GEXSTM

Sistema para o controle patrimonial de equipamentos de TI da Gerência Executiva do INSS, totalmente desenvolvido em Java para auxiliar no gerenciamento de computadores, monitores e impressoras.

---

## Sobre o Projeto

O **Sistema de Controle Patrimonial de Equipamentos de TI** foi desenvolvido com o objetivo de resolver uma lacuna encontrada durante o meu estágio na área de Tecnologia da Informação na Gerência Executiva do INSS de Santa Maria (GEXSTM), e também, para trabalhar com todos os conceitos da disciplina de Programação Orientada a Objetos.

Durante as atividades diárias no estágio, é necessário manter o controle patrimonial dos equipamentos presentes nas 13 APS (Agência da Previdência Social) da região, porém existem limitações no acesso ao sistema do próprio INSS responsável por esse controle, uma vez que eles dependem de permissões específicas e do uso de token de acesso que apenas servidores públicos especializados em logística possuem.

Devido a essas limitações, o meu controle e dos outros estagiários acaba sendo realizado por meio de planilhas, o que dificulta a organização e a atualização dos dados. E esse projeto acaba sendo uma alternativa simples para auxiliar no meu controle pessoal desses equipamentos, proporcionando uma forma mais estruturada para armazenar e consultar informações importantes, como o número de patrimônio, número de série, servidor responsável pelo equipamento, o setor e a localização, além de que facilitaria também em um controle de inventário mais preciso e eficaz, sabendo onde está exatamente cada computador e todos seus dados e substituindo o uso de planilhas longas.

---

## Aplicação de requisitos no projeto

### 1. Classes, Objetos e Atributos

O sistema foi modelado por meio das seguintes classes:

* Equipamento (classe abstrata e classe mãe);
* Computador (classe filha);
* Monitor (classe filha);
* Impressora (classe filha);
* Usuario (classe para o usuário responsável pelos equipamentos);
* Inventario (classe responsável pelo gerenciamento dos equipamentos cadastrados).

Essas classes representam entidades do problema e permitem a criação de objetos com os seus atributos específicos, como marca, modelo, número de série, patrimônio, nome do responsável, setor e localização.

### 2. Construtores

As classes possuem construtores padrão que permitem a criação dos objetos. Também é utilizada sobrecarga de construtores para possibilitar diferentes formas de inicialização.

A sobrecarga de construtores foi aplicada na classe `Usuario`, que possui um construtor padrão, um construtor parametrizado com nome, setor e localização e outro construtor que recebe apenas o nome do responsável.

### 3. Encapsulamento

Os atributos das classes são declarados como privados, sendo acessados por meio de métodos getters e setters, garantindo maior segurança e controle sobre os dados armazenados. O encapsulamento foi aplicado principalmente nas classes `Equipamento` e `Usuario`, impedindo o acesso direto aos atributos e permitindo que sua manipulação seja realizada de forma controlada.

### 4. Herança

A classe abstrata `Equipamento` representa todos equipamentos cadastrados. As classes `Computador`, `Monitor` e `Impressora` herdam suas características, reutilizando o código da classe mãe.

### 5. Polimorfismo

O sistema utiliza polimorfismo por meio de uma coleção do tipo ArrayList<Equipamento> em `Inventario`, permitindo que diferentes tipos de equipamentos sejam tratados. Além disso, métodos sobrescritos nas classes filhas de `Equipamento` permitem um comportamento específico para cada tipo de equipamento.

### 6. Classe Abstrata e Interface

A classe `Equipamento` foi definida como abstrata, servindo como base para os demais equipamentos. Também foi criada a interface `Manutencao`, estabelecendo métodos que devem ser implementado pelas classes filhas que precisa ser realizada alguma manutenção.

### 7. Tratamento de Exceções

Foi criada uma exceção personalizada chamada `PatrimonioInvalidoException`, responsável por garantir que o número de patrimônio seja composto por exatamente 9 dígitos, que é um padrão nacional de todos os itens com patrimônio do INSS. O sistema também faz uso de blocos try-catch-finally na própria `Main` do projeto para tratar situações excepcionais e evitar falhas na execução do programa.

---

## Tecnologias Utilizadas

* Java
* Visual Studio Code

---

## Estrutura do Projeto

```
SistemaControlePatrimonialTI/
│
├── Main.java                            # Execução principal do sistema
├── Equipamento.java                     # Classe abstrata dos equipamentos de TI
├── Usuario.java                         # Servidor responsável pelos equipamentos
├── Computador.java                      # Classe dos computadores
├── Monitor.java                         # Classe dos monitores
├── Impressora.java                      # Classe das impressoras
├── Manutencao.java                      # Interface de manutenção
├── Inventario.java                      # Onde será o controle dos equipamentos cadastrados
└── PatrimonioInvalidoException.java     # Exceção personalizada, onde o patrimônio só será válido se tiver 9 digitos
```

---

## Funcionamento

O sistema realiza:

### 1. Cadastro dos Equipamentos

* Cadastro de computadores
* Cadastro de monitores
* Cadastro de impressoras
* Armazenamento de marca, modelo, número de série e patrimônio

### 2. Controle dos Responsáveis

* Servidor responsável pelo equipamento
* Setor onde está o equipamento
* Localização do setor onde está o equipamento

### 3. Gerenciamento do Inventário

* Armazenamento dos equipamentos em uma coleção
* Consulta dos equipamentos cadastrados
* Organização das informações em um único lugar

### 4. Validação dos Dados

* Verificação do número do patrimônio
* Tratamento de exceções para patrimônios inválidos
* Utilização de blocos try-catch-finally para evitar falhas durante a execução

---

## Como Executar

### 1. Clone o repositório

```bash
git clone <repositorio>
```

### 2. Abra o projeto no Visual Studio Code

Certifique-se de possuir o Java instalado e configurado.

### 3. Execute

Execute o arquivo:

```bash
Main.java
```

---

## Autor

Lucas Camargo de Souza

Projeto desenvolvido para uso pessoal no meu estágio e como trabalho final da disciplina de Programação Orientada a Objetos.
