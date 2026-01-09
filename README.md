# Teleprompter por Reconhecimento de Voz

O **Teleprompter por Reconhecimento de Voz** é um MVP desenvolvido para automatizar a rolagem do teleprompter durante transmissões e gravações.  
A aplicação usa **reconhecimento de voz em tempo real** para acompanhar o ritmo de leitura do apresentador e avançar o texto automaticamente, reduzindo a necessidade de um operador.

O sistema foi pensado para:
- Reduzir falhas humanas  
- Dar mais fluidez e naturalidade à apresentação  
- Funcionar **100% localmente**, usando o modelo offline **Vosk**

---

## Tecnologias Utilizadas

- **Python 3.10+**
- **Flask** — Servidor web  
- **Flask‑SocketIO** — Comunicação em tempo real  
- **Eventlet** — Suporte para WebSockets  
- **Vosk** — Reconhecimento de voz offline  
- **PyAudio** — Captura de áudio  
- **HTML + CSS + JavaScript** — Interface

---

## Interface do Teleprompter  

A interface estará disponível em:  
**http://127.0.0.1:5500**

---

## Estrutura Final do Projeto

A estrutura deve ficar assim:

<pre>
Projeto-Porto-Digital/
├── app.py
├── model/
│   └── (arquivos do modelo vosk)
├── templates/
│   └── index.html
└── README.md
├── roteiro.txt
├── teleprompter_log.json
</pre>

# Passo a Passo para Execução do MVP

A seguir está o passo a passo completo para **recriar, instalar e executar** o MVP em qualquer computador Windows partindo de um ambiente totalmente limpo.

---

## 1. Requisitos

### ✔ Python 3.10+  
Baixe em: https://www.python.org/downloads  
> Marque a opção: **Add Python to PATH**

### ✔ Git  
Baixe em: https://git-scm.com/downloads  

---

## 2. Clonar o Projeto

Abra o terminal ou Git Bash na pasta desejada e execute:

```bash
git clone https://github.com/codedbydaph/Projeto-Porto-Digital.git
cd Projeto-Porto-Digital
```

---

##  3. Criar Ambiente Virtual

Dentro da pasta do projeto:

```bash
python -m venv venv
```

Ativar ambiente virtual (Windows):

```bash
.\venv\Scripts\activate
```

---

## 4. Instalar Dependências

### ✔ Instalando PyAudio corretamente (Windows)

```bash
pip install pipwin
pipwin install pyaudio
```

### ✔ Instalar o restante das dependências

```bash
pip install flask flask-socketio eventlet vosk
```

---

## 5. Executar o Teleprompter

Com o ambiente virtual ativado, execute:

```bash
python app.py
```

O sistema solicitará a senha:

```
123456
```

Se tudo estiver correto, o servidor ficará disponível em:

```
http://127.0.0.1:5500
```

---

## 6. Como Usar

1. Abra o navegador  
2. Acesse o endereço acima  
3. Cole ou escreva o roteiro desejado  
4. Comece a ler em voz alta  
5. A rolagem acontecerá automaticamente 📜✨

Quando o terminal mostrar:

```
--- NO AR: Monitorando X linhas ---
```

Significa que o microfone está ativo 🎙️

---

##  Arquitetura do Sistema  

Fluxo simplificado:

1. 🎙️ Captura de áudio pelo microfone  
2. 🧠 Áudio enviado para o modelo Vosk (offline)  
3. 🛰️ Flask-SocketIO processa e envia atualizações  
4. 🌐 Interface web recebe comandos e rola o texto automaticamente  

---

##  7. Possíveis Melhorias Futuras

- Captura de áudio via navegador  
- Deploy remoto para uso multiusuário  
- Painel de controle para operadores  
- Ajustes automáticos de velocidade com IA  

---

##  Autores

Projeto desenvolvido:

- Ana Clara Lélis (Líder) – Product Owner & Analista de Requisitos (Gestão de Documentação).
- Diego Marcelo – Desenvolvedor Full Stack (Back-End & Front-End).
- Ana Luisa Moreira – Desenvolvedora Back-End.
- Arthur Braga – Analista de Requisitos & Speaker (Apresentação).
- Daphine Milani – Analista de Requisitos & Speaker (Documentação e Apresentação).
- Ana Luiza Galati – Social Media & Video Producer (Documentação e Pitch).
- Arthur Ramalho – Technical Writer (Documentação Técnica).
  
---
