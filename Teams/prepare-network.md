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
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099565"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar a rede da organização para o Microsoft Teams 

## <a name="network-requirements"></a>Requisitos de rede

Se você já otimizou sua rede para [o Microsoft 365 ou o Office 365,](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)provavelmente está pronto para o Microsoft Teams. De qualquer forma, e especialmente se você estiver implantando o Teams rapidamente como sua primeira  carga de trabalho do Microsoft 365 ou do Office 365 para dar suporte a trabalhadores remotos, verifique o seguinte antes de começar a implantação do Teams:

1.  Todos os seus locais têm acesso à Internet (para que possam se conectar ao Microsoft 365 ou ao Office 365)? No mínimo, além do tráfego normal da Web, certifique-se de abrir o seguinte, para todos os locais, para mídia no Teams:

    |  |  |
    |---------|---------|
    |Portas     |Portas UDP <strong>3478</strong> a <strong>3481</strong>        |
    |[Endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18,</strong> <strong>52.112.0.0/14</strong>e <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Se você precisar se federar com o Skype for Business, local ou online, será necessário configurar alguns registros DNS adicionais.
    >
    >|Registros CNAME / nome do host  |Ttl  |Aponta para endereço ou valor  |
    >|---------|---------|---------|
    >|Sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Você tem um domínio verificado para o Microsoft 365 ou o Office 365 (por exemplo, contoso.com)?
    
    - Se sua organização não tiver lançado o Microsoft 365 ou o Office 365, consulte [Começar.](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)
    - Se sua organização não tiver adicionado ou configurado um domínio verificado para o Microsoft 365 ou o Office 365, consulte as perguntas [frequentes sobre Domínios.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)

3.  Sua organização implantou o Exchange Online e o SharePoint Online?
    
    - Se sua organização não tiver o Exchange Online, veja [como o Exchange e o Microsoft Teams interagem.](exchange-teams-interact.md)
    - Se sua organização não tiver o SharePoint Online, veja Como o SharePoint Online e o [OneDrive for Business interagem com o Microsoft Teams.](sharepoint-onedrive-interact.md)

Depois de verificar se você atender a esses requisitos de rede, talvez esteja pronto para [lançar o Teams.](How-to-roll-out-teams.md) Se você é uma grande empresa multinacional ou se sabe que tem algumas limitações de rede, continue lendo para saber como avaliar e otimizar sua rede para o Teams.

> [!IMPORTANT]
> **Para instituições de ensino:** se sua organização for uma instituição de ensino e você usar um SIS (Sistema de Informações do Aluno), implante o [School Data Sync](https://docs.microsoft.com/schooldatasync/) antes de implantar o Teams.
>  
> Executando o **Skype for Business Server** local: se sua organização estiver executando o Skype for Business Server local (ou o Lync Server), você deverá configurar o [Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar seu diretório local com o Microsoft 365 ou o Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Práticas práticas: monitorar sua rede usando o CQD e a análise de chamada 

Use o [Painel de Qualidade de Chamada (CQD)](turning-on-and-using-call-quality-dashboard.md) para obter informações sobre a qualidade das chamadas e reuniões no Teams. O CQD pode ajudá-lo a otimizar sua rede, acompanhando a qualidade, a confiabilidade e a experiência do usuário. O CQD analisa a telemetria agregada de uma organização inteira, onde os padrões gerais podem se tornar aparentes, o que permite identificar problemas e planejar a correção. Além disso, o CQD fornece relatórios de métricas ricas que fornecem informações sobre a qualidade geral, a confiabilidade e a experiência do usuário. 

Você usará a análise [de chamada](set-up-call-analytics.md) para investigar problemas de chamada e reunião de um usuário individual.

## <a name="network-optimization"></a>Otimização de rede

As tarefas a seguir são opcionais e não são necessárias para a implantação do Teams, especialmente se você for uma pequena empresa e já tiver lançado o Microsoft 365 ou o Office 365. Use esta orientação para otimizar o desempenho da rede e do Teams ou se você sabe que tem algumas limitações de rede.

Talvez você queira fazer otimização de rede adicional se:

  - O Teams é lento (talvez você tenha largura de banda insuficiente)
  - As chamadas continuam sendo soltas (pode ser devido a bloqueadores de proxy ou firewall)
  - As chamadas são estáticas e cortadas, ou as vozes soam como robôs (pode ser tremida ou perda de pacote)

Para uma discussão aprofundada sobre otimização de rede, incluindo diretrizes para identificar e corrigir deficiências de rede, leia Os Princípios de Conectividade de Rede do Microsoft 365 e do [Office 365.](https://aka.ms/pnc)

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
<td><p>Para ajudar a avaliar sua rede, incluindo cálculos de largura de banda e requisitos de rede em todos os locais físicos da sua organização, confira a ferramenta <a href="https://docs.microsoft.com/microsoftteams/network-planner">Planejador</a> de Rede, no Centro de <a href="https://admin.teams.microsoft.com">administração do Teams.</a> Quando você fornece os detalhes da rede e o uso do Teams, o Planejador de Rede calcula seus requisitos de rede para implantar o Teams e a voz na nuvem nos locais físicos da sua organização.</p>
<p>Para ver um cenário de exemplo, consulte <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Usando o Planejador de Rede - cenário de exemplo.</a></p></td>
</tr>
<tr class="even">
<td>Consultor do Teams</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">O Advisor para Teams</a> faz parte do Centro <a href="https://admin.teams.microsoft.com">de administração do Teams.</a> Ele avalia o ambiente do seu Microsoft 365 ou Office 365 e identifica as configurações mais comuns que talvez sejam necessárias atualizar ou modificar antes de poder implantar o Teams com êxito.</td>
</tr>
<tr class="odd">
<td>Resolução de Nome Externo</td>
<td>Certifique-se de que todos os computadores que executam o cliente Teams possam resolver consultas DNS externas para descobrir os serviços fornecidos pelo Microsoft 365 ou pelo Office 365 e que seus firewalls não estão impedindo o acesso. Para obter informações sobre como configurar portas de firewall, vá para URLs e intervalos IP do <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 e office 365.</a></td>
</tr>
<tr class="odd">
<td>Manter persistência de sessão</td>
<td>Certifique-se de que o firewall não altere os endereços ou portas mapeados de Conversão de Endereço de Rede (NAT) para UDP.</td>
</tr><tr class="odd">
<td>Validar o tamanho do pool NAT</td>
<td>Validar o tamanho do pool de conversão de endereços de rede (NAT) necessário para a conectividade do usuário. Quando vários usuários e dispositivos acessam o Microsoft 365 ou o Office 365 usando NAT <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">(Network Address Translation) ou Port Address Translation (PAT),</a>você precisa garantir que os dispositivos ocultos atrás de cada endereço IP rouável publicamente não excedam o número suportado. Certifique-se de que endereços IP públicos adequados sejam atribuídos aos pools NAT para evitar o esgotamento das portas. A exaustão de portas contribuirá para que usuários internos e dispositivos não consiga se conectar ao serviço do Microsoft 365 ou do Office 365.</td>
</tr>
<tr class="even">
<td>Roteamento para data centers da Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implemente o roteamento mais eficiente para data centers da Microsoft.</a> Identifique locais que podem usar pontos de saída locais ou regionais para se conectar à rede da Microsoft da maneira mais eficiente possível.</td>
</tr>
<tr class="odd">
<td>Diretrizes de prevenção e detecção de invasão</td>
<td>Se seu ambiente <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a> tiver um Sistema de Detecção ou Prevenção contra Invasão (IDS/IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de permitir todas as URLs do Microsoft 365 ou do Office 365.</td>
</tr>
<tr class="even">
<td>Configurar VPN de túnel dividido</td>
<td><p>Recomendamos que você forneça um caminho alternativo para o tráfego do Teams que ignora a VPN (rede virtual privada), normalmente conhecida como <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">VPN de túnel dividido.</a> Dividir túnel significa que o tráfego do Microsoft 365 ou do Office 365 não passa pela VPN, mas vai diretamente para o Microsoft 365 ou o Office 365. Ignorar sua VPN terá um impacto positivo na qualidade do Teams e reduzirá a carga dos dispositivos VPN e da rede da organização. Para implementar uma VPN de túnel dividido, trabalhe com seu fornecedor de VPN.</p>
<p>Outros motivos pelos quais recomendamos ignorar a VPN:
<ul>
<li><p>Normalmente, as VPNs não são projetadas ou configuradas para dar suporte a mídias em tempo real.</p></li> 
<li><p>Algumas VPNs também podem não dar suporte a UDP (que é necessário para o Teams).</p></li> 
<li><p>As VPNs também introduzem uma camada extra de criptografia sobre o tráfego de mídia que já está criptografado.</p></li> 
<li><p>A conectividade com o Teams pode não ser eficiente devido a fixar o tráfego por meio de um dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementar a QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Use qoS (Qualidade de Serviço)</a> para configurar a priorização de pacotes. Isso melhorará a qualidade da chamada no Teams e ajudará você a monitorar e solucionar problemas de qualidade de chamada. A QoS deve ser implementada em todos os segmentos de uma rede gerenciada. Mesmo quando uma rede foi adequadamente provisionada para largura de banda, a QoS fornece redução de riscos no caso de eventos de rede inesperados. Com a QoS, o tráfego de voz é priorizado para que esses eventos inesperados não afetem negativamente a qualidade.</td>
</tr>
<tr class="even">
<td>Otimizar o WiFi</td>
<td><p>Semelhante à VPN, as redes WiFi não são necessariamente projetadas ou configuradas para dar suporte a mídias em tempo real. Planejar ou otimizar uma rede WiFi para dar suporte ao Teams é uma consideração importante para uma implantação de alta qualidade. Considere estes fatores:</p>
<ul>
<li><p>Implemente qoS ou WiFi Multimedia (WMM) para garantir que o tráfego de mídia seja priorizado adequadamente em suas redes WiFi.</p></li>
<li><p>Planeje e otimize as faixas WiFi e o posicionamento do ponto de acesso. O intervalo de 2,4 GHz pode proporcionar uma experiência adequada dependendo do posicionamento do ponto de acesso, mas os pontos de acesso costumam ser afetados por outros dispositivos do consumidor que operam nesse intervalo. O intervalo de 5 GHz é mais adequado para mídias em tempo real devido ao seu intervalo desnado, mas requer mais pontos de acesso para obter cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquele intervalo e ser configurados para utilizar essas bandas corretamente.</p></li>
<li><p>Se você estiver usando redes WiFi de duas bandas, considere implementar a direção da faixa. <em>A direção de</em> banda é uma técnica implementada por fornecedores de WiFi para influenciar clientes de banda dupla a usar o intervalo de 5 GHz.</p></li>
<li><p>Quando os pontos de acesso do mesmo canal estão muito próximos, eles podem causar sobreposição de sinal e concorrência não intencional, resultando em uma experiência ruim para o usuário. Certifique-se de que os pontos de acesso que estão próximos uns dos outros estão em canais que não se sobrepõem.</p></li>
</ul>
<p>Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Consulte seu fornecedor do WiFi para obter orientações específicas.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisitos de largura de banda

O Teams foi projetado para dar a melhor experiência de compartilhamento de áudio, vídeo e conteúdo, independentemente de suas condições de rede. Dito isso, quando a largura de banda é insuficiente, o Teams prioriza a qualidade do áudio em relação à qualidade do vídeo.

Quando  a largura de banda não é limitada, o Teams otimiza a qualidade da mídia, incluindo até 1080p de resolução de vídeo, até 30fps para vídeo e 15fps para conteúdo e áudio de alta fidelidade. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Tópicos Relacionados

[Princípios de conectividade de rede do Microsoft 365 e do Office 365](https://aka.ms/pnc)

[Pontos de extremidade em todo o mundo: Skype for Business Online e Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Servidores proxy para o Teams](proxy-servers-for-skype-for-business-online.md)

[Mídia no Teams: por que as reuniões são simples](https://aka.ms/teams-media)

[Mídia no Teams: imersão profunda nos fluxos de mídia](https://aka.ms/teams-media-flows)

[Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md)

[Como implantar o Teams](How-to-roll-out-teams.md)

[Solução de problemas do Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
