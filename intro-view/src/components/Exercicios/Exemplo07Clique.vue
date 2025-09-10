        <script setup>
        import { ref } from 'vue'

        const contador = ref(0)
        const estado = ref('ativo') // 'ativo', 'inativo', 'carregando'

        function incrementar() {
        if (estado.value === 'ativo') {
            estado.value = 'carregando'
            setTimeout(() => {
            contador.value++
            estado.value = 'ativo'
            }, 800)
        }
        }

        function inativar() {
        estado.value = 'inativo'
        }

        function ativar() {
        estado.value = 'ativo'
        }
        </script>

        <template>
        <div>
            <h2>Contador: {{ contador }}</h2>
            <button
            :class="estado"
            @click="incrementar"
            :disabled="estado !== 'ativo'"
            >
            <span v-if="estado === 'carregando'">Carregando...</span>
            <span v-else>Incrementar</span>
            </button>
            <button
            :class="{'ativo': estado !== 'inativo', 'inativo': estado === 'inativo'}"
            @click="inativar"
            :disabled="estado === 'inativo'"
            >
            Inativar
            </button>
            <button
            :class="{'ativo': estado === 'inativo', 'inativo': estado !== 'inativo'}"
            @click="ativar"
            :disabled="estado === 'ativo'"
            >
            Ativar
            </button>
        </div>
        </template>

        <style scoped>
        .ativo {
        background: #2ecc40;
        color: #fff;
        border: none;
        margin: 0.3rem;
        padding: 0.6rem 1.2rem;
        border-radius: 0.4rem;
        cursor: pointer;
        }
        .inativo {
        background: #ff4136;
        color: #fff;
        border: none;
        margin: 0.3rem;
        padding: 0.6rem 1.2rem;
        border-radius: 0.4rem;
        opacity: 0.6;
        cursor: not-allowed;
        }
        .carregando {
        background: #ffdc00;
        color: #222;
        border: none;
        margin: 0.3rem;
        padding: 0.6rem 1.2rem;
        border-radius: 0.4rem;
        cursor: wait;
        }
        </style>