# Consultas SQL para Filmes e Atores 
 Este repositório contém um conjunto de consultas SQL para um banco de dados de filmes e atores. As consultas abrangem desde a recuperação de informações básicas até junções complexas entre tabelas. Abaixo está a descrição de cada consulta e seu propósito.
 
---
## Consultas:

1. **Consultar Nome e Ano dos Filmes**:
   ```sql
   SELECT Nome, Ano FROM Filmes;
    ```
2. **Consulta o nome e ano dos filmes, ordenados por ordem crescente pelo ano**
    ```sql
    SELECT * FROM Filmes ORDER BY(Ano)
    ```
3. **Buscar pelo filme de volta para o futuro, trazendo o nome, ano e a duração**
    ```sql
    SELECT * FROM Filmes
    where Nome = 'De Volta para o Futuro';
    ```
4. **Buscar os filmes lançados em 1997**
    ```sql
    SELECT * FROM Filmes
    where Ano = '1997'
    ```
5. **Buscar os filmes lançados APÓS o ano 2000**
    ```sql
    SELECT * FROM Filmes
    where Ano > '2000'
    ```
6. **Buscar os filmes com a duracao maior que 100 e menor que 150, ordenando pela duracao em ordem crescente**
    ```sql
    SELECT * FROM Filmes
    where Duracao > 100 AND Duracao < 150 ORDER BY(Duracao)
    ```
7. **Buscar a quantidade de filmes lançadas no ano, agrupando por ano, ordenando pela duracao em ordem decrescente**
    ```sql
    SELECT Ano, COUNT(*) AS Quantidade
    FROM Filmes
    GROUP BY Ano
    ORDER BY Ano;
    ```
8. **Buscar os Atores do gênero masculino, retornando o PrimeiroNome, UltimoNome**
    ```sql
    SELECT PrimeiroNome, UltimoNome
    FROM Atores
    WHERE Genero = 'M';
    ```
9. **Buscar os Atores do gênero feminino, retornando o PrimeiroNome, UltimoNome, e ordenando pelo PrimeiroNome**
    ```sql
    SELECT PrimeiroNome, UltimoNome
    FROM Atores
    WHERE Genero = 'F'
    ORDER BY(PrimeiroNome);
    ```
10. **Buscar o nome do filme e o gênero**
    ```sql
    SELECT F.Nome, G.Genero
    FROM Filmes F
    JOIN FilmesGenero FG ON F.Id = FG.IdFilme
    JOIN Generos G ON FG.IdGenero = G.Id;
    ```
11. **Buscar o nome do filme e o gênero do tipo "Mistério"**
    ```sql
    SELECT F.Nome, G.Genero
    FROM Filmes F
    JOIN FilmesGenero FG ON F.Id = FG.IdFilme
    JOIN Generos G ON FG.IdGenero = G.Id
    WHERE G.Genero = 'Mistério'
    ```
12. **Buscar o nome do filme e os atores, trazendo o PrimeiroNome, UltimoNome e seu Papel**
    ```sql
    SELECT F.Nome, A.PrimeiroNome, A.UltimoNome, EF.papel
    FROM Filmes F
    JOIN ElencoFilme EF ON F.Id = EF.IdFilme
    JOIN Atores A ON EF.IdAtor = A.Id;
    ```
---

## Como Utilizar

1. Certifique-se de ter um banco de dados SQL configurado com as tabelas mencionadas acima.

2. Copie e cole as consultas SQL conforme necessário para obter os dados desejados.

3. Modifique as consultas conforme necessário para ajustar às suas necessidades específicas.