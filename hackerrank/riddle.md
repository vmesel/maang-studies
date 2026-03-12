Neste exercício, precisamos achar o máximo dos minimos dada janelas móveis de uma lista

Dada uma lista [1, 2, 3], devemos calcular todas as janelas móveis possíveis, neste caso, de 1 a 3 itens por janela móvel, pegar o minimo item da sliding window e achar o máximo valor de todas as sliding windows de mesmo tamanho.

```
def riddle(arr):
    sliding_windows = {}
    max_values = []
    for sliding_window_size in range(1, len(arr) + 1):
        sliding_windows[sliding_window_size] = []
        for idx in range(len(arr)):
            sliding_window = arr[idx: idx + sliding_window_size]
            if len(sliding_window) < sliding_window_size:
                continue
            sliding_windows[sliding_window_size].append(min(sliding_window))
        
        max_values.append(max(sliding_windows[sliding_window_size]))
        
    return max_values
```
