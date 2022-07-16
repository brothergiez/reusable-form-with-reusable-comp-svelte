<script>
  export let type = "button";
  export let btnLabel = "Button";
  export let onClick = null;
</script>

<button
  {type}
  class="bg-red-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
  {onClick}
>
  {btnLabel}
</button>
