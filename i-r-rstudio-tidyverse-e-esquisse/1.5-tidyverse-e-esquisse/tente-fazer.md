# 🤟 Tente fazer

Tente reproduzir no seu computador a análise apresentada no vídeo com os dados do `data.frame` questionário do pacote {dados}; O _script_ em anexo contém os códigos apresentados no vídeo da aula 1.5.

#### Código exemplo da atividade 1.5

```r
# _        __
#(_)      / _|                 
# _ _ __ | |_ ___  ___  ___   ___  
#| | '_ \|  _/ _ \/ __|/ _ \ / __| 
#| | | | | || (_) \__ \ (_) | (__  
#|_|_| |_|_| \___/|___/\___/ \___| 
# ...................................................
# Informática Aplicada às Ciências Sociais
# Centro de Letras e Ciências Humanas - CCH
# Universidade Estadual de Londrina - UEL
# Autores: - Prof. Ronaldo Baltar
#          - Prof.ª Cláudia Siqueira Baltar
# Curso: Explorando Indicadores Sociais com R e RStudio 
# Atividade 1
# Versão: 2023  


# Esse script é uma referência para a realização
# das atividades proposta no curso.


# Instale os pacotes, caso ainda não tenham sido instalados
install.packages(c("tidyverse","esquisse","dados"))

# Carrege o pacote {tidyverse}
library(tidyverse)

# Execute o esquisse
esquisse::esquisser(viewer = "browser")

# Tente gerar no esquisse, com o data.frame
# questionarios
# do pacote dados
# os gráficos correspondentes ao códigos
# a seguir, conforme mostrado no vídeo

##############################
# CÓDIGOS CRIADOS COM ESQUISSE
##############################

# Gráfico 2
# Código para gerar um gráfico do 
# tipo Box Plot com casos de pessoas
# que assistem 5 ou mais horas de TV,
# por religião e partido

library(dplyr)
library(ggplot2)

dados::questionario %>%
 filter(ano >= 2011.8 & ano <= 2014) %>%
 filter(!is.na(idade)) %>%
 filter(partido %in% 
 c("Fortemente democrata", "Fortemente republicano")) %>%
 filter(religiao %in% c("Católica", "Protestante"
)) %>%
 filter(horas_tv >= 5L & horas_tv <= 24L & !is.na(horas_tv)) %>%
 ggplot() +
 aes(x = partido, y = horas_tv, fill = religiao) +
 geom_boxplot() +
 scale_fill_hue(direction = 1) +
 theme_minimal()



# Gráfico 1
# Código para gerar um gráfico do 
# tipo Box Plot pelo total de horas TV
# assistidas, por religião e partido


dados::questionario %>%
 filter(ano >= 2011.8 & ano <= 2014) %>%
 filter(!is.na(idade)) %>%
 filter(partido %in% 
 c("Fortemente democrata", "Fortemente republicano")) %>%
 filter(religiao %in% c("Católica", "Protestante"
)) %>%
 filter(!is.na(horas_tv)) %>%
 ggplot() +
 aes(x = partido, y = horas_tv, fill = religiao) +
 geom_boxplot() +
 scale_fill_hue(direction = 1) +
 theme_minimal()

## Faça outros gráficos de exploração
## dos dados, conforme seu interesse e
## curiosidade e transfira o resultado do código
## para esse scprit.


```
