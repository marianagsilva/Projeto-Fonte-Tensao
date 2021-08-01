# SSC0180 - Eletrônica para Computação // Projeto - Fonte de Tensão

## Especificações do projeto: projetar e construir uma fonte de tensão ajustável de 3V á 12V com capacidade de 100mA 

Alunos:
- Mariana de Lourdes Godoy da Silva
- Gustavo Siqueira Barbosa 
- Ana Beatriz Araujo Ferreira 

### Projeto e simulação no Falstad:

![circuit-20210801-0928](https://user-images.githubusercontent.com/32443360/127772648-b18b0ee1-d02a-4978-82b9-3e16def6467b.png)

[Link para o circuito](https://tinyurl.com/ydrcjp7r)

### Objetivo dos componentes

Os componentes do circuito são, da esquerda para a direita:
- **Fonte de corrente alternada:** simula a tensão de rede com 127V, 60Hz de frequência e 180V de tensão de pico;
- **Transformador:** responsável por reduzir a diferença de potencial elétrico (DDP) de 127V da tensão de rede, para a tensão esperada do projeto 3V á 12V;
- **Ponte Retificadora:** a ponte de diodos tem a função de abastecer o circuito de corrente contínua em ambos os ciclos da corrente alternada proveniente da tomada; 
- **Capacitor:** armazena a carga durante os ciclos da corrente alternada, liberando corrente quando a tensão interna é maior que a tensão vinda da fonte. Descarrega quando ocorre a inversão de ciclos;
- **Diodo Zener:** responsável pela regulação de tensão de ruptura do circuito, por isso só conduz corrente quando a tensão que chega á ele alcança a tensão nominal do diodo de 13V, se a tensão do circuito for menor que isso, o diodo não interfere no circuito;
- **Potenciômetro:** resistor variável que permite o controle da tensão dentro do circuito entre 3V e 12V;
- **Transistor:** um transistor tem e função de amplificar a corrente elétrica ou barrar a sua passagem. Quando na função de amplificador, os transistores são alimentados por uma baixa corrente elétrica de entrada, amplificando-a e, assim, produzindo uma corrente elétrica de saída com maior intensidade, mas também podem funcionar como interruptores, ligando ou desligando a corrente elétrica em um circuito;
- **Resistores:** complementam o circuito limitando a passagem de corrente em determinados lugares;

### Cálculo dos valores do circuito

#### Para o transformador:
  -  Considerando que a tensão máxima que entra no circuito é V x sqrt(2)
  -  Para 127v ela é cerca de 180.
  -  Como a fonte final deve ter 12v, considera-se alguns volts a mais para percas durante o circuito, fazendo com que a razão do transformador seja cerca de 0,1.
  -  Ou seja, após o transformador temos +-18v no circuito.
#### Ponte retificadora:
  -  é sempre composta por 4 diodos de silício de 0,7v cada;
  -  a corrente passa somente por 2 de cada vezes, fazendo com que após o retificador, o circuito tenha +- 16v;
#### O capacitor:
  - Foi calculado considerando um ripple de 10%, no caso, cerca de 1,656;
  - Pela fórmula C = i / f * Vr -> C = 0,12 / 120 * 1,656 -> C ~= 0,0006094
  - Arrendondando para o mais próximo valor comercial, **C = 620uF**
#### LED + resistor:
  - Foi usado um LED vermelho comum, que precisa receber 1,8v-2v;
  - Assim, o resistor necessário é R = V - Vled / i -> R = 15 - 2 / 0,013 -> **R = 1000Ohms**
 #### Para os componentes do regulador:
  - O **diodo zener** deve ser capaz de aguentar a voltagem final pedida e potência do circuito;
  - O mínimo que chega no resistor é 14,5, que deve diminuir a voltagem para +- 13v (para admitir flutuações)
  - Assim o resistor é R = V - Vdiodo / i -> R = 14,5 - 13 / 0,02 -> R = 1,5 / 0,02 -> **R = 75**
  - A potência do zener deve ser Vz × Imax -> Pot = 13 * (0,110) = 1,330 
  - Ajustando para os valores do mercado, foram usados um **resistor de 100Ohms**, e um **diodo de 13v e 5W**;
#### Para o potênciometro:
  - ?? calculo do potenciometro
  - Tem que ser 5k ohms mesmo


### Tabela de componentes e valores
|        COMPONENTE        |QTD| LINK | VALOR UNITÁRIO |
|:------------------------:|---|------|----------------|
| Transformador            | 1 |[Baú da Eletrônica](https://eletronicagpl.com.br/produto/transformador-hayama-181-18v18v-1a-bivolt/)| R$ 40,00  |
| Diodos                   | 4 |[Baú da Eletrônica](https://www.baudaeletronica.com.br/diodo-1n4004.html) | R$    |
| Capacitor 620uF          | 1 |[Mercado Livre](https://produto.mercadolivre.com.br/MLB-1777842290-capacitor-eletrolitico-7x-680uf-x-25v-3x-470uf-x-25v-105-_JM#position=6&search_layout=grid&type=item&tracking_id=4ae0b597-7503-403c-a6e1-cb694ebc05a3) | R$    |
| LED                      | 1 |[Baú da Eletrônica](https://www.baudaeletronica.com.br/resistor-1k-5-1-4w.html)|R$    |
| Resistor 1KΩ             | 1 |[Baú da Eletrônica](https://www.baudaeletronica.com.br/resistor-1k-5-1-4w.html)     | R$    |
| Resistor 100Ω            | 1 |[Baú da Eletrônica](https://www.baudaeletronica.com.br/resistor-100r-5-1-4w.html)     | R$    |
| Resistor 1.2KΩ           | 1 |[Baú da Eletrônica](https://www.baudaeletronica.com.br/resistor-100r-5-1-4w.html)     | R$    |
| Diodo Zener              | 1 |[Baú da Eletrônica](https://www.baudaeletronica.com.br/diodo-zener-1n5350b-13v-5w.html)    | R$    |
| Potenciômetro            | 1 |[Baú da Eletrônica](https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html)    | R$    |
|VALOR TOTAL               | R$ |

### Circuito esquemático e Placa de Ciruito Impresso (PCB)


![Esquemático.png](https://raw.githubusercontent.com/marianagsilva/Projeto-Fonte-Tensao/main/Esquem%C3%A1tico.png)

![Board.jpg](https://raw.githubusercontent.com/marianagsilva/Projeto-Fonte-Tensao/main/Board.jpg)





