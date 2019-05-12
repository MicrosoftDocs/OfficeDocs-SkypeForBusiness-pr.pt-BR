---
title: Implementar Qualidade de Serviço no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Prepare a rede da sua organização para a Qualidade de Serviço (QoS) no Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.qos
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 261d581582208a1bff94e16b35d06ab8e564a08b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885079"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar a qualidade do serviço (QoS) em equipes da Microsoft

Este artigo ajudará você a preparar a rede da sua organização Quality of a Service (QoS) no Microsoft Teams. Se você oferece suporte a um grupo grande de usuários e eles estiver encontrando algum dos problemas mencionados a seguir, você provavelmente precisará implementar QoS. Uma pequena empresa com alguns usuários talvez não seja necessário QoS, mas ainda há deve ser úteis.

QoS é uma maneira para permitir o tráfego de rede em tempo real (como fluxos de voz ou vídeo) sensível a atrasos de rede "cortar na linha" na frente de tráfego menos confidencial (como fazer o download de um novo aplicativo, onde um segundo extra para baixar não é importante). QoS identifica e marca todos os pacotes de fluxos em tempo real (usando objetos de diretiva de grupo do Windows e um recurso de roteamento chamado porta-based Access Control Lists, mais sobre aqueles está abaixo) que ajuda a sua rede para dar a voz, vídeo e fluxos de compartilhamento de tela um parte dedicada da largura de banda de rede.

Sem algum tipo de QoS, talvez você veja os seguintes problemas de qualidade de voz e vídeo:

- Tremulação – pacotes de mídia que chegam ao diferentes taxas, que podem resultar em ausentes palavras ou sílabas em chamadas.
- Perda de pacote – pacotes descartados, que também pode resultar em menor qualidade de voz e grave entender fala.
- Adiar o tempo de ida e volta (RTT) – os pacotes de mídia demorando muito para alcançar seus destinos, o que resulta em atrasos perceptíveis entre duas partes em uma conversa, fazendo com que as pessoas falar sobre umas às outras.

A maneira menos complexa para solucionar esses problemas é para aumentar o tamanho das conexões de dados, tanto internamente e out à internet. Desde que geralmente é caro, QoS fornece uma maneira de gerenciar com mais eficiência os recursos que você tem em vez de adicionar os novos recursos. Para resolver problemas de qualidade totalmente use QoS através da implementação e adicionar conectividade somente onde absolutamente necessário.

Para QoS para serem eficientes, você terá que aplicar as configurações de QoS consistentes ponta a ponta em sua organização (Isso inclui todos os usuário PCs, comutadores de rede e roteadores para a internet), porque qualquer parte do caminho que está falhando para dar suporte a suas prioridades de QoS pode prejudicar o qualidade das chamadas, vídeo e compartilhamento de tela.

_Figura 1. A relação entre redes de uma organização e serviços do Office 365_

![A relação entre redes de uma organização e serviços do Office 365: conectam a rede e os dispositivos com uma rede de interconexão, que por sua vez, se conecta com os serviços do Office 365 nuvem voz e conferência de áudio no local.](media/Qos-in-Teams-Image1.png)

Na maioria dos casos, a rede de sua empresa conectar-se para a nuvem será uma rede não gerenciada onde você não conseguirá confiável definir opções de QoS. Uma opção disponível para QoS de ponta a ponta de endereços é [ExpressRoute do Azure](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), mas ainda recomendamos que você implemente o QoS em sua rede local. Isso irá aumentar a qualidade das cargas de trabalho de comunicação em tempo real em toda sua implantação e atenuar os pontos de estrangulamento.

## <a name="verify-your-network-is-ready"></a>Verifique se a que sua rede está pronta

Se você estiver considerando uma implementação de QoS, você já deve ter determinado seus requisitos de largura de banda e outros [requisitos de rede](prepare-network.md). Cálculos de largura de banda for Microsoft Teams são complexos e para ajudar com isso, uma calculadora foi criada. Para acessar a Calculadora, vá para [Planejador de rede](https://aka.ms/bwcalc/) em MyAdvisor.
  
  Congestionamento de tráfego em uma rede muito afetará a qualidade da mídia. Falta de largura de banda leva a degradação do desempenho e uma experiência de usuário ruim. À medida que cresce de uso e a adoção de equipes, use a emissão de relatórios, [análise de chamada e o painel de controle de qualidade de chamada](difference-between-call-analytics-and-call-quality-dashboard.md) para identificar problemas e faça ajustes usando QoS e adições seletiva de largura de banda.

### <a name="vpn-considerations"></a>Considerações de VPN

QoS só funciona conforme o esperado quando implementada em todos os links entre os chamadores. Se você usar o QoS em uma rede interna e um usuário entrar em um local remoto, você pode priorizar somente dentro de sua rede interna, gerenciada. Embora os locais remotos podem receber uma conexão gerenciada por meio da implementação de uma rede virtual privada (VPN), uma VPN naturalmente adiciona sobrecarga de pacotes e cria atrasos no tráfego em tempo real. Recomendamos que você evite executando o tráfego de comunicação em tempo real através de uma VPN.

> [!NOTE]
> Usuários remotos conectados VPN devem implementar túnel em divisão para maximizar a qualidade da experiência do usuário. O documento [Túnel de divisão de orientação-Deploy-VPN](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_9 ) está disponível em MyAdvisor e possui mais informações.

Em uma organização global com links gerenciadas que abrangem continentes, é altamente recomendável QoS porque a largura de banda para esses links é limitada em comparação com o da LAN.

## <a name="introduction-to-qos-queues"></a>Introdução às filas de QoS

Para fornecer a QoS, os dispositivos de rede devem ter uma maneira de classificação de tráfego e devem ser capazes de distinguir voz ou vídeo de outros tráfego de rede.

Quando o tráfego de rede entra em um roteador, o tráfego é colocado em uma fila. Se uma política de QoS não estiver configurada, há apenas uma fila e todos os dados são tratados como first-in, First com a mesma prioridade. Isso significa que o tráfego de voz (que é muito sensível a atrasos) pode cair por trás de tráfego onde um atraso de alguns milissegundos extras não seria um problema.

Quando você implementa a QoS, você define várias filas usando um dos vários recursos de gerenciamento de congestionamento (por exemplo, da Cisco enfileiramento prioritário e baseada em classe ponderado justo Queueing [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) e recursos de prevenção de congestionamento (como ponderada aleatório no início detecção [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).

_Figura 2. Exemplos de filas de QoS_

![Largura de banda total disponível é dividida entre várias filas — áudio, vídeo e outros tráfegos — que tiverem sido atribuídas prioridades diferentes.] (media/Qos-in-Teams-Image2.png "Largura de banda total disponível é dividida entre várias filas — áudio, vídeo e outros tráfegos — que tiverem sido atribuídas prioridades diferentes.")

Uma simples analogia é que a QoS cria virtual "pistas expressa, mas" em seus dados para alguns tipos de dados nunca ou raramente encontrarem um atraso de rede. Depois de criar essas pistas, você pode ajustar seu tamanho relativo e muito mais efetivamente gerenciar a largura de banda de conexão que você tiver, enquanto continua a fornecer experiências de nível de negócios para os usuários da sua organização.

## <a name="select-a-qos-implementation-method"></a>Selecione um método de implementação de QoS

Você poderia implementar QoS via baseados na porta marcação, usando listas de controle de acesso (ACLs) nos roteadores da sua rede. A marcação baseados na porta é o método mais confiável porque ele funciona em ambientes mistos Windows e Mac e é mais fácil implementar. Clientes móveis não fornecem um mecanismo para marcar o tráfego usando valores DSCP, portanto, eles precisarão esse método.  

Usar esse método, roteador da sua rede examina um pacote de entrada, e se o pacote chegou usando uma porta ou intervalo de portas, identifica-lo como um determinado tipo de mídia e o coloca na fila para aquele tipo, adicionando uma marca de [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada ao IP Cabeçalho de pacote para que outros dispositivos que possam reconhecer seu tipo de tráfego e dê a ela prioridade em sua fila de espera.

Embora isso funcione em todas as plataformas, ele marca somente o tráfego da borda WAN (não totalmente para a máquina cliente) e cria sobrecarga de gerenciamento. Você deve consultar a documentação fornecida pelo fabricante do roteador para obter instruções sobre como implementar esse método.

* * *

Você também pode implementar QoS implementado por meio de um objeto de diretiva de grupo (GPO) para direcionar os dispositivos cliente para inserir um marcador de DSCP em cabeçalhos de pacotes IP identificá-lo como um tipo específico de tráfego (por exemplo, voz). Roteadores e outros dispositivos de rede podem ser configurados para reconhecer isso e colocar o tráfego em uma fila de prioridade mais alta, separada.

Embora esta situação é totalmente válida, ele só funcionará para clientes associados a um domínio do Windows. Qualquer dispositivo que não é um cliente do domínio do Windows não será ativado para DSCP marcação. Clientes como o Mac OS tem codificadas marcas e serão sempre marcar o tráfego.

No sinal de mais lado, controlando a via GPO de marcação de DSCP garante que todos os computadores associados a um domínio recebem as mesmas configurações e somente um administrador pode gerenciá-los. Clientes que podem usar o GPO serão marcados no dispositivo de origem e, em seguida, os dispositivos de rede configurados podem reconhecer o fluxo em tempo real pelo código DSCP e dê a ela uma prioridade adequado.

* * *

Recomendamos uma combinação de marcações de DSCP no ponto de extremidade e baseados na porta ACLs em roteadores, se possível. Usando um objeto de diretiva de grupo para acompanhar a maioria dos clientes e também usando marcação de DSCP baseados na porta garantirá que mobile, Mac e outros clientes ainda obterão tratamento de QoS (pelo menos parcialmente).

Marcações DSCP podem ser comparadas a carimbos de postagem que indicam a trabalhadores postais como urgentes é a entrega e a melhor maneira classificá-las para entrega veloz. Depois que você configurou a sua rede para priorizam fluxos de mídia em tempo real, pacotes perdidos e tardia deve diminuir drasticamente.

Depois que todos os dispositivos na rede estiver usando o mesmo classificações, as marcas e prioridades, é possível reduzir ou eliminar atrasos, pacotes descartados e tremulação, alterando o tamanho dos intervalos de porta atribuído às filas usadas para cada tipo de tráfego. Sob a perspectiva de equipes, a etapa de configuração mais importante é a classificação e a marcação dos pacotes, mas para QoS de ponta a ponta obter êxito, você também precisará Alinhe cuidadosamente a configuração do aplicativo com a configuração de rede subjacente. Depois de QoS totalmente é implementado, o gerenciamento contínuo é uma pergunta de ajustar os intervalos de porta atribuídos a cada tipo de tráfego com base nas necessidades da sua organização e o uso real.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Escolha os intervalos de porta inicial para cada tipo de mídia

O valor DSCP informa uma rede correspondentemente configurada qual a prioridade para conceder a um pacote ou fluxo, se a marca de DSCP é atribuída por clientes ou na rede em si, com base nas configurações de ACL. Cada carga de trabalho de mídia obtém seu próprio valor DSCP exclusivo (outros serviços podem permitir que as cargas de trabalho compartilhar uma marcação de DSCP, equipes não) e um intervalo de porta definido e separado usados para cada tipo de mídia. Outros ambientes podem ter uma estratégia de QoS existente no lugar, que ajudará você a determinar a prioridade das cargas de trabalho de rede.

O tamanho relativo dos intervalos de porta para diferentes cargas de trabalho streaming em tempo real define a proporção de largura de banda disponível total dedicado para essa carga de trabalho. Para retornar à nossa analogia postal anteriormente: uma letra com um carimbo de "Air Mail" poderia obter executada dentro de uma hora para o mais próximo aeroporto, enquanto um pequeno pacote marcado "Email em massa" mark pode esperar que um dia antes da viagem sobre land em uma série de caminhões.

A tabela a seguir mostra as marcações de DSCP necessárias para equipes com ExpressRoute e as portas associadas para filas de carga de trabalho. Esses intervalos podem servir como um bom ponto de partida para os clientes que não tem certeza sobre o que usar em seus próprios ambientes. Para saber mais, consulte [Requisitos de QoS para o ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Recomendado de intervalos de porta inicial_

|Tipo de tráfego de mídia| Intervalo de porta de origem do cliente |Protocolo|Valor de DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000 – 50,019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50,020 – 50,039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela do aplicativo| 50,040 – 50,059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Esteja ciente dos seguintes quando você usa estas configurações:

- Se você pretende implementar ExpressRoute no futuro e ainda não foi implementado QoS, recomendamos que você siga as orientações para que os valores DSCP são os mesmos do remetente para o receptor.
- Todos os clientes, incluindo clientes móveis e dispositivos de equipes, usarão esses intervalos de porta e serão afetados pela implementar qualquer política DSCP que usa esses intervalos de porta de origem. Os únicos clientes que continuarão a usar portas dinâmicas são os clientes baseados em navegador (ou seja, os clientes que permitem que os participantes participar de reuniões usando seus navegadores).
- Embora o cliente do Mac usa os mesmos intervalos de porta, ele também usa valores codificados para (EF) de áudio e vídeo (AF41). Esses valores não são configuráveis.
- Se posteriormente você precisa ajustar os intervalos de porta para melhorar a experiência do usuário, os intervalos de porta não podem sobrepor-se e devem ser adjacentes entre si.

## <a name="migrate-qos-to-teams"></a>Migrar de QoS para equipes

Se você tiver implantado anteriormente Skype para negócios Online, incluindo a marcação de QoS e intervalos de porta e está agora implantando equipes, equipes respeitam a configuração existente e usarão os mesmos intervalos de porta e marcação como o Skype para o cliente de negócios. Na maioria dos casos, nenhuma configuração adicional será necessária.

> [!NOTE]
> Se você estiver usando a QoS de nome de aplicativo marcação via diretiva de grupo, você deve adicionar Teams.exe como o nome do aplicativo.

## <a name="qos-implementation-steps"></a>Etapas de implementação de QoS

Em um nível muito alto, a implementação da QoS exige estas etapas:

1. [Verifique se a que sua rede está pronta](#verify-your-network-is-ready)
2. [Selecione um método de implementação de QoS](#select-a-qos-implementation-method)
3. [Escolha os intervalos de porta inicial para cada tipo de mídia](#choose-initial-port-ranges-for-each-media-type)
4. Implemente as configurações de QoS:
   1. Nos clientes que usam um GPO para [definir intervalos de porta do dispositivo cliente e marcações](QoS-in-Teams-clients.md)
   2. Em roteadores (consulte a documentação do fabricante) ou outros dispositivos de rede. Isso pode incluir ACLs baseados na porta ou simplesmente definindo as filas de QoS e marcações DSCP ou todos eles.

      > [!IMPORTANT]
      > É recomendável implementando essas políticas de QoS usando as portas de origem do cliente e um endereço IP de origem e destino de "Nenhum". Isso irá capturar ambas tráfego de mídia de entrada e saída na rede interna.  

   3. No [Centro de administração de equipes](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)
5. [Validar a implementação de QoS](#validate-the-qos-implementation) ao analisar o tráfego de equipes na rede.

Como se preparar para implementar o QoS, lembre-se as seguintes diretrizes:

- O caminho mais curto para o Office 365 é melhor.
- Fechando portas apenas levará a degradação da qualidade.
- Qualquer obstáculos intermediária, como proxies, não são recomendados.
- Limite o número de saltos de:
  - Cliente para a borda da rede – saltos de 3 a 5.
  - ISP para a borda da rede Microsoft – 3 saltos
  - Borda da rede Microsoft ao destino final – irrelevante

Para obter informações sobre como configurar portas de firewall, vá para o [Office 365 URLs e intervalos IP](office-365-urls-ip-address-ranges.md).

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gerenciando as portas de origem no Centro de administração de equipes

Nas equipes, as portas de origem de QoS usadas por diferentes cargas de trabalho devem ficar ativamente gerenciadas e ajustado conforme necessário. Referindo-se à tabela em [Escolher intervalos de porta inicial para cada tipo de mídia](#choose-initial-port-ranges-for-each-media-type), os intervalos de porta são ajustáveis, mas as marcas de DSCP não são configuráveis. Depois que você implementou essas configurações, você pode achar que mais ou menos portas são necessárias para um determinado tipo de mídia. [Análise de chamada e o painel de controle de qualidade de chamada](difference-between-call-analytics-and-call-quality-dashboard.md) deve ser usado na tomada de decisão para ajustar os intervalos de portas depois que tiver sido implementado equipes e periodicamente conforme as necessidades de alteração.

> [!NOTE]
> Se você já tiver configurado a QoS com base em intervalos de porta de origem e marcações de DSCP para Skype para Business Online, a mesma configuração se aplicará a equipes e nenhuma outra cliente ou alterações na rede para o mapeamento será necessárias, embora talvez você tenha a [definido os intervalos usado no Centro de administração de equipes](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) para coincidir com o que foi configurado para Skype para negócios Online.

Se você tiver implantado anteriormente Skype para Business Server local, você pode precisar reexaminar suas políticas de QoS e os ajuste conforme necessário para corresponder às configurações de intervalo de porta que forem verificadas fornecer uma experiência de usuário de qualidade para equipes.

## <a name="validate-the-qos-implementation"></a>Validar a implementação de QoS

Para QoS para serem eficientes, o DSCP valor definido pelo objeto de diretiva de grupo deve estar presente em ambas as extremidades de uma chamada. Analisando o tráfego gerado pelo cliente equipes, verifique se o valor DSCP não será alterado ou retirado quando o tráfego de carga de trabalho de equipes percorre movimentações através da rede.

De preferência, você capturar o tráfego no ponto de saída de rede. Você pode usar o espelhamento de porta em um comutador ou roteador para ajudá-lo com isso.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Use o Monitor de rede para verificar os valores DSCP

Monitor de rede é uma ferramenta que você pode [fazer o download da Microsoft](https://www.microsoft.com/download/4865) para analisar o tráfego de rede.

1. No PC executando o Monitor de rede, conecte-se à porta que foi configurada para o espelhamento de porta e iniciar a captura de pacotes.

2. Fazer uma chamada usando o cliente de equipes. Certifique-se de mídia foi estabelecida antes de desligar a chamada.

3. Pare a captura.

4. No campo de **Filtro de exibição** , use o endereço IP de origem do PC que fez a chamada e refinar o filtro definindo o valor DSCP 46 (hex 0xb8) como critérios de pesquisa, conforme mostrado no exemplo a seguir:

    Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0xb8

    ![Captura de tela da caixa de diálogo de filtro de exibição no Monitor de rede, mostrando os filtros a serem aplicados.] (media/Qos-in-Teams-Image4.png "Captura de tela da caixa de diálogo de filtro de exibição no Monitor de rede, mostrando os filtros a serem aplicados.")

5. Selecione **Aplicar** para ativar o filtro.

6. Na janela de **Quadro de resumo** , selecione o primeiro pacote UDP.

7. Na janela **Detalhes do quadro** , expanda o item de lista de IPv4 e observe o valor no final da linha que começa com **DSCP**.

    ![Captura de tela da caixa de diálogo Detalhes do quadro no Monitor de rede, as configurações de DSCP de realce.] (media/Qos-in-Teams-Image5.png "Captura de tela da caixa de diálogo Detalhes do quadro no Monitor de rede, as configurações de DSCP de realce.")

Neste exemplo, o valor DSCP é definido como 46. Isso está correto, porque a porta de origem usada é 50019, que indica que isso é uma carga de trabalho de voz.

Repita a verificação para cada carga de trabalho que foi marcada pelo GPO.

## <a name="more-information"></a>Mais informações

[Vídeo: Planejamento de rede](https://aka.ms/teams-networking)

[Preparar a rede da organização para o Microsoft Teams](prepare-network.md)

[Requisitos de ExpressRoute QoS](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
