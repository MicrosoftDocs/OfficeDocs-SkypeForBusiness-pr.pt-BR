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
localization_priority: Priority
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
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420826"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a><span data-ttu-id="28fbc-103">Preparar a rede da organização para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28fbc-103">Prepare your organization's network for Microsoft Teams</span></span> 

## <a name="network-requirements"></a><span data-ttu-id="28fbc-104">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="28fbc-104">Network requirements</span></span>

<span data-ttu-id="28fbc-105">Se você já tiver[otimizado sua rede para o Microsoft 365 ou o Office 365](/Office365/Enterprise/assessing-network-connectivity), provavelmente já está pronto para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="28fbc-105">If you've already [optimized your network for Microsoft 365 or Office 365](/Office365/Enterprise/assessing-network-connectivity), you're probably ready for Microsoft Teams.</span></span> <span data-ttu-id="28fbc-106">De qualquer forma, e especialmente se você estiver implantando o Teams rapidamente como sua primeira carga de trabalho do Microsoft 365 ou do Office 365 para dar suporte **a trabalhadores remotos**, verifique o seguinte antes de iniciar a implantação do Teams:</span><span class="sxs-lookup"><span data-stu-id="28fbc-106">In any case - and especially if you're rolling out Teams quickly as your first Microsoft 365 or Office 365 workload to support **remote workers** - check the following before you begin your Teams rollout:</span></span>

1.  <span data-ttu-id="28fbc-107">Todos os seus locais têm acesso à Internet (para que possam se conectar ao Microsoft 365 ou Office 365)?</span><span class="sxs-lookup"><span data-stu-id="28fbc-107">Do all your locations have internet access (so they can connect to Microsoft 365 or Office 365)?</span></span> <span data-ttu-id="28fbc-108">Além do tráfego normal da web, verifique se você abriu as portas TCP e os endereços IP listados para o Teams nas [URLs do Office 365 e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="28fbc-108">In addition to normal web traffic, make sure you've opened the TCP ports and IP addresses listed for Teams in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="28fbc-109">Se for necessário federar com o Skype for Business, seja local ou online, você precisará configurar um registro DNS adicional.</span><span class="sxs-lookup"><span data-stu-id="28fbc-109">If you need to federate with Skype for Business, either on-premises or online, you will need to configure an additional DNS record.</span></span>
    >
    >|<span data-ttu-id="28fbc-110">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="28fbc-110">DNS record</span></span>  |<span data-ttu-id="28fbc-111">Serviço</span><span class="sxs-lookup"><span data-stu-id="28fbc-111">Service</span></span>  |<span data-ttu-id="28fbc-112">Protocolo</span><span class="sxs-lookup"><span data-stu-id="28fbc-112">Protocol</span></span>  |<span data-ttu-id="28fbc-113">Prioridade</span><span class="sxs-lookup"><span data-stu-id="28fbc-113">Priority</span></span>  |<span data-ttu-id="28fbc-114">Peso</span><span class="sxs-lookup"><span data-stu-id="28fbc-114">Weight</span></span>  |<span data-ttu-id="28fbc-115">Porta</span><span class="sxs-lookup"><span data-stu-id="28fbc-115">Port</span></span>  |<span data-ttu-id="28fbc-116">Destino</span><span class="sxs-lookup"><span data-stu-id="28fbc-116">Target</span></span>  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|<span data-ttu-id="28fbc-117">SRV</span><span class="sxs-lookup"><span data-stu-id="28fbc-117">SRV</span></span>     |<span data-ttu-id="28fbc-118">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="28fbc-118">sipfederationtls</span></span>     |<span data-ttu-id="28fbc-119">TCP</span><span class="sxs-lookup"><span data-stu-id="28fbc-119">TCP</span></span>     |<span data-ttu-id="28fbc-120">100</span><span class="sxs-lookup"><span data-stu-id="28fbc-120">100</span></span>     |<span data-ttu-id="28fbc-121">1</span><span class="sxs-lookup"><span data-stu-id="28fbc-121">1</span></span>     |<span data-ttu-id="28fbc-122">5061</span><span class="sxs-lookup"><span data-stu-id="28fbc-122">5061</span></span>     |<span data-ttu-id="28fbc-123">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="28fbc-123">sipfed.online.lync.com</span></span>     |
    
2.  <span data-ttu-id="28fbc-124">Você tem um domínio verificado para o Microsoft 365 ou para o Office 365 (por exemplo, contoso.com)?</span><span class="sxs-lookup"><span data-stu-id="28fbc-124">Do you have a verified domain for Microsoft 365 or Office 365 (for example, contoso.com)?</span></span>
    
    - <span data-ttu-id="28fbc-125">Se sua organização não tiver lançado o Microsoft 365 ou o Office 365, consulte [Começar](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="28fbc-125">If your organization hasn't rolled out Microsoft 365 or Office 365, see [Get started](/microsoft-365/admin/admin-overview/get-started-with-office-365).</span></span>
    - <span data-ttu-id="28fbc-126">Se sua organização ainda não adicionou ou configurou um domínio verificado para o Microsoft 365 ou para o Office 365, consulte as [Perguntas frequentes de Domínio](/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="28fbc-126">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see the [Domains FAQ](/microsoft-365/admin/setup/domains-faq).</span></span>

3.  <span data-ttu-id="28fbc-127">Sua organização implantou o Exchange Online e o SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="28fbc-127">Has your organization deployed Exchange Online and SharePoint Online?</span></span>
    
    - <span data-ttu-id="28fbc-128">Se a sua organização não tiver o Exchange Online, consulte [Saiba como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="28fbc-128">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](exchange-teams-interact.md).</span></span>
    - <span data-ttu-id="28fbc-129">Se a sua organização não tiver o SharePoint Online, consulte [Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="28fbc-129">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

<span data-ttu-id="28fbc-130">Depois de verificar se você atende a esses requisitos de rede, você pode estar pronto para [Implementar o Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="28fbc-130">Once you've verified that you meet these network requirements, you may be ready to [Roll out Teams](./deploy-overview.md).</span></span> <span data-ttu-id="28fbc-131">Se você tiver uma grande empresa multinacional ou se tiver algumas limitações de rede, continue a ler para saber como avaliar e otimizar sua rede para o Teams.</span><span class="sxs-lookup"><span data-stu-id="28fbc-131">If you're a large multinational enterprise, or if you know you've got some network limitations, read on to learn how to assess and optimize your network for Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="28fbc-132">**Para instituições de ensino**: se sua organização for uma instituição educacional e você usar um SIS (Sistema de Informações do Aluno), [implante o School Data Sync](/schooldatasync/) antes de implantar o Teams.</span><span class="sxs-lookup"><span data-stu-id="28fbc-132">**For educational institutions**: If your organization is an educational institution and you use a Student Information System (SIS), [deploy School Data Sync](/schooldatasync/) before you roll out Teams.</span></span>
>  
> <span data-ttu-id="28fbc-133">**Executando o Skype for Business Server** Se a sua organização estiver executando o Skype for Business Server (ou Lync Server) local, você deverá [Configurar o Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) para sincronizar seu diretório local com o Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="28fbc-133">**Running on-premises Skype for Business Server**: If your organization is running on-premises Skype for Business Server (or Lync Server), you must [configure Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) to synchronize your on-premises directory with Microsoft 365 or Office 365.</span></span>

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a><span data-ttu-id="28fbc-134">Prática recomendada: monitore sua rede usando o CQD e a análise de chamada</span><span class="sxs-lookup"><span data-stu-id="28fbc-134">Best practice: Monitor your network using CQD and call analytics</span></span> 

<span data-ttu-id="28fbc-135">Use o [CQD (Painel de Controle de Qualidade de Chamada)](turning-on-and-using-call-quality-dashboard.md) para obter informações sobre a qualidade das chamadas e das reuniões no Teams.</span><span class="sxs-lookup"><span data-stu-id="28fbc-135">Use the [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to gain insight into the quality of calls and meetings in Teams.</span></span> <span data-ttu-id="28fbc-136">O CQD pode ajudá-lo a otimizar a rede, acompanhando de perto a qualidade, a confiabilidade e a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="28fbc-136">CQD can help you optimize your network by keeping a close eye on quality, reliability, and the user experience.</span></span> <span data-ttu-id="28fbc-137">O CQD analisa a telemetria agregada de uma organização inteira onde os padrões gerais podem se tornar intermediários, o que permite identificar problemas e planejar a mediação.</span><span class="sxs-lookup"><span data-stu-id="28fbc-137">CQD looks at aggregate telemetry for an entire organization where overall patterns can become apparent, which lets you identify problems and plan remediation.</span></span> <span data-ttu-id="28fbc-138">Além disso, o CQD fornece relatórios de métricas abrangentes que fornecem informações sobre a qualidade geral, a confiabilidade e a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="28fbc-138">Additionally, CQD provides rich metrics reports that provide insight into overall quality, reliability, and user experience.</span></span> 

<span data-ttu-id="28fbc-139">Você usará o recurso de [análise de chamada](set-up-call-analytics.md) para investigar problemas de chamada e reunião de um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="28fbc-139">You'll use [call analytics](set-up-call-analytics.md) to investigate call and meeting problems for an individual user.</span></span>

## <a name="network-optimization"></a><span data-ttu-id="28fbc-140">Otimização de rede</span><span class="sxs-lookup"><span data-stu-id="28fbc-140">Network optimization</span></span>

<span data-ttu-id="28fbc-141">As tarefas a seguir são opcionais e não são necessárias para a implantação do Teams, especialmente se você for uma pequena empresa e já tiver implantado o Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="28fbc-141">The following tasks are optional and aren't required for rolling out Teams, especially if you're a small business and you've already rolled out Microsoft 365 or Office 365.</span></span> <span data-ttu-id="28fbc-142">Use essas orientações para otimizar o desempenho da rede e do Teams ou se tiver certeza de que tem algumas limitações de rede.</span><span class="sxs-lookup"><span data-stu-id="28fbc-142">Use this guidance to optimize your network and Teams performance or if you know you've got some network limitations.</span></span>

<span data-ttu-id="28fbc-143">Talvez você queira fazer uma otimização de rede adicional se:</span><span class="sxs-lookup"><span data-stu-id="28fbc-143">You might want to do additional network optimization if:</span></span>

  - <span data-ttu-id="28fbc-144">O Teams estiver muito lento (talvez você não tenha largura de banda insuficiente)</span><span class="sxs-lookup"><span data-stu-id="28fbc-144">Teams runs slowly (maybe you have insufficient bandwidth)</span></span>
  - <span data-ttu-id="28fbc-145">As chamadas continuam caindo (pode ser devido a bloqueadores de firewall ou proxy)</span><span class="sxs-lookup"><span data-stu-id="28fbc-145">Calls keep dropping (might be due to firewall or proxy blockers)</span></span>
  - <span data-ttu-id="28fbc-146">As chamadas estão estáticas e cortadas, ou as vozes soam como robôs (pode ser instabilidade ou perda de pacotes)</span><span class="sxs-lookup"><span data-stu-id="28fbc-146">Calls have static and cut out, or voices sound like robots (could be jitter or packet loss)</span></span>

<span data-ttu-id="28fbc-147">Para uma discussão aprofundada sobre otimização de rede, incluindo orientações sobre como identificar e corrigir deficiências de rede, leia [Princípios de Conectividade de Rede do Microsoft 365 e do Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span><span class="sxs-lookup"><span data-stu-id="28fbc-147">For an in-depth discussion of network optimization, including guidance for identifying and fixing network impairments, read [Microsoft 365 and Office 365 Network Connectivity Principles](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="28fbc-148">Tarefa de otimização de rede</span><span class="sxs-lookup"><span data-stu-id="28fbc-148">Network optimization task</span></span></th>
<th><span data-ttu-id="28fbc-149">Detalhes</span><span class="sxs-lookup"><span data-stu-id="28fbc-149">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="28fbc-150">Planejador de rede</span><span class="sxs-lookup"><span data-stu-id="28fbc-150">Network planner</span></span></td>
<td><p><span data-ttu-id="28fbc-151">Para ajudar a avaliação de sua rede, incluindo cálculos de largura de banda e requisitos de rede nos locais físicos da organização, confira a ferramenta <a href="/microsoftteams/network-planner">Planejador de rede</a>, no <a href="https://admin.teams.microsoft.com">centro de administração do Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="28fbc-151">For help assessing your network, including bandwidth calculations and network requirements across your org's physical locations, check out the <a href="/microsoftteams/network-planner">Network Planner</a> tool, in the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="28fbc-152">Quando você fornece detalhes de sua rede e uso do Teams, o Planejador de Rede calcula seus requisitos de rede para implantar o Teams e o cloud voice nos locais físicos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="28fbc-152">When you provide your network details and Teams usage, the Network Planner calculates your network requirements for deploying Teams and cloud voice across your organization's physical locations.</span></span></p>
<p><span data-ttu-id="28fbc-153">Para ver um cenário de exemplo, confira <a href="/microsoftteams/tutorial-network-planner-example">Como usar o Planejador de rede, exemplo de cenário</a>.</span><span class="sxs-lookup"><span data-stu-id="28fbc-153">For an example scenario, see <a href="/microsoftteams/tutorial-network-planner-example">Using Network Planner - example scenario</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28fbc-154">Consultor para o Teams</span><span class="sxs-lookup"><span data-stu-id="28fbc-154">Advisor for Teams</span></span></td>
<td><span data-ttu-id="28fbc-155"><a href="/microsoftteams/use-advisor-teams-roll-out">O Assistente do Teams</a> faz parte do<a href="https://admin.teams.microsoft.com"> centro de administração do Teams</a>.</span><span class="sxs-lookup"><span data-stu-id="28fbc-155"><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor for Teams</a> is part of the <a href="https://admin.teams.microsoft.com">Teams admin center</a>.</span></span> <span data-ttu-id="28fbc-156">Ele avalia o ambiente do seu Microsoft 365 ou Office 365 e identifica as configurações mais comuns que talvez sejam necessárias atualizar ou modificar antes de poder implantar o Teams com êxito.</span><span class="sxs-lookup"><span data-stu-id="28fbc-156">It assesses your Microsoft 365 or Office 365 environment and identifies the most common configurations that you may need to update or modify before you can successfully roll out Teams.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28fbc-157">Resolução do nome externo</span><span class="sxs-lookup"><span data-stu-id="28fbc-157">External Name Resolution</span></span></td>
<td><span data-ttu-id="28fbc-158">Certifique-se de que todos os computadores que executam o cliente Teams possam resolver consultas DNS externas para descobrir os serviços fornecidos pelo Microsoft 365 ou pelo Office 365 e que seus firewalls não estejam impedindo o acesso.</span><span class="sxs-lookup"><span data-stu-id="28fbc-158">Be sure that all computers running the Teams client can resolve external DNS queries to discover the services provided by Microsoft 365 or Office 365 and that your firewalls are not preventing access.</span></span> <span data-ttu-id="28fbc-159">Para saber mais sobre como configurar portas de firewall, vá para<a href="/microsoftteams/office-365-urls-ip-address-ranges">URLs e intervalos IP do Microsoft 365 e do Office 365</a>.</span><span class="sxs-lookup"><span data-stu-id="28fbc-159">For information about configuring firewall ports, go to <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 and Office 365 URLs and IP ranges</a>.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28fbc-160">Manter a persistência da sessão</span><span class="sxs-lookup"><span data-stu-id="28fbc-160">Maintain session persistence</span></span></td>
<td><span data-ttu-id="28fbc-161">Certifique-se de que seu firewall não altere os endereços ou portas de conversão de endereços de rede (NAT) mapeados para UDP.</span><span class="sxs-lookup"><span data-stu-id="28fbc-161">Make sure your firewall doesn't change the mapped Network Address Translation (NAT) addresses or ports for UDP.</span></span></td>
</tr><tr class="odd">
<td><span data-ttu-id="28fbc-162">Validar o tamanho do pool de NAT</span><span class="sxs-lookup"><span data-stu-id="28fbc-162">Validate NAT pool size</span></span></td>
<td><span data-ttu-id="28fbc-163">Valide o tamanho de pool de conversão de endereços de rede (NAT) necessário para conectividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="28fbc-163">Validate the network address translation (NAT) pool size required for user connectivity.</span></span> <span data-ttu-id="28fbc-164">Quando vários usuários e dispositivos acessam o Microsoft 365 ou o Office 365 usando a <a href="/office365/enterprise/nat-support-with-office-365">Conversão de Endereços de Rede (NAT) ou Conversão de Endereços de Porta (PAT)</a>, você precisa assegurar que os dispositivos ocultos em cada um dos endereços IP publicamente roteáveis não excedam o número suportado.</span><span class="sxs-lookup"><span data-stu-id="28fbc-164">When multiple users and devices access Microsoft 365 or Office 365 using <a href="/office365/enterprise/nat-support-with-office-365">Network Address Translation (NAT) or Port Address Translation (PAT)</a>, you need to ensure that the devices hidden behind each publicly routable IP address do not exceed the supported number.</span></span> <span data-ttu-id="28fbc-165">Certifique-se de que os endereços IP públicos adequados sejam atribuídos aos pools de NAT para prevenir o esgotamento de portas.</span><span class="sxs-lookup"><span data-stu-id="28fbc-165">Ensure that adequate public IP addresses are assigned to the NAT pools to prevent port exhaustion.</span></span> <span data-ttu-id="28fbc-166">A exaustão da porta contribuirá para que usuários e dispositivos internos não consigam se conectar ao serviço Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="28fbc-166">Port exhaustion will contribute to internal users and devices being unable to connect to the Microsoft 365 or Office 365 service.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28fbc-167">Roteamento para data centers da Microsoft</span><span class="sxs-lookup"><span data-stu-id="28fbc-167">Routing to Microsoft data centers</span></span></td>
<td><span data-ttu-id="28fbc-168"><a href="/office365/enterprise/client-connectivity">Implemente o roteamento mais eficiente para data centers da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="28fbc-168"><a href="/office365/enterprise/client-connectivity">Implement the most efficient routing to Microsoft data centers</a>.</span></span> <span data-ttu-id="28fbc-169">Identifique locais que podem usar pontos de saída locais ou regionais para se conectar à rede da Microsoft da forma mais eficiente possível.</span><span class="sxs-lookup"><span data-stu-id="28fbc-169">Identify locations that can use local or regional egress points to connect to the Microsoft network as efficiently as possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28fbc-170">Detecção de invasão e orientação de prevenção</span><span class="sxs-lookup"><span data-stu-id="28fbc-170">Intrusion Detection and Prevention Guidance</span></span></td>
<td><span data-ttu-id="28fbc-171">Se seu ambiente tiver uma <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Detecção de Invasão</a> ou um Sistema de Prevenção (IDS/IPS) implantado para uma camada extra de segurança para conexões de saída, certifique-se de permitir todas as URLs do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="28fbc-171">If your environment has an <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Intrusion Detection</a> or Prevention System (IDS/IPS) deployed for an extra layer of security for outbound connections, be sure to allow all Microsoft 365 or Office 365 URLs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28fbc-172">Configurar o VPN com túnel dividido</span><span class="sxs-lookup"><span data-stu-id="28fbc-172">Configure split-tunnel VPN</span></span></td>
<td><p><span data-ttu-id="28fbc-173">Recomendamos que você forneça um caminho alternativo para o tráfego do Teams que ignore a VPN (rede virtual privada), normalmente conhecida como <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN split-tunnel</a>.</span><span class="sxs-lookup"><span data-stu-id="28fbc-173">We recommend that you provide an alternate path for Teams traffic that bypasses the virtual private network (VPN), commonly known as <a href="/windows/security/identity-protection/vpn/vpn-routing">split-tunnel VPN</a>.</span></span> <span data-ttu-id="28fbc-174">Split-tunneling significa que o tráfego para o Microsoft 365 ou o Office 365 não vai para a VPN, e sim diretamente para o Microsoft 365 ou o Office 365.</span><span class="sxs-lookup"><span data-stu-id="28fbc-174">Split tunneling means that traffic for Microsoft 365 or Office 365 doesn't go through the VPN but instead goes directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="28fbc-175">Ignorar sua VPN terá um impacto positivo na qualidade do Teams e reduzirá a carga dos dispositivos VPN e da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="28fbc-175">Bypassing your VPN will have a positive impact on Teams quality, and it reduces load from the VPN devices and the organization's network.</span></span> <span data-ttu-id="28fbc-176">Para implementar uma VPN split-tunnel por meio de um plano VPN, trabalhe com seu fornecedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="28fbc-176">To implement a split-tunnel VPN, work with your VPN vendor.</span></span></p>
<p><span data-ttu-id="28fbc-177">Outros motivos pelos quais recomendamos ignorar a VPN:</span><span class="sxs-lookup"><span data-stu-id="28fbc-177">Other reasons why we recommend bypassing the VPN:</span></span>
<ul>
<li><p><span data-ttu-id="28fbc-178">As VPNs em geral não são projetadas ou configuradas para dar suporte a mídia em tempo real.</span><span class="sxs-lookup"><span data-stu-id="28fbc-178">VPNs are typically not designed or configured to support real-time media.</span></span></p></li> 
<li><p><span data-ttu-id="28fbc-179">Algumas VPNs também podem não dar suporte a UDP (que é necessária para o Teams).</span><span class="sxs-lookup"><span data-stu-id="28fbc-179">Some VPNs might also not support UDP (which is required for Teams).</span></span></p></li> 
<li><p><span data-ttu-id="28fbc-180">As VPNs também introduzem uma camada extra de criptografia sobre o tráfego de mídia que já está criptografado.</span><span class="sxs-lookup"><span data-stu-id="28fbc-180">VPNs also introduce an extra layer of encryption on top of media traffic that's already encrypted.</span></span></p></li> 
<li><p><span data-ttu-id="28fbc-181">A conectividade com o Teams pode não ser eficiente devido ao tráfego excessivo por meio de um dispositivo VPN.</span><span class="sxs-lookup"><span data-stu-id="28fbc-181">Connectivity to Teams might not be efficient due to hair-pinning traffic through a VPN device.</span></span></p></li></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="28fbc-182">Implementar a QoS</span><span class="sxs-lookup"><span data-stu-id="28fbc-182">Implement QoS</span></span></td>
<td><span data-ttu-id="28fbc-183"><a href="/microsoftteams/qos-in-teams">Use a tecnologia QoS (Qualidade do Serviço)</a> para configurar a priorização de pacotes.</span><span class="sxs-lookup"><span data-stu-id="28fbc-183"><a href="/microsoftteams/qos-in-teams">Use Quality of Service (QoS)</a> to configure packet prioritization.</span></span> <span data-ttu-id="28fbc-184">Isso melhorará a qualidade da chamada no Teams e o ajudará a monitorar e solucionar problemas de qualidade da chamada.</span><span class="sxs-lookup"><span data-stu-id="28fbc-184">This will improve call quality in Teams and help you monitor and troubleshoot call quality.</span></span> <span data-ttu-id="28fbc-185">O QoS deve ser implementado em todos os segmentos de uma rede gerenciada.</span><span class="sxs-lookup"><span data-stu-id="28fbc-185">QoS should be implemented on all segments of a managed network.</span></span> <span data-ttu-id="28fbc-186">Mesmo quando uma rede foi adequadamente provisionada para largura de banda, o QoS fornece redução de riscos em caso de eventos de rede inesperados.</span><span class="sxs-lookup"><span data-stu-id="28fbc-186">Even when a network has been adequately provisioned for bandwidth, QoS provides risk mitigation in the event of unanticipated network events.</span></span> <span data-ttu-id="28fbc-187">Com o QoS, o tráfego de voz é priorizado para que esses eventos não inesperados não afetem a qualidade negativamente.</span><span class="sxs-lookup"><span data-stu-id="28fbc-187">With QoS, voice traffic is prioritized so that these unanticipated events don't negatively affect quality.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="28fbc-188">Otimizar o WiFi</span><span class="sxs-lookup"><span data-stu-id="28fbc-188">Optimize WiFi</span></span></td>
<td><p><span data-ttu-id="28fbc-189">Como a VPN, as redes WiFi não são necessariamente projetadas ou configuradas para oferecer suporte à mídia em tempo real.</span><span class="sxs-lookup"><span data-stu-id="28fbc-189">Similar to VPN, WiFi networks aren't necessarily designed or configured to support real-time media.</span></span> <span data-ttu-id="28fbc-190">Planejar ou otimizar uma rede WiFi para oferecer suporte ao Teams é uma consideração importante para uma implantação de alta qualidade.</span><span class="sxs-lookup"><span data-stu-id="28fbc-190">Planning for, or optimizing, a WiFi network to support Teams is an important consideration for a high-quality deployment.</span></span> <span data-ttu-id="28fbc-191">Considere estes fatores:</span><span class="sxs-lookup"><span data-stu-id="28fbc-191">Consider these factors:</span></span></p>
<ul>
<li><p><span data-ttu-id="28fbc-192">Implemente o QoS ou WiFi Multimídia (WMM) para garantir que o tráfego de mídia seja priorizado adequadamente em suas redes WiFi.</span><span class="sxs-lookup"><span data-stu-id="28fbc-192">Implement QoS or WiFi Multimedia (WMM) to ensure that media traffic is getting prioritized appropriately over your WiFi networks.</span></span></p></li>
<li><p><span data-ttu-id="28fbc-193">Planeje e otimize as faixas de WiFi e o posicionamento do ponto de acesso.</span><span class="sxs-lookup"><span data-stu-id="28fbc-193">Plan and optimize the WiFi bands and access point placement.</span></span> <span data-ttu-id="28fbc-194">O intervalo de 2,4 GHz pode proporcionar uma experiência adequada dependendo do posicionamento do ponto de acesso, mas os pontos de acesso costumam ser afetados por outros dispositivos do consumidor que operam nesse intervalo.</span><span class="sxs-lookup"><span data-stu-id="28fbc-194">The 2.4 GHz range might provide an adequate experience depending on access point placement, but access points are often affected by other consumer devices that operate in that range.</span></span> <span data-ttu-id="28fbc-195">A frequência de 5 GHz é mais adequada para mídia em tempo real porque é mais densa, mas requer mais pontos de acesso para proporcionar cobertura suficiente.</span><span class="sxs-lookup"><span data-stu-id="28fbc-195">The 5 GHz range is better suited to real-time media due to its dense range, but it requires more access points to get sufficient coverage.</span></span> <span data-ttu-id="28fbc-196">Os pontos de extremidade também precisam dar suporte àquela frequência e ser configurados para utilizar essas bandas corretamente.</span><span class="sxs-lookup"><span data-stu-id="28fbc-196">Endpoints also need to support that range and be configured to leverage those bands accordingly.</span></span></p></li>
<li><p><span data-ttu-id="28fbc-197">Se você estiver usando redes WiFi de duas faixas, considere implementar o suporte da faixa.</span><span class="sxs-lookup"><span data-stu-id="28fbc-197">If you're using dual-band WiFi networks, consider implementing band steering.</span></span> <span data-ttu-id="28fbc-198"><em>A direção de banda</em> é uma técnica implementada por fornecedores de Wi-Fi para influenciar os clientes de banda dupla a usar o intervalo de 5 GHz.</span><span class="sxs-lookup"><span data-stu-id="28fbc-198"><em>Band steering</em> is a technique implemented by WiFi vendors to influence dual-band clients to use the 5 GHz range.</span></span></p></li>
<li><p><span data-ttu-id="28fbc-199">Quando pontos de acesso do mesmo canal estão muito próximos, eles podem causar sobreposição de sinal e competir involuntariamente, resultando em uma experiência não satisfatória para o usuário.</span><span class="sxs-lookup"><span data-stu-id="28fbc-199">When access points of the same channel are too close together, they can cause signal overlap and unintentionally compete, resulting in a bad experience for the user.</span></span> <span data-ttu-id="28fbc-200">Certifique-se de que os pontos de acesso próximos um do outro estejam em canais que não se sobreponham.</span><span class="sxs-lookup"><span data-stu-id="28fbc-200">Ensure that access points that are next to each other are on channels that don't overlap.</span></span></p></li>
</ul>
<p><span data-ttu-id="28fbc-201">Cada fornecedor de redes sem fio tem suas próprias recomendações de implantação da solução sem fio.</span><span class="sxs-lookup"><span data-stu-id="28fbc-201">Each wireless vendor has its own recommendations for deploying its wireless solution.</span></span> <span data-ttu-id="28fbc-202">Consulte o fornecedor de wifi para obter orientações específicas.</span><span class="sxs-lookup"><span data-stu-id="28fbc-202">Consult your WiFi vendor for specific guidance.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a><span data-ttu-id="28fbc-203">Requisitos de largura de banda</span><span class="sxs-lookup"><span data-stu-id="28fbc-203">Bandwidth requirements</span></span>

<span data-ttu-id="28fbc-204">O Teams foi projetado para dar a você a melhor experiência de compartilhamento de áudio, vídeo e conteúdo, independentemente das condições da sua rede.</span><span class="sxs-lookup"><span data-stu-id="28fbc-204">Teams is designed to give the best audio, video, and content sharing experience regardless of your network conditions.</span></span> <span data-ttu-id="28fbc-205">Dessa forma, quando a largura de banda não é suficiente, o Teams prioriza a qualidade de áudio em relação à qualidade do vídeo.</span><span class="sxs-lookup"><span data-stu-id="28fbc-205">That said, when bandwidth is insufficient, Teams prioritizes audio quality over video quality.</span></span>

<span data-ttu-id="28fbc-206">Quando a largura de banda não é limitada, o Teams otimiza a qualidade da mídia, incluindo áudio de alta fidelidade, resolução de vídeo de até 1080p e até 30fps (quadros por segundo) para vídeo e conteúdo.</span><span class="sxs-lookup"><span data-stu-id="28fbc-206">Where bandwidth isn't limited, Teams optimizes media quality, including high-fidelity audio, up to 1080p video resolution, and up to 30fps (frames per second) for video and content.</span></span>

<span data-ttu-id="28fbc-207">Essa tabela descreve como o Teams usa a largura de banda.</span><span class="sxs-lookup"><span data-stu-id="28fbc-207">This table describes how Teams uses bandwidth.</span></span> <span data-ttu-id="28fbc-208">O Teams é sempre prudente na utilização de largura de banda e pode oferecer qualidade de vídeo HD em 1,5Mbps.</span><span class="sxs-lookup"><span data-stu-id="28fbc-208">Teams is always conservative on bandwidth utilization and can deliver HD video quality in under 1.5Mbps.</span></span> <span data-ttu-id="28fbc-209">O consumo real de largura de banda em cada chamada de áudio/vídeo ou reunião varia com base em vários fatores, como layout de vídeo, resolução de vídeo e quadros de vídeo por segundo.</span><span class="sxs-lookup"><span data-stu-id="28fbc-209">The actual bandwidth consumption in each audio/video call or meeting will vary based on several factors, such as video layout, video resolution, and video frames per second.</span></span> <span data-ttu-id="28fbc-210">Quando houver mais largura de banda, a qualidade e o uso aumentarão, oferecendo a melhor experiência possível.</span><span class="sxs-lookup"><span data-stu-id="28fbc-210">When more bandwidth is available, quality and usage will increase to deliver the best experience.</span></span>

:::row:::
   :::column span="":::
      <span data-ttu-id="28fbc-211">**Modalidade**</span><span class="sxs-lookup"><span data-stu-id="28fbc-211">**Modality**</span></span>
   :::column-end:::
   :::column span="3":::
      <span data-ttu-id="28fbc-212">**Requisitos de largura de banda (KB/s de taxa de bits para cima/para baixo)**</span><span class="sxs-lookup"><span data-stu-id="28fbc-212">**Bandwidth requirements (bitrate KB/s up/down)**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="28fbc-213">**Mínimo**</span><span class="sxs-lookup"><span data-stu-id="28fbc-213">**Minimum**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="28fbc-214">**Recomendado**</span><span class="sxs-lookup"><span data-stu-id="28fbc-214">**Recommended**</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="28fbc-215">**Melhor desempenho**</span><span class="sxs-lookup"><span data-stu-id="28fbc-215">**Best performance**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="28fbc-216">**Áudio**</span><span class="sxs-lookup"><span data-stu-id="28fbc-216">**Audio**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-217">Individual</span><span class="sxs-lookup"><span data-stu-id="28fbc-217">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-218">10/10</span><span class="sxs-lookup"><span data-stu-id="28fbc-218">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-219">58/58</span><span class="sxs-lookup"><span data-stu-id="28fbc-219">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-220">76/76</span><span class="sxs-lookup"><span data-stu-id="28fbc-220">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-221">Reuniões</span><span class="sxs-lookup"><span data-stu-id="28fbc-221">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-222">10/10</span><span class="sxs-lookup"><span data-stu-id="28fbc-222">10/10</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-223">58/58</span><span class="sxs-lookup"><span data-stu-id="28fbc-223">58/58</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-224">76/76</span><span class="sxs-lookup"><span data-stu-id="28fbc-224">76/76</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="28fbc-225">**Vídeo**</span><span class="sxs-lookup"><span data-stu-id="28fbc-225">**Video**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-226">Individual</span><span class="sxs-lookup"><span data-stu-id="28fbc-226">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-227">150/150</span><span class="sxs-lookup"><span data-stu-id="28fbc-227">150/150</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-228">1.500/1.500</span><span class="sxs-lookup"><span data-stu-id="28fbc-228">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-229">4.000/4.000</span><span class="sxs-lookup"><span data-stu-id="28fbc-229">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-230">Reuniões</span><span class="sxs-lookup"><span data-stu-id="28fbc-230">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-231">150/200</span><span class="sxs-lookup"><span data-stu-id="28fbc-231">150/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-232">2.500/4.000</span><span class="sxs-lookup"><span data-stu-id="28fbc-232">2,500/4,000</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-233">4.000/4.000</span><span class="sxs-lookup"><span data-stu-id="28fbc-233">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="28fbc-234">**Compartilhamento de tela**</span><span class="sxs-lookup"><span data-stu-id="28fbc-234">**Screen sharing**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-235">Individual</span><span class="sxs-lookup"><span data-stu-id="28fbc-235">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-236">200/200</span><span class="sxs-lookup"><span data-stu-id="28fbc-236">200/200</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-237">1.500/1.500</span><span class="sxs-lookup"><span data-stu-id="28fbc-237">1,500/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-238">4.000/4.000</span><span class="sxs-lookup"><span data-stu-id="28fbc-238">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-239">Reuniões</span><span class="sxs-lookup"><span data-stu-id="28fbc-239">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-240">250/250</span><span class="sxs-lookup"><span data-stu-id="28fbc-240">250/250</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-241">2.500/2.500</span><span class="sxs-lookup"><span data-stu-id="28fbc-241">2,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-242">4.000/4.000</span><span class="sxs-lookup"><span data-stu-id="28fbc-242">4,000/4,000</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      <span data-ttu-id="28fbc-243">**Modo conferência**</span><span class="sxs-lookup"><span data-stu-id="28fbc-243">**Together Mode**</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-244">Individual</span><span class="sxs-lookup"><span data-stu-id="28fbc-244">One-to-one</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-245">Não disponível</span><span class="sxs-lookup"><span data-stu-id="28fbc-245">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-246">Não disponível</span><span class="sxs-lookup"><span data-stu-id="28fbc-246">N/A</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-247">Não disponível</span><span class="sxs-lookup"><span data-stu-id="28fbc-247">N/A</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        <span data-ttu-id="28fbc-248">Reuniões</span><span class="sxs-lookup"><span data-stu-id="28fbc-248">Meetings</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-249">1.000/1.500</span><span class="sxs-lookup"><span data-stu-id="28fbc-249">1,000/1,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-250">1.500/2.500</span><span class="sxs-lookup"><span data-stu-id="28fbc-250">1,500/2,500</span></span>
   :::column-end:::
   :::column span="":::
        <span data-ttu-id="28fbc-251">2.500/4.000</span><span class="sxs-lookup"><span data-stu-id="28fbc-251">2,500/4,000</span></span>
   :::column-end:::
:::row-end:::

<span data-ttu-id="28fbc-252">Os requisitos de largura de banda **Mínimo**, **Recomendado** e **Melhor desempenho** são baseados no uso por ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="28fbc-252">**Minimum**, **Recommended**, and **Best performance** bandwidth requirements are based on per-endpoint usage.</span></span> <span data-ttu-id="28fbc-253">Normalmente, há um ponto de extremidade por usuário, como um computador ou dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="28fbc-253">Typically, there's one endpoint per user, such as a computer or mobile device.</span></span> <span data-ttu-id="28fbc-254">No entanto, se um usuário ingressar em uma reunião do Teams *ambos* em um computador e em um *dispositivo móvel*, dois pontos de extremidade serão associados a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="28fbc-254">However, if a user joins a Teams meeting on *both* a computer *and* a mobile device, two endpoints are associated with that user.</span></span>

- <span data-ttu-id="28fbc-255">Os requisitos **mínimos** de largura de banda para chamadas de vídeo são resolução de até 240p, taxas de enquadramento de conteúdo de compartilhamento de tela adaptáveis de 1,875 a 7,5fps e vídeo modo conferência/galeria grande de até 540p de resolução.</span><span class="sxs-lookup"><span data-stu-id="28fbc-255">**Minimum** Bandwidth requirements for video calls are up to 240p resolution, screen sharing content frame rates adaptive 1.875 to 7.5fps, and Together Mode/Large Gallery video up to 540p resolution.</span></span>  

- <span data-ttu-id="28fbc-256">Os requisitos **mínimos** de largura de banda para chamadas de vídeo são resolução de até 1080p<sup>\*</sup>, taxas de enquadramento de conteúdo de compartilhamento de tela adaptáveis de 7,5 a 7,30fps e vídeo modo conferência/galeria grande de até 1080p de resolução<sup>\*</sup>.</span><span class="sxs-lookup"><span data-stu-id="28fbc-256">**Recommended** Bandwidth requirements for video calls are up to 1080p resolution<sup>\*</sup>, screen sharing content frame rates adaptive 7.5 to 30fps, and Together Mode/Large Gallery video up to 1080p resolution<sup>\*</sup>.</span></span>  

- <span data-ttu-id="28fbc-257">As diretrizes de **melhor desempenho** permitem um vídeo de fidelidade mais alta para reuniões com maiores participantes, ambientes de alta perda e maior conteúdo de movimento com taxas adaptáveis de enquadramento de conteúdo de compartilhamento de tela de 15 a 30fps.</span><span class="sxs-lookup"><span data-stu-id="28fbc-257">**Best Performance** Guidance allows higher fidelity video for larger attendee meetings, high loss environments, and higher motion content with screen sharing content frame rates adaptive 15 to 30fps.</span></span>

<span data-ttu-id="28fbc-258"><sup>\*</sup>Espere até 1080p de qualidade, mas dependendo das condições de rede, a resolução de vídeo e a qualidade serão otimizadas adequadamente.</span><span class="sxs-lookup"><span data-stu-id="28fbc-258"><sup>\*</sup>Expect up to 1080p quality but depending on your network conditions, video resolution and quality will be optimized accordingly.</span></span>  

## <a name="related-topics"></a><span data-ttu-id="28fbc-259">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="28fbc-259">Related Topics</span></span>

[<span data-ttu-id="28fbc-260">Princípios de conectividade de rede do Microsoft 365 e do Office 365</span><span class="sxs-lookup"><span data-stu-id="28fbc-260">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="28fbc-261">Pontos de extremidade em todo o mundo: Skype for Business Online e Teams</span><span class="sxs-lookup"><span data-stu-id="28fbc-261">Worldwide endpoints: Skype for Business Online and Teams</span></span>](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[<span data-ttu-id="28fbc-262">Servidores proxy para o Teams</span><span class="sxs-lookup"><span data-stu-id="28fbc-262">Proxy servers for Teams</span></span>](proxy-servers-for-skype-for-business-online.md)

[<span data-ttu-id="28fbc-263">Mídia no Teams: por que as reuniões são simples</span><span class="sxs-lookup"><span data-stu-id="28fbc-263">Media in Teams: Why meetings are simple</span></span>](https://aka.ms/teams-media)

[<span data-ttu-id="28fbc-264">Mídia no Teams: adoção profunda dos fluxos de mídia</span><span class="sxs-lookup"><span data-stu-id="28fbc-264">Media in Teams: Deep dive into media flows</span></span>](https://aka.ms/teams-media-flows)

[<span data-ttu-id="28fbc-265">Modelos de identidade e autenticação no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28fbc-265">Identity models and authentication in Teams</span></span>](identify-models-authentication.md)

[<span data-ttu-id="28fbc-266">Como implantar o Teams</span><span class="sxs-lookup"><span data-stu-id="28fbc-266">How to roll out Teams</span></span>](./deploy-overview.md)

[<span data-ttu-id="28fbc-267">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="28fbc-267">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
