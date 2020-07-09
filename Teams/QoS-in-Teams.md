---
title: Implementar Qualidade de Serviço no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Saiba como preparar a rede da sua organização para a qualidade do serviço (QoS) no Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ef2fca810a7125c4150ff4de2c3eea8fd7970d2e
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085277"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementar a QoS (qualidade de serviço) no Microsoft Teams

A QoS (qualidade de serviço) no Microsoft Teams é uma maneira de permitir o tráfego de rede em tempo real que é sensível a atrasos na rede (por exemplo, fluxos de voz ou vídeo) para "recortar na linha" na frente do tráfego que é menos confidencial (como baixar um novo aplicativo, onde um segundo adicional para baixar não é um negócio importante). A QoS identifica e marca todos os pacotes em fluxos em tempo real (usando objetos de política de grupo do Windows e um recurso de roteamento chamado de listas de controle de acesso baseado em portas, mais sobre os que estão abaixo) que, em seguida, ajudam sua rede a fornecer voz, vídeo e compartilhamento de tela transmite fluxos de largura de banda de rede.

Se você estiver oferecendo suporte a um grande grupo de usuários e ele estiver enfrentando algum dos problemas descritos abaixo, é provável que você precise implementar QoS. Uma pequena empresa com poucos usuários pode não precisar de QoS, mas até lá deve ser útil.

Sem alguma forma de QoS, você pode ver os seguintes problemas de qualidade em voz e vídeo:

- Tremulação – pacotes de mídia chegando a tarifas diferentes, o que pode resultar em palavras ausentes ou sílabas nas chamadas
- Perda de pacotes – pacotes descartados, que também podem resultar em baixa qualidade de voz e dificuldade para entender a fala
- Tempo de resposta (RTT) atrasado – pacotes de mídia demorando muito tempo para alcançar seus destinos, o que resulta em atrasos perceptíveis entre duas partes em uma conversa, fazendo com que as pessoas conversem umas sobre as outras

A maneira menos complexa de solucionar esses problemas é aumentar o tamanho das conexões de dados, interna e externamente à Internet. Como isso é sempre caro, a QoS oferece uma maneira de gerenciar com mais eficiência os recursos que você tem em vez de adicionar largura de banda. Para solucionar problemas de qualidade, recomendamos que você use a QoS pela primeira vez e, em seguida, adicione largura de banda somente quando necessário.

Para que a QoS seja eficiente, você aplicará as configurações de QoS consistentes em toda a sua organização, porque qualquer parte do caminho que não dê suporte a suas prioridades de QoS poderá diminuir a qualidade das chamadas, vídeo e compartilhamento de tela. Isso inclui a aplicação de configurações a todos os computadores ou dispositivos de usuário, switches de rede, roteadores para a Internet e o serviço Teams.

_Figura 1. A relação entre as redes da organização e os serviços do Microsoft 365 ou do Office 365_

![Ilustração da relação entre redes e serviços](media/Qos-in-Teams-Image1.png "A relação entre as redes da organização e os serviços do Microsoft 365 ou do Office 365: rede local e dispositivos se conectam a uma rede Interconnect, que, por sua vez, se conecta com o Microsoft 365 ou o Office 365 Cloud Voice and audio Conferencing Services.")

## <a name="qos-implementation-checklist"></a>Lista de verificação de implementação de QoS

Em um nível alto, faça o seguinte para implementar QoS:

1. [Verifique se a sua rede está pronta](#make-sure-your-network-is-ready)

1. [Selecionar um método de implementação de QoS](#select-a-qos-implementation-method)

1. [Escolher intervalos de porta iniciais para cada tipo de mídia](#choose-initial-port-ranges-for-each-media-type)

1. Implementar as configurações de QoS:
   1. Em clientes que usam um GPO para [definir intervalos e marcas de porta do dispositivo cliente](QoS-in-Teams-clients.md)
   2. Em roteadores (consulte a documentação do fabricante) ou outros dispositivos de rede. Isso pode incluir ACLs baseadas em porta ou simplesmente definir as filas de QoS e as marcações de DSCP, ou todas elas.

      > [!IMPORTANT]
      > Recomendamos implementar essas políticas de QoS usando as portas de origem do cliente e um endereço IP de origem e de destino de "any". Isso irá capturar o tráfego de mídia de entrada e saída na rede interna.  

   3. [Defina como você deseja manipular o tráfego de mídia para reuniões de equipes](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Valide a implementação de QoS](#validate-your-qos-implementation) analisando o tráfego da equipe na rede.

Ao se preparar para implementar a QoS, tenha em mente as seguintes diretrizes:

- O caminho mais curto para o Microsoft 365 é melhor
- As portas de fechamento só levarão à degradação de qualidade
- Qualquer obstáculos entre, como proxies, não é recomendado
- Limite o número de saltos:
  - Borda de cliente para rede – 3 a 5 saltos
  - ISP para borda de rede da Microsoft – 3 saltos
  - Borda de rede da Microsoft para destino final – irrelevante

Para obter informações sobre como configurar portas de firewall, vá para [URLs e intervalos de IP do Office 365](office-365-urls-ip-address-ranges.md).


## <a name="make-sure-your-network-is-ready"></a>Verifique se a sua rede está pronta

Se estiver considerando uma implementação de QoS, você já deve ter determinado seus requisitos de largura de banda e outros [requisitos de rede](prepare-network.md). 
  
O congestionamento do tráfego em uma rede afetará significativamente a qualidade da mídia. A falta de largura de banda leva à degradação do desempenho e a uma experiência de usuário ruim. À medida que a adoção e o uso das equipes se expandem, use o relatório, a [análise de chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md)e o [painel de qualidade de chamada (CQD)](turning-on-and-using-call-quality-dashboard.md) para identificar problemas e fazer ajustes usando QoS e adições seletivas de largura de banda.

### <a name="vpn-considerations"></a>Considerações de VPN

A QoS funciona apenas como esperado quando implementada em todos os links entre chamadores. Se você usar o QoS em uma rede interna e um usuário entrar em um local remoto, você só poderá priorizar dentro da rede gerenciada interna. Apesar de locais remotos receberem uma conexão gerenciada implementando uma rede virtual privada (VPN), a VPN adiciona inerentemente a sobrecarga de pacotes e cria atrasos no tráfego em tempo real. Recomendamos que você evite a execução de tráfego de comunicação em tempo real em uma VPN.

Em uma organização global com links gerenciados que incluem continentes, é altamente recomendável QoS, pois a largura de banda dos links é limitada em comparação com a LAN.

## <a name="introduction-to-qos-queues"></a>Introdução às filas de QoS

Para fornecer QoS, os dispositivos de rede devem ter uma maneira de classificar o tráfego e devem ser capazes de distinguir voz ou vídeo de outro tráfego de rede.

Quando o tráfego de rede entra em um roteador, o tráfego é colocado em uma fila. Se uma política de QoS não está configurada, há apenas uma fila, e todos os dados são tratados como first-in, First-out com a mesma prioridade. Isso significa que o tráfego de voz (que é muito sensível a atrasos) pode ficar preso atrás do tráfego em que um atraso de alguns milésimos de segundo extras não seria um problema.

Ao implementar o QoS, você define várias filas usando um dos vários recursos de gerenciamento de congestionamento (como a enfileiramento de prioridade da Cisco, o recurso de enfileiramento [justo baseado em classe (CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641))) e os recursos de impedimento de congestionamento (como [WRED (detecção antecipada aleatória ponderada)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).

_Figura 2. Exemplos de filas de QoS_

![Ilustração de filas de QoS e divisão de largura de banda](media/Qos-in-Teams-Image2.png "A largura de banda total disponível é dividida entre várias filas, áudio, vídeo e outros tipos de tráfego, que receberam prioridades diferentes.")

Uma simples analogia é que a QoS cria "pistas carona" virtuais na sua rede de dados, assim alguns tipos de dados nunca ou raramente encontram um atraso. Depois de criar essas pistas, você pode ajustar o tamanho relativo e gerenciar com muito mais eficiência a largura de banda da conexão que tem e ainda fornecer experiências de nível empresarial para os usuários da sua organização.

## <a name="select-a-qos-implementation-method"></a>Selecionar um método de implementação de QoS

Você pode implementar o QoS via marcação baseada em portas, usando as listas de controle de acesso (ACLs) nos roteadores da sua rede. A marcação baseada em porta é o método mais confiável porque funciona em ambientes mistos Windows, Mac e Linux e é o mais fácil de implementar. Os clientes móveis não fornecem um mecanismo para marcar o tráfego usando valores DSCP, portanto, eles precisarão desse método.  

Usando marcação baseada em porta, o roteador da sua rede examina um pacote de entrada e, se o pacote chegou usando uma determinada porta ou intervalo de portas, ele a identifica como um determinado tipo de mídia e coloca-o na fila desse tipo, adicionando uma marca [DSCP](https://tools.ietf.org/html/rfc2474) predeterminada ao cabeçalho do pacote IP para que outros dispositivos possam reconhecer seu tipo de tráfego e dar prioridade à sua fila.

Embora isso funcione entre plataformas, ele só marca o tráfego na borda da rede de longa distância (não toda a maneira da máquina cliente) e cria uma sobrecarga de gerenciamento. Você deve consultar a documentação fornecida pelo fabricante do roteador para obter instruções sobre a implementação desse método.

### <a name="insert-dscp-markers"></a>Inserir marcadores DSCP

Você também pode implementar o QoS usando um GPO (objeto de política de grupo) para direcionar dispositivos cliente para inserir um marcador DSCP em cabeçalhos de pacote IP identificando-o como um determinado tipo de tráfego (por exemplo, voz). Roteadores e outros dispositivos de rede podem ser configurados para reconhecer isso e colocar o tráfego em uma fila separada de prioridade mais alta.

Embora esse cenário seja totalmente válido, ele só funcionará em clientes Windows associados a um domínio. Qualquer dispositivo que não seja um cliente do Windows associado a um domínio não será habilitado para marcação DSCP. Clientes como o Mac OS têm marcas embutidas em código e sempre marcarão tráfego.

No lado mais, controlar a marcação DSCP por meio do GPO garante que todos os computadores associados a um domínio recebam as mesmas configurações e que somente um administrador possa gerenciá-los. Os clientes que podem usar o GPO serão marcados no dispositivo de origem, e os dispositivos de rede configurados poderão reconhecer o fluxo em tempo real pelo código DSCP e dar a ele uma prioridade adequada.

### <a name="best-practice"></a>Prática recomendada

Recomendamos uma combinação de marcações DSCP no ponto de extremidade e ACLs baseadas na porta em roteadores, se possível. Usar um objeto de política de grupo para capturar a maioria dos clientes e usar a marcação de DSCP baseada na porta garantirá que o celular, o Mac e outros clientes ainda recebam tratamento de QoS (pelo menos parcialmente).

As marcações de DSCP podem ser likeneddas para os carimbos de postagem que indicam a trabalhadores em comum qual é a urgência da entrega e como classificá-lo para agilizar a entrega. Depois de configurar sua rede para dar prioridade a fluxos de mídia em tempo real, os pacotes perdidos e os pacotes atrasados devem diminuir bastante.

Quando todos os dispositivos na rede estiverem usando as mesmas classificações, marcações e prioridades, é possível reduzir ou eliminar atrasos, pacotes ignorados e Tremulação alterando o tamanho dos intervalos de porta atribuídos às filas usadas para cada tipo de tráfego. Da perspectiva do Teams, a etapa de configuração mais importante é a classificação e a marcação de pacotes, mas para que a QoS ponto a ponto seja bem-sucedida, você também precisa alinhar cuidadosamente a configuração do aplicativo com a configuração de rede subjacente. Depois que a QoS é totalmente implementada, o gerenciamento contínuo é uma questão de ajustar os intervalos de porta atribuídos a cada tipo de tráfego com base nas necessidades da sua organização e no uso real.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Escolher intervalos de porta iniciais para cada tipo de mídia

O valor de DSCP informa à rede uma rede configurada correspondente qual prioridade para fornecer um pacote ou fluxo, seja a marca de DSCP atribuída por clientes ou pela rede em si com base nas configurações da ACL. Cada carga de trabalho de mídia obtém seu próprio valor de DSCP exclusivo (outros serviços podem permitir que as cargas de trabalho compartilhem uma marcação DSCP, o Teams não) e um intervalo de porta definido e separado usado para cada tipo de mídia. Outros ambientes podem ter uma estratégia de QoS existente no local, o que o ajudará a determinar a prioridade das cargas de trabalho da rede.

O tamanho relativo dos intervalos de porta para cargas de trabalho de streaming em tempo real diferentes define a proporção entre a largura de banda total disponível dedicada a essa carga de trabalho. Para voltar à nossa analogia comum anterior: uma letra com um selo "mensagens de ar" pode ser retirada dentro de uma hora para o aeroporto mais próximo, enquanto um pacote pequeno marcado como "Bulk Mail" pode esperar por um dia antes de viajar em uma série de caminhões.

_Intervalos de portas iniciais recomendados_

|Tipo de tráfego de mídia| Intervalo de portas de origem do cliente  |Protocolo|Valor DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Áudio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Vídeo| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Compartilhamento de tela/aplicativo| 50.040-50.059|TCP/UDP|dezoito|Assured Forwarding (AF21)|
||||||

Lembre-se do seguinte ao usar estas configurações:

- Se você planeja implementar o ExpressRoute no futuro e ainda não implementou a QoS, recomendamos que siga as orientações para que os valores de DSCP sejam iguais do remetente ao destinatário.
- Todos os clientes, incluindo clientes móveis e dispositivos de equipe, usarão esses intervalos de porta e serão afetados por qualquer política de DSCP implementada que use esses intervalos de porta de origem. Os únicos clientes que continuarão a usar portas dinâmicas são os clientes baseados em navegador (ou seja, os clientes que permitem que os participantes ingressem em reuniões usando seus navegadores).
- Embora o cliente Mac use os mesmos intervalos de porta, ele também usa valores embutidos em áudio (EF) e vídeo (AF41). Esses valores não são configuráveis.
- Se, posteriormente, você precisar ajustar os intervalos de porta para melhorar a experiência do usuário, os intervalos de porta não poderão se sobrepor e devem ser adjacentes.

## <a name="migrate-qos-to-teams"></a>Migrar QoS para o Teams

Se você já implantou o Skype for Business Online, incluindo a marcação de QoS e os intervalos de porta, e agora está implantando equipes, o Teams respeitará a configuração existente e usará os mesmos intervalos de porta e marcação que o cliente Skype for Business. Na maioria dos casos, nenhuma configuração adicional será necessária.

> [!NOTE]
> Se você estiver usando a marcação de QoS de nome do aplicativo por meio da política de grupo, será necessário adicionar Teams.exe como o nome do aplicativo.


## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gerenciar portas de origem no centro de administração do teams

No Teams, as portas de origem de QoS usadas pelas diferentes cargas de trabalho devem ser gerenciadas ativamente e ajustadas conforme necessário. Fazendo referência à tabela em [escolher intervalos de portas iniciais para cada tipo de mídia](#choose-initial-port-ranges-for-each-media-type), os intervalos de porta são ajustáveis, mas as marcações de DSCP não são configuráveis. Depois de implementar essas configurações, você pode descobrir que mais ou menos portas são necessárias para um determinado tipo de mídia. O painel de [análise de chamadas por usuário](use-call-analytics-to-troubleshoot-poor-call-quality.md) e o [painel de qualidade de chamada (CQD)](turning-on-and-using-call-quality-dashboard.md) devem ser usados para tomar uma decisão de ajustar os intervalos de porta após a implementação das equipes e, periodicamente, as necessidades serem alteradas.

> [!NOTE]
> Se você já configurou o QoS com base em intervalos de porta de origem e marcações DSCP para o Skype for Business Online, a mesma configuração será aplicada às equipes e não será necessária nenhuma outra alteração de cliente ou de rede para o mapeamento, mas talvez seja necessário [definir os intervalos usados no Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) para corresponder ao que foi configurado para o Skype for Business online.

Se você já implantou o Skype for Business Server no local, talvez seja necessário examinar novamente suas políticas de QoS e ajustá-las para corresponder às configurações de intervalo de porta que você verificou fornecer uma experiência de usuário de qualidade para equipes.

## <a name="validate-your-qos-implementation"></a>Validar a implementação de QoS

Para que a QoS seja eficiente, o valor de DSCP definido pelo objeto de política de grupo precisa estar presente em ambas as extremidades de uma chamada. Ao analisar o tráfego gerado pelo cliente da equipe, você pode verificar se o valor de DSCP não foi alterado ou removido quando o tráfego de carga de trabalho do teams se move pela rede.

Preferencialmente, você captura o tráfego no ponto de saída de rede. Você pode usar o espelhamento de porta em um switch ou um roteador para obter ajuda com isso.


## <a name="related-topics"></a>Tópicos relacionados

[Vídeo: Planejamento de rede](https://aka.ms/teams-networking)

[Preparar a rede da organização para o Microsoft Teams](prepare-network.md)

[Implementar QoS no cliente do teams](QoS-in-Teams-clients.md)
