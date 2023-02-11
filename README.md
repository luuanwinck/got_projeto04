# got_projeto04
 
Curso Programadores Cariocas
Projeto em Grupo Módulo 4 – Resilia
Grupo:

Leticia da Silva
Luan da Silva


CONTEXTO: Temos um problema e precisaremos da sua ajuda para resolver! Acumulamos alguns conjuntos de dados e não conseguimos ter uma visão padronizada desses dados. O conjunto de dados disponíveis podem ser encontrados aqui:https://drive.google.com/drive/folders/1F9Rwbzzz4LJCxZU-mTR4JqDT_2vJ7-sC?usp=sharing.


⇨ Nesse projeto você e sua squad deverão montar um dashboard com base no conjunto de dados escolhidos por vocês, a fim de realizar uma apresentação com a exploração dos dados.


A partir dos dados fornecidos optamos por utilizar a tabela GOT_episodes_v4.cvs que apresenta dados sobre os episódios e temporadas da série Game of Thrones. Durante o Brainstorm sobre perguntas que podem ser respondidas pelos dados selecionamos as seguintes perguntas:

Quantas temporadas a série possui?
Quantos episódios a série possui?
Quantos episódios cada temporada possui?
Qual o episódio mais bem avaliado de cada temporada?
Qual o episódio com maior duração?
Qual o episódio com menor duração?

Abaixo consta o script de criação do banco de dados .

CREATE DATABASE db_game_of_thrones;

USE db_game_of_thrones;

CREATE TABLE GOT_episodes ( id INT NOT NULL AUTO_INCREMENT, season INT NOT NULL, episode INT NOT NULL, title VARCHAR(100) NOT NULL, rating DECIMAL(10 , 1) NOT NULL, duration INT NOT NULL, PRIMARY KEY (id) );


/Quantas temporadas a série possui?/
SELECT COUNT(DISTINCT season) AS quantidade_de_temporadas FROM got_episodes;

/Quantos episódios a série possui?/
SELECT COUNT(episode) AS quantidade_de_episódios FROM got_episodes;

/Quantos episódios cada temporada possui?/
SELECT season, COUNT(episode) AS quantidade_de_episódios_por_temporada FROM got_episodes GROUP BY season;

/Qual o episódio mais bem avaliado de cada temporada?/
SELECT * FROM got_episodes WHERE season = 1 ORDER BY rating DESC LIMIT 1; SELECT * FROM got_episodes WHERE season = 2 ORDER BY rating DESC LIMIT 1; SELECT * FROM got_episodes WHERE season = 3 ORDER BY rating DESC LIMIT 1; SELECT * FROM got_episodes WHERE season = 4 ORDER BY rating DESC LIMIT 1; SELECT * FROM got_episodes WHERE season = 5 ORDER BY rating DESC LIMIT 1; SELECT * FROM got_episodes WHERE season = 6 ORDER BY rating DESC LIMIT 1; SELECT * FROM got_episodes WHERE season = 7 ORDER BY rating DESC LIMIT 1; SELECT * FROM got_episodes WHERE season = 8 ORDER BY rating DESC LIMIT 1;

/Qual o episódio com maior duração?/
SELECT season, episode, title, duration FROM got_episodes ORDER BY duration DESC;

/Qual o episódio com menor duração?/
SELECT season, episode, title, duration FROM got_episodes ORDER BY duration ASC;