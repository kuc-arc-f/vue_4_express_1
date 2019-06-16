<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <hr />
        <div class="form-group">
        <label for="TopicTitle">タイトル</label>
        <input type="text" class="form-control" id="title" v-model="title">
    </div>
    <div class="form-group">
        <label for="TopicContent">content</label>
        <textarea class="form-control" id="content" rows="3" v-model="content"></textarea>
    </div>
    <button v-on:click="send_post">投稿</button>

  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'HelloWorld',
    data () {
        return {
            message : 'msg-123',
            msg : "",
            title : "",
            content : "",
        }
    },
    created () {
        this.get_foo()
    },
    methods: {
        get_foo () {
            axios.get("/api_test1")
            .then(res =>  {
                var items = res.data.docs
                console.log(items)
                items.forEach( function (item) {
                    console.log(item)
                });
//                this.msg = res.data.msg
            })
        },
        send_post(){
            var task = {
                'title': this.title,
                'content': this.content
            };
            axios.post('/api_post1' , task ).then(res => {
                console.log(res.data );
//                console.log(res.data.content);
            });
        },
    }
}
</script>
