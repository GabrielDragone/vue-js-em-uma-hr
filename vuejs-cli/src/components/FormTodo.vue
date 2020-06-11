<template>
    <div class="form-todo form-group">
        <p>
            <input placeholder="Digite seu Nome" type="text" name="author" class="form-control" v-model="name" />
        </p>
        <p>
            <textarea placeholder="Digite seu Comentário" name="message" class="form-control" v-model="message"></textarea>
        </p>
        <button v-on:click="addComment" type="submit" class="btn btn-primary">Comentar</button>
    </div>
</template>

<script>
    export default{
        data(){
            return{
                name: '',
                message: ''
            }
        },
        methods: {
            addComment() { //v-on:click="addComment"
                console.log('Entrou no addComment()');
                console.log(this.name);
                console.log(this.message);

                if(this.message.trim() === ''){
                    alert('É necessário informar o Comentário para prosseguir!');
                    return;
                }

                //Método que o VueJs disponibiliza que dispara o evento para todos os componentes que estiverem ouvindo, ou seja passara para o Comments no <FormTodo>:
                this.$emit('add-todo', {
                    name: this.name,
                    message: this.message,
                });

                this.name = '';
                this.message = '';

                alert('Registro inserido!');
            },
        }
    }
    
</script>