# 🛡️ LAB 02: Insecure Output Handling & XSS via IA (OWASP LLM02)

Este repositório contém o laboratório prático de cibersegurança em Inteligência Artificial focado em **Insecure Output Handling**, exploração de **XSS via IA** e implementação de **Sanitização de Saída (*Output Guardrails*)**.

---
## 🎯 Objetivo do Laboratório
Demonstrar na prática como a confiança cega na saída gerada por uma LLM (Large Language Model) sem a devida sanitização pode permitir a injeção e execução de scripts maliciosos (XSS/Code Injection), e como implementar camadas defensivas em Python e Front-End para mitigar esse risco.
---
## 🧪 Estrutura da Atividade

### 🔴 Red Team (Ataque)
* **Conceito:** Exploração da vulnerabilidade **OWASP LLM02**, onde o texto retornado pela IA é renderizado diretamente na interface do usuário sem higienização ou validação de código.
* **Desafio:** Utilizar técnicas de *Prompt Injection* para induzir a IA a gerar cargas úteis (*payloads*) em HTML e JavaScript (`<script>alert('XSS_VIA_IA')</script>`), simulando o comprometimento de sessões de usuários.

### 🔵 Blue Team (Defesa)
* **Conceito:** Aplicação de sanitização estrita de saída e codificação de caracteres (*HTML Encoding*).
* **Solução:** Implementação de um *Output Guardrail* em Python que analisa e higieniza a resposta da IA antes de renderizá-la, neutralizando tags executáveis e impedindo a execução de scripts no navegador.
---
## 🚀 Como Executar no Google Colab

1. Acesse o notebook do laboratório clicando em [`INSECURE_OUTPUT_HANDLING.ipynb`](./INSECURE_OUTPUT_HANDLING.ipynb) ou abra diretamente pelo Google Colab.
2. Certifique-se de ativar a GPU T4:
   * Menu: `Ambiente de Execução` ➔ `Alterar tipo de ambiente de execução` ➔ `Acelerador de Hardware: GPU T4`.
3. Execute as células em sequência para carregar o modelo `TinyLlama/TinyLlama-1.1B-Chat-v1.0`.
4. Faça as missões práticas de **Red Team** e **Blue Team** indicadas no notebook.
---
## 🧰 Tecnologias Utilizadas
* **Ambiente:** Google Colab (GPU T4)
* **Linguagem:** Python 3.10+
* **Frameworks:** Hugging Face `transformers`, `torch`, `html` / `IPython.display`
* **Modelo LLM:** `TinyLlama/TinyLlama-1.1B-Chat-v1.0`
