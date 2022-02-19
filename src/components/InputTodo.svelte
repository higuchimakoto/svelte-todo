<script>
    export let title = ''
    $: disabledCreateButton = title === ''

    export let handleClickCreate
</script>

<div>
    <label>
        タイトル
        <input bind:value={title} />
    </label>
    <button disabled={disabledCreateButton} on:click={handleClickCreate}>作成</button>
</div>
