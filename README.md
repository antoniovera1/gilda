```Matlab
% Reporte 3 - Parte 1
disp(sprintf('\n\n\n----Tic Tac Toe---\nComputadora VS Computadora'))
gameset = [' ', ' ', ' ', ' ', ' ', ' ', ' ', ' ', ' '];

for round = 1:9
    if mod(round,2) == 0
    % Intercambiar de jugador según la ronda 
        player_symbol = 'O';
    else 
        player_symbol = 'X';
    end
    
    % ----------
    % Asignar valor a las casillas
    % ----------
    while 1
        box = randi([1 9],1,1);
        if gameset(1, box) == ' '
            gameset(1, box) = player_symbol;
            break
        end
    end
    % ----------
    % Mostrar el juego en cada ronda
    % ----------
    fprintf('---- Turno %d -----\n\n', round);
    fprintf('%s | %s | %s\n%s | %s | %s\n%s | %s | %s\n\n', gameset(1, 1), gameset(1, 2), gameset(1, 3), 
            gameset(1, 4), gameset(1, 5), gameset(1, 6), gameset(1, 7), gameset(1, 8), gameset(1, 9));
    
    % ----------
    % Revisar al ganador
    % ----------
    
    % Horizontal
    for i = 1:3:9
        if gameset(1,i) == player_symbol && gameset(1,i+1) == player_symbol && gameset(1,i+2) == player_symbol 
            fprintf('Felicidades, ¡Ganaste, ¨%s¨!', player_symbol);
            return
        end
    end
    % Vertical
    for i = 1:3
        if gameset(1,i) == player_symbol && gameset(1,i+3) == player_symbol && gameset(1,i+6) == player_symbol 
            fprintf('Felicidades, ¡Ganaste, ¨%s¨!', player_symbol);
            return
        end
    end
    % Diagonal 1
    if gameset(1,1) == player_symbol && gameset(1,5) == player_symbol && gameset(1,9) == player_symbol 
        fprintf('Felicidades, ¡Ganaste, ¨%s¨!', player_symbol);
        return
    end 
    
    % Diagonal 2
    if gameset(1,3) == player_symbol && gameset(1,5) == player_symbol && gameset(1,7) == player_symbol 
        fprintf('Felicidades, ¡Ganaste, ¨%s¨!', player_symbol);
        return
    end    
end
```
