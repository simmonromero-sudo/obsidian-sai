
### Probabilidad conjunta

La probabilidad conjunta de los eventos A y B, denotada como $P(A\cap B)$, es la probabilidad de que ocurran **ambos** eventos A y B, de modo que llamaremos:
$$
P(A\cap B) = Probabilidades \ conjuntas
$$
### Probabilidad marginal

La probabilidad marginal de A es la suma de las probabilidades conjuntas de $A\ y \ B_j$, donde la suma se efectúa sobre todos los eventos $B_j$. O sea:

|         | $B_1$             | $B_2$             | ......... | $B_j$             | ......... | $B_n$             |          |
| ------- | ----------------- | ----------------- | --------- | ----------------- | --------- | ----------------- | -------- |
| $A_1$   | $P(A_1 \cap B_1)$ | $P(A_1 \cap B_2)$ |           | $P(A_1 \cap B_j)$ |           | $P(A_1 \cap B_n)$ | $P(A_1)$ |
| $A_2$   |                   |                   |           |                   |           |                   |          |
| ......  |                   |                   |           | $P(A_i \cap B_j)$ |           |                   |          |
| $A_i$   |                   |                   |           |                   |           |                   |          |
| ....... |                   |                   |           |                   |           |                   |          |
| $A_m$   |                   |                   |           |                   |           | $P(A_m \cap B_n)$ |          |
|         |                   |                   |           |                   |           |                   |          |
$$
P(A_1)=P(A_1 \cap B_1) + P(A_1 \cap B_2) + ....+P(A_1 \cap B_j)+....+P(A_1 \cap B_n)=p(\sum_{j=1}^{i=n}A_1 \cap B_j)
$$
### Probabilidad condicional

Sean A y B dos eventos asociados a un experimento $\epsilon$. Indicaremos como $P(A/B)$ la probabilidad condicional de A, dado que el evento B ha ocurrido
$$
P(A/B)=\frac{P(A\cap B)}{P(B)} \ \ \ \ siendo \ P(B) > 0
$$
La probabilidad condicional de A dado que el evento B ha ocurrido es el cociente de la probabilidad conjunta de A y B, con respecto a la probabilidad marginal de B; siendo $P(B)>0$

**Ejemplo:** sea $S=\{0,1,2,3,4,5,6,7,8,9\}$ y definimos dos eventos A y B como:
- $A=\{x_i/x_i\ es\ par\ \}=\{0,2,4,6,8 \}$
- $\{x_i/x_i > 5\}=\{6,7,8,9\}$
![[Pasted image 20260420155702.png]]

Observando el dibujo se puede calcular:
$$P(A)=\frac{5}{10} \quad ; \quad P(B)=\frac{4}{10} \quad ; \quad P(A \cap B)=\frac{2}{10}$$

$$P(A/B)=\frac{P(A \cap B)}{P(B)}=\frac{\frac{2}{10}}{\frac{4}{10}}=\frac{2}{4}=\frac{1}{2}=0,5$$

$$P(B/A)=\frac{P(A \cap B)}{P(A)}=\frac{\frac{2}{10}}{\frac{5}{10}}=\frac{2}{5}=0,4$$
**Esta expresión cumple:**
1. $0\le P(A/B)\le 1$
2. $P(S/A)=\frac{P(S\cap A)}{P(A)}=\frac{P(A)}{P(A)}=1$
3. Si $A_1$ y $A_2$ son mutuamente excluyentes, entonces:	$$
	P(A_1 \cup A_2 /B)=P(A_1/B)+P(A_2/B)
	$$
**Regale de la multiplicación**
$$
P(A\cap B)=P(A)\cdot P(B/A)=P(B)\cdot P(A/B)
$$
### Eventos estadísticamente independientes

Sean A y B dos eventos cualesquiera en el espacio de muestra S. Se dice que el evento A es **estadísticamente independiente** del evento B si se cumple:
$$
P(A/B)=P(A)
$$
Por lo tanto se verifica que:

1. $P(A/B)=P(A)$
2. $P(B/A)=P(B)$
3. $P(A\cap B)=P(A)\cdot P(B)$

### Partición

Decimos que $B_1,B_2,....,B_k$ representa una partición del espacio muestral **S** si:

1. Se verifica que $B_i \cap B_j=\Phi$  Para todo $i\neq j$  
2. Se verifica que $B_1 \cup B_2 \cup .... \cup B_k = S$ 
3. Se verifica que $P(B_i)\ge 0$  

Es decir que al efectuar el experimento $\epsilon$, ocurre uno solo de los eventos B. También puede decirse que los eventos agotan (o cubren) el espacio muestral.

### Teorema de probabilidad total
Sea A algún evento respecto de S y sea $B_1, B_2, ..., B_k$ una partición de S
![[Pasted image 20260420161708.png]]

Podemos escribir:
$$
A=(A\cap B_1) \cup (A \cap B_2)\ \cup ... \cup\ (A\cap B_k)
$$
Algún $A \cap B_j$ son **mutuamente excluyentes.** Por lo tanto, aplicando probabilidades, se tiene:
$$
P(A)=P(A\cap B_1)+P(A\cap B_2) + ...+P(A\cap B_k)
$$
Luego, aplicando la regla de la multiplicación se obtiene la fórmula de la **Probabilidad Total:**
$$
P(A) = P(A/B_1)\cdot P(B_1)+P(A/B_2)\cdot P(B_2) + ... + P(A/B_k)\cdot P(B_k)
$$

### Teorema de Bayes

Sean $B_1, B_2, ..., B_k$ una partición del espacio muestral S y sea A un evento asociado con S. 
Aplicando la definición de probabilidad condicional podemos escribir:

$$P(B_i/A) = \frac{P(B_i \cap A)}{P(A)} = \frac{P(A/B_i) \cdot P(B_i)}{P(A/B_1) \cdot P(B_1) + P(A/B_2) \cdot P(B_2) + \dots + P(A/B_j) \cdot P(B_j)}$$

o más sintéticamente:

$$P(B_i/A) = \frac{P(A/B_i) \cdot P(B_i)}{\sum_{j=1}^{j=k} P(A/B_j) \cdot P(B_j)}$$

Este resultado se conoce como **Teorema de Bayes**; también se llama fórmula para la probabilidad de las casas.
