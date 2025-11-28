# Resolução Numérica da Equação de Van der Waals 

> Trabalho prático da disciplina de Cálculo Numérico do curso de Engenharia de Computação - IFMG Campus Bambuí.

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![License](https://img.shields.io/badge/License-MIT-green)

##  Sobre o Projeto

Este projeto tem como objetivo aplicar métodos numéricos para resolver problemas de engenharia que não possuem solução analítica trivial. O foco do estudo é a **Equação de Estado de Van der Waals**, utilizada para descrever o comportamento de gases reais sob altas pressões, onde a Lei dos Gases Ideais ($PV=nRT$) falha.

O trabalho consiste na implementação de algoritmos para encontrar o **Volume Molar ($V$)** do Dióxido de Carbono ($CO_2$) sob condições específicas de pressão e temperatura.

###  Autores
* **Gabriel Henrique Silva Duque**
* **Rafael Gonçalves Oliveira**

---

##  O Problema Físico

A equação de Van der Waals é dada por:

$$\left( P + \frac{a}{V^2} \right) (V - b) = RT$$

Para aplicar os métodos numéricos (zero de função), a equação foi manipulada para a forma polinomial $f(V) = 0$:

$$f(V) = PV^3 - (Pb + RT)V^2 + aV - ab = 0$$

### Parâmetros Utilizados (Gás: $CO_2$)
* **Pressão ($P$):** 50 atm
* **Temperatura ($T$):** 350 K
* **Constante $a$:** $3.592 \, L^2 \cdot atm/mol^2$
* **Constante $b$:** $0.04267 \, L/mol$
* **Constante $R$:** $0.082057 \, L \cdot atm / (K \cdot mol)$

---

##  Métodos Implementados

Foram implementados e comparados três métodos iterativos para encontrar a raiz da função:

1. **Método da Bisseção:** Método de quebra de intervalo (robustez garantida pelo Teorema de Bolzano).
2. **Método de Newton-Raphson:** Método de ponto aberto que utiliza a derivada $f'(V)$ para convergência quadrática.
3. **Método da Secante:** Similar ao Newton, mas aproxima a derivada usando a inclinação entre dois pontos anteriores.

---

##  Resultados Obtidos

Os testes foram realizados considerando uma tolerância de erro de $1 \times 10^{-6}$.

| Método | Volume Encontrado (L/mol) | Iterações |
| :--- | :---: | :---: |
| **Newton-Raphson** | 0.480950 | **4** |
| **Secante** | 0.480950 | 16 |
| **Bisseção** | 0.480950 | 20 |

> **Conclusão:** O volume molar calculado (~0.481 L/mol) é significativamente menor que o previsto pela Lei dos Gases Ideais (~0.574 L/mol), comprovando a necessidade da correção de Van der Waals. O método de Newton-Raphson mostrou-se o mais eficiente computacionalmente.

---

##  Como Executar o Projeto

Para rodar este projeto localmente, siga as instruções abaixo no seu terminal:

### 1. Clonar o repositório
Faça o download do código fonte para sua máquina:
```bash
git clone https://github.com/SEU-USUARIO/NOME-DO-REPO.git
cd NOME-DO-REPO
```

### 2. Instalar as dependências
Certifique-se de ter as bibliotecas necessárias instaladas:
```bash
pip install numpy matplotlib jupyter
```

### 3. Iniciar o Jupyter Notebook
Execute o comando para abrir o ambiente de desenvolvimento no seu navegador:
```bash
jupyter notebook
```

### 4. Abrir o arquivo principal
No painel do Jupyter que abrirá no navegador, localize e clique no arquivo:

> **`trabalho1_calc_num.ipynb`**

Em seguida, vá no menu **Cell** e selecione **Run All** para executar todos os blocos de código e visualizar os gráficos e resultados.

---

##  Referências Bibliográficas

As seguintes fontes foram utilizadas para a elaboração do código, obtenção das constantes físicas e fundamentação teórica dos métodos numéricos:

1. **CHAPRA, Steven C.; CANALE, Raymond P.** *Métodos Numéricos para Engenharia*. 7ª Edição. Editora AMGH, 2016.
2. **NumPy Documentation**. Biblioteca fundamental para computação científica em Python. Disponível em: https://numpy.org/.
3. **Matplotlib Documentation**. Biblioteca para criação de visualizações estáticas, animadas e interativas em Python. Disponível em: https://matplotlib.org/.
4. **WebElements**. *Carbon dioxide: van der Waals constants*. Disponível em: https://www.webelements.com/. (Fonte dos parâmetros $a$ e $b$ para o $CO_2$).

---
