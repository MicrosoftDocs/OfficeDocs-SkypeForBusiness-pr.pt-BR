---
title: "Preparo da rede da sua organização para o Microsoft Teams | Suporte da Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como preparar e gerenciar sua rede para o Microsoft Teams. As informações incluem requisitos de rede, requisitos de largura de banda e considerações adicionais."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 399a0a6ed6ac5bfabeac97f41e82e0237bca0b74
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2017
---
<a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparo da rede da sua organização para o Microsoft Teams
=================================================

O Microsoft Teams combinam três formas de tráfego:

-   O tráfego de dados entre o ambiente online do Office 365 e o cliente Microsoft Teams (sinalização, presença, bate-papo, upload e download de arquivos, sincronização do OneNote).

-   Tráfego de comunicação de ponto a ponto em tempo real (áudio, vídeo, compartilhamento de desktop).

-   Tráfego de comunicação de conferências em tempo real (áudio, vídeo, compartilhamento de desktop).

Isso impacta a rede em dois níveis: o tráfego fluirá entre os clientes Microsoft Teams diretamente para o ponto a ponto, e o tráfego fluirá entre o ambiente do Office 365 e os clientes Microsoft Teams para atender aos cenários. Para garantir um fluxo de tráfego ideal, o tráfego deve ser permitido entre os segmentos internos da rede (por exemplo, entre sites da WAN), bem como entre os sites da rede e o Office 365. Deixar de abrir as portas corretas ou bloquear ativamente as portas especificadas prejudicará a experiência.

|  |  |
|---------|---------|
|![Ícone de importante.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image1.png)<br></br>Importante    |No momento, as reuniões têm suporte nos dispositivos móveis iOS e Android, mas não no Windows Phone (o Windows Phone terá suporte em breve).       |

Para ter uma boa experiência com mídia em tempo real no Microsoft Teams, é necessário atender aos requisitos de rede do Office 365 (consulte a seguinte fonte para obter mais detalhes: [Qualidade de mídia e desempenho da conectividade de rede para o Skype for Business Online](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917?ui=en-US&rs=en-US&ad=US) )

Os dois segmentos de rede a ser definidos (Cliente para o Microsoft Edge e Edge do cliente para o Microsoft Edge) devem atender aos seguintes requisitos:


|Valor  |Cliente para o Microsoft Edge  |Edge do cliente para o Microsoft Edge  |
|---------|---------|---------|
|**Latência (unidirecional)**     |< 50 ms          |< 30 ms          |
|**Latência (RTT ou tempo-resposta)** |< 100 ms         |< 60 ms         |
|**Perda de pacote de intermitência**    |<10% durante qualquer intervalo de 200 ms         |<1% durante qualquer intervalo de 200 ms         |
|**Perda de pacote**     |<1% durante qualquer intervalo de 15 s          |<0,1% durante qualquer intervalo de 15 s         |
|**Tremulação entre chegadas de pacote**    |<30 ms durante qualquer intervalo de 15 s         |<15 ms durante qualquer intervalo de 15 s         |
|**Novo pedido de pacotes**    |<0,05% de pacotes com problemas         |<0,01% de pacotes com problemas         |

Para testar ambos os segmentos de rede, pode ser usada uma ferramenta de avaliação de rede (fonte: [https://www.microsoft.com/en-us/download/details.aspx?id=53885](https://go.microsoft.com/fwlink/?linkid=855799)). Essa ferramenta ode ser implantada no cliente PC diretamente e no PC/laptop conectado ao Customer Network Edge. Essa ferramenta contém uma documentação limitada, mas uma documentação mais profunda do uso da ferramenta pode ser encontrada aqui: [Avaliação da prontidão da rede](https://go.microsoft.com/fwlink/?linkid=855800). Ao executar essa Avaliação da prontidão da rede, você pode validar a prontidão da sua rede para executar aplicativos de mídia em tempo real, como o Microsoft Teams.

|  |  |
|---------|---------|
|![Ícone de nota.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image2.png)<br></br>Nota    |Essa é a mesma Avaliação da prontidão da rede recomendada para clientes que estão buscando implantar o Skype for Business.         |

<a name="bandwidth-requirements"></a>Requisitos de largura de banda
----------

Os cálculos de largura de banda do Microsoft Teams são complexos e, para ajudar, foi criada uma calculadora. Para acessar a calculadora, acesse aqui: <http://aka.ms/bwcalc/>.

O conteúdo que você encontrar abaixo pode ser usado como informações complementares básicas; entretanto, é recomendado que os clientes usem a [Calculadora de largura de banda](https://aka.ms/bwcalc) para rastrear suas necessidades.

|  |  |
|---------|---------|
|![Ícone de nota.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image2.png)<br></br>Nota    |Se não houver a largura de banda necessária, a pilha de mídia dentro do Microsoft Teams prejudicará a qualidade da sessão de áudio/vídeo para acomodar essa menor largura de banda disponível, afetando a qualidade da chamada/reunião. O cliente Microsoft Teams tentará priorizar a qualidade do áudio em relação à qualidade do vídeo. Assim, é extremamente importante ter a largura de banda esperada disponível.       |


|Atividade  |Largura de banda para download  |Largura de banda para upload  |Fluxo de tráfego |
|---------|---------|---------|---------|
|**Chamada de áudio ponto a ponto**     |0,1 Mb         |0,1 Mb         |Cliente <> Cliente         |
|**Chamada de vídeo ponto a ponto**     |4 Mb         |4 Mb         |Cliente <> Cliente          |
|**Compartilhamento de desktop ponto a ponto (resolução de 1920*1080)**     |4 Mb         |4 Mb         |Cliente <> Cliente          |
|**Reunião com 2 participantes**     |4 Mb         |4 Mb         |Cliente <> Office 365         |
|**Reunião com 3 participantes**     |8 Mb         |6,5 Mb         |Cliente <> Office 365           |
|**Reunião com 4 participantes**     |5,5 Mb         |4 Mb         |Cliente <> Office 365           |
|**Reunião com 5 ou mais participantes**     |6 Mb         |1,5 Mb         |Cliente <> Office 365           |


<a name="additional-network-considerations"></a>Considerações de rede adicionais
---------------

#### <a name="external-name-resolution"></a>**Resolução do nome externo**

Certifique-se de que todos os computadores que executarem o cliente Microsoft Teams possam resolver consultas externas de DNS para descobrir os serviços fornecidos pelo Office 365.

#### <a name="nat-pool-size"></a>**Tamanho do pool de NAT**

Quando vários usuários/dispositivos acessam o Office 365 usando Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT), você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado.

Para reduzir esse risco, garanta que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para prevenir o esgotamento de portas. O esgotamento de portas fará com que dispositivos e usuários finais internos enfrentem problemas ao se conectarem aos serviços do Office 365. Para obter mais informações, consulte o guia [Suporte de NAT com o Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Detecção de intrusões e guia de prevenção**

Se o seu ambiente tiver um Sistema de Detecção e/u Prevenção de Intrusões (IDS / IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de que qualquer tráfego com destino para URLs do Office 365 esteja na lista de permissões.

<a name="network-health-determination"></a>Determinação da integridade de rede
-----------------

Ao planejar a implementação do Microsoft Teams na sua rede, você precisa garantir ter a largura de banda necessária, ter acesso todos os endereços IP necessários, ter as portas corretas abertas e que atendam aos requisitos de desempenho para mídias em tempo real.

Caso saiba da impossibilidade de atender a esses critérios, seus usuários finais não obterão uma experiência ideal no Microsoft Teams devido à má qualidade de chamadas e reuniões.

Caso não atenda a esses critérios, essa é a hora de considerar pausar o projeto para garantir que você esteja atendendo ao critérios antes de prosseguir.


|  |  |  |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Ponto de decisão         |Você avaliou seus recursos de rede para suporte a mídia em tempo real?<br></br>Caso sua rede não tenha sido devidamente avaliada ou caso saiba que ela não consegue suportar mídia em tempo real, você vai desativar os recursos de vídeo e compartilhamento de tela para reduzir o impacto de rede e as experiências deficientes do Teams?         |
|![Ícone de próximos passos.](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Próximos passos         |Qualidade de rede desconhecida: Siga as orientações de Avaliação da prontidão da rede em skypeoperationsframework.com para determinar se sua rede está pronta para mídia em tempo real.<br></br>Qualidade de rede deficiente: Execute as etapas de remediação de rede para proporcionar um ambiente adequado e de alta qualidade para mídia em tempo real.<br></br>Satisfatoriedade de rede: Garanta que todas as portas e endereços IP possam ser acessados adequadamente.           |

