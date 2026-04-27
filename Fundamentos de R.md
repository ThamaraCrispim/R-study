# 📘 Fundamentos de R — Objetos, Tipos e Ambiente
# Autor: Thamara Bezerra
# Objetivo: Revisão prática dos conceitos básicos de R para análise de dados

# =====================================================
# 🔹 1. Tipos de objetos no R
# =====================================================

# Vetor numérico
my_x <- 1:10

# Vetor caractere
my_char <- "ABC"

# Estrutura dos objetos
str(my_x)      # int
str(my_char)   # chr

# Classe dos objetos
class(my_x)
class(my_char)

# =====================================================
# 🔹 2. Principais tipos de dados no R
# =====================================================

# Numérico (numeric / integer)
num <- 10

# Caractere (character)
char <- "texto"

# Lógico (TRUE / FALSE)
logico <- TRUE

# Fator (categorias)
fator <- factor(c("A", "B", "A"))

# Complexo
complexo <- 1 + 2i

# Data (formato padrão: YYYY-MM-DD)
data <- as.Date("2010-01-01")
print(data)

# Estruturas mais usadas
# - data.frame → tabela
# - lista → estrutura flexível
# - matriz → dados numéricos organizados

# Tudo no R é um objeto
class(data)

# =====================================================
# 🔹 3. Boas práticas de escrita
# =====================================================

# Evite caracteres especiais (pode dar erro em código/projetos)
# ❌ Errado:
# minha.variável <- 1

# ✅ Correto:
minha_variavel <- 1

# Padrão internacional:
# - Decimal com ponto (.)
# - Datas no formato YYYY-MM-DD

decimal <- 0.1

# =====================================================
# 🔹 4. Criação de vetores
# =====================================================

# Vetor numérico
vec_num <- c(1, 2, 3, 4)

# Vetor caractere
vec_char <- c("abc", "xyz", "teste")

# =====================================================
# 🔹 5. Operações básicas
# =====================================================

# Média
my_mean <- mean(1:10)
print(my_mean)

# Exemplo com parâmetro trim (remove extremos)
x <- c(0:10, 50)
xm <- mean(x)

c(
  media_normal = xm,
  media_ajustada = mean(x, trim = 0.10)
)

# =====================================================
# 🔹 6. Gerenciamento de memória
# =====================================================

# Remove objeto específico
rm(my_char)

# Remove tudo do ambiente
# rm(list = ls())

# =====================================================
# 🔹 7. Ajuda no R
# =====================================================

# Documentação de função
?mean

# Busca por funções
help.search("mean")

# =====================================================
# 🔹 8. Pacotes no R
# =====================================================

# Instalar pacote
# install.packages("dplyr")

# Observação: nome correto do pacote
# install.packages("BatchGetSymbols")

# Carregar pacote
library(BatchGetSymbols)

# Usar função sem carregar pacote
BatchGetSymbols::BatchGetSymbols()

# Alternativa (menos usada hoje)
require("BatchGetSymbols")

# =====================================================
# 🔹 9. CRAN — repositório de pacotes
# =====================================================

df_cran <- available.packages()

class(df_cran)
str(df_cran)

# Número de pacotes disponíveis
nrow(df_cran)

# =====================================================
# 🔹 10. Produtividade (autocomplete)
# =====================================================

# Use TAB para completar nomes
# Exemplo:
# my_ → mostra objetos que começam com "my_"

# Funciona também para pacotes e funções

# =====================================================
# 🔹 11. Interação com o sistema
# =====================================================

# Listar arquivos
list.files()

# Listar diretórios
list.dirs()

# Ver diretório atual
getwd()

# Definir diretório
# setwd("caminho/do/seu/projeto")
