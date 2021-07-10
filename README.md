1)Escreva a função quantosSaoIguais que recebe 3 inteiros e retorna
a quantidade de argumentos recebidos iguais.
import Data.List
quantosSaoIguais xs
 |resultado >0 = resultado+1
 |otherwise = resultado
 where resultado = length xs - length(nub xs)
main::IO()
main = do
 print (quantosSaoIguais[3,2,1])
2) Defina a função minEmax que retorna uma tupla com o maior e
menor de três números: minEmax :: Int -> Int -> Int -> (Int, Int)
minEmax :: Int -> Int -> Int -> (Int,Int)
minEmax a b c = ((min a (min b c)), (max a(max b c)))
main::IO()
main = do
 print(minEmax 6 5 9)
Questão 3)Defina uma função max3 que recebe três valores inteiros
e resulta no maior deles. Use expressões condicionais aninhadas.
Faça uma anotação de tipo para a função em seu código.
max3 :: Int -> Int -> Int -> (Int)
max3 a b c
 |a>b && a>c = a
 |b>a && b>c = b
 |c>a && c>b = c
 |otherwise = 0
main::IO()
main = do
 print(max3 6 8 4)
Questão 4) Defina a função ordenaTupla :: (Int, Int, Int) -> (Int, Int, Int)
que coloca os elementos da tupla em ordem crescente.
ordenaTupla :: (Int, Int, Int) -> (Int, Int, Int)
ordenaTupla (a, b, c)
 |a>=b && b>=c= (c,b,a)
 |a>=c && c>=b = (b,c,a)
 |b>=a && a>=c = (c,a,b)
 |b>=c && c>=a = (a,c,b)
 |c>=a && a>=b = (b,a,c)
 |otherwise = (a,b,c)
main::IO()
main = do
 print(ordenaTupla (0,0,7))
Questão 5)
Escreva uma função anônima que recebe uma tripla formada pelo
nome, peso e altura de uma pessoa e resulta no seu índice de massa
corporal, dado pela razão entre o peso e o quadrado da altura da
pessoa.

imc ::String-> Double ->(Double -> Double)
imc p1= (\a -> (\b -> a/(b*b)))
main::IO()
main = do
 print(imc "Matheus" 62.0 1.80)
Questão 6)
Escreva uma expressão para selecionar (filtrar) os elementos
múltiplos de 3 em uma lista de números. Para auxiliar use a função
definida filter. Especifique a função que determina a propriedade a
ser satisfeita pelos elementos selecionados usando uma expressão
lambda
import Data.List
multiplosDeTres::[Int]->[Int]
multiplosDeTres = (\x -> sort (filter (rule) x))
 where rule x = mod x 3 == 0
main::IO()
main = do
 print(multiplosDeTres[1,2,3,66,33])
