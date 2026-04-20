# 🎙️ Assistente de Voz Inteligente: Whisper + GPT-4 + gTTS

Este projeto é um assistente de voz completo desenvolvido no ambiente Google Colab. Ele utiliza uma combinação de tecnologias web e inteligência artificial para ouvir, processar e responder aos usuários por voz, simulando uma interação humana.

## 🚀 Como Funciona

O fluxo da aplicação é dividido em três pilares principais:

1.  **Captura e Transcrição (STT):** 
    - O áudio é gravado diretamente no navegador através de uma interface **JavaScript** que utiliza a *MediaStream Recording API*.
    - O arquivo resultante é processado pelo modelo **Whisper da OpenAI** (versão `small`), que converte a fala em texto com alta precisão.
2.  **Processamento de IA (LLM):** 
    - O texto transcrito é enviado ao **GPT-4** (via biblioteca `g4f`), que analisa o contexto e gera uma resposta inteligente.
3.  **Síntese de Voz (TTS):** 
    - A resposta é convertida em áudio natural utilizando o **gTTS (Google Text-to-Speech)**.

## 🛠️ Tecnologias Utilizadas

*   **Python:** Linguagem base do projeto.
*   **JavaScript:** Utilizado para a ponte de comunicação entre o hardware (microfone) e o ambiente Colab.
*   **OpenAI Whisper:** Modelo avançado de reconhecimento de fala.
*   **g4f (GPT4Free):** Interface para modelos GPT-4.
*   **gTTS:** Biblioteca para geração de voz.
*   **IPython Display:** Para execução de scripts JS e reprodução de áudio.

## 📋 Integração com Microfone (JS)

Para permitir a gravação no ambiente de nuvem do Google Colab, o projeto utiliza um script JavaScript customizado que:
- Solicita permissão de áudio ao usuário (`getUserMedia`).
- Grava os dados em pedaços (*chunks*) via `MediaRecorder`.
- Converte o áudio para `base64` para ser processado pelo Python.

## 📖 Como Usar

1.  Abra o notebook no **Google Colab**.
2.  Instale as dependências necessárias:
    ```bash
    pip install openai-whisper g4f gtts
    ```
3.  Execute as células para carregar o modelo Whisper e a função de gravação.
4.  Ao iniciar a célula de voz, fale por **5 segundos** (ou o tempo definido).
5.  O assistente exibirá a transcrição e reproduzirá a resposta automaticamente.


