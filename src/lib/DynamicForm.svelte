<script>
  import InputComponent from "./inputComponent.svelte";
  import ButtonComponent from "./ButtonComponent.svelte";
  export let handleConfirmBtn;
  export let componentForm;

  let componentField = {};
  componentForm.forEach((key) => {
    componentField[key.componentKey] = key.value;
  });

  const onSubmit = () => {
    handleConfirmBtn(componentField);
  };
</script>

<div class="w-1/2 mt-10 px-6">
  <form on:submit|preventDefault={onSubmit}>
    {#each componentForm as field}
      <InputComponent
        label={field.label}
        id={field.id}
        placeholder={field.placeholder}
        type={field.type}
        required={field.required}
        bind:value={componentField[field.componentKey]}
      />
    {/each}
    <div class="px-1 py-3 sm:px-3 sm:flex sm:flex-row-reverse">
      <ButtonComponent type='submit' btnLabel='Submit' />
    </div>
  </form>
</div>
