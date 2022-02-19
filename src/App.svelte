<script>
    import InputTodo from './components/InputTodo.svelte'

    import TodoList from './components/TodoList.svelte'
    let todoList = []
    let title

    // 作成ボタンを押したときの挙動
    const handleClickCreate = () => {
        todoList = [...todoList, title]
        title = ''
    }
</script>

<main>
    <InputTodo {handleClickCreate} bind:title/>
    <TodoList {todoList} />
</main>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>
