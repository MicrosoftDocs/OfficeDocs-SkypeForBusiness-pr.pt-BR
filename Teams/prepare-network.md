---
title: Preparo da rede da sua organização para o Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Saiba mais sobre como preparar a rede da sua organização para o Microsoft Teams, incluindo requisitos de rede, otimização de rede e requisitos de largura de banda.
ms.localizationpriority: high
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
ms.openlocfilehash: 66cc7a7db5098154a99073acd0bb1952727a3760
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045450"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparar a rede da organização para o Microsoft Teams

## <a name="network-requirements"></a>Requisitos de rede

Se você já tiver[otimizado sua rede para o Microsoft 365 ou o Office 365](/Office365/Enterprise/assessing-network-connectivity), provavelmente já está pronto para o Microsoft Teams. De qualquer forma, e especialmente se você estiver implantando o Teams rapidamente como sua primeira carga de trabalho do Microsoft 365 ou do Office 365 para dar suporte **a trabalhadores remotos**, verifique o seguinte antes de iniciar a implantação do Teams:

1. Todos os seus locais têm acesso à Internet (para que possam se conectar ao Microsoft 365 ou Office 365)? Além do tráfego normal da web, verifique se você abriu as portas TCP e os endereços IP listados para o Teams nas [URLs do Office 365 e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

    > [!IMPORTANT]
    > Se for necessário federar com o Skype for Business, seja local ou online, você precisará configurar um registro DNS adicional.
    >
    >|Registro DNS  |Serviço  |Protocolo  |Prioridade  |Peso  |Porta  |Destino  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|SRV     |sipfederationtls     |TCP     |100     |1     |5061     |sipfed.online.lync.com     |

2. Você tem um domínio verificado para o Microsoft 365 ou para o Office 365 (por exemplo, contoso.com)?

    - Se sua organização não tiver lançado o Microsoft 365 ou o Office 365, consulte [Começar](/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - Se sua organização ainda não adicionou ou configurou um domínio verificado para o Microsoft 365 ou para o Office 365, consulte as [Perguntas frequentes de Domínio](/microsoft-365/admin/setup/domains-faq).

3. Sua organização implantou o Exchange Online e o SharePoint Online?

    - Se a sua organização não tiver o Exchange Online, consulte [Saiba como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md).
    - Se a sua organização não tiver o SharePoint Online, consulte [Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).

Depois de verificar se você atende a esses requisitos de rede, você pode estar pronto para [Implementar o Teams](./deploy-overview.md). Se você tiver uma grande empresa multinacional ou se tiver algumas limitações de rede, continue a ler para saber como avaliar e otimizar sua rede para o Teams.

> [!IMPORTANT]
> **Para instituições de ensino**: se sua organização for uma instituição educacional e você usar um SIS (Sistema de Informações do Aluno), [implante o School Data Sync](/schooldatasync/) antes de implantar o Teams.
>
> **Executando o Skype for Business Server** Se a sua organização estiver executando o Skype for Business Server (ou Lync Server) local, você deverá [Configurar o Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar seu diretório local com o Microsoft 365 ou Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Prática recomendada: monitore sua rede usando o CQD e a análise de chamada

Use o [CQD (Painel de Controle de Qualidade de Chamada)](turning-on-and-using-call-quality-dashboard.md) para obter informações sobre a qualidade das chamadas e das reuniões no Teams. O CQD pode ajudá-lo a otimizar a rede, acompanhando de perto a qualidade, a confiabilidade e a experiência do usuário. O CQD analisa a telemetria agregada de uma organização inteira onde os padrões gerais podem se tornar intermediários, o que permite identificar problemas e planejar a mediação. Além disso, o CQD fornece relatórios de métricas abrangentes que fornecem informações sobre a qualidade geral, a confiabilidade e a experiência do usuário.

Você usará o recurso de [análise de chamada](set-up-call-analytics.md) para investigar problemas de chamada e reunião de um usuário individual.

## <a name="network-optimization"></a>Otimização de rede

As tarefas a seguir são opcionais e não são necessárias para a implantação do Teams, especialmente se você for uma pequena empresa e já tiver implantado o Microsoft 365 ou o Office 365. Use essas orientações para otimizar o desempenho da rede e do Teams ou se tiver certeza de que tem algumas limitações de rede.

Talvez você queira fazer uma otimização de rede adicional se:

- O Teams estiver muito lento (talvez você não tenha largura de banda insuficiente)
- As chamadas continuam caindo (pode ser devido a bloqueadores de firewall ou proxy)
- As chamadas estão estáticas e cortadas, ou as vozes soam como robôs (pode ser instabilidade ou perda de pacotes)

Para uma discussão aprofundada sobre otimização de rede, incluindo orientações sobre como identificar e corrigir deficiências de rede, leia [Princípios de Conectividade de Rede do Microsoft 365 e do Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).

<table>
<thead>
<tr class="header">
<th>Tarefa de otimização de rede</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Planejador de rede</td>
<td><p>Para ajudar a avaliação de sua rede, incluindo cálculos de largura de banda e requisitos de rede nos locais físicos da organização, confira a ferramenta <a href="/microsoftteams/network-planner">Planejador de rede</a>, no <a href="https://admin.teams.microsoft.com">centro de administração do Teams</a>. Quando você fornece detalhes de sua rede e uso do Teams, o Planejador de Rede calcula seus requisitos de rede para implantar o Teams e o cloud voice nos locais físicos da sua organização.</p>
<p>Para ver um cenário de exemplo, confira <a href="/microsoftteams/tutorial-network-planner-example">Como usar o Planejador de rede, exemplo de cenário</a>.</p></td>
</tr>
<tr class="even">
<td>Consultor para o Teams</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">O Assistente do Microsoft Teams</a> faz parte do <a href="https://admin.teams.microsoft.com">centro de administração do Microsoft Teams </a>. Ele avalia o ambiente do seu Microsoft 365 ou Office 365 e identifica as configurações mais comuns que você pode precisar atualizar ou modificar antes de poder implantar com êxito o Microsoft Teams.</td>
</tr>
<tr class="odd">
<td>Resolução do nome externo</td>
<td>Certifique-se de que todos os computadores que executam o cliente Teams possam resolver consultas DNS externas para descobrir os serviços fornecidos pelo Microsoft 365 ou pelo Office 365 e que seus firewalls não estejam impedindo o acesso. Para saber mais sobre como configurar portas de firewall, vá para<a href="/microsoftteams/office-365-urls-ip-address-ranges">URLs e intervalos IP do Microsoft 365 e do Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Manter a persistência da sessão</td>
<td>Certifique-se de que seu firewall não altere os endereços ou portas de conversão de endereços de rede (NAT) mapeados para UDP.</td>
</tr><tr class="odd">
<td>Validar o tamanho do pool de NAT</td>
<td>Valide o tamanho de pool de conversão de endereços de rede (NAT) necessário para conectividade do usuário. Quando vários usuários e dispositivos acessam o Microsoft 365 ou o Office 365 usando a <a href="/office365/enterprise/nat-support-with-office-365">Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT)</a>, você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado. Certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para prevenir o esgotamento de portas. A exaustão da porta contribuirá para que usuários e dispositivos internos não consigam se conectar ao serviço Microsoft 365 ou Office 365.</td>
</tr>
<tr class="even">
<td>Roteamento para data centers da Microsoft</td>
<td><a href="/office365/enterprise/client-connectivity">Implemente o roteamento mais eficiente para os data centers da Microsoft</a>. Identifique locais que podem usar pontos de saída locais ou regionais para se conectar à rede da Microsoft da forma mais eficiente possível.</td>
</tr>
<tr class="odd">
<td>Detecção de invasão e orientação de prevenção</td>
<td>Se seu ambiente tiver uma <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Detecção de Invasão</a> ou um Sistema de Prevenção (IDS/IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de permitir todas as URLs do Microsoft 365 ou do Office 365.</td>
</tr>
<tr class="even">
<td>Configurar o VPN com túnel dividido</td>
<td><p>Recomendamos que você forneça um caminho alternativo para o tráfego do Teams que ignore a VPN (rede virtual privada), normalmente conhecida como <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN split-tunnel</a>. Split-tunneling significa que o tráfego para o Microsoft 365 ou o Office 365 não vai para a VPN, e sim diretamente para o Microsoft 365 ou o Office 365. Ignorar sua VPN terá um impacto positivo na qualidade do Teams e reduzirá a carga dos dispositivos VPN e da rede da organização. Para implementar uma VPN split-tunnel por meio de um plano VPN, trabalhe com seu fornecedor de VPN.</p>
<p>Outros motivos pelos quais recomendamos ignorar a VPN:
<ul>
<li><p>As VPNs em geral não são projetadas ou configuradas para dar suporte a mídia em tempo real.</p></li>
<li><p>Algumas VPNs também podem não dar suporte a UDP (que é necessária para o Teams).</p></li>
<li><p>As VPNs também introduzem uma camada extra de criptografia sobre o tráfego de mídia que já está criptografado.</p></li>
<li><p>A conectividade com o Teams pode não ser eficiente devido ao tráfego excessivo por meio de um dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementar a QoS</td>
<td><a href="/microsoftteams/qos-in-teams">Use a tecnologia QoS (Qualidade do Serviço)</a> para configurar a priorização de pacotes. Isso melhorará a qualidade da chamada no Teams e o ajudará a monitorar e solucionar problemas de qualidade da chamada. O QoS deve ser implementado em todos os segmentos de uma rede gerenciada. Mesmo quando uma rede foi adequadamente provisionada para largura de banda, o QoS fornece redução de riscos em caso de eventos de rede inesperados. Com o QoS, o tráfego de voz é priorizado para que esses eventos não inesperados não afetem a qualidade negativamente.</td>
</tr>
<tr class="even">
<td>Otimizar o WiFi</td>
<td><p>Como a VPN, as redes WiFi não são necessariamente projetadas ou configuradas para oferecer suporte à mídia em tempo real. Planejar ou otimizar uma rede WiFi para oferecer suporte ao Teams é uma consideração importante para uma implantação de alta qualidade. Considere estes fatores:</p>
<ul>
<li><p>Implemente o QoS ou WiFi Multimídia (WMM) para garantir que o tráfego de mídia seja priorizado adequadamente em suas redes WiFi.</p></li>
<li><p>Planeje e otimize as faixas de WiFi e o posicionamento do ponto de acesso. O intervalo de 2,4 GHz pode proporcionar uma experiência adequada dependendo do posicionamento do ponto de acesso, mas os pontos de acesso costumam ser afetados por outros dispositivos do consumidor que operam nesse intervalo. A frequência de 5 GHz é mais adequada para mídia em tempo real porque é mais densa, mas requer mais pontos de acesso para proporcionar cobertura suficiente. Os pontos de extremidade também precisam dar suporte àquela frequência e ser configurados para utilizar essas bandas corretamente.</p></li>
<li><p>Se você estiver usando redes WiFi de duas faixas, considere implementar o suporte da faixa. <em>A direção de banda</em> é uma técnica implementada por fornecedores de Wi-Fi para influenciar os clientes de banda dupla a usar o intervalo de 5 GHz.</p></li>
<li><p>Quando pontos de acesso do mesmo canal estão muito próximos, eles podem causar sobreposição de sinal e competir involuntariamente, resultando em uma experiência não satisfatória para o usuário. Certifique-se de que os pontos de acesso próximos um do outro estejam em canais que não se sobreponham.</p></li>
</ul>
<p>Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio. Consulte o fornecedor de wifi para obter orientações específicas.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisitos de largura de banda

O Teams foi projetado para dar a você a melhor experiência de compartilhamento de áudio, vídeo e conteúdo, independentemente das condições da sua rede. Dessa forma, quando a largura de banda não é suficiente, o Teams prioriza a qualidade de áudio em relação à qualidade do vídeo.

Onde a largura de banda não é limitada, o Teams otimiza a qualidade da mídia, incluindo áudio de alta fidelidade, resolução de vídeo de até 1080p e até 30 fps (quadros por segundo) para vídeo e conteúdo.

Essa tabela descreve como o Teams usa a largura de banda. O Teams é sempre prudente na utilização de largura de banda e pode oferecer qualidade de vídeo HD em 1,5Mbps. O consumo real de largura de banda em cada chamada de áudio/vídeo ou reunião varia com base em vários fatores, como layout de vídeo, resolução de vídeo e quadros de vídeo por segundo. Quando houver mais largura de banda, a qualidade e o uso aumentarão, oferecendo a melhor experiência possível.

:::row:::
   :::column span="":::
      **Modalidade**
   :::column-end:::
   :::column span="3":::
      **Requisitos de largura de banda (taxa de bits kB/s para cima/para baixo)**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      **Mínimo**
   :::column-end:::
   :::column span="":::
      **Recomendado**
   :::column-end:::
   :::column span="":::
      **Melhor desempenho**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Áudio**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Individual
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Reuniões
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Vídeo**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Individual
   :::column-end:::
   :::column span="":::
        150/150
   :::column-end:::
   :::column span="":::
        1.500/1.500
   :::column-end:::
   :::column span="":::
        4.000/4.000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Reuniões
   :::column-end:::
   :::column span="":::
        150/200
   :::column-end:::
   :::column span="":::
        2.500/4.000
   :::column-end:::
   :::column span="":::
        4.000/4.000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Compartilhamento de tela**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Individual
   :::column-end:::
   :::column span="":::
        200/200
   :::column-end:::
   :::column span="":::
        1.500/1.500
   :::column-end:::
   :::column span="":::
        4.000/4.000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Reuniões
   :::column-end:::
   :::column span="":::
        250/250
   :::column-end:::
   :::column span="":::
        2.500/2.500
   :::column-end:::
   :::column span="":::
        4.000/4.000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Modo conferência**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Individual
   :::column-end:::
   :::column span="":::
        Não disponível
   :::column-end:::
   :::column span="":::
        Não disponível
   :::column-end:::
   :::column span="":::
        Não disponível
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Reuniões
   :::column-end:::
   :::column span="":::
        1.000/1.500
   :::column-end:::
   :::column span="":::
        1.500/2.500
   :::column-end:::
   :::column span="":::
        2.500/4.000
   :::column-end:::
:::row-end:::

Os requisitos de largura de banda **Mínimo**, **Recomendado** e **Melhor desempenho** são baseados no uso por ponto de extremidade. Normalmente, há um ponto de extremidade por usuário, como um computador ou dispositivo móvel. No entanto, se um usuário ingressar em uma reunião do Teams *ambos* em um computador e em um *dispositivo móvel*, dois pontos de extremidade serão associados a esse usuário.

- Os requisitos **mínimos** de largura de banda para chamadas de vídeo são resolução de até 240p, taxas de enquadramento de conteúdo de compartilhamento de tela adaptáveis de 1,875 a 7,5fps e vídeo modo conferência/galeria grande de até 540p de resolução.

- Os requisitos **mínimos** de largura de banda para chamadas de vídeo são resolução de até 1080p <sup>\*</sup>, taxas de enquadramento de conteúdo de compartilhamento de tela adaptáveis de 7,5 a 7,30fps e vídeo modo conferência/galeria grande de até 1080p de resolução <sup>\*</sup>.

- As diretrizes de **melhor desempenho** permitem um vídeo de fidelidade mais alta para reuniões com maiores participantes, ambientes de alta perda e maior conteúdo de movimento com taxas adaptáveis de enquadramento de conteúdo de compartilhamento de tela de 15 a 30fps.

<sup>\*</sup>Espere até 1080p de qualidade, mas dependendo das condições de rede, a resolução de vídeo e a qualidade serão otimizadas adequadamente.

## <a name="related-topics"></a>Tópicos Relacionados

[Princípios de conectividade de rede do Microsoft 365 e do Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Pontos de extremidade em todo o mundo: Skype for Business Online e Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Servidores proxy para o Teams](proxy-servers-for-skype-for-business-online.md)

[Mídia no Teams: por que as reuniões são simples](https://aka.ms/teams-media)

[Mídia no Teams: adoção profunda dos fluxos de mídia](https://aka.ms/teams-media-flows)

[Modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md)

[Como implantar o Teams](./deploy-overview.md)

[Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
