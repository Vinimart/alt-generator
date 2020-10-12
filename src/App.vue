<template>
	<body id="app">
		<section class="hero is-primary is-bold">
			<div class="hero-body">
				<div class="container">
					<h1 class="title">ALT GENERATOR</h1>
					<h2 class="subtitle">A simple tool to generate HTML alt properties</h2>
				</div>
			</div>
		</section>

		<section class="section">
			<div class="container">
				<h1 class="title">Input</h1>
				<h2 class="subtitle">Insert below your HTML code:</h2>
			</div>

			<section class="section">
				<div class="container">
					<b-field vertical label="HTML Code">
						<b-input id="inputCode" type="textarea"></b-input>
					</b-field>

					<b-field vertical
						><!-- Label left empty for spacing -->
						<p class="control">
							<button @click="setInputInOutput" class="button is-large is-primary">
								Generate
							</button>
						</p>
					</b-field>
				</div>
			</section>
		</section>

		<section class="section">
			<div class="container">
				<h1 class="title">Output</h1>
				<h2 class="subtitle">Here is your HTML code plus the ALT properties set:</h2>
			</div>

			<section class="section">
				<div class="container">
					<b-field vertical label="HTML Code">
						<b-input id="outputCode" type="textarea" v-model="outputCode"></b-input>
					</b-field>

					<b-field vertical
						><!-- Label left empty for spacing -->
						<p class="control">
							<button class="button is-large is-primary">
								Copy
							</button>
						</p>
					</b-field>
				</div>
			</section>
		</section>

		<footer class="footer">
			<div class="content has-text-centered">
				<p><strong>Alt Generator</strong> by <a href="https://github.com/vinimart">Vinicius Martins</a>. The source code is licensed <a href="http://opensource.org/licenses/mit-license.php">MIT</a>. The website content is licensed <a href="http://creativecommons.org/licenses/by-nc-sa/4.0/">CC BY NC SA 4.0</a>.</p>
			</div>
		</footer>
	</body>
</template>

<script>
export default {
	data() {
		return {
			inputCode: "",
			outputCode: `<div class="card">
	<div class="card-content">
		<p class="title">
		“There are two hard things in computer science: cache invalidation, naming things, and off-by-one errors.”
		</p>
		<p class="subtitle">
		Jeff Atwood
		</p>
	</div>
	<footer class="card-footer">
		<p class="card-footer-item">
		<span>
			View on <a href="https://twitter.com/codinghorror/status/506010907021828096">Twitter</a>
		</span>
		</p>
		<p class="card-footer-item">
		<span>
			Share on <a href="#">Facebook</a>
		</span>
		</p>
	</footer>
</div>`,
		};
	},
	methods: {
		setInputInOutput() {
			//this.checkAltProp();
			this.stringIntoArray()
		},

		getInputCode() {
			const inputCode = document.getElementById("inputCode").value;
			return inputCode;
		},

		checkAltProp() {
			const input = this.getInputCode();
			if (input.includes("alt=")) {
				return (this.outputCode = input);
			}
		},

		stringIntoArray() {
			// let input = this.getInputCode();
			// const re = /^<img/i;
			// // let inputSplit = input.split(re)
			// // console.log(inputSplit);
			// let array = Array.from(input)
			// console.log(array);
		}
	},
};
</script>

<style></style>
