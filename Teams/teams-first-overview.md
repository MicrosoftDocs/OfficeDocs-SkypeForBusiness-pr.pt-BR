---
title: Roll out Microsoft Teams First
author: LaszloSomi
ms.author: lsomi
manager: swerth
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: lsomi
localization_priority: Normal
search.appverid: MET150
description: Use essas diretrizes para lançar Microsoft Teams como sua primeira carga de trabalho Microsoft 365 ou Office 365 primeira.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 81ecf9a0f963a1be577149c585424c140df2abd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119350"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="a8290-103">Roll out Microsoft Teams First</span><span class="sxs-lookup"><span data-stu-id="a8290-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="a8290-104">Microsoft Teams pode ajudar seus funcionários a permanecer conectados e colaborar uns com os outros, especialmente no momento atual sem precedentes em que o trabalho remoto é uma realidade de funcionários em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="a8290-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="a8290-105">Poder conversar, fazer reuniões em vídeo e colaborar em Office documentos dentro Teams pode ajudar as empresas a se manter produtivas.</span><span class="sxs-lookup"><span data-stu-id="a8290-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="a8290-106">Se você é uma pequena empresa, uma organização sem fins lucrativos ou uma grande, você pode começar com o Teams como a primeira carga de trabalho no Microsoft 365 ou no pacote Office 365 antes de implantar qualquer outro Aplicativo do Office ou serviço.</span><span class="sxs-lookup"><span data-stu-id="a8290-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="a8290-107">Este artigo detalha as considerações que você deve fazer com a abordagem "Teams Primeiro".</span><span class="sxs-lookup"><span data-stu-id="a8290-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8290-108">Embora Teams possa ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação Teams deve fazer parte da estratégia geral de implantação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="a8290-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="a8290-109">Se você já tiver lançado outros serviços Microsoft 365 ou Office 365 e Teams for sua próxima carga de trabalho a ser rolada (em vez da primeira), comece com [Como](./deploy-overview.md)lançar Teams .</span><span class="sxs-lookup"><span data-stu-id="a8290-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="a8290-110">Iniciar aqui</span><span class="sxs-lookup"><span data-stu-id="a8290-110">Start here</span></span>

<span data-ttu-id="a8290-111">Para começar a Teams primeira implantação, você precisará atender, no mínimo, a alguns pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="a8290-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="a8290-112">A lista a seguir mostrará o que você deve ter para sua organização antes que Teams possa ser habilitado:</span><span class="sxs-lookup"><span data-stu-id="a8290-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="a8290-113">Uma Microsoft 365 ou Office 365 configurada com seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="a8290-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="a8290-114">Azure Active Directory conectividade (conexão AAD) ou solução de sincronização de identidade de nuvem semelhante – com todos os atributos necessários sincronizados com seu locatário</span><span class="sxs-lookup"><span data-stu-id="a8290-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="a8290-115">Para entender os atributos sincronizados com a sincronização do AAD, leia [Azure AD Conexão sincronização:](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized) Atributos sincronizados com Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a8290-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="a8290-116">Licenças de usuário apropriadas atribuídas Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="a8290-117">Para entender Teams licenciamento, leia [Microsoft Teams descrição do serviço.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="a8290-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="a8290-118">Rede da organização preparada para Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="a8290-119">Para entender a preparação da rede, leia [Prepare your organization's network for Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="a8290-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="a8290-120">Permitir acesso à rede Exchange, Sharepoint e OneDrive for Business em Microsoft 365 ou Office 365: [Office 365 URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="a8290-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="a8290-121">Os locatários criados após 1º de setembro de 2019 são provisionados Teams modo Somente.</span><span class="sxs-lookup"><span data-stu-id="a8290-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="a8290-122">Se você tiver Skype for Business Server implantado e seu locatário tiver sido provisionado APÓS 1º de setembro de 2019, entre em contato com o suporte para habilitar recursos de coexistência para Teams.</span><span class="sxs-lookup"><span data-stu-id="a8290-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="a8290-123">Certifique-se de que sua "política de atualização de toda a organização" seja definida como "modo <span class="underline">ilha"</span> antes de atribuir Teams licenças a um usuário.</span><span class="sxs-lookup"><span data-stu-id="a8290-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="a8290-124">Pontos de partida da migração</span><span class="sxs-lookup"><span data-stu-id="a8290-124">Migration Starting points</span></span>

<span data-ttu-id="a8290-125">Sua jornada para Microsoft 365 ou Office 365 recursos disponíveis no Teams, dependendo do ponto de partida e da existência do servidor local Skype for Business ou Lync.</span><span class="sxs-lookup"><span data-stu-id="a8290-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="a8290-126">As seções a seguir detalham recursos básicos e opções de configuração, além dos pré-requisitos acima.</span><span class="sxs-lookup"><span data-stu-id="a8290-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="a8290-127">Nós quebramos os cenários de ponto de partida para os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="a8290-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="a8290-128">**Configuração Teams locatário**: Os modos de locatário e usuário são usados para controlar o comportamento do destinatário.</span><span class="sxs-lookup"><span data-stu-id="a8290-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="a8290-129">Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização.</span><span class="sxs-lookup"><span data-stu-id="a8290-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="a8290-130">Para saber mais, leia [Coexistência com Skype for Business](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="a8290-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="a8290-131">**Chat / Comunicação externa no Teams:** Os serviços de chat referem-se a conversas de chat ponto a ponto ou grupo dentro e organização ou externamente à organização.</span><span class="sxs-lookup"><span data-stu-id="a8290-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="a8290-132">A comunicação externa também é chamada de federação no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a8290-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="a8290-133">Criar e exibir reuniões em **Teams:** um usuário sempre pode criar reuniões online por meio do Outlook Teams e o discagem PSTN estará disponível em todos os cenários depois que o usuário for licenciado.</span><span class="sxs-lookup"><span data-stu-id="a8290-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="a8290-134">Teams e Skype for Business de calendário na caixa de correio de Exchange do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8290-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="a8290-135">No local, Exchange servidor deve ser Exchange Server 2016 CU3 ou superior para que o cliente Teams possa interagir com a caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8290-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="a8290-136">Sem Exchange caixa de correio acessar o ícone Calendário no Teams não aparecerá e o usuário não poderá exibir, criar ou modificar reuniões no cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="a8290-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="a8290-137">**Recursos de chamada VoIP/PSTN no Teams:** a chamada pode ser VoIP (Voz sobre IP) ou PSTN (Rede Telefônica Pública Comugada).</span><span class="sxs-lookup"><span data-stu-id="a8290-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a8290-138">A conectividade VoIP acontece de forma nativa entre Teams clientes, enquanto a conectividade PSTN acontece quando um usuário disca um número de telefone externo.</span><span class="sxs-lookup"><span data-stu-id="a8290-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="a8290-139">Teams suporte a dois tipos de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="a8290-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="a8290-140">Plano de Chamadas da Microsoft, quando a Microsoft fornece infraestrutura de telefonia, incluindo o número de telefone para um usuário ou configuração de Roteamento Direto, em que o cliente fornece a conectividade de telefonia por meio de um Controlador de Borda de Sessão (SBC) para o usuário Teams de sessão.</span><span class="sxs-lookup"><span data-stu-id="a8290-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="a8290-141">Para saber mais, leia [Qual Plano de Chamadas é o certo para você?](calling-plan-landing-page.md) e Sistema de Telefonia [Roteamento Direto.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="a8290-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="a8290-142">**Teams e colaboração de** canais em Teams : no Teams, as equipes são grupos de pessoas reunidas para trabalho, projetos ou interesses comuns.</span><span class="sxs-lookup"><span data-stu-id="a8290-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="a8290-143">Teams são feitos de canais.</span><span class="sxs-lookup"><span data-stu-id="a8290-143">Teams are made up of channels.</span></span> <span data-ttu-id="a8290-144">Cada canal é criado em torno de um tópico, como "Eventos de Equipe", um nome de departamento ou apenas por diversão.</span><span class="sxs-lookup"><span data-stu-id="a8290-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="a8290-145">Canais são onde você faz reuniões, conversa e trabalha em arquivos juntos.</span><span class="sxs-lookup"><span data-stu-id="a8290-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="a8290-146">Durante a colaboração</span><span class="sxs-lookup"><span data-stu-id="a8290-146">During collaboration</span></span>

<span data-ttu-id="a8290-147">OneDrive for Business (compartilhamento de arquivos **P2P)** no Teams: fora do Teams e canais, os usuários do Teams podem compartilhar arquivos ponto a ponto usando o OneDrive para empresas ou outros programas de arquivo de compartilhamento P2P, como Arquivos Citrix, DropBox, Box e Google Drive.</span><span class="sxs-lookup"><span data-stu-id="a8290-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="a8290-148">Para OneDrive para empresas, um usuário deve ter uma licença SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="a8290-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="a8290-149">**Plataforma de** Aplicativos : os aplicativos fornecem ferramentas in-locar para que sua organização receba mais informações Teams.</span><span class="sxs-lookup"><span data-stu-id="a8290-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="a8290-150">Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, construídos por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8290-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="a8290-151">Recursos de segurança e **conformidade:** o Teams tem uma ampla variedade de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, Proteção contra Perda de Dados (DLP), Descoberta e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a8290-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="a8290-152">Para saber mais, leia [Segurança e conformidade em Microsoft Teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8290-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="a8290-153">Os recursos avançados de Descoberta Desdiscovery exigem licenciamento do E5.</span><span class="sxs-lookup"><span data-stu-id="a8290-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="a8290-154">[Comparar opções de licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="a8290-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="a8290-155">Leia [Como Exchange e Microsoft Teams interagir](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis em seu cenário.</span><span class="sxs-lookup"><span data-stu-id="a8290-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="a8290-156">Organizações **<span class="underline">sem</span>** Skype for Business ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8290-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="a8290-157">Esse ponto de partida supõe que sua organização não usa o Skype for Business ou o Lync Server no momento e Teams será seu primeiro aplicativo no Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8290-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a8290-158">A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final para Teams para serviços principais.</span><span class="sxs-lookup"><span data-stu-id="a8290-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="a8290-159">Item</span><span class="sxs-lookup"><span data-stu-id="a8290-159">Item</span></span></th>
<th><span data-ttu-id="a8290-160">Observações</span><span class="sxs-lookup"><span data-stu-id="a8290-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8290-161">Configuração Teams locatário</span><span class="sxs-lookup"><span data-stu-id="a8290-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="a8290-162">Teams Somente modo, todos os recursos de chat e chamada estão Teams Somente.</span><span class="sxs-lookup"><span data-stu-id="a8290-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-163">Chat/Comunicação Externa no Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="a8290-164">Interna (dentro Microsoft 365 ou Office 365) e comunicação de chat externo possível a partir Teams.</span><span class="sxs-lookup"><span data-stu-id="a8290-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="a8290-165"><em>Observação: as entradas DNS devem ser configuradas para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="a8290-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="a8290-166">Skype for Business Os registros DNS são necessários mesmo que você não tenha Skype for Business local ou no Microsoft 365 ou Office 365, para permitir a federação com o Lync e Skype for Business ambientes:</span><span class="sxs-lookup"><span data-stu-id="a8290-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="a8290-167">
<a href="/office365/enterprise/external-domain-name-system-records">Registros do Sistema de Nomes de Domínio Externo</a></em></span><span class="sxs-lookup"><span data-stu-id="a8290-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8290-168">Criar e exibir reuniões em Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="a8290-169">Capaz de criar reuniões internas e externas Outlook um complemento.</span><span class="sxs-lookup"><span data-stu-id="a8290-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="a8290-170">O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="a8290-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="a8290-171">Teams de calendário requer Exchange cu3+ 2016 local implantado com Exchange híbrido estabelecido: Criar uma implantação híbrida com o assistente de Configuração <a href="/exchange/hybrid-deployment/deploy-hybrid">Híbrida.</a> </span><span class="sxs-lookup"><span data-stu-id="a8290-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="a8290-172">Além de Exchange configuração híbrida, estabeleça Exchange autenticação OAuth: Configure <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> OAuth authentication between Exchange and Exchange Online organizations".</span><span class="sxs-lookup"><span data-stu-id="a8290-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-173">Recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="a8290-173">Calling Features</span></span><br />
<span data-ttu-id="a8290-174">VoIP/PSTN no Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="a8290-175">VoIP interna e externamente para o locatário está disponível.</span><span class="sxs-lookup"><span data-stu-id="a8290-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="a8290-176">Os serviços PSTN podem ser configurados por meio Telefone Microsoft System, além de adicionar um Plano de Chamadas da Microsoft ou Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="a8290-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8290-177">Teams e colaboração de canais Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="a8290-178">Para ter uma experiência completa, incluindo recursos de conformidade, uma licença SharePoint Online precisa ser atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a8290-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="a8290-179">A migração de sites SharePoint locais existentes não é necessária.</span><span class="sxs-lookup"><span data-stu-id="a8290-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-180">OneDrive for Business (compartilhamento de arquivos P2P)</span><span class="sxs-lookup"><span data-stu-id="a8290-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="a8290-181">OneDrive for Business requer que um usuário tenha uma licença SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="a8290-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="a8290-182">Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</span><span class="sxs-lookup"><span data-stu-id="a8290-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8290-183">Plataforma de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a8290-183">Application platform</span></span></td>
<td><span data-ttu-id="a8290-184">Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="a8290-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="a8290-185">Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></span><span class="sxs-lookup"><span data-stu-id="a8290-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-186">Recursos de segurança e conformidade</span><span class="sxs-lookup"><span data-stu-id="a8290-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="a8290-187">As políticas de retenção estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a8290-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="a8290-188">Há suporte para a Descoberta EDiscovery e a Responsabilidade Legal para conformidade em mensagens de canal.</span><span class="sxs-lookup"><span data-stu-id="a8290-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="a8290-189">As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a8290-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="a8290-190">Conjunto de recursos completo disponível com Exchange Online; Exchange local oferece suporte à maioria desses recursos.</span><span class="sxs-lookup"><span data-stu-id="a8290-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="a8290-191">Para ver uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span><span class="sxs-lookup"><span data-stu-id="a8290-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="a8290-192">Etapas de habilitação para organizações sem Skype for Business ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="a8290-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="a8290-193">Atender pré-requisitos detalhados na seção Iniciar aqui acima</span><span class="sxs-lookup"><span data-stu-id="a8290-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="a8290-194">Alternar locatário para Teams modo Somente (somente para locatários existentes): Definindo suas [configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="a8290-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="a8290-195">Configure seu locatário de acordo com as políticas de negócios/empresa da sua empresa: Gerenciar Microsoft Teams [configurações da sua organização.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a8290-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="a8290-196">Implantar o Teams cliente para seus usuários: [Obter clientes para Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="a8290-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="a8290-197">Conduzir seu programa de adoção</span><span class="sxs-lookup"><span data-stu-id="a8290-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="a8290-198">Adotar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="a8290-199">Lista de verificação de início rápido da adoção do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="a8290-200">Comece a planejar a movimentação de outras cargas de trabalho para Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="a8290-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="a8290-201">Organizações **<span class="underline">com</span>** Skype for Business ou servidor Lync</span><span class="sxs-lookup"><span data-stu-id="a8290-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="a8290-202">Esse ponto de partida supõe que sua organização utiliza o servidor Skype for Business 2019 ou 2015+ ou Lync 2013+ no local.</span><span class="sxs-lookup"><span data-stu-id="a8290-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="a8290-203">Já temos orientações abrangentes para as organizações migrarem de servidores locais para Teams e devem ser seguidas para esses cenários.</span><span class="sxs-lookup"><span data-stu-id="a8290-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="a8290-204">Essa orientação é específica para o cenário em que Teams é o primeiro aplicativo que você usa no Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="a8290-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="a8290-205">A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final para Teams para serviços principais.</span><span class="sxs-lookup"><span data-stu-id="a8290-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="a8290-206">Item</span><span class="sxs-lookup"><span data-stu-id="a8290-206">Item</span></span></th>
<th><span data-ttu-id="a8290-207">Observações</span><span class="sxs-lookup"><span data-stu-id="a8290-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a8290-208">Configuração Teams locatário</span><span class="sxs-lookup"><span data-stu-id="a8290-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="a8290-209">Modo de ilhas.</span><span class="sxs-lookup"><span data-stu-id="a8290-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-210">Chat/Comunicação Externa no Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="a8290-211">Interna somente em seu próprio locatário, a comunicação externa (federação) é por meio da implantação do Skype for Business ou do servidor Lync.</span><span class="sxs-lookup"><span data-stu-id="a8290-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8290-212">Criar e exibir reuniões em Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="a8290-213">Capaz de criar reuniões internas e externas Outlook um complemento.</span><span class="sxs-lookup"><span data-stu-id="a8290-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="a8290-214">O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="a8290-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="a8290-215">Teams acesso ao calendário requer Exchange 2016 CU3+ local implantado com Exchange híbrido estabelecido:</span><span class="sxs-lookup"><span data-stu-id="a8290-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="a8290-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Crie uma implantação híbrida com o assistente de Configuração Híbrida.</a></span><span class="sxs-lookup"><span data-stu-id="a8290-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="a8290-217">O administrador pode controlar o Skype for Business Outlook do Teams por meio do atributo PreferredMeetingProviderForIslandsMode da política de reunião do Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span><span class="sxs-lookup"><span data-stu-id="a8290-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-218">Recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="a8290-218">Calling Features</span></span><br />
<span data-ttu-id="a8290-219">VoIP/PSTN no Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="a8290-220">O VoIP internamente para o locatário está disponível.</span><span class="sxs-lookup"><span data-stu-id="a8290-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="a8290-221">Os serviços PSTN ou Plano de Chamada não estarão disponíveis até que o usuário seja movido para Teams somente experiência.</span><span class="sxs-lookup"><span data-stu-id="a8290-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8290-222">Teams e colaboração de canais Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="a8290-223">Para ter uma experiência completa, incluindo recursos de conformidade, uma licença SharePoint Online precisa ser atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="a8290-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="a8290-224">A migração de sites SharePoint locais existentes não é necessária.</span><span class="sxs-lookup"><span data-stu-id="a8290-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-225">OneDrive for Business (compartilhamento de arquivos P2P)</span><span class="sxs-lookup"><span data-stu-id="a8290-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="a8290-226">OneDrive for Business requer que um usuário tenha uma licença SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="a8290-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="a8290-227">Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</span><span class="sxs-lookup"><span data-stu-id="a8290-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a8290-228">Plataforma de aplicativos</span><span class="sxs-lookup"><span data-stu-id="a8290-228">Application platform</span></span></td>
<td><span data-ttu-id="a8290-229">Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="a8290-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="a8290-230">Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></span><span class="sxs-lookup"><span data-stu-id="a8290-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a8290-231">Recursos de segurança e conformidade</span><span class="sxs-lookup"><span data-stu-id="a8290-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="a8290-232">As políticas de retenção estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a8290-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="a8290-233">Há suporte para a Descoberta EDiscovery e a Responsabilidade Legal para conformidade em mensagens de canal.</span><span class="sxs-lookup"><span data-stu-id="a8290-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="a8290-234">As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a8290-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="a8290-235">Conjunto de recursos completo disponível com Exchange Online; Exchange local oferece suporte à maioria desses recursos.</span><span class="sxs-lookup"><span data-stu-id="a8290-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="a8290-236">Para uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span><span class="sxs-lookup"><span data-stu-id="a8290-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="a8290-237">Etapas de habilitação para organizações com Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a8290-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="a8290-238">Atender a pré-requisitos detalhados na seção Iniciar aqui acima.</span><span class="sxs-lookup"><span data-stu-id="a8290-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="a8290-239">Alternar locatário para o modo Ilhas (para locatários provisionados APÓS 1/9/2019, entre em contato com o suporte para fazer essa alteração)</span><span class="sxs-lookup"><span data-stu-id="a8290-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="a8290-240">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="a8290-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="a8290-241">Configurar seu locatário de acordo com as políticas de negócios/empresa da sua empresa</span><span class="sxs-lookup"><span data-stu-id="a8290-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="a8290-242">Gerenciar as configurações do Microsoft Teams para sua organização</span><span class="sxs-lookup"><span data-stu-id="a8290-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="a8290-243">Implantar o Teams cliente</span><span class="sxs-lookup"><span data-stu-id="a8290-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="a8290-244">Obter clientes para o Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="a8290-245">Conduzir seu programa de adoção</span><span class="sxs-lookup"><span data-stu-id="a8290-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="a8290-246">Adotar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="a8290-247">Lista de verificação de início rápido da adoção do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="a8290-248">Comece a planejar a movimentação de outras cargas de trabalho para Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="a8290-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="a8290-249">Estabeleça Skype for Business híbrido e siga os caminhos de atualização recomendados para servidores Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="a8290-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="a8290-250">Atualizar do Skype for Business local para o Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="a8290-251">Instrução Closing</span><span class="sxs-lookup"><span data-stu-id="a8290-251">Closing statement</span></span>

<span data-ttu-id="a8290-252">Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, funcionários da informação e funcionários da Linha de Frente em uma única plataforma.</span><span class="sxs-lookup"><span data-stu-id="a8290-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="a8290-253">Você pode [começar hoje.](https://products.office.com/microsoft-teams/group-chat-software)</span><span class="sxs-lookup"><span data-stu-id="a8290-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="a8290-254">Você pode manter contato com todos os nossos comunicados mais recentes e atualizações mensais de produtos [aqui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span><span class="sxs-lookup"><span data-stu-id="a8290-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="a8290-255">Além disso, à medida que as empresas em todo o mundo gerenciam a situação atual do COVID-19, criamos uma série de conteúdos que o ajudarão a utilizar o Teams para o impacto máximo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a8290-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="a8290-256">Nosso [compromisso com os clientes durante o COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="a8290-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="a8290-257">2 semanas em: o que aprendemos sobre o trabalho remoto</span><span class="sxs-lookup"><span data-stu-id="a8290-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="a8290-258">Entrega de reuniões e eventos online</span><span class="sxs-lookup"><span data-stu-id="a8290-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="a8290-259">Ajudar empresas pequenas e de médio porte a trabalhar remotamente com o Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="a8290-260">Transformação digital de eventos ao vivo: observações de Bob Bejan da linha de frente</span><span class="sxs-lookup"><span data-stu-id="a8290-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="a8290-261">As 9 principais maneiras que o TI da Microsoft está possibilitando o trabalho remoto para seus funcionários</span><span class="sxs-lookup"><span data-stu-id="a8290-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="a8290-262">Trabalhar remotamente, manter-se seguro– dicas para CISOs</span><span class="sxs-lookup"><span data-stu-id="a8290-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="a8290-263">Ajudar professores e alunos a mudar para o aprendizado remoto</span><span class="sxs-lookup"><span data-stu-id="a8290-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="a8290-264">Manter-se produtivo enquanto trabalha remotamente com Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="a8290-265">Referência dos Serviços de Suporte</span><span class="sxs-lookup"><span data-stu-id="a8290-265">Support Services reference</span></span>

<span data-ttu-id="a8290-266">Teams conta com grupos Exchange Online, SharePoint Online, OneDrive for Business e Microsoft 365 para fornecer aos usuários uma experiência de Microsoft 365 ou Office 365 integrada.</span><span class="sxs-lookup"><span data-stu-id="a8290-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="a8290-267">Conforme mencionado acima, Teams funcionará sem a implantação completa desses serviços – com recursos limitados.</span><span class="sxs-lookup"><span data-stu-id="a8290-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="a8290-268">Você pode ler mais sobre Teams e seus pré-requisitos aqui: [Bem-vindo ao Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a8290-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="a8290-269">Para detalhes sobre cada um dos serviços listados acima, siga os links abaixo:</span><span class="sxs-lookup"><span data-stu-id="a8290-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="a8290-270">Exchange Online é usado para recursos de calendário e armazenamento de mensagens ponto a ponto em Teams.</span><span class="sxs-lookup"><span data-stu-id="a8290-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="a8290-271">Para saber mais, leia [Como Exchange e Teams interagir](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="a8290-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8290-272">Para Teams a Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange conforme descrito em [Configure OAuth authentication](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)between Exchange and Exchange Online organizations .</span><span class="sxs-lookup"><span data-stu-id="a8290-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="a8290-273">SharePoint é usado para compartilhamento de arquivos em canais, enquanto /OneDrive for Business é usado para compartilhamento de arquivos em 1:1 ou chat em grupo.</span><span class="sxs-lookup"><span data-stu-id="a8290-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="a8290-274">Para saber mais, leia [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="a8290-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="a8290-275">[Microsoft 365 Grupos](office-365-groups.md) são usados para criação/gerenciamento de equipe e canal.</span><span class="sxs-lookup"><span data-stu-id="a8290-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a8290-276">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a8290-276">Related topics</span></span>

[<span data-ttu-id="a8290-277">Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="a8290-278">Planejar conectividade híbrida entre o Skype for Business Server e o Office 365</span><span class="sxs-lookup"><span data-stu-id="a8290-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="a8290-279">Dar suporte a funcionários remotos usando Teams</span><span class="sxs-lookup"><span data-stu-id="a8290-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="a8290-280">Trabalhar remotamente com Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8290-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)