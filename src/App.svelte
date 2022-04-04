<script>
	import DisplayInput from './DisplayInput.svelte';
	import Button from './Button.svelte';
  import calculatorStore from "./calculator-store";
 
  const { setValue } = $calculatorStore;

  const handleClearButtonClick = () => {
  setValue("");
  }

  const handleButtonClick = (text) => () => { //high ordered function (used for extending event callback with text variable)
  setValue($calculatorStore.value + text);
  }

  const handleResultButtonClick = () => {
    try {
      const newValue= eval($calculatorStore.value);
      setValue(newValue + "");
    } catch (err) {
      alert(err.message);
    }
  }
</script>

<p class="text-align-center">
	<img src="img/owl1.png" alt="logo" height="200px" width="200px" />
</p>
<h2>My JS Calculator</h2>
<DisplayInput />
<table class="center">
	<tr>
		<td>
			<Button text="C" onClick={handleClearButtonClick} />
      <Button text="**" onClick={handleButtonClick("**")} />
      <Button text="%" onClick={handleButtonClick("%")} />
      <Button text="/" onClick={handleButtonClick("/")} />
		</td>
	</tr>
  <tr>
		<td>
			<Button text="7" onClick={handleButtonClick("7")} />
      <Button text="8" onClick={handleButtonClick("8")} />
      <Button text="9" onClick={handleButtonClick("9")} />
      <Button text="*" onClick={handleButtonClick("*")} />
		</td>
	</tr>
  <tr>
		<td>
			<Button text="4" onClick={handleButtonClick("4")} />
      <Button text="5" onClick={handleButtonClick("5")} />
      <Button text="6" onClick={handleButtonClick("6")} />
      <Button text="-" onClick={handleButtonClick("-")} />
		</td>
	</tr>
  <tr>
		<td>
			<Button text="1" onClick={handleButtonClick("1")} />
      <Button text="2" onClick={handleButtonClick("2")} />
      <Button text="3" onClick={handleButtonClick("3")} />
      <Button text="+" onClick={handleButtonClick("+")} />
		</td>
	</tr>
  <tr>
		<td>
			<Button text="." onClick={handleButtonClick(".")} />
      <Button text="0" onClick={handleButtonClick("0")} />
      <Button text="=" className="calc-button-result" onClick={handleResultButtonClick} />
		</td>
	</tr>
</table>

<style>
	:global(html), :global(body) {
  margin: 0;
  background-color: #F0FFF0;
  font-family: sans-serif;
  padding: 10px 20px;
}

h2 {
  font-size: 40px;
  text-align: center;
}

:global(.text-align-center) {
  text-align: center;
}

.center {
  margin-left: auto;
  margin-right: auto;
  padding-bottom: 100px;
}

</style>