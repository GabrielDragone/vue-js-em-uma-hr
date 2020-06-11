# vue-js-em-uma-hra
Projeto e ensinamentos da aula https://www.youtube.com/watch?v=cSa-SMVMGsE

Nesse projeto o professor ensinou a fazer um processo de cadastro, visualização e remoção simulando uma página de Comentários.

Um pouco mais sobre VueJs:
- Criado por Evan You, quando trabalhava no Google decidiu criar sua própria biblioteca de UI.
- 07/07/2013.
- Tudo é component.
- MVVM:
-- Model: Banco de Dados.
-- View: A tela.
-- View-Model: É a conexão, ou seja, o data binding entre o Model e a View.
- Two-way Data Binding: Característica do VueJs que sincroniza a View com o Model, se altera algo na interface, já salva no model. Se tem alguma operação no model, ele reflete na interface.
- Será feito um projeto para simular comentários, a partir daqui, conferir comentários no código.
- Importação Bootstrap.
- Importação Vuejs e como utilizar (Forma tradicional).
- Reativo.
- Diretivas: Maneira como acessar o html através do código.
- Single File Component:
-- O Vuejs através de seus compiladores permite que criemos um arquivo do tipo vue, pra criar o template e js que será o compenente.
-- Para isso, utilizamos os compiladores do Vuejs.
-- VueCLI, ferramenta de terminal que instalamos no computador através de npm, que cria um projeto com tudo configurado. (https://br.vuejs.org/v2/guide/installation.html#NPM)
-- Após instalar digitar no cmd: vue ui para abrir http://localhost:8000/project/select e criar o projeto.
-- Após criar, abrir a pasta do projeto criado e digitar no cmd npm run serve
-- A nivel de server-side o vuejs pega os arquivos e compila para JavaScript puro antes de ir pro browser.
-- Pasta Components encontram-se os form's e maneira como comunicam-se e trocam dados.
-- Comentários ao longo do código.