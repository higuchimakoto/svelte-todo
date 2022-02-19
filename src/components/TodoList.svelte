<script>
    export let todoList

    const handleClickDelete = (index) => {
        todoList.splice(index, 1)
        todoList = [...todoList]
    }
</script>

<div>
    {#if todoList.length === 0}
        <div>アイテムを作成してください</div>
    {:else}
        <ul>
            {#each todoList as todoItem, index}
                <li class="todoItem">
                    <div>{todoItem}</div>
                    <button on:click={() => handleClickDelete(index)}>削除</button>
                </li>
            {/each}
        </ul>
    {/if}
</div>

<style>
    .todoItem {
        display: flex;
        width: 300px;
        justify-content: space-around;
        align-items: center;
        margin: 0 auto 20px;
    }
</style>
