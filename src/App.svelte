<script>
  import DynamicForm from "./lib/DynamicForm.svelte";

  const content = DynamicForm;
  const componentForm = [
    {
      autofocus: true,
      label: "Input Text",
      id: "InputText",
      placeholder: "Input Text",
      componentKey: "name",
      type: "text",
      required: true
    },
    {
      label: "Input Password",
      id: "InputPassword",
      placeholder: "Input Password",
      componentKey: "password",
      type: "password",
      required: true,
      value: "This Is Password Value",
    },
    {
      label: "Input Number",
      id: "InputNumber",
      placeholder: "Input Number",
      componentKey: "age",
      type: "number",
      required: true,
      value: 19,
    },
    {
      label: "Textarea",
      id: "Input2",
      placeholder: "Textarea",
      componentKey: "address",
      type: "textarea",
      required: true,
      value: "This Is Default Value Textarea",
    },
  ];

  const handleConfirmBtn = (formData) => {
    alert(JSON.stringify(formData));
  };
</script>

<main>
  <svelte:component this={content} {handleConfirmBtn} {componentForm} />
</main>
