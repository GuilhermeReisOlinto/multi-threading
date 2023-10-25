API para aplicar conceitos de threads no Node.js, utilizando o módulo 'worker_threads'. A API inclui três rotas, duas das quais fazem uso de threads. Uma dessas rotas utiliza uma thread auxiliar, enquanto a outra aproveita quatro threads simultâneas. Importante notar que, mesmo enquanto as threads estão em ação, a terceira rota continua funcionando sem interrupções.

O Node.js opera com um modelo de event loop que utiliza uma thread principal para delegar tarefas a outras threads por meio da biblioteca libuv. No entanto, durante a execução do event loop, a aplicação fica bloqueada até que as tarefas sejam concluídas. Para melhorar o desempenho da aplicação e contornar esse problema, optamos por delegar tarefas intensivas para threads separadas. Essas threads funcionam em paralelo e retornam os resultados quando concluem suas tarefas, permitindo que a aplicação continue operando de forma eficiente e responsiva.

Rode no terminal linux para obter o tempo da requeste
# time curl --get http://localhost:3000/blocking

Rode no terminal linux para obter o tempo da requeste
# time curl --get http://localhost:3000/blocking-fourthreads

1. Rodar aplicação
npm run start