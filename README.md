# SD-PrioridadeThreadsJava# SD-PrioridadeThreadsJava

Atividade prática da disciplina Sistemas Distribuídos  
Demonstração do impacto da prioridade de threads em Java.

## Objetivo
- Entender como as prioridades (`Thread.MIN_PRIORITY` e `Thread.MAX_PRIORITY`) influenciam o escalonamento.
- Observar que a thread de alta prioridade (10) domina quase completamente a CPU.
- Comparar comportamento com e sem `sleep()`/`yield()`.
- Demonstrar encerramento limpo usando `interrupt()` + ShutdownHook.

## O que você vai observar na execução
- A thread de **alta prioridade** imprime muito mais linhas ("-> 10") do que a de baixa.
- A thread de **baixa prioridade** mal consegue executar (pode até parecer "travada").
- Isso acontece porque o escalonador do Java/SO dá preferência a threads de prioridade maior quando há disputa por CPU.

## Como compilar e executar

```bash
# Compilar
javac LancadorPrioridade.java

# Executar em background com log 
java LancadorPrioridade > LancadorPrioridade_$(date +%Y%m%d_%H%M%S).log &

# Ou executar em foreground e parar com CTRL+C
java LancadorPrioridade
