# Analisando uma base da dados com Pandas

Vamos analisar uma base de vendas de uma determinada empresa de Ecommerce, para isso teremos acesso a um arquivo *‘.csv’* com as vendas de um determinado período, neste nosso exemplo aqui vamos utilizar o *Pandas* para ler esse arquivo, consolidar as vendas por bandeira de cartão de crédito e ao final gravar esse resultado em uma nova base *‘.csv’*. Toda análise será feita utilizando o *Jupyter Notebook* com o *Python 3*.

## Vamos lá para o passo a passo:

### 1º Importar a base de vendas.

```python
import pandas as pd
base_vendas = pd.read_csv("Ecommerce.csv", delimiter=",")
display(base_vendas)
```

![Imagem base de vendas](https://drive.google.com/uc?export=view&id=18z708nC2lDMnyEmI1mlx-_4-hH5fvsmm)

### 2º agrupar as vendas por bandeira de cartão de crédito com seus respectivos valores sumarizados.

```python
resumo_vendas = pd.DataFrame(base_vendas.groupby(by="bandeira_cartao").valor.sum()).rename(columns={"valor":"Total"})
display(resumo_vendas)
```

![Resumo base de vendas](https://drive.google.com/uc?export=1D8M5xCjeziAbrOLmRsNSWX41YztTspJN)

### 3º Criar uma nova base com o resultado da análise.

```python
resumo_vendas.to_csv("resumo_vendas.csv", sep=";")
```

![arquivo resumo base de vendas](https://drive.google.com/uc?export=1Dv_HdHKbUBf48oh7kc5leJENklKqao-I)

Esse foi um exemplo bem básico, mas o suficiente para mostrar como é simples e rápido fazer uma análise de dados utilizando o Python, Pandas e o Jupyter notebook.

Para instalar as bibliotecas necessárias no Python utilize o arquivo *requeriments.txt* e execute o seguinte comando:

```bash
pip install -r requeriments.txt
```

### Requisitos mínimos:

>> Sistema operacional Linux (Ubuntu 20.04.2 LTS) <br/>Memória RAM de 4GB ou mais <br/>Python 3 e Jupyter Notebook instalados

**Até breve!**

> **Referências:**   
> Mockaroo, Random Data Generator and API Mocking Tool. Disponível em: <https://www.mockaroo.com/>. Acesso em: 03 fev. 2022.
