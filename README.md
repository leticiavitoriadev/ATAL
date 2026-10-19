## Sudoku

Resolve um Sudoku de N² x N² casas com blocos N x N, para N de 2 a 5 (4x4, 9x9, 16x16 e 25x25). Imprime a solução ou avisa quando o problema não tem solução ou o tabuleiro inicial é inválido.

### Como usar

    python3 sudoku.py entrada.txt     # lê de um arquivo
    python3 sudoku.py < entrada.txt   # lê da entrada padrão
    python3 sudoku.py                 # resolve os exemplos embutidos

A entrada começa com N, seguido das N² linhas do tabuleiro, com valores separados por espaço e `0` ou `.` nas casas vazias:

    2
    1 0 0 0
    0 0 3 0
    0 4 0 0
    0 0 0 2

### Como funciona

Usa backtracking com máscaras de bits para registrar os valores já usados em cada linha, coluna e bloco. Em cada passo, ramifica pela opção mais restrita:

- a casa vazia com menos candidatos (heurística MRV), ou
- o valor que cabe em menos casas de alguma linha, coluna ou bloco.

Com essa escolha, tabuleiros de até 16x16 resolvem instantaneamente e os de 25x25 em alguns segundos.
