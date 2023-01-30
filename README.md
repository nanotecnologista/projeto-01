Boa noite galera!

## Resolvi trazer esse conteúdo, pois um amigo meu teve o mesmo problema que vou relatar.

Meu amigo começou a usar o Git e o GitHub para versionar seus projetos, porém ele cometeu um erro que o fez deixar algumas pastas inacessíveis em seu repositório do GitHub.

![Exemplo 1 - demonstração do erro em vídeo - GitHub](https://raw.githubusercontent.com/nanotecnologista/example-git/master/midia/nanotecnologista_example-git.gif)
---

### Explicação:

**O que acontece é que, quando você dá um git init no seu repositório, uma pasta é criada com as configurações do git. Geralmente não reparamos, pois ela fica como arquivo oculto, mas se você habilitar a opção de ver arquivos ocultos, verá a pasta.**

Assim como na imagem a seguir:
![Exemplo 2 - Pasta .git - GitHub](https://github.com/nanotecnologista/example-git/blob/master/midia/nanotecnologista_example_git.png?raw=true)

A pasta .git é onde ficam as configurações necessárias para que o git monitore as modificações do seu projeto. Além disso, ela é responsável por guardar e setar em qual versão o seu projeto está.

---

Até aí tudo bem. O problema é quando você já tem um arquivo .git na pasta principal, mas cria outras pastas dentro dela e dá um git init dentro da pasta criada.

### Vou exemplificar melhor: 

1. **Em meu computador, criei uma pasta chamada 'Projetos':**
![Demonstração - imagem 1](https://github.com/nanotecnologista/example-git/blob/master/midia/projetos.png?raw=true)

2. **Em seguida, dei um git init na pasta e subi ela para o GitHub:**
![Demonstração - imagem 2](https://github.com/nanotecnologista/example-git/blob/master/midia/nanotecnologista_repositorio_example.png?raw=true)

3. **Após isso, criei uma pasta chamada 'Projeto-01':**
   - Dentro dela dei um git init e adicionei um arquivo.
![Demonstração - imagem 3](https://github.com/nanotecnologista/example-git/blob/master/midia/projeto-01_git.png?raw=true)

---

*Se eu estiver dentro da pasta e publicar somente o 'Projeto-01' no GitHub, ele vai funcionar e ser acessível tranquilamente.
Caso queira ver o repositório do 'Projeto-01', aqui está o [link](https://github.com/nanotecnologista/projeto-01).*

---

4. **Repeti os mesmos passos e criei mais uma pasta chamada 'Projeto-02' (porém não publiquei ela no GitHub).**
![Demonstração - imagem 4](https://github.com/nanotecnologista/example-git/blob/master/midia/projeto-02_git.png?raw=true)




5. **Logo depois, retornei a pasta projetos, commitei as alterações e subi para o GitHub:**

           É AI QUE APARECE O PROBLEMA!

   - **O GitHub vai deixar as pastas 'Projeto-01' e 'Projeto-02' inacessíveis e o ícone da pasta recebe o ícone de uma seta dentro, pois dentro delas também existe um arquivo de configuração .git o que faz o GitHub travar o acesso à sua pasta.**
   ![Demonstração - imagem 5](https://github.com/nanotecnologista/example-git/blob/master/midia/nanotecnologista-example-git%20(1).png?raw=true)

---

## Solução:

**Bom, depende do seu objetivo. É bom você levar em conta alguns pontos:**

- Você quer deixar só um repositório contendo os seus projetos?
   - *Se sim, você pode **apenas deletar a pasta .git de 'Projeto-01' e 'Projeto-02'** e deixa apenas o .git da pasta Projetos.*


- Você quer apenas publicar seus projetos individualmente?
   - *Se sim, recomendo que **apague o apenas .git da pasta 'Projetos'** e também apague o repositório de Projetos, já que você vai publicar cada projeto individualmente. Pronto, agora é só modificar os seus projetos individualmente e publicá-los.* 
 
 
 - Você quer manter os dois (Vish, vou lhe sugerir a seguir uma gambiarra kkkk)? 
    - *Primeiro, copie os projetos 01 e 02, e cole fora da pasta Projetos (o local é da sua preferência), como as configurações dos projetos estão lá, nada se perderá.*
    
    - *Depois, **dentro da pasta Projetos**, você terá que **apagar o .git existente nas pastas dos projetos 01 e 02.***
    
    - Agora vem a gambis, rsrsrs! É só mexer nos projetos fora dessa pasta e subir as modificações normalmente. Maaaas, uma vez que o .git foi apagado de dentro dos projetos 01 e 02 da pasta Projetos, toda vez que houver uma alteração você terá que ficar copiando (das pasta que estão fora) e colando(dentro da pasta Projetos) as alterações que fizer nos projetos 01 e 02 . Então você vai poder commitar normalmente e os seus repositórios vão funcionar normalmente.

---
---
---
Galera, peço que me perdoem pela repetição de palavras e também se eu não consegui ser muito explicita.
Se vocês tiverem dúvidas ou outras alternativas ou puderem complementar o conteúdo, por favor, sintam-se à vontade para comentar. 

Eu também tentei adicionar ao .gitignore de Projetos o .git, mas mesmo assim ele não destravou o acesso as subpastas no GitHub.