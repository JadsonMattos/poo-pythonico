# Boas-vindas ao repositório do exercício Loja Virtual Pythonica

<details>
<summary><strong>🧑‍💻 O que deverá ser desenvolvido</strong></summary><br />

Neste exercício, você vai praticar os seus conhecimentos de POO em Python. Você vai criar um programa que simula uma loja virtual elaborando códigos que façam o uso de _tipagem estática_ em Python.

</details>
  
<details>
  <summary><strong>📝 Habilidades a serem trabalhadas</strong></summary><br />

Neste exercício, verificamos se você é capaz de:

- Elaborar códigos que façam o uso de _tipagem estática_ em Python.
- Elaborar códigos utilizando a linguagem Python que utilizam _Classes_, _Construtores_, _Instâncias_, _Atributos_ e _Métodos_.
- Examinar um projeto em Python que utiliza o paradigma de _Programação Orientada a Objetos_.
- Escrever código Python que passa em testes de integração.

</details>

# Orientações específicas deste projeto

<details>
  <summary><strong>🏕️ Ambiente Virtual</strong></summary><br />
  
O Python oferece um recurso chamado de ambiente virtual, onde permite sua máquina rodar sem conflitos, diferentes tipos de projetos com diferentes versões de bibliotecas.

1. Criar o ambiente virtual

```bash
python3 -m venv .venv
```

2. Ativar o ambiente virtual

```bash
source .venv/bin/activate
```

3. Instalar as dependências no ambiente virtual

```bash
python3 -m pip install -r dev-requirements.txt
```

Com o seu ambiente virtual ativo, as dependências serão instaladas neste ambiente.
Quando precisar desativar o ambiente virtual, execute o comando "deactivate". Lembre-se de ativar novamente quando voltar a trabalhar no projeto.

O arquivo `dev-requirements.txt` contém todas as dependências que serão utilizadas no projeto, ele está agindo como se fosse um `package.json` de um projeto `Node.js`.

</details>

## Requisitos

### 1 - Desenvolver a classe `Produto`

> **Implemente em:** `src/produto.py`

<details>

<summary><strong>Crie uma classe <code>Produto</code></strong>
</summary><br/>
 
Seu objetivo é implementar uma classe chamada `Produto`, que representa um produto no estoque. Essa classe deve conter as seguintes características:

**Atributos**:

- `nome (string)` - será inicializado com o valor do parâmetro;
- `código (string)` - será inicializado com o valor do parâmetro;
- `preço (float)` - será inicializado com o valor do parâmetro;
- `quantidade (int)` - será inicializado com o valor do parâmetro.

Todos os atributos devem ser privados.

Além disso, a classe deve possuir os seguintes métodos:

**Métodos**:

- `__init__` - construtor que inicializa os atributos da classe.
- `atualizar_preco` - método que atualiza o preço do produto. O preço não pode ser negativo.
- `adicionar_estoque_do_produto` - método que adiciona a quantidade informada ao estoque do produto.
- `remover_estoque_do_produto` - método que remove a quantidade informada do estoque do produto. Deve verificar se existe a possibilidade de remover a quantidade pedida e lançar um `ValueError` caso isso não seja possível.

</details>

### 2 - Desenvolver a classe `Estoque`

> **Implemente em:** `src/estoque.py`

<details>

<summary><strong>Crie uma classe <code>Estoque</code></strong>
</summary><br/>

Sua tarefa é implementar a classe `Estoque` utilizando tipagem estática. A classe deve permitir a adição, remoção e atualização de produtos no estoque, além de permitir a visualização do estoque atualizado. Essa classe deve conter as seguintes características:

**Atributos**:

- `produtos (dict)` - dicionário que armazena os produtos do estoque e suas quantidades;

Além disso, a classe deve possuir os seguintes métodos:

**Métodos**:

- `__init__ (self, produtos : dict)` - construtor que inicializa o dicionário produtos.
- `adicionar_produto_no_estoque(self, nome: str, quantidade: int)` - método que adiciona um produto ao estoque, juntamente com sua quantidade. Caso o produto já exista no estoque, a quantidade deve ser somada à quantidade já existente.
- `remover_produto_do_estoque(self, nome: str, quantidade: int)` - método que remove um produto do estoque, juntamente com sua quantidade. Caso a quantidade informada seja maior do que a quantidade disponível no estoque, o método deve lançar uma exceção (ValueError).
- `atualizar_produto_no_estoque(self, nome: str, nova_quantidade: int)` - método que atualiza a quantidade de um produto no estoque. Caso o produto não exista no estoque, o método deve lançar uma exceção (ValueError).
- `visualizar_estoque(self)` - método que exibe o estoque atualizado.

</details>

### 3 - Testar o construtor/inicializador da classe Livro

> **Crie o teste em:** tests/livro/test_livro.py

<details>

<summary><strong>Crie o teste do construtor/inicializador para a classe <code>Livro</code></strong>
</summary><br/>

Dentro do arquivo `src/livro/livro.py` você encontrará a classe `Livro` já criada.

Agora você precisa implementar um teste que certifica se o método `__init__` da classe `Livro` esta funcionando corretamente.

O nome deste teste deve ser `test_cria_livro`, e ele deve verificar se é possível criar um objeto do tipo Livro com os seguintes atributos:

- `titulo (string)`
- `autor (string)`
- `paginas (int)`

</details>

### 4 - Testar a descrição do Livro

> **Crie o teste em:** tests/descricao_livro/test_descricao_livro.py

<details>

<summary><strong>Crie o teste para o método que traz a descrição do <code>Livro</code></strong>
</summary><br/>

Agora precisamos testar se a descrição do livro está sendo retornada corretamente.

Para desenvolver este relatório, utilizamos o recurso `__repr__` do Python, que permite alterar a representatividade do objeto, para que sempre que usarmos um print nele, no lugar de endereço de memória, teremos uma String personalizada.

Exemplo de frase:

> O livro pequenos jangadeiros, de Aristides Fraga Lima, possui 96 páginas.

O nome deste teste deve ser `test_descricao_livro`, e ele deve instanciar um objeto Livro e verificar se é retornada a frase correta.

</details>
