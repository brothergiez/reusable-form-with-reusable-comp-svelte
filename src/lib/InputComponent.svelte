<script>
  export let autofocus = false;
  export let required = true;
  export let disabled = false;
  export let id;
  export let label;
  export let type = "text";
  export let value = "";
  export let rows = 5;
  export let placeholder = "";

  $: if (!value) value = "";

  const handleInput = (e) => {
    value = type.match(/^(number|range)$/) ? +e.target.value : e.target.value;
  };
</script>

<div class="w-full px-3  mb-6 md:mb-0">
  <label
    class="block uppercase tracking-wide text-black text-md font-bold mb-2"
    for={id}
    >{label}
  </label>

  {#if type !== "textarea"}
    <input
      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
      {id}
      {value}
      {disabled}
      {required}
      {placeholder}
      {autofocus}
      {type}
      on:input={handleInput}
    />
  {:else}
    <textarea
      class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
      {id}
      {value}
      {rows}
      {disabled}
      {required}
      {placeholder}
      {autofocus}
      on:input={handleInput}
    />
  {/if}
</div>
