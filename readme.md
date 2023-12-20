UnB - Universidade de Brasilia

FGA - Faculdade do Gama

# TPPE - TP2
Repositório para trabalho 2 da disciplina de TÉCNICAS DE PROGRAMAÇÃO EM PLATAFORMAS EMERGENTES (TPPE).

## Alunos

Matrícula | Nome
|--|--|
190025379 | Brenno Oliveira Silva
190012307 | Eduardo Afonso Dutra Silva
190047968 | Paulo Vitor Silva Abi Acl

## Simplicidade
- **Descrição:** A simplicidade é uma das características mais importantes de um bom projeto de software. Ela se refere à facilidade com que o código pode ser lido e compreendido. Um código simples é direto, conciso e não contém elementos desnecessários ou redundantes, é escrito de uma maneira que é fácil de entender, mesmo para alguém que não está familiarizado com o projeto. Seu impacto está presente na estruturação dos códigos, onde seu tamanho deve ser o menor possível, buscando realizar o máximo com o mínimo.
- **Característica com Maus-cheiros:** Os maus-cheiros de código indicam problemas no design do software, podendo dificultar a compreensão e manutenção do código Um exemplo de mau-cheiro de código que viola a simplicidade é o “Método longo”. Métodos longos são se complexos e desafiadores de entender, pois podem abrigar uma quantidade excessiva de lógica, propiciando a presença de duplicação de código. Outro exemplo é o “Classe Grande”, que é uma classe que tenta fazer mais do que ela deveria e acaba sendo grande e complicada. Essas classes são difíceis de entender e manter, e geralmente são um sinal de que a classe deve ser dividida em classes menores e mais simples.
- **Operação de refatoração:** Existem algumas operações de refatoração que podem ser usadas para melhorar a simplicidade do código. Como exemplo, a técnica de refatoração conhecida como "Extrair Método" pode ser útil para lidar com a questão do "Método Longo". Esse processo implica na criação de um novo método isolando trechos de códigos em partes menores. Outra estratégia de refatoração que tenta resolver o problema da "Classe Grande" é "Extrair Classe", que se revela eficaz ao dividir uma "Classe Extensa" em classes menores e mais acessíveis.

<details open>
<summary>Exemplo prático</summary>
 
#### Antes:
 
```python
def metodo_longo():
    objeto = {"item_1": 1, "item_2": 2, "item_3": 3}
    
    if (objeto['item_1'] + objeto['item_2'] == objeto['item_3']):
        print("Operação concluida")
    else:
        print("Operação não concluida")
```

#### Depois

```python
def metodo_longo():
    objeto = metodo_curto_1()
    metodo_curto_2(objeto)

def metodo_curto_1():
    return {"item_1": 1, "item_2": 2, "item_3": 3}


def metodo_curto_2(objeto):
    if objeto["item_1"] + objeto["item_2"] == objeto["item_3"]:
        print("Operação concluida")
    else:
        print("Operação não concluida")

```
</details>

## Elegância
- **Descrição:** Costumeiramente está relacionada à simplicidade, com foco na estruturação de um código onde os fluxos sejam coesos, com partes complementares sem acoplamentos que impactem áreas indevidas, facilitam a leitura, manutenção e compreensão do código-fonte. Códigos elegantes são geralmente bem estruturados, utilizam boas práticas de programação e seguem convenções que tornam o código mais legível. 
- **Característica com Maus-cheiros:** Na busca pela elegância em projetos de software, é importante evitar a presença de classes inchadas, pois estas comprometem a qualidade do código. Um código elegante prescinde do uso de classes extensas, uma vez que o excesso de variáveis em uma única classe pode evidenciar uma baixa coesão, tornando a compreensão e manutenção mais desafiadoras. Outro aspecto relevante é a necessidade de evitar a generalidade especulativa, uma prática que pode indicar a presença de trechos de código desnecessários ou que poderiam ser mais apropriadamente localizados em outras partes do sistema.
- **Operação de refatoração:** Para operações de refatoração que contribuem com a elegância do código A remoção de parâmetros surge como uma técnica válida para manter apenas os parâmetros essenciais nos métodos.

<details open>
<summary>Exemplo prático</summary>
 
#### Antes:
 
```python
def soma_dois_valores(valor_1: int, valor_2: int, valor_3: int):
    return valor_1 + valor_2
```

#### Depois

```python
def soma_dois_valores(valor_1: int, valor_2: int):
    return valor_1 + valor_2

```
</details>

## Modularidade
- **Descrição:** A modularidade representa uma peça fundamental em um design de software robusto. Está diretamente ligada à alta coesão, onde os componentes de um módulo estão fortemente relacionados entre si, compartilhando uma finalidade comum. Ao mesmo tempo visa manter um baixo acoplamento entre os diferentes módulos, minimizando as dependências entre eles que, juntos, formam uma solução completa. A vantagem de adotar a modularidade reside na facilitação da compreensão do código, permitindo que os desenvolvedores se concentrem em partes específicas do sistema sem se perderem em complexidades desnecessárias.
- **Característica com Maus-cheiros:** Os Maus-cheiros que comprometem a modularidade incluem o Método Longo e Classe Inchada. Ao adotar uma abordagem modular, é possível reduzir o Código Duplicado, isso se deve à capacidade de criar módulos reutilizáveis, os quais abrigam funcionalidades comuns, evitando assim repetições desnecessárias. Além disso a modularidade pode ser utilizada para quebrar métodos longos em menores, pois promove a implementação de métodos mais curtos e específicos, facilitando a leitura, manutenção e compreensão do código. No caso da Classe Inchada, a modularidade permite decompor uma classe com muitas responsabilidades entre diferentes módulos, evitando que uma única classe cresça excessivamente. 
- **Operação de refatoração:** No contexto da "Classe Inchada", a estratégia de refatoração denominada "Extrair Classe" se mostra valiosa nessa situação. Ela proporciona uma maneira eficaz de lidar com o desafio de uma classe que cresceu excessivamente em tamanho e complexidade, ao dividir suas responsabilidades em classes menores e mais coesas. Ao identificar conjuntos lógicos de responsabilidades, essa técnica contribui diretamente para a criação de módulos independentes, facilitando a compreensão e manutenção do código.
 
<details open>
<summary>Exemplo prático</summary>
 
#### Antes:
 
```python
class Veiculo():
    def __init__(self, marca, modelo, ano, nome_motorista, cidade_motorista, documento_motorista):
        self.marca = marca
        self.modelo = modelo
        self.ano = ano
        self.nome_motorista = nome_motorista
        self.cidade_motorista = cidade_motorista
        self.documento_motorista = documento_motorista
```

#### Depois

```python
class Veiculo():
    def __init__(self, marca, modelo, ano, motorista):
        self.marca = marca
        self.modelo = modelo
        self.ano = ano
        self.motorista = motorista
        
class Motorista():
    def __init__(self, nome, cidade, documento):
        self.nome = nome
        self.cidade = cidade
        self.documento = documento
```
</details>

## Extensibilidade
- **Descrição:** O conceito de extensibilidade diz respeito à capacidade do código-fonte de ser ampliado e adaptado de maneira fácil para incorporar novas funcionalidades ou realizar modificações sem impactar de forma drástica a estrutura já existente. Em outras palavras, envolve a habilidade de organizar novos códigos em áreas já estabelecidas, mantendo um equilíbrio entre as funcionalidades presentes e as futuras. Códigos com extensibilidade são caracterizados pela flexibilidade, permitindo a adição de novos recursos de maneira modular.
- **Característica com Maus-cheiros:** Um dos maus-cheiros que compromete a extensibilidade é o "Método Longo". Isso ocorre quando desenvolvemos um código rico em funcionalidades, sendo comum nos depararmos com métodos que acabam por realizar mais tarefas do que o ideal. Esse cenário não apenas compromete a clareza do código, mas também pode dificultar sua manutenção. Outro problema associado à extensibilidade é a ocorrência de "Mudanças Divergentes". Em códigos extensos, é possível que as alterações necessárias se tornem numerosas e se desdobrem em diferentes partes do código já desenvolvido. Isso não apenas aumenta a complexidade, mas também torna as mudanças mais propensas a erros. Por fim, um ultimo exemplo de mau-cheiro de extensibilidade seria o "Homem do meio", que representa o caso onde existem classes que não realizam nenhuma ação além de chamar métodos de outras classes, aumentando assim a complexididade do código e dificultando de ampliação e adição de novas funcionalidades.
- **Operação de refatoração:** Quando se trata de operações de refatoração para mitigar esses desafios, a técnica "Remover homem do meio" surge como uma ferramenta valiosa. Essa técnica permite que a classe realize a função ao invés de delegar para outra.
 
<details open>
<summary>Exemplo prático</summary>
 
#### Antes:
 
```python
class Disco():
    def __init__(self, ano, estilo):
        self.ano = ano
        self.estilo = estilo
        
class Musico():
    def __init__(self, nome):
        self.nome = nome
        self.discos = []
    
    def adicionar_disco(disco):
        self.discos.append(disco)
        
    def conta_discos():
        return len(self.discos)
        
class Produtor():
    def conta_total_discos(self, musico):
        return musico.conta_discos()
```

#### Depois

```python
class Disco():
    def __init__(self, ano, estilo):
        self.ano = ano
        self.estilo = estilo
        
class Musico():
    def __init__(self, nome):
        self.nome = nome
        self.discos = []
    
    def adicionar_disco(disco):
        self.discos.append(disco)
        
    def conta_discos():
        return len(self.discos)
```
</details>

## Ausência de Duplicidades
- **Descrição:** A ausência de duplicidades está associada à organização do código de modo a evitar repetições desnecessárias e promover a criação de módulos independentes e interconectados. A eliminação de duplicidades proporciona elegância e simplicidade ao código ao não possuir trechos redundantes, mas também facilita a manutenção, uma vez que alterações podem ser realizadas em módulos isoladamente.
- **Característica com Maus-cheiros:** A importância da ausência de duplicidade no design de software é evidente ao considerar os maus cheiros de código, como o "Código Duplicado". A duplicação de código é o inverso do tópico abordado, pois a ausência de duplicidades não deve apresentar esse mau-cheiro, a eliminação adequada de duplicidades permite encapsular funcionalidades compartilhadas em módulos reutilizáveis, evitando a duplicação.
- **Operação de refatoração:** A refatoração de "Extrair Função" é uma estratégia eficaz na refatoração de código para lidar com a presença de duplicação de código, pode ser utilizada para transformar um código utilizado em vários locais em uma função que pode ser chamada no local. Essa prática não apenas elimina a duplicação, mas também contribui para a legibilidade e manutenibilidade, uma vez que a lógica compartilhada é centralizada em um único local.


<details open>
<summary>Exemplo prático</summary>
 
#### Antes:
 
```python
def conta_rap(musicos):
    contador = 0
    for musico in musicos:
        if musico.genero == "RAP":
            contador += 1

    return contador


def conta_funk(musicos):
    contador = 0
    for musico in musicos:
        if musico.genero == "FUNK":
            contador += 1

    return contador
```

#### Depois

```python
def conta_estilo(musicos, estilo):
    contador = 0
    for musico in musicos:
        if musico.genero == estilo:
            contador += 1

    return contador
```
</details>
