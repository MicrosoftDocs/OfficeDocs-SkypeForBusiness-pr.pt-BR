---
title: Preparo da rede da sua organização para o Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Antes de implantar o Microsoft Teams, avalie e prepare a sua rede para ter certeza de que ela está pronta para o Teams. As informações incluem requisitos de rede, requisitos de largura de banda e orientação de otimização da rede.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bcdee7e1a4ce7f36a9089fd5231cf2a63e9d5b
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43109470"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparo da rede da sua organização para o Microsoft Teams 

## <a name="network-requirements"></a>Requisitos de rede

Se você já [otimizou a sua rede para o Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), provavelmente está pronto para o Microsoft Teams. Em qualquer caso-e especialmente se você estiver distribuindo o Teams rapidamente como sua primeira carga de trabalho do Office 365 para dar suporte a **trabalhadores remotos** , verifique o seguinte antes de começar a distribuição do seu Teams:

1.  Fazer com que todos os seus locais tenham acesso à Internet (para que possam se conectar ao Office 365)? No mínimo, além do tráfego normal da Web, certifique-se de ter aberto o seguinte, para todos os locais, para mídia no Microsoft Teams:

    |  |  |
    |---------|---------|
    |Portas     |Portas UDP de <strong>3478</strong> a <strong>3481</strong>        |
    |[Endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>e <strong>52.120.0.0/14</strong>         |

    
2.  Você tem um domínio verificado para o Office 365 (por exemplo, contoso.com)?
    
      - Se a sua organização ainda não distribuiu o Office 365, consulte [introdução ao office 365 para empresas](https://docs.microsoft.com/office365/admin/admin-overview/get-started-with-office-365).
      - Se a sua organização ainda não adicionou ou configurou um domínio verificado para o Office 365, consulte [verificar seu domínio do office 365](https://docs.microsoft.com/office365/admin/setup/domains-faq).

3.  Sua organização implantou o Exchange Online e o SharePoint Online?
    
      - Se a sua organização não tiver o Exchange Online, confira [entender como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md).
      - Se sua organização não tiver o SharePoint Online, confira [entender como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).

Depois de verificar que atende a esses requisitos de rede, você pode estar pronto para [implantar o Microsoft Teams](How-to-roll-out-teams.md). Se você for uma grande empresa multinacionais ou se souber que tem algumas limitações de rede, continue a ler para saber como avaliar e otimizar sua rede para o Microsoft Teams.

> [!IMPORTANT]
> **Para instituições educacionais**: se a sua organização for uma instituição educacional e você usar um sistema de informações do aluno (SIS), [implante a sincronização de dados da escola](https://docs.microsoft.com/schooldatasync/) antes de distribuir o Teams.
>  
> **Executando o Skype for Business Server local**: se a sua organização estiver executando o Skype for Business Server (ou Lync Server) local, você deverá [Configurar o Azure ad Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar o diretório local com o Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Prática recomendada: monitorar sua rede usando o CQD e a análise de chamadas 

Use o [painel de qualidade de chamada (CQD)](turning-on-and-using-call-quality-dashboard.md) para obter informações sobre a qualidade de chamadas e reuniões no Microsoft Teams. O CQD pode ajudá-lo a otimizar sua rede mantendo um olho de qualidade, confiabilidade e experiência do usuário. CQD examina a telemetria de agregação para uma organização inteira, em que os padrões gerais podem se tornar aparentes, o que permite que você identifique problemas e planeje a correção. Além disso, o CQD fornece relatórios de métricas robustos que fornecem uma visão geral da qualidade, da confiabilidade e da experiência do usuário. 

Você usará a [análise de chamadas](set-up-call-analytics.md) para investigar problemas de chamada e reunião para um usuário individual.

## <a name="network-optimization"></a>Otimização da rede

As tarefas a seguir são opcionais e não são necessárias para a implementação de equipes, especialmente se você for uma pequena empresa e já tiver feito o Office 365. Use esta orientação para otimizar o desempenho da rede e do Teams, ou se você sabe que tem algumas limitações de rede.

Você pode querer fazer uma otimização de rede adicional se:

  - O Teams é executado lentamente (talvez você não tenha largura de banda suficiente)
  - As chamadas continuam descartando (podem ser por causa dos bloqueadores de firewall ou proxy)
  - As chamadas têm estática e recortada, ou as vozes parecem robôs (pode haver tremulação ou perda de pacote)

Para uma discussão aprofundada da otimização da rede, incluindo orientações para identificar e corrigir deficiências na rede, leia os [princípios de conectividade de rede do Office 365](https://aka.ms/pnc).

<table>
<thead>
<tr class="header">
<th><strong>Tarefa de otimização da rede</strong></th>
<th><strong>Detalhes</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planejador de rede</td>
<td><p>Para obter ajuda para avaliar sua rede, incluindo cálculos de largura de banda e requisitos de rede nos locais físicos da sua organização, confira a ferramenta <a href="https://docs.microsoft.com/microsoftteams/network-planner">planejador de rede</a> , no <a href="https://admin.teams.microsoft.com">centro de administração do teams</a>. Quando você fornece os detalhes da rede e o uso das equipes, o planejador de rede calcula os requisitos de rede para a implantação de equipes e voz na nuvem nos locais físicos da sua organização.</p>
<p>Para obter um exemplo de cenário, consulte <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">como usar o planejador de rede-exemplo de cenário</a>.</p></td>
</tr>
<tr class="even">
<td>Advisor para Teams</td>
<td>O <a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> faz parte do <a href="https://admin.teams.microsoft.com">centro de administração do teams</a>. Ele avalia o ambiente do Office 365 e identifica as configurações mais comuns que talvez seja necessário atualizar ou modificar antes de poder implantar o Teams com êxito.</td>
</tr>
<tr class="odd">
<td>Resolução de nomes externos</td>
<td>Certifique-se de que todos os computadores que executam o cliente do teams possam resolver consultas DNS externas para descobrir os serviços fornecidos pelo Office 365 e que seus firewalls não impedem o acesso. Para obter informações sobre como configurar portas de firewall, vá para <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">URLs e intervalos de IP do Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Validar (NAT) o tamanho do pool</td>
<td>Valide o tamanho do pool de NAT (conversão de endereços de rede) necessário para a conectividade do usuário. Quando vários usuários e dispositivos acessam o Office 365 usando a <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">NAT (conversão de endereços de rede) ou Pat (conversão de endereço de porta)</a>, você precisa garantir que os dispositivos ocultos atrás de cada endereço IP roteável publicamente não exceda o número compatível. Certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para evitar a exaustão de portabilidade. A exaustão da porta contribuirá para que os usuários internos e dispositivos não consigam se conectar ao serviço do Office 365.</td>
</tr>
<tr class="even">
<td>Roteamento para data centers da Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implemente o roteamento mais eficiente para os data centers da Microsoft</a>. Identifique locais que podem usar pontos de saída locais ou regionais para se conectar à rede Microsoft da maneira mais eficiente possível.</td>
</tr>
<tr class="odd">
<td>Orientação de detecção e prevenção de invasões</td>
<td>Se seu ambiente tem um sistema de detecção ou prevenção de <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">intrusão</a> (IDS/IPS) implantado para obter uma camada adicional de segurança para conexões de saída, certifique-se de ter todas as URLs do Office 365.</td>
</tr>
<tr class="even">
<td>Configurar VPN de encapsulamento de divisão</td>
<td><p>Recomendamos que você forneça um caminho alternativo para o tráfego do teams que ignora a rede virtual privada (VPN), comumente conhecida como [VPN de encapsulamento dividido](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing). O tunelamento dividido significa que o tráfego do Office 365 não passa pela VPN, mas, em vez disso, passa diretamente para o Office 365. Ignorar sua VPN terá um impacto positivo sobre a qualidade das equipes e reduzirá a carga dos dispositivos VPN e da rede da organização. Para implementar uma VPN de encapsulamento dividido, trabalhe com o seu fornecedor de VPN.</p>
<p>Outros motivos pelos quais recomendamos ignorar a VPN:
<ul>
<li><p>As VPNs normalmente não são projetadas ou configuradas para dar suporte à mídia em tempo real.</p></li> 
<li><p>Algumas VPNs também podem não oferecer suporte ao UDP (que é necessário para o Teams).</p></li> 
<li><p>As VPNs também introduzem uma camada adicional de criptografia na parte superior do tráfego de mídia que já está criptografado.</p></li> 
<li><p>A conectividade com o Microsoft Teams pode não ser eficiente devido ao tráfego de cabelo de cabelo por meio de um dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementar a QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use a QoS (qualidade de serviço)</a> para configurar a priorização do pacote. Isso irá melhorar a qualidade da chamada no Teams e ajudar você a monitorar e solucionar problemas de qualidade da chamada. A QoS deve ser implementada em todos os segmentos de uma rede gerenciada. Mesmo quando uma rede tem sido provisionada de forma adequada para largura de banda, a QoS permite a mitigação de risco no caso de eventos de rede não esperados. Com a QoS, o tráfego de voz é priorizado para que esses eventos desprevistos não afetem negativamente a qualidade.</td>
</tr>
<tr class="even">
<td>Otimizar WiFi</td>
<td><p>Semelhante à VPN, as redes WiFi não são necessariamente projetadas ou configuradas para dar suporte à mídia em tempo real. Planejar ou otimizar uma rede WiFi para dar suporte a equipes é uma consideração importante para uma implantação de alta qualidade. Considere estes fatores:</p>
<ul>
<li><p>Implemente a QoS ou a multimídia WiFi (WMM) para garantir que o tráfego de mídia esteja recebendo a prioridade apropriadamente nas redes WiFi.</p></li>
<li><p>Planeje e otimize as faixas WiFi e o posicionamento do ponto de acesso. O intervalo de 2,4 GHz pode proporcionar uma experiência adequada dependendo do posicionamento do ponto de acesso, mas os pontos de acesso costumam ser afetados por outros dispositivos do consumidor que operam nesse intervalo. O intervalo de 5 GHz é mais adequado para mídia em tempo real devido ao seu alcance denso, mas requer mais pontos de acesso para obter cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.</p></li>
<li><p>Se você estiver usando redes WiFi de banda dupla, considere a implementação do direcionamento de banda. <em>Direcionamento de banda</em> é uma técnica implementada por fornecedores WiFi para influenciar clientes de banda dupla para usar o intervalo de 5 GHz.</p></li>
<li><p>Quando pontos de acesso do mesmo canal estiverem muito próximos uns dos outros, eles poderão causar sobreposição de sinal e concorrência não intencional, resultando em uma experiência ruim para o usuário. Certifique-se de que os pontos de acesso próximos uns dos outros estejam em canais que não se sobreponham.</p></li>
</ul>
<p>Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Consulte o fornecedor do WiFi para obter orientação específica.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisitos de largura de banda

O Teams foi projetado para oferecer a melhor experiência de áudio, vídeo e compartilhamento de conteúdo, independentemente das condições da rede. Dito que, quando a largura de banda é insuficiente, o Teams prioriza a qualidade de áudio com qualidade de vídeo.

Onde a largura de banda *não é* limitada, o Teams otimiza a qualidade da mídia, incluindo até 1080p de resolução de vídeo, até 30 qps para vídeo e 15fps para conteúdo e áudio de alta fidelidade. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Tópicos Relacionados

[Princípios de conectividade de rede do Office 365](https://aka.ms/pnc)

[Pontos de extremidade mundiais: Skype for Business Online e Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Servidores proxy para Teams](proxy-servers-for-skype-for-business-online.md)

[Mídia no Teams: por que as reuniões são simples](https://aka.ms/teams-media)

[Mídia no Teams: Mergulhe detalhada nos fluxos de mídia](https://aka.ms/teams-media-flows)

[Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md)

[Como implantar o Teams](How-to-roll-out-teams.md)


