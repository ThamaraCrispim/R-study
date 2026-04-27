# 📘 Fundamentos de R — Objetos, Tipos e Ambiente

Este material resume conceitos iniciais de R para quem está começando em análise de dados e modelagem estatística.

---

## 🔹 1. Objetos no R

No R, praticamente tudo é um objeto: valores, vetores, tabelas, funções, listas e resultados.

```r
# Objeto numérico
my_x <- 1:10

# Objeto caractere
my_char <- "ABC"

# Ver estrutura do objeto
str(my_x)
str(my_char)

# Ver classe do objeto
class(my_x)
class(my_char)
```

---

## 🔹 2. Tipos básicos de dados

```r
# Numérico
num <- 10

# Decimal
my_decimal <- 0.1

# Caractere
char <- "texto"

# Lógico
logico <- TRUE

# Fator: usado para variáveis categóricas
categoria <- factor(c("baixo", "medio", "alto"))

# Complexo
complexo <- 1 + 2i

# Data
my_date <- as.Date("2010-01-01")
print(my_date)
```

📌 Observações importantes:

* Decimais usam ponto: `0.1`
* Datas seguem o padrão: `YYYY-MM-DD`
* Textos podem usar aspas simples ou duplas, mas escolha um padrão.

---

## 🔹 3. Estruturas importantes

```r
# Vetor numérico
my_vec_num <- c(1, 2, 3, 4)

# Vetor caractere
my_vec_char <- c("abc", "ags", "dsd")

# Data frame: estrutura parecida com tabela
clientes <- data.frame(
  id = 1:3,
  idade = c(25, 40, 32),
  renda = c(2500, 6000, 4200)
)

# Lista: guarda objetos diferentes juntos
info_cliente <- list(
  nome = "Cliente A",
  idade = 25,
  renda = 2500,
  inadimplente = FALSE
)

# Matriz: estrutura tabular com o mesmo tipo de dado
matriz_exemplo <- matrix(1:9, nrow = 3)
```

---

## 🔹 4. Boas práticas de escrita

Use nomes claros e sem acento:

```r
# Evite:
# minha.variável <- 1

# Prefira:
minha_variavel <- 1
```

Boas práticas:

* Use nomes descritivos: `renda_cliente`, `idade_cliente`
* Evite acentos e espaços
* Use `_` para separar palavras
* Comente o código quando fizer sentido
* Organize o script por blocos

---

## 🔹 5. Operações básicas

```r
# Média simples
my_mean <- mean(1:10)
print(my_mean)

# Exemplo com outlier
x <- c(0:10, 50)

# Média normal
xm <- mean(x)

# Média ajustada removendo extremos
mean_trim <- mean(x, trim = 0.10)

c(
  media_normal = xm,
  media_ajustada = mean_trim
)
```

📌 Interpretação:

Quando existe um valor muito alto ou muito baixo, a média pode ser puxada por esse valor.
Por isso, em algumas análises, usamos uma média ajustada.

---

## 🔹 6. Limpeza de memória

```r
# Remove um objeto específico
rm(my_char)

# Remove tudo do ambiente
# rm(list = ls())
```

⚠️ Use `rm(list = ls())` com cuidado, porque ele apaga todos os objetos criados na sessão.

---

## 🔹 7. Ajuda no R

```r
# Abre a documentação da função
?mean

# Busca ajuda por palavra-chave
help.search("mean")
```

---

## 🔹 8. Pacotes no R

Pacotes são conjuntos de funções prontas que ampliam o R.

```r
# Instalar pacotes
# install.packages("dplyr")
# install.packages("BatchGetSymbols")

# Carregar pacote
library(BatchGetSymbols)

# Usar uma função sem carregar o pacote
BatchGetSymbols::BatchGetSymbols()

# Outra forma de carregar pacote
require("BatchGetSymbols")
```

📌 Diferença simples:

* `install.packages()` instala uma vez
* `library()` carrega o pacote para usar
* `pacote::funcao()` usa uma função específica sem carregar tudo

---

## 🔹 9. CRAN

O CRAN é o repositório oficial de pacotes do R.

```r
df_cran <- available.packages()

class(df_cran)
str(df_cran)

# Quantidade de pacotes disponíveis
nrow(df_cran)
```

---

## 🔹 10. Autocomplete

No RStudio, use a tecla `TAB` para completar nomes de objetos, funções e pacotes.

Exemplo:

```r
# Digite:
# my_

# Depois aperte TAB para ver objetos que começam com my_
```

---

## 🔹 11. Interação com arquivos e pastas

```r
# Lista arquivos da pasta atual
list.files()

# Lista diretórios
list.dirs()

# Mostra a pasta atual
getwd()

# Define a pasta de trabalho
# setwd("caminho/do/projeto")
```

📌 Em projetos profissionais, prefira trabalhar com um projeto `.Rproj`, evitando depender muito de `setwd()`.

---

## 🔹 12. Mini exemplo aplicado

Imagine uma pequena base de clientes:

```r
clientes <- data.frame(
  id_cliente = 1:5,
  idade = c(22, 35, 41, 29, 50),
  renda = c(2000, 4500, 7000, 3200, 9000),
  inadimplente = c(TRUE, FALSE, FALSE, TRUE, FALSE)
)

str(clientes)
summary(clientes)

mean(clientes$renda)
table(clientes$inadimplente)
```

📌 Esse tipo de análise ajuda a entender:

* perfil dos clientes
* renda média
* quantidade de inadimplentes
* estrutura da base

---

## ✅ Conclusão

Nesta primeira etapa, foram revisados conceitos fundamentais de R:

* criação de objetos
* tipos de dados
* vetores
* data frames
* pacotes
* ajuda no R
* interação com o ambiente
* boas práticas de organização

Esses fundamentos são importantes para avançar em análise exploratória, `data.table`, R Markdown e modelagem estatística.
