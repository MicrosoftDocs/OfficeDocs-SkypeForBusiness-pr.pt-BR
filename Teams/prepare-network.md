---
title: Preparo da rede da sua organização para o Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Saiba mais sobre como preparar a rede da sua organização para o Microsoft Teams, incluindo requisitos de rede, otimização de rede e requisitos de largura de banda.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 1c84a753146899011fa34be56e0746cc0c600b31
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117749"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar a rede da organização para o Microsoft Teams 

## <a name="network-requirements"></a>Requisitos de rede

Se você já otimizou sua rede para [o Microsoft 365 ou o Office 365,](/Office365/Enterprise/assessing-network-connectivity)provavelmente está pronto para o Microsoft Teams. Em qualquer caso - e especialmente se você estiver implantando o Teams rapidamente como sua primeira carga de trabalho do Microsoft 365 ou Office 365 para dar suporte a funcionários remotos **-** verifique o seguinte antes de começar a implantação do Teams:

1.  Todos os seus locais têm acesso à Internet (para que eles possam se conectar ao Microsoft 365 ou Ao Office 365)? No mínimo, além do tráfego da Web normal, certifique-se de ter aberto o seguinte, para todos os locais, para mídia no Teams:

    |  |  |
    |---------|---------|
    |Portas     |Portas UDP <strong>3478</strong> a <strong>3481</strong>        |
    |[Endereços IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>e <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Se você precisar se federar com o Skype for Business, local ou online, será necessário configurar alguns registros DNS adicionais.
    >
    >|CNAME Records / Nome do host  |TTL  |Pontos para endereço ou valor  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Você tem um domínio verificado para o Microsoft 365 ou o Office 365 (por exemplo, contoso.com)?
    
    - Se sua organização não tiver lançado o Microsoft 365 ou o Office 365, consulte [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - Se sua organização não tiver adicionado ou configurado um domínio verificado para o Microsoft 365 ou Office 365, consulte a Perguntas [frequentes sobre domínios.](/microsoft-365/admin/setup/domains-faq)

3.  Sua organização implantou o Exchange Online e o SharePoint Online?
    
    - Se sua organização não tiver o Exchange Online, consulte [Entenda como o Exchange e o Microsoft Teams interagem.](exchange-teams-interact.md)
    - Se sua organização não tiver o SharePoint Online, consulte Entenda como o SharePoint Online e [o OneDrive for Business interagem com o Microsoft Teams.](sharepoint-onedrive-interact.md)

Depois de verificar se você atender a esses requisitos de rede, talvez esteja pronto para [lançar o Teams.](./deploy-overview.md) Se você é uma grande empresa multinacional ou se sabe que tem algumas limitações de rede, leia para saber como avaliar e otimizar sua rede para o Teams.

> [!IMPORTANT]
> **Para instituições educacionais**: se sua organização for uma instituição educacional e você usar um Sistema de Informações do Aluno (SIS), [implante](/schooldatasync/) a Sincronização de Dados Escolares antes de implantar o Teams.
>  
> Executando o **Skype for Business Server** local: se sua organização estiver executando o Skype for Business Server local (ou o Lync Server), você deve configurar o [Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar seu diretório local com o Microsoft 365 ou o Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Prática prática: monitorar sua rede usando CQD e análise de chamada 

Use o [Painel de Qualidade de Chamadas (CQD)](turning-on-and-using-call-quality-dashboard.md) para obter informações sobre a qualidade das chamadas e reuniões no Teams. O CQD pode ajudá-lo a otimizar sua rede, mantendo um olho atento à qualidade, confiabilidade e à experiência do usuário. O CQD analisa a telemetria agregada para uma organização inteira, onde os padrões gerais podem se tornar aparentes, o que permite identificar problemas e planejar a correção. Além disso, o CQD fornece relatórios de métricas rich que fornecem informações sobre a qualidade geral, a confiabilidade e a experiência do usuário. 

Você usará a análise [de chamada para](set-up-call-analytics.md) investigar problemas de chamada e reunião para um usuário individual.

## <a name="network-optimization"></a>Otimização de rede

As tarefas a seguir são opcionais e não são necessárias para a implantação do Teams, especialmente se você for uma pequena empresa e já tiver lançado o Microsoft 365 ou o Office 365. Use esta orientação para otimizar o desempenho da rede e do Teams ou se você sabe que tem algumas limitações de rede.

Talvez você queira fazer otimização de rede adicional se:

  - O Teams é executado lentamente (talvez você tenha largura de banda insuficiente)
  - As chamadas continuam a cair (pode ser devido a bloqueadores de firewall ou proxy)
  - Chamadas são estáticas e cortadas, ou as vozes soam como robôs (pode ser tremida ou perda de pacote)

Para uma discussão detalhada sobre otimização de rede, incluindo diretrizes para identificar e corrigir deficiências de rede, leia Princípios de Conectividade de Rede do [Microsoft 365 e office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).

<table>
<thead>
<tr class="header">
<th><strong>Tarefa de otimização de rede</strong></th>
<th><strong>Detalhes</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planejador de rede</td>
<td><p>Para ajudar a avaliar sua rede, incluindo cálculos de largura de banda e requisitos de rede em todos os locais físicos da sua organização, confira a ferramenta <a href="/microsoftteams/network-planner">Planejador</a> de Rede, no Centro de administração <a href="https://admin.teams.microsoft.com">do Teams.</a> Quando você fornece os detalhes da rede e o uso do Teams, o Planejador de Rede calcula seus requisitos de rede para implantar o Teams e a voz na nuvem nos locais físicos da sua organização.</p>
<p>Para um cenário de exemplo, consulte <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</p></td>
</tr>
<tr class="even">
<td>Consultor do Teams</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">O Consultor do Teams</a> faz parte do <a href="https://admin.teams.microsoft.com">Centro de administração do Teams.</a> Ele avalia o ambiente do seu Microsoft 365 ou Office 365 e identifica as configurações mais comuns que talvez sejam necessárias atualizar ou modificar antes de poder implantar o Teams com êxito.</td>
</tr>
<tr class="odd">
<td>Resolução de Nome Externo</td>
<td>Certifique-se de que todos os computadores que executam o cliente do Teams possam resolver consultas DNS externas para descobrir os serviços fornecidos pelo Microsoft 365 ou Office 365 e que seus firewalls não estão impedindo o acesso. Para obter informações sobre como configurar portas de firewall, vá para URLs e intervalos IP do <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 e Office 365.</a></td>
</tr>
<tr class="odd">
<td>Manter a persistência da sessão</td>
<td>Certifique-se de que o firewall não altere os endereços nat (conversão de endereço de rede) mapeados ou portas para UDP.</td>
</tr><tr class="odd">
<td>Validar o tamanho do pool NAT</td>
<td>Valide o tamanho do pool nat (conversão de endereço de rede) necessário para conectividade do usuário. Quando vários usuários e dispositivos acessam o Microsoft 365 ou o Office 365 usando NAT (Conversão de Endereço de Rede) ou PAT (Conversão de Endereço de <a href="/office365/enterprise/nat-support-with-office-365">Porta),</a>você precisa garantir que os dispositivos ocultos atrás de cada endereço IP publicamente routable não excedam o número suportado. Certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools NAT para evitar o esgotamento da porta. O esgotamento da porta contribuirá para que os usuários internos e dispositivos não consiga se conectar ao serviço do Microsoft 365 ou do Office 365.</td>
</tr>
<tr class="even">
<td>Roteamento para data centers da Microsoft</td>
<td><a href="/office365/enterprise/client-connectivity">Implemente o roteamento mais eficiente para data centers da Microsoft.</a> Identifique locais que podem usar pontos de saída locais ou regionais para se conectar à rede da Microsoft da maneira mais eficiente possível.</td>
</tr>
<tr class="odd">
<td>Diretrizes de Prevenção e Detecção de Intrusões</td>
<td>Se seu ambiente <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a> tiver um Sistema de Detecção ou Prevenção de Intrusão (IDS/IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de permitir todas as URLs do Microsoft 365 ou office 365.</td>
</tr>
<tr class="even">
<td>Configurar VPN de túnel dividido</td>
<td><p>Recomendamos que você forneça um caminho alternativo para o tráfego do Teams que ignora a VPN (rede virtual privada), comumente conhecida como VPN de túnel <a href="/windows/security/identity-protection/vpn/vpn-routing">dividido.</a> O túnel dividido significa que o tráfego para o Microsoft 365 ou Office 365 não passa pela VPN, mas vai diretamente para o Microsoft 365 ou o Office 365. Ignorar sua VPN terá um impacto positivo na qualidade do Teams e reduz a carga dos dispositivos VPN e da rede da organização. Para implementar uma VPN de túnel dividido, trabalhe com seu fornecedor vpn.</p>
<p>Outros motivos pelos quais recomendamos ignorar a VPN:
<ul>
<li><p>As VPNs geralmente não são projetadas ou configuradas para dar suporte a mídia em tempo real.</p></li> 
<li><p>Algumas VPNs também podem não dar suporte a UDP (o que é necessário para o Teams).</p></li> 
<li><p>As VPNs também introduzem uma camada extra de criptografia sobre o tráfego de mídia que já está criptografado.</p></li> 
<li><p>A conectividade com o Teams pode não ser eficiente devido ao tráfego de fixamento de cabelos por meio de um dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementar a QoS</td>
<td><a href="/microsoftteams/qos-in-teams">Use a QoS (Qualidade do Serviço)</a> para configurar a priorização de pacotes. Isso melhorará a qualidade das chamada no Teams e o ajudará a monitorar e solucionar problemas de qualidade de chamada. O QoS deve ser implementado em todos os segmentos de uma rede gerenciada. Mesmo quando uma rede foi adequadamente provisionada para largura de banda, o QoS fornece mitigação de riscos em caso de eventos de rede não antecipados. Com a QoS, o tráfego de voz é priorizado para que esses eventos não antecipados não afetem negativamente a qualidade.</td>
</tr>
<tr class="even">
<td>Otimizar WiFi</td>
<td><p>Semelhante à VPN, as redes WiFi não são necessariamente projetadas ou configuradas para dar suporte a mídia em tempo real. Planejar ou otimizar uma rede WiFi para dar suporte ao Teams é uma consideração importante para uma implantação de alta qualidade. Considere esses fatores:</p>
<ul>
<li><p>Implemente QoS ou WiFi Multimedia (WMM) para garantir que o tráfego de mídia está sendo priorizado adequadamente sobre suas redes WiFi.</p></li>
<li><p>Planeje e otimize as bandas WiFi e o posicionamento do ponto de acesso. O intervalo de 2,4 GHz pode proporcionar uma experiência adequada dependendo do posicionamento do ponto de acesso, mas os pontos de acesso costumam ser afetados por outros dispositivos do consumidor que operam nesse intervalo. O intervalo de 5 GHz é mais adequado à mídia em tempo real devido ao seu intervalo densa, mas exige mais pontos de acesso para obter cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.</p></li>
<li><p>Se você estiver usando redes WiFi de banda dupla, considere implementar a direção de banda. <em>A direção</em> de banda é uma técnica implementada por fornecedores WiFi para influenciar clientes de banda dupla a usar o intervalo de 5 GHz.</p></li>
<li><p>Quando os pontos de acesso do mesmo canal estão muito próximos, eles podem causar sobreposição de sinal e competir sem querer, resultando em uma experiência ruim para o usuário. Certifique-se de que os pontos de acesso que estão próximos um do outro estão em canais que não se sobrepõem.</p></li>
</ul>
<p>Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Consulte seu fornecedor WiFi para obter orientações específicas.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisitos de largura de banda

O Teams foi projetado para dar a melhor experiência de compartilhamento de áudio, vídeo e conteúdo, independentemente das condições de rede. Dito isso, quando a largura de banda é insuficiente, o Teams prioriza a qualidade de áudio em relação à qualidade do vídeo.

Onde  a largura de banda não é limitada, o Teams otimiza a qualidade da mídia, incluindo resolução de vídeo de até 1080p, até 30fps para vídeo e 15fps para conteúdo e áudio de alta fidelidade. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Tópicos Relacionados

[Princípios de conectividade de rede do Microsoft 365 e do Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Pontos de extremidade mundiais: Skype for Business Online e Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Servidores proxy para Teams](proxy-servers-for-skype-for-business-online.md)

[Mídia no Teams: por que as reuniões são simples](https://aka.ms/teams-media)

[Mídia no Teams: imersão profunda nos fluxos de mídia](https://aka.ms/teams-media-flows)

[Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md)

[Como implantar o Teams](./deploy-overview.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)