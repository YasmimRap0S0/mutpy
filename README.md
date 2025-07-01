# Caractéristicas do mupty:
> altera propositalmente o código-fonte. <br>
> verificar se os testes unitários conseguem detectar essas mudanças. <br>
> Se teste falha ao detectar a mutação, o mutante sobrevive. Se o teste detecta e falha como esperado, o mutante é morto. <br>

# Etapas do mupty_tutorial:

<h3> **Etapa 1**: Execução de testes normais:</>
![alt text](image.png)
<h3> **Etapa 2**: Ao tentar utilizar o mupty, o mupty tenta usar função find_loader no Python 3.12, ocasionando erro. Como alternativa, editamos o arquivo __init__.py do venv</>
<h3> **Etapa 3**: Em seguida, é possível executar os testes unitários com as mutações por meio do seguinte comando:</>

```sh
mut.py --target calculator --unit-test test_calculator -m 
```

> Especificações:
--target: especifica o arquivo alvo que será testado
--unit-test: especifica o arquivo de teste unitário que será usado para testar as mutações
-m : mostra as mutações que foram feitas no código

Após a execução do comando, obtemos a log:

```sh
(venv) @YasmimRap0S0 ➜ /workspaces/mutpy/mutpy_tutorial (main) $ python -m unittest test_calculator.py
....
----------------------------------------------------------------------
Ran 4 tests in 0.001s

OK
(venv) @YasmimRap0S0 ➜ /workspaces/mutpy/mutpy_tutorial (main) $ mut.py --target calculator --unit-test test_calculator -m
[*] Start mutation process:
   - targets: calculator
   - tests: test_calculator
[*] 4 tests passed:
   - test_calculator [0.00022 s]
[*] Start mutants generation and execution:
   - [#   1] AOR calculator: 
--------------------------------------------------------------------------------
   1: 
   2: def add(a, b):
-  3:     return a + b
+  3:     return a - b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
--------------------------------------------------------------------------------
[0.00368 s] killed by test_add (test_calculator.TestCalculator.test_add)
   - [#   2] AOR calculator: 
--------------------------------------------------------------------------------
   1: 
   2: def add(a, b):
   3:     return a + b
   4: def subtract(a, b):
-  5:     return a - b
+  5:     return a + b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
   9:     if b == 0:
--------------------------------------------------------------------------------
[0.00360 s] killed by test_subtract (test_calculator.TestCalculator.test_subtract)
   - [#   3] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a / b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00362 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   4] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a // b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00361 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   5] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a ** b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00358 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   6] AOR calculator: 
--------------------------------------------------------------------------------
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
- 12:     return a / b
+ 12:     return a // b
--------------------------------------------------------------------------------
[0.00496 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   7] AOR calculator: 
--------------------------------------------------------------------------------
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
- 12:     return a / b
+ 12:     return a * b
--------------------------------------------------------------------------------
[0.00450 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   8] COI calculator: 
--------------------------------------------------------------------------------
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
-  9:     if b == 0:
+  9:     if not (b == 0):
  10:         raise ValueError('Cannot divide by zero!')
  11:     
  12:     return a / b
--------------------------------------------------------------------------------
[0.00364 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   9] ROR calculator: 
--------------------------------------------------------------------------------
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
-  9:     if b == 0:
+  9:     if b != 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
  12:     return a / b
--------------------------------------------------------------------------------
[0.00424 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
[*] Mutation score [0.11672 s]: 100.0%
   - all: 9
   - killed: 9 (100.0%)
   - survived: 0 (0.0%)
   - incompetent: 0 (0.0%)
   - timeout: 0 (0.0%)
(venv) @YasmimRap0S0 ➜ /workspaces/mutpy/mutpy_tutorial (main) $ python -m unittest test_calculator.py
....
----------------------------------------------------------------------
Ran 4 tests in 0.000s

OK
(venv) @YasmimRap0S0 ➜ /workspaces/mutpy/mutpy_tutorial (main) $ mut.py --target calculator --unit-test test_calculator -m
[*] Start mutation process:
   - targets: calculator
   - tests: test_calculator
[*] 4 tests passed:
   - test_calculator [0.00022 s]
[*] Start mutants generation and execution:
   - [#   1] AOR calculator: 
--------------------------------------------------------------------------------
   1: 
   2: def add(a, b):
-  3:     return a + b
+  3:     return a - b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
--------------------------------------------------------------------------------
[0.00359 s] killed by test_add (test_calculator.TestCalculator.test_add)
   - [#   2] AOR calculator: 
--------------------------------------------------------------------------------
   1: 
   2: def add(a, b):
   3:     return a + b
   4: def subtract(a, b):
-  5:     return a - b
+  5:     return a + b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
   9:     if b == 0:
--------------------------------------------------------------------------------
[0.00363 s] killed by test_subtract (test_calculator.TestCalculator.test_subtract)
   - [#   3] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a / b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00355 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   4] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a // b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00365 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   5] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a ** b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00474 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   6] AOR calculator: 
--------------------------------------------------------------------------------
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
- 12:     return a / b
+ 12:     return a // b
--------------------------------------------------------------------------------
[0.00484 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   7] AOR calculator: 
--------------------------------------------------------------------------------
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
- 12:     return a / b
+ 12:     return a * b
--------------------------------------------------------------------------------
[0.00424 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   8] COI calculator: 
--------------------------------------------------------------------------------
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
-  9:     if b == 0:
+  9:     if not (b == 0):
  10:         raise ValueError('Cannot divide by zero!')
  11:     
  12:     return a / b
--------------------------------------------------------------------------------
[0.00351 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   9] ROR calculator: 
--------------------------------------------------------------------------------
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
-  9:     if b == 0:
+  9:     if b != 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
  12:     return a / b
--------------------------------------------------------------------------------
[0.00438 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
[*] Mutation score [0.11796 s]: 100.0%
   - all: 9
   - killed: 9 (100.0%)
   - survived: 0 (0.0%)
   - incompetent: 0 (0.0%)
   - timeout: 0 (0.0%)
(venv) @YasmimRap0S0 ➜ /workspaces/mutpy/mutpy_tutorial (main) $ mut.py --target calculator --unit-test test_calculator -m
[*] Start mutation process:
   - targets: calculator
   - tests: test_calculator
[*] 4 tests passed:
   - test_calculator [0.00025 s]
[*] Start mutants generation and execution:
   - [#   1] AOR calculator: 
--------------------------------------------------------------------------------
   1: 
   2: def add(a, b):
-  3:     return a + b
+  3:     return a - b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
--------------------------------------------------------------------------------
[0.00369 s] killed by test_add (test_calculator.TestCalculator.test_add)
   - [#   2] AOR calculator: 
--------------------------------------------------------------------------------
   1: 
   2: def add(a, b):
   3:     return a + b
   4: def subtract(a, b):
-  5:     return a - b
+  5:     return a + b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
   9:     if b == 0:
--------------------------------------------------------------------------------
[0.00365 s] killed by test_subtract (test_calculator.TestCalculator.test_subtract)
   - [#   3] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a / b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00367 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   4] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a // b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00372 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   5] AOR calculator: 
--------------------------------------------------------------------------------
   3:     return a + b
   4: def subtract(a, b):
   5:     return a - b
   6: def multiply(a, b):
-  7:     return a * b
+  7:     return a ** b
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
--------------------------------------------------------------------------------
[0.00474 s] killed by test_multiply (test_calculator.TestCalculator.test_multiply)
   - [#   6] AOR calculator: 
--------------------------------------------------------------------------------
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
- 12:     return a / b
+ 12:     return a // b
--------------------------------------------------------------------------------
[0.00441 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   7] AOR calculator: 
--------------------------------------------------------------------------------
   8: def divide(a, b):
   9:     if b == 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
- 12:     return a / b
+ 12:     return a * b
--------------------------------------------------------------------------------
[0.00489 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   8] COI calculator: 
--------------------------------------------------------------------------------
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
-  9:     if b == 0:
+  9:     if not (b == 0):
  10:         raise ValueError('Cannot divide by zero!')
  11:     
  12:     return a / b
--------------------------------------------------------------------------------
[0.00375 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
   - [#   9] ROR calculator: 
--------------------------------------------------------------------------------
   5:     return a - b
   6: def multiply(a, b):
   7:     return a * b
   8: def divide(a, b):
-  9:     if b == 0:
+  9:     if b != 0:
  10:         raise ValueError('Cannot divide by zero!')
  11:     
  12:     return a / b
--------------------------------------------------------------------------------
[0.00446 s] killed by test_divide (test_calculator.TestCalculator.test_divide)
[*] Mutation score [0.12225 s]: 100.0%
   - all: 9
   - killed: 9 (100.0%)
   - survived: 0 (0.0%)
   - incompetent: 0 (0.0%)
   - timeout: 0 (0.0%)

```









