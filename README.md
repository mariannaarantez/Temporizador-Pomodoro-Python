# 🍅 Temporizador Pomodoro em Python

Um aplicativo de desktop simples e eficaz para gerenciamento de tempo, construído com Python e Tkinter.s

1.  Descrição do Projeto
2.  Funcionalidades
3.  Tecnologias Utilizadas
4.  Instalação e Execução
5.  Desafios Técnicos e Soluções
6.  Possíveis Melhorias
7.  Autores

# Descrição do Projeto

Este projeto é a implementação de um Temporizador Pomodoro, uma ferramenta de produtividade cujo objetivo é ajudar estudantes e profissionais a otimizar suas sessões de estudo e trabalho. Baseado na conhecida técnica de gerenciamento de tempo, o aplicativo automatiza o ciclo de focar intensamente em uma tarefa por 25 minutos (um "Pomodoro") e intercalá-lo com pausas curtas de 5 minutos — além de uma pausa mais longa após quatro ciclos. Dessa forma, a ferramenta busca eliminar distrações e combater a procrastinação em um aplicativo de desktop simples, leve e eficaz.

#  Funcionalidades

* **Ciclos de Foco e Pausa:** Alterna automaticamente entre períodos de Foco, Pausa Curta e Pausa Longa.  
* **Contagem de Ciclos:** Mantém um registro visual do número de ciclos Pomodoro completos.  
* **Cronômetro de Sessão:** Exibe o tempo total decorrido desde o início da sessão de trabalho.  
* **Alertas Integrados:** Emite notificações sonoras e visuais (pop-up) para sinalizar o fim de cada intervalo.  
* **Interface Intuitiva:** Uma GUI limpa e fácil de usar, construída com tkinter, com controles claros para iniciar e resetar o temporizador.  
* **Feedback Visual:** O título da janela muda dinamicamente para indicar o estado atual e a contagem de sessões (ex: "Trabalho 1/4").

#  **Tecnologias Utilizadas**

* **Linguagem:** Python 3
* **Interface Gráfica (GUI):** tkinter (Biblioteca padrão do Python)  
* **Alertas Sonoros:** winsound (Módulo nativo do Windows)

# ⚙️ **Instalação e Execução**

# **Pré-requisitos**

* **Python 3.x** instalado em sua máquina.  
* O aplicativo foi desenvolvido e testado no **Windows**, devido ao uso da biblioteca winsound para os alertas sonoros. Em outros sistemas operacionais, o programa funcionará, mas sem som.

# **Passos para Execução**

1. **Clone ou baixe o repositório:**  
   * Faça o download dos arquivos do projeto, incluindo pomodoro\_timer.py.  
2. **Imagem (Opcional):**  
   * Para uma melhor experiência visual, certifique-se de que o arquivo de imagem TOMATEEE.png esteja na mesma pasta que o script. Se a imagem não for encontrada, um círculo vermelho será exibido em seu lugar.  
3. **Execute o script:**  
   * Abra seu terminal ou prompt de comando, navegue até a pasta do projeto e execute o seguinte comando:

python pomodoro\_timer.py

4. **Uso do Aplicativo:**  
   * Clique em **Start** para iniciar o primeiro ciclo de trabalho.  
   * Clique em **Reset** para parar e reiniciar todos os contadores.

# 🧠 **Desafios Técnicos e Soluções**

Durante o desenvolvimento, enfrentamos alguns desafios interessantes:

# **1\. Implementação do Alerta Sonoro**

A necessidade de um alerta sonoro apresentou uma escolha entre portabilidade e simplicidade. O uso do módulo subprocess para chamar um player de áudio externo, embora multiplataforma, adicionaria complexidade e dependências externas.

**Solução:** Optei por uma solução otimizada para o ambiente Windows: o módulo winsound. A função winsound.Beep() permitiu gerar um alerta com uma única linha de código, sem arquivos de áudio externos. Para garantir que o programa não quebrasse em outros sistemas, encapsulei a chamada em um bloco try-except.

# **2\. Criação da Interface Gráfica Responsiva**

O principal desafio em qualquer GUI com temporizadores é evitar o congelamento da interface. Um loop while tradicional com time.sleep(1) travaria a janela, tornando-a inoperável.

**Solução:** Utilizei o método window.after(), um recurso do tkinter que agenda a execução de uma função após um intervalo de tempo especificado. Criei uma função count\_down recursiva que se auto-agenda a cada segundo. Isso permite que a contagem regressiva ocorra de forma assíncrona, mantendo o loop principal da interface livre para responder às interações do usuário.

#  **Possíveis Melhorias**

* **Customização de Tempos:** Permitir que o usuário defina a duração dos ciclos de trabalho e pausa através da interface.  
* **Multiplataforma:** Substituir winsound por uma biblioteca de áudio multiplataforma (como playsound ou pygame.mixer) para funcionalidade sonora em macOS e Linux.  
* **Seleção de Sons:** Adicionar a opção para o usuário escolher entre diferentes sons de alarme.  
* **Relatórios de Produtividade:** Salvar e exibir estatísticas de uso (ex: número de Pomodoros concluídos por dia).

