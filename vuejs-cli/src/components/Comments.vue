<template>
    <div class="container">
        <h1>Comentários</h1>
        <hr />
        <!-- Importa o Form do compontente FormTodo.vue: -->
        <FormTodo v-on:add-todo="addComment"></FormTodo>
        <hr />
        <p v-if="comments.length <= 0">Sem comentários...</p>
        <p v-if="comments.length > 0">{{comments.length}} comentários</p>
        <div class="list-group">
            <div class="list-group-item" v-for="(comment, index) in allComments" v-bind:key="index">
                <span class="comment__author">Autor: <strong>{{ comment.name }}</strong></span>
                <p>{{ comment.message }}</p>
                <div>
                    <a href="#" title="Excluir" v-on:click.prevent="removeComment(index)">Excluir</a>
                </div>
            </div>
            <hr />
        </div>
    </div>

</template>

<script>
    import FormTodo from './FormTodo';
    //Pega esse objeto e instância em um new vue:
    export default{
        components: {
            FormTodo
        },
        data() { 
            return {
                comments: [
                    {
                        name: 'Gabriel',
                        message: 'Olá Mundo'
                    },
                ],
                //name: '', //v-model="name" diretiva
                //message: '', //v-model="message" 
            }
        },
        //Cria todos os métodos que são disponinilizados no template através de diretivas:
        methods: {
            //Foi passada pro FormTodo.vue para separar código
            /*addComment() { //v-on:click="addComment"
                console.log('Entrou no addComment()');
                console.log(this.name);
                console.log(this.message);

                if(this.message.trim() === ''){
                    alert('É necessário informar o Comentário para prosseguir!');
                    return;
                }

                //Adiciona no array:
                this.comments.push({
                    name: this.name,
                    message: this.message
                });

                this.name = '';
                this.message = '';

                alert('Registro inserido!');
            },*/
            addComment(comment){
                console.log('Entrou no addComment enviado pelo FormTodo');
                this.comments.push(comment);
            },
            removeComment(index){ //v-on:click="removeComment", (comment, index)
            //O .prevent previne que o js não execute a ação comum do href
                console.log('Entrou removeComment()');

                //Remove o item da posição index e segundo parâmetro é informado para verificar quantos a partir do index serão removidos:
                this.comments.splice(index, 1);

                alert('Comentário excluído!');
            }
        },
        //Disponibiliza variáveis para serem utilizadas no template, está mais relacionado com a interface, parte de visualização; Utilizado para não fazer lógica dentro do template:
        computed: {
            allComments(){
                return this.comments.map(comment => ({
                    ...comment,
                    name: comment.name.trim() === '' ? 'Anônimo' : comment.name
                }))
            }
        },
        //Monitora ação em qualquer propriedade afim de tomar uma ação. Exemplo toda vez que alteramos essa variável, ele salva no banco de dados :
        watch: {
            comments(val){
                console.log('val', val);
            }
        }
    }
</script>
