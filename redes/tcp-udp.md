# TCP e UDP

## [02/09/2026] — Fonte: Estudo autônomo (mentoria com IA)

Na camada de Transporte vivem o TCP e o UDP.

O TCP é o protocolo que garante que os dados cheguem completos, na ordem certa, ao seu destino. Ele divide a informação a ser transmitida em vários pacotes — o número de pacotes depende do volume de dados —, porque se a rede alocasse uma linha inteira e dedicada para cada transmissão (como as linhas telefônicas antigas faziam), haveria muito congestionamento e o sistema seria inviável em larga escala. Em vez disso, os pacotes vão sendo entregues aproveitando os espaços vagos da rede, os momentos em que ninguém mais está usando aquele trecho.

Cada pacote é numerado, e à medida que chegam, são reorganizados na ordem correta para entregar o arquivo com integridade. Quando o TCP percebe que um pacote específico, de acordo com a numeração, não chegou, ele faz uma requisição diretamente à outra ponta da conversa — o dispositivo remetente original —, pedindo o reenvio apenas daquele pacote específico que faltou, sem precisar reenviar tudo de novo.

O UDP, por outro lado, prioriza a rapidez da transmissão em vez dessa garantia de entrega completa. Um exemplo de uso real onde isso compensa é numa chamada de vídeo: nesse caso, é melhor manter a fluidez e a rapidez do envio de informação — mesmo que isso signifique perder algum trecho de áudio ocasionalmente — do que garantir a entrega completa às custas de mais lentidão na transmissão.
