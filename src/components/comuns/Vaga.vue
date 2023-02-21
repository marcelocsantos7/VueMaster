<template>
	<div class="card">
		<div class="card-header bg-dark text-white">{{ titulo }}</div>
		<div class="card-body">
			<p>{{ descricao }}</p>
		</div>
		<div class="card-footer">
			<small class="text-muted">Salário: {{ salario }} | Modalidade: {{ getModalidade }} | Tipo: {{ getTipo }} |
				Publicação: {{
					getPublicacao }}</small>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Vaga',
	// props: ['titulo', 'descricao-vaga', 'salario', 'modalidade', 'tipo', 'publicacao']
	props: {
		titulo: {
			type: String,
			required: true,
			validator(prop) {
				console.log(`titulo lenght = ${prop.length}`)
				return prop.length <= 30 && true
			}
		},
		descricao: {
			type: String,
			// default: 'O contratante nao encaminhou dados pra vaga'
			default() {
				return `*`.repeat(20)
			}
		},
		salario: {
			type: [Number, String],
			required: true
		},
		modalidade: {
			type: String,
			required: true
		},
		tipo: {
			type: String,
			required: true
		},
		publicacao: {
			type: [String, Date],
			required: true
		},
	},
	computed: {
		getModalidade() {
			switch (this.modalidade) {
				case "1": return 'Home Office'
				case "2": return 'Presencial'
			}
			return ''
		},
		getTipo() {
			switch (this.tipo) {
				case "1": return 'CLT'
				case "2": return 'PJ'
			}
			return ''
		},
		getPublicacao() {
			let dataPublicacao = new Date(this.publicacao)
			return dataPublicacao.toLocaleDateString('pt-BR')
		}
	}
	// created() {
	// 	console.log('titulo =', typeof this.titulo)
	// 	console.log('descricao =', typeof this.descricaoVaga)
	// 	console.log('salario =', typeof this.salario)
	// 	console.log('modalidade =', typeof this.modalidade)
	// 	console.log('tipo =', typeof this.tipo)
	// 	console.log('publicacao =', typeof this.publicacao)
	// },
}
</script>