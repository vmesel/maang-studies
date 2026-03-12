O problema do luck balance é um problema onde devemos conservar e manter a maior luck score possível, sem perder mais que K concursos.

Esse problema é basicamente o somatório de todos os concursos que podemos perder - todos os concursos importantes que devemos ganhar

```python
def luck_balance(k, contests):
    important_ones = []
    luck = 0
    for c in contests:
        if c[1] == 0:
            luck += c[0]
        
        else:
            important_ones.append(c[0])
    
    sorted_important_ones = sorted(important_ones, reverse=True)
    return luck - sum(sorted_important_ones[k:]) + sum(sorted_important_ones[:k])

```
