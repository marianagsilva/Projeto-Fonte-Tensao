## Projeto - Fonte de Tensão Ajustável


*Repositório criado para a disciplina de SSC0180 - Eletrônica para Computação, no qual consiste uma fonte de tensão ajustável de 3V á 12V para 100mA.* 


Alunos:
- Mariana de Lourdes Godoy da Silva
- Gustavo Siqueira Barbosa 
- Ana Beatriz Araujo Ferreira 

### Projeto do circuito Falstad:

![circuit-20210801-0928](https://user-images.githubusercontent.com/32443360/127772648-b18b0ee1-d02a-4978-82b9-3e16def6467b.png)

Os componentes do circuito são, da esquerda para a direita:
- fonte de corrente alternada de 127v e 60Hz;
- transformador;
- ponte retificadora de onda completa (com 4 diodos retificadores);
- capacitor;
- amperímetro e voltímetro (para a checagem dos valores);
- LED e resistor;
- regulador, que consiste em um resistor ligado ao diodo zener;
- um potenciômetro para a regulagem da voltagem final desejada;
- resistor ligado junto ao potenciômetro (função?);
- e um resistor final que representa a carga a ser conectada na fonte.

### Cálculo dos valores

- para o transformador:
  -  considerando que a Voltagem máxima que entra no circuito é V x sqrt(2)
  -  Para 127v ela é cerca de 180.
  -  como a fonte final deve ter 12v, considera-se alguns volts a mais para percas durante o circuito, fazendo com que a razão do transformador seja cerca de 0,1.
  -  ou seja, após o transformador temos +-18v no circuito.
- a ponte retificadora:
  -  é sempre composta por 4 diodos de silício de 0,7v cada;
  -  a corrente passa somente por 2 de cada vezes, fazendo com que após o retificador, o circuito tenha +- 16v;
- o capacitor:
  - foi calculado considerando um ripple de 10%, no caso, cerca de 1,656;
  - pela fórmula C = i / f * Vr -> C = 0,12 / 120 * 1,656 -> C ~= 0,0006094
  - arrendondando para o mais próximo valor comercial, **C = 620uF**
- LED + resistor:
  - foi usado um LED vermelho comum, que precisa receber 1,8v-2v;
  - assim, o resistor necessário é R = V - Vled / i -> R = 15 - 2 / 0,013 -> **R = 1000Ohms**
- para os componentes do regulador:
  - o **diodo zener** deve ser capaz de aguentar a voltagem final pedida e potência do circuito;
  - o mínimo que chega no resistor é 14,5, que deve diminuir a voltagem para +- 13v (para admitir flutuações)
  - assim o resistor é R = V - Vdiodo / i -> R = 14,5 - 13 / 0,02 -> R = 1,5 / 0,02 -> **R = 75**
  - a potência do zener deve ser Vz × Imax -> Pot = 13 * (0,110) = 1,330 
  - ajustando para os valores do mercado, foram usados um **resistor de 100Ohms**, e um **diodo de 13v e 5W**;
- para o potênciometro:
  - ?? calculo do potenciometro
  - tem que ser 5k ohms mesmo


### Tabela de componentes e valores
|        COMPONENTE        | LINK | VALOR |
|:------------------------:|------|-------|
| Transformador            | https://eletronicagpl.com.br/produto/transformador-hayama-181-18v18v-1a-bivolt/| R$ 40,00  |
| 4 x diodos retificadores |  https://www.baudaeletronica.com.br/diodo-1n4004.html | R$    |
| capacitor 680uF          | https://produto.mercadolivre.com.br/MLB-1777842290-capacitor-eletrolitico-7x-680uf-x-25v-3x-470uf-x-25v-105-_JM#position=6&search_layout=grid&type=item&tracking_id=4ae0b597-7503-403c-a6e1-cb694ebc05a3 | R$    |
| LED                      |      | R$    |
| resistor 1kOhms          | https://www.baudaeletronica.com.br/resistor-1k-5-1-4w.html     | R$    |
| resistor 100Ohms         | https://www.baudaeletronica.com.br/resistor-100r-5-1-4w.html     | R$    |
| diodo zener              |  https://www.baudaeletronica.com.br/diodo-zener-1n5350b-13v-5w.html    | R$    |
| potenciômetro            |  https://www.baudaeletronica.com.br/potenciometro-linear-de-5k-5000.html    | R$    |
