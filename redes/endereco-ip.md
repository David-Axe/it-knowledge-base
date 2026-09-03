# Endereço IP

## [02/09/2026] — Fonte: Estudo autônomo (mentoria com IA)

Na camada de Internet vive o endereçamento entre redes diferentes: o IP. Uma máquina identifica para qual outra máquina específica enviar dados através do endereço IP — de forma parecida com um endereço residencial: para mandar uma carta a alguém, uso o endereço atual daquela pessoa. Uso a palavra "atual" de propósito, porque assim como uma pessoa pode morar num endereço hoje e mudar para outro depois — sem deixar de ser a mesma pessoa — um computador também tem um endereço atual (o IP), que pode mudar quando ele muda de rede, mesmo mantendo sua identidade fixa (o MAC).

O responsável por atribuir automaticamente o endereço IP a cada dispositivo que entra na rede é o DHCP (Dynamic Host Configuration Protocol — Protocolo de Configuração Dinâmica de Hospedeiro). O DHCP não é um objeto físico nem um dispositivo — é um protocolo, ou seja, um conjunto de regras, como as regras de etiqueta de um jantar formal. Para essas regras serem de fato aplicadas, existe um software (o servidor DHCP) rodando geralmente no roteador, que efetivamente distribui os IPs seguindo essas regras.

Na mesma rede, uma máquina pode mudar de endereço IP por diversos motivos, a não ser que um técnico configure para que aquela máquina sempre use o mesmo endereço IP ao se conectar — algo comum, por exemplo, quando um analista de segurança programa os equipamentos de uma empresa para facilitar o monitoramento.
