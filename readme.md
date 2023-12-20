UnB - Universidade de Brasilia

FGA - Faculdade do Gama

# TPPE - TP2
Repositório para trabalho 2 da disciplina de TÉCNICAS DE PROGRAMAÇÃO EM PLATAFORMAS EMERGENTES (TPPE).

## Alunos

Matrícula | Nome
|--|--|
190025379 | Brenno Oliveira Silva

## Simplicidade
- **Descrição:** Um código simples é fácil de entender e implementar, sendo consistente e coerente. Seu impacto está presente na estruturação dos códigos, onde seu tamanho deve ser o menor possível, buscando realizar o máximo com o mínimo.
- **Característica com Maus-cheiros:**
  - Código duplicado: Um código simples busca não possuir código duplicado.
  - Método longo: A simplicidade pode ser utilizada para quebrar métodos longos em menores e de melhor entendimento.
- **Operação de refatoração:**
  - Para alcançar a simplicidade, a técnica de "Extrair Função" pode ser útil, isolando trechos de códigos em partes menores, facilitando a compreensão.

## Elegância
- **Descrição:** Costumeiramente está relacionada à simplicidade, com foco na estruturação de um código onde os fluxos sejam coesos, com partes complementares sem acoplamentos que impactem áreas indevidas.
- **Característica com Maus-cheiros:**
  - Classe inchada: Um código elegante não utiliza classes grandes, pois o excesso de variáveis pode evidenciar baixa coesão.
  - Generalidade especulativa: A utilização de generalidade especulativa pode mostrar que trechos de códigos são desnecessários ou poderiam estar inseridos em outros locais.
- **Operação de refatoração:**
  - A remoção de parâmetros pode ser uma técnica válida para manter apenas os parâmetros necessários nos métodos.

## Modularidade
- **Descrição:** A modularidade está diretamente ligada à alta coesão e baixo acoplamento, dividindo problemas em partes menores que, juntas, formam uma solução completa.
- **Característica com Maus-cheiros:**
  - Método longo: A modularidade pode ser utilizada para quebrar métodos longos em menores.
  - Classe inchada: Um código modular decompõe uma classe com muitas responsabilidades.
- **Operação de refatoração:**
  - Pode ser utilizada a extração de interfaces, permitindo a alteração da interface para melhor atender e organizar o uso ao avaliar a utilização da classe.

## Extensibilidade
- **Descrição:** A extensibilidade organiza novos códigos em espaços já existentes, balanceando as funcionalidades presentes com as futuras.
- **Característica com Maus-cheiros:**
  - Método longo: Ao desenvolver um código com muitas funcionalidades, podem surgir métodos que fazem mais do que deveriam.
  - Mudanças divergentes: Um código extenso pode gerar um excesso de mudanças no que já foi desenvolvido.
- **Operação de refatoração:**
  - A extração de classes pode ser útil para organizar o código e deixar mais clara a responsabilidade de cada classe.

## Ausência de Duplicidades
- **Descrição:** A ausência de duplicidades proporciona elegância e simplicidade ao código ao não possuir trechos redundantes.
- **Característica com Maus-cheiros:**
  - Código duplicado: O código duplicado é o inverso do tópico abordado, pois a ausência de duplicidades não deve apresentar esse mau-cheiro.
- **Operação de refatoração:**
  - A refatoração de "Extrair Função" pode ser utilizada para transformar um código utilizado em vários locais em uma função que pode ser chamada no local.
