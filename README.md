# Atividade-7---Perceptron-

--- INÍCIO DO TREINAMENTO ---
Pesos Iniciais: [0. 0. 0.]
Taxa de aprendizado (alpha): 0.1

=== ÉPOCA 1 ===
Aluno: Joãozinho | Entrada (com bias): [1 0 0]
   Soma: 0.00 -> Saída h(x): 0 | Esperado (y): 0 | Erro: 0
   -> Sem atualização.
------------------------------
Aluno: Huguinho | Entrada (com bias): [1 0 1]
   Soma: 0.00 -> Saída h(x): 0 | Esperado (y): 0 | Erro: 0
   -> Sem atualização.
------------------------------
Aluno: Zezinho | Entrada (com bias): [1 1 0]
   Soma: 0.00 -> Saída h(x): 0 | Esperado (y): 1 | Erro: 1
   -> ATUALIZAÇÃO: w_antigo:[0. 0. 0.] + (alpha*1*x) = w_novo:[0.1 0.1 0. ]
------------------------------
Aluno: Luizinho | Entrada (com bias): [1 1 1]
   Soma: 0.20 -> Saída h(x): 1 | Esperado (y): 1 | Erro: 0
   -> Sem atualização.
------------------------------
Fim do Ciclo 1. Pesos finais da época: [0.1 0.1 0. ]

=== ÉPOCA 2 ===
Aluno: Joãozinho | Entrada (com bias): [1 0 0]
   Soma: 0.10 -> Saída h(x): 1 | Esperado (y): 0 | Erro: -1
   -> ATUALIZAÇÃO: w_antigo:[0.1 0.1 0. ] + (alpha*-1*x) = w_novo:[0.  0.1 0. ]
------------------------------
Aluno: Huguinho | Entrada (com bias): [1 0 1]
   Soma: 0.00 -> Saída h(x): 0 | Esperado (y): 0 | Erro: 0
   -> Sem atualização.
------------------------------
Aluno: Zezinho | Entrada (com bias): [1 1 0]
   Soma: 0.10 -> Saída h(x): 1 | Esperado (y): 1 | Erro: 0
   -> Sem atualização.
------------------------------
Aluno: Luizinho | Entrada (com bias): [1 1 1]
   Soma: 0.10 -> Saída h(x): 1 | Esperado (y): 1 | Erro: 0
   -> Sem atualização.
------------------------------
Fim do Ciclo 2. Pesos finais da época: [0.  0.1 0. ]

RESUMO FINAL DOS PESOS:
Bias (theta_0): 0.0
Peso Estudou (theta_1): 0.1
Peso Trabalho (theta_2): 0.0
