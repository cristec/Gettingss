Após criar o menu, certifique-se de estar no branch new_menu e faça o commit, conforme a figura a seguir.

<img src="http://tableless.com.br/uploads/2015/09/new_menu_commit.png" alt="new_menu_commit" width="716" height="536" class="alignleft size-full wp-image-51254" />

Agora temos algumas modificações no branch new\_menu, e podemos trabalhar nesse branch por quanto tempo for necessário, já que o master está intacto. Aqui temos uma funcionalidade interessante, que se destaca em relação as outras ferramentas de versionamento. Suponha que, no meio do seu desenvolvimento do menu, surge a necessidade de resolver um bug crítico no master, algo como &#8220;está faltando o h1 no título do seu site&#8221;&#8230;. Ou seja, estamos no branch new\_menu e precisamos alterar o master. Para isso, use o comando `git checkout master`. Ao fazer isso, retornamos ao master e aquele menu que criamos não está mais presente, conforme a figura a seguir.

<img src="http://tableless.com.br/uploads/2015/09/back_to_master.png" alt="back_to_master" width="624" height="686" class="alignleft size-full wp-image-51255" />

É claro que não perdemos o menu, ele está apenas no branch new_menu. Quando retornarmos a ele, voltará. Agora altere o título do site, incluindo o h1, veja:

<pre class="lang-html">&lt;!DOCTYPE html&gt;


# Gettingss

Após alterar, faça commit e o push! Veja:

<img src="http://tableless.com.br/uploads/2015/09/git_push2.png" alt="git_push2" width="687" height="529" class="alignleft size-full wp-image-51256" />

Agora que resolvemos o problema do título, podemos voltar ao new_menu: `git checkout new_menu`. Após realizar este comando, temos o menu de volta no arquivo index.html, mas veja que o título não possui a tag H1. Isso acontece que estamos em outro branch. Tudo que acontece no master, fica no master. Tudo que acontece no new\_menu, fica no new\_menu

## Merge com conflitos

Se desejar trazer o título do master para o new_menu, devemos fazer uma operação chamada `merge`, que irá juntar um código no outro. Então, estando no branch new_menu, e querendo trazer uma alteração do master para este branch, precisamos realizar o seguinte comando: `git merge master`. Caso existam alterações nas mesmas linhas entre mesmos arquivos, um conflito será gerado, como no exemplo a seguir:

<img src="http://tableless.com.br/uploads/2015/09/conflict.png" alt="conflict" width="595" height="616" class="alignleft size-full wp-image-51259" />

Este é um exemplo de conflito que podo ocorrer quando realizamos um merge, indicado em `1`. Perceba que o código html possui uma definição entre dois blocos, o primeiro, em `2` mostra como é o código do branch new_menu, e o segundo bloco, em `3`, mostra como é o código no branch master. Edite o arquivo repassando para a seguinte forma:

<img src="http://tableless.com.br/uploads/2015/09/merge2.png" alt="merge2" width="578" height="613" class="alignleft size-full wp-image-51260" />

Ou seja, ajustamos os dois blocos, como se fosse um merge manual. Após resolver o conflito, vamos prepará-lo para o commit no branch new_menu, com o comando `git add`. Veja:

<img src="http://tableless.com.br/uploads/2015/09/merge3.png" alt="merge3" width="779" height="105" class="alignleft size-full wp-image-51261" />

Ou seja, resolvemos o conflito &#8220;na mão&#8221; e depois comitamos normalmente.

## Merge sem conflitos

Quando não alteremos a mesma linha de um arquivo em branches diferentes, conseguimos realizar um merge sem ocasionar conflitos. Isso pode ser notado ao trazermos o menu do branch new_menu para o master, da seguinte forma:

<img src="http://tableless.com.br/uploads/2015/09/merge4.png" alt="merge4" width="585" height="652" class="alignleft size-full wp-image-51262" />

Se não houver conflitos, basta realizar um commit normal para confirmar o merge.

## Vendo branches e merges

O github possui uma ferramenta gráfica para exibir os branches e merges do seu projeto. Clique no ícone em forma de gráfico no menu à direita do site e clique na aba Network, para se ter um resultado semelhante a figura a seguir:

<img src="http://tableless.com.br/uploads/2015/09/graph.png" alt="graph" width="1027" height="446" class="alignleft size-full wp-image-51265" />

## Lendo mais

Você pode ler mais sobre git e entender mais sobre controles de versão, nesses artigos do Tableless:

  * <a href="http://tableless.com.br/alguns-comandos-git/" target="_blank">Comandos Iniciais do Git</a> 
  * <a href="http://tableless.com.br/slides-devs-10-git/" target="_blank">Apresentações sobre GIT</a> 
  * <a href="http://tableless.com.br/iniciando-no-git-parte-1/" target="_blank">Iniciando com GIT &#8211; Parte 1</a> 
  * <a href="http://tableless.com.br/iniciando-no-git-parte-2/" target="_blank">Iniciando com GIT &#8211; Parte 2</a> 
  * <a href="http://tableless.com.br/git-com-interface-grafica/" target="_blank">Git com Interface Gráfica</a>
