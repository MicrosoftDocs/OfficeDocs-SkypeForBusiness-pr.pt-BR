---
title: Lançar o Microsoft Teams First
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
description: Use esta orientação para lançar o Microsoft Teams como sua primeira carga de trabalho do Microsoft 365 ou Office 365.
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
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="7f12e-103">Lançar o Microsoft Teams First</span><span class="sxs-lookup"><span data-stu-id="7f12e-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="7f12e-104">O Microsoft Teams pode ajudar seus funcionários a permanecer conectados e colaborar uns com os outros, especialmente no momento atual sem precedentes em que o trabalho remoto é uma realidade de funcionários em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="7f12e-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="7f12e-105">Poder conversar, fazer reuniões em vídeo e colaborar em documentos do Office no Teams pode ajudar as empresas a se manter produtivas.</span><span class="sxs-lookup"><span data-stu-id="7f12e-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="7f12e-106">Se você é uma pequena empresa, uma organização sem fins lucrativos ou uma grande organização, você pode começar com o Teams como a primeira carga de trabalho no Microsoft 365 ou no pacote do Office 365 antes de implantar qualquer outro aplicativo ou serviço do Office.</span><span class="sxs-lookup"><span data-stu-id="7f12e-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Microsoft 365 or Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="7f12e-107">Este artigo detalha as considerações que você deve fazer com a abordagem "Teams First".</span><span class="sxs-lookup"><span data-stu-id="7f12e-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f12e-108">Embora o Teams possa ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação do Teams deve fazer parte da estratégia geral de implantação na nuvem.</span><span class="sxs-lookup"><span data-stu-id="7f12e-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="7f12e-109">Se você já tiver lançado outros serviços do Microsoft 365 ou Office 365 e o Teams for sua próxima carga de trabalho a ser lançado (em vez do primeiro), comece com Como lançar o [Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7f12e-109">If you have already rolled out other Microsoft 365 or Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out Teams](./deploy-overview.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="7f12e-110">Iniciar aqui</span><span class="sxs-lookup"><span data-stu-id="7f12e-110">Start here</span></span>

<span data-ttu-id="7f12e-111">Para começar a implantação do Teams First, você precisará atender, no mínimo, a alguns pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="7f12e-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="7f12e-112">A lista a seguir mostrará o que você deve ter para sua organização antes que o Teams possa ser habilitado:</span><span class="sxs-lookup"><span data-stu-id="7f12e-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="7f12e-113">Uma organização do Microsoft 365 ou Office 365 configurada com seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="7f12e-113">A Microsoft 365 or Office 365 organization configured with your domain name</span></span>

2.  <span data-ttu-id="7f12e-114">Conectividade do Azure Active Directory (conexão AAD) ou solução de sincronização de identidade de nuvem semelhante – com todos os atributos necessários sincronizados com seu locatário</span><span class="sxs-lookup"><span data-stu-id="7f12e-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="7f12e-115">Para entender os atributos sincronizados com a sincronização do AAD, leia Sincronização do [Azure AD Connect: Atributos sincronizados com o Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="7f12e-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="7f12e-116">Licenças de usuário apropriadas atribuídas ao Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="7f12e-117">Para entender o licenciamento do Teams, leia a descrição [do serviço do Microsoft Teams.](/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="7f12e-117">To understand Teams licensing, read [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

4.  <span data-ttu-id="7f12e-118">Rede da organização preparada para o Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="7f12e-119">Para entender a preparação da rede, leia [Preparar a rede da sua organização para o Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="7f12e-120">Permitir acesso de rede ao Exchange, Sharepoint e OneDrive for Business no Microsoft 365 ou Office 365: [URLs do Office 365](/office365/enterprise/urls-and-ip-address-ranges)e intervalos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="7f12e-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Microsoft 365 or Office 365: [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="7f12e-121">Os locatários criados após 1º de setembro de 2019 são provisionados no modo Somente equipes.</span><span class="sxs-lookup"><span data-stu-id="7f12e-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="7f12e-122">Se você tiver o Skype for Business Server implantado e seu locatário tiver sido provisionado APÓS 1º de setembro de 2019, entre em contato com o suporte para habilitar recursos de coexistência para o Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="7f12e-123">Certifique-se de que sua "política de atualização de toda a organização" seja definida como "modo <span class="underline">ilha"</span> antes de atribuir licenças do Teams a um usuário.</span><span class="sxs-lookup"><span data-stu-id="7f12e-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="7f12e-124">Pontos de partida da migração</span><span class="sxs-lookup"><span data-stu-id="7f12e-124">Migration Starting points</span></span>

<span data-ttu-id="7f12e-125">Sua jornada para o Microsoft 365 ou Office 365 e recursos disponíveis no Teams, dependendo do ponto de partida e da existência do skype for Business local ou do servidor Lync.</span><span class="sxs-lookup"><span data-stu-id="7f12e-125">Your journey to Microsoft 365 or Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="7f12e-126">As seções a seguir detalham recursos básicos e opções de configuração, além dos pré-requisitos acima.</span><span class="sxs-lookup"><span data-stu-id="7f12e-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="7f12e-127">Nós quebramos os cenários de ponto de partida para os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="7f12e-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="7f12e-128">**Configuração do Tenant Teams**: Os modos de locatário e usuário são usados para controlar o comportamento do destinatário.</span><span class="sxs-lookup"><span data-stu-id="7f12e-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="7f12e-129">Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização.</span><span class="sxs-lookup"><span data-stu-id="7f12e-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="7f12e-130">Para saber mais, leia [Coexistência com o Skype for Business.](coexistence-chat-calls-presence.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="7f12e-131">**Chat / Comunicação externa no Teams**: os serviços de chat referem-se a conversas de chat ponto a ponto ou grupo dentro e organização ou externamente à organização.</span><span class="sxs-lookup"><span data-stu-id="7f12e-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="7f12e-132">A comunicação externa também é conhecida como federação no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7f12e-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="7f12e-133">**Criar e exibir** reuniões no Teams : um usuário sempre pode criar reuniões online por meio do complemento do Outlook Teams e o discagem PSTN está disponível em todos os cenários depois que o usuário é licenciado.</span><span class="sxs-lookup"><span data-stu-id="7f12e-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="7f12e-134">As informações de calendário do Teams e do Skype for Business armazenam na caixa de correio do Exchange do usuário.</span><span class="sxs-lookup"><span data-stu-id="7f12e-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="7f12e-135">No local, o servidor exchange deve ser Exchange Server cu3 2016 ou superior para que o cliente do Teams possa interagir com a caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="7f12e-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="7f12e-136">Sem o acesso à caixa de correio do Exchange, o ícone Calendário no Teams não será exibido e o usuário não poderá exibir, criar ou modificar reuniões no cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="7f12e-137">**Recursos de chamada VoIP/PSTN no Teams**: Chamar pode ser Voz sobre IP (VoIP) ou Rede Telefônica Pública Comugada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="7f12e-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="7f12e-138">A conectividade VoIP acontece na verdade entre clientes do Teams, enquanto a conectividade PSTN acontece quando um usuário disca um número de telefone externo.</span><span class="sxs-lookup"><span data-stu-id="7f12e-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="7f12e-139">O Teams suporta dois tipos de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="7f12e-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="7f12e-140">Plano de Chamadas da Microsoft, quando a Microsoft fornece infraestrutura de telefonia, incluindo o número de telefone para um usuário ou configuração de Roteamento Direto, onde o cliente fornece a conectividade de telefonia por meio de um Controlador de Borda de Sessão (SBC) para o usuário do Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="7f12e-141">Para saber mais, leia [Qual Plano de Chamadas é o certo para você?](calling-plan-landing-page.md) e [Roteamento Direto do Sistema de Telefonia.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="7f12e-142">**Colaboração de equipes** e canais no Teams : no Teams, as equipes são grupos de pessoas reunidas para trabalho, projetos ou interesses comuns.</span><span class="sxs-lookup"><span data-stu-id="7f12e-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="7f12e-143">As equipes são feitas de canais.</span><span class="sxs-lookup"><span data-stu-id="7f12e-143">Teams are made up of channels.</span></span> <span data-ttu-id="7f12e-144">Cada canal é criado em torno de um tópico, como "Eventos de Equipe", um nome de departamento ou apenas por diversão.</span><span class="sxs-lookup"><span data-stu-id="7f12e-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="7f12e-145">Canais são onde você faz reuniões, conversa e trabalha em arquivos juntos.</span><span class="sxs-lookup"><span data-stu-id="7f12e-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="7f12e-146">Durante a colaboração</span><span class="sxs-lookup"><span data-stu-id="7f12e-146">During collaboration</span></span>

<span data-ttu-id="7f12e-147">OneDrive for Business (compartilhamento de arquivos **P2P)** no Teams : fora do Teams e canais, os usuários do Teams podem compartilhar arquivos ponto a ponto usando o OneDrive for business ou outros programas de arquivo de compartilhamento P2P, como Arquivos Citrix, DropBox, Box e Google Drive.</span><span class="sxs-lookup"><span data-stu-id="7f12e-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="7f12e-148">Para o OneDrive for Business, um usuário deve ter a licença do SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="7f12e-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="7f12e-149">**Plataforma de** Aplicativos : os aplicativos fornecem ferramentas in-locar para sua organização obter mais do Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="7f12e-150">Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, construídos por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f12e-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="7f12e-151">**Recursos de segurança e conformidade:** O Teams tem uma ampla variedade de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, Proteção contra Perda de Dados (DLP), Descoberta e retenção legal para canais, chats e arquivos, pesquisa de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="7f12e-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="7f12e-152">Para saber mais, leia [Segurança e conformidade no Microsoft Teams.](security-compliance-overview.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="7f12e-153">Os recursos avançados de Descoberta Desdiscovery exigem licenciamento do E5.</span><span class="sxs-lookup"><span data-stu-id="7f12e-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="7f12e-154">[Comparar opções de licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="7f12e-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="7f12e-155">Leia [Como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis em seu cenário.</span><span class="sxs-lookup"><span data-stu-id="7f12e-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="7f12e-156">Organizações **<span class="underline">sem</span>** Skype for Business ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="7f12e-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync Server</span></span>

<span data-ttu-id="7f12e-157">Esse ponto de partida supõe que sua organização não usa o Skype for Business ou o Lync Server no momento e o Teams será seu primeiro aplicativo no Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f12e-157">This starting point assumes that your organization does not utilize Skype for Business or Lync Server currently and Teams will be your first application in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7f12e-158">A tabela a seguir detalha a configuração de alto nível e os recursos de usuário final do Teams para serviços principais.</span><span class="sxs-lookup"><span data-stu-id="7f12e-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="7f12e-159">Item</span><span class="sxs-lookup"><span data-stu-id="7f12e-159">Item</span></span></th>
<th><span data-ttu-id="7f12e-160">Observações</span><span class="sxs-lookup"><span data-stu-id="7f12e-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7f12e-161">Configuração do Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="7f12e-162">Modo Somente equipes, todos os recursos de chat e chamada estão somente no Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-162">Teams Only mode, all chat and calling features are in Teams Only.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-163">Chat/Comunicação Externa no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="7f12e-164">Interna (dentro da organização do Microsoft 365 ou office 365) e comunicação de chat externo possível do Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-164">Internal (intra Microsoft 365 or Office 365 organization) and external chat communication possible from Teams.</span></span></p>
<p><span data-ttu-id="7f12e-165"><em>Observação: as entradas DNS devem ser configuradas para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="7f12e-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="7f12e-166">Os registros DNS do Skype for Business são necessários mesmo que você não tenha o Skype for Business local ou no Microsoft 365 ou Office 365, para permitir a federação com ambientes do Lync e do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="7f12e-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises, or in Microsoft 365 or Office 365, to allow federation with Lync and Skype for Business environments:</span></span><br /><span data-ttu-id="7f12e-167">
<a href="/office365/enterprise/external-domain-name-system-records">Registros do Sistema de Nomes de Domínio Externo</a></em></span><span class="sxs-lookup"><span data-stu-id="7f12e-167">
<a href="/office365/enterprise/external-domain-name-system-records">External Domain Name System records</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7f12e-168">Criar e exibir reuniões no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-168">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="7f12e-169">Capaz de criar reuniões internas e externas por meio do complemento do Outlook.</span><span class="sxs-lookup"><span data-stu-id="7f12e-169">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="7f12e-170">O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7f12e-170">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="7f12e-171">O acesso ao calendário do Teams requer o Exchange 2016 CU3+ local implantado com o Exchange híbrido estabelecido: Criar uma implantação híbrida com o <a href="/exchange/hybrid-deployment/deploy-hybrid">assistente de Configuração Híbrida.</a> </span><span class="sxs-lookup"><span data-stu-id="7f12e-171">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a> </span></span></p>
<p><span data-ttu-id="7f12e-172">Além da configuração híbrida do Exchange, estabeleça a autenticação OAuth do Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help"> Configure OAuth authentication between Exchange and Exchange Online organizations".</span><span class="sxs-lookup"><span data-stu-id="7f12e-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations".</span></span></p>

</p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-173">Recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="7f12e-173">Calling Features</span></span><br />
<span data-ttu-id="7f12e-174">VoIP/PSTN no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="7f12e-175">VoIP interna e externamente para o locatário está disponível.</span><span class="sxs-lookup"><span data-stu-id="7f12e-175">VoIP internally and externally to the tenant is available.</span></span></p>
<p><span data-ttu-id="7f12e-176">Os serviços PSTN podem ser configurados por meio do Microsoft Phone System, além de adicionar um Plano de Chamadas da Microsoft ou Roteamento Direto.</span><span class="sxs-lookup"><span data-stu-id="7f12e-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7f12e-177">Colaboração de equipes e canais no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="7f12e-178">Para ter uma experiência completa, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7f12e-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="7f12e-179">A migração de sites locais existentes do SharePoint não é necessária.</span><span class="sxs-lookup"><span data-stu-id="7f12e-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-180">OneDrive for Business (compartilhamento de arquivos P2P)</span><span class="sxs-lookup"><span data-stu-id="7f12e-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="7f12e-181">O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="7f12e-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="7f12e-182">Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</span><span class="sxs-lookup"><span data-stu-id="7f12e-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7f12e-183">Plataforma de aplicativos</span><span class="sxs-lookup"><span data-stu-id="7f12e-183">Application platform</span></span></td>
<td><span data-ttu-id="7f12e-184">Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7f12e-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="7f12e-185">Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></span><span class="sxs-lookup"><span data-stu-id="7f12e-185">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-186">Recursos de segurança e conformidade</span><span class="sxs-lookup"><span data-stu-id="7f12e-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="7f12e-187">As políticas de retenção estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7f12e-187">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="7f12e-188">Há suporte para a Descoberta EDiscovery e a Responsabilidade Legal para conformidade em mensagens de canal.</span><span class="sxs-lookup"><span data-stu-id="7f12e-188">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="7f12e-189">As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7f12e-189">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="7f12e-190">Conjunto de recursos completo disponível com o Exchange Online; O Exchange local oferece suporte à maioria desses recursos.</span><span class="sxs-lookup"><span data-stu-id="7f12e-190">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="7f12e-191">Para ver uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem.</a></span><span class="sxs-lookup"><span data-stu-id="7f12e-191">For a full list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a>.</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="7f12e-192">Etapas de habilitação para organizações sem Skype for Business ou Lync Server</span><span class="sxs-lookup"><span data-stu-id="7f12e-192">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="7f12e-193">Atender pré-requisitos detalhados na seção Iniciar aqui acima</span><span class="sxs-lookup"><span data-stu-id="7f12e-193">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="7f12e-194">Alternar locatário para o modo Somente do Teams (somente para locatários [existentes): Definindo suas configurações de coexistência e atualização.](setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-194">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="7f12e-195">Configure seu locatário de acordo com as políticas de negócios/empresa da sua empresa: Gerenciar as configurações do [Microsoft Teams para sua organização.](enable-features-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-195">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="7f12e-196">Implantar o cliente do Teams para seus usuários: [Obter clientes para o Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-196">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="7f12e-197">Conduzir seu programa de adoção</span><span class="sxs-lookup"><span data-stu-id="7f12e-197">Drive your adoption program</span></span>  
    [<span data-ttu-id="7f12e-198">Adotar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-198">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="7f12e-199">Lista de verificação de início rápido da adoção do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-199">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="7f12e-200">Comece a planejar a movimentação de outras cargas de trabalho para o Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="7f12e-200">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="7f12e-201">Organizações **<span class="underline">com</span>** o Skype for Business ou o servidor Lync</span><span class="sxs-lookup"><span data-stu-id="7f12e-201">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="7f12e-202">Esse ponto de partida supõe que sua organização utilize o servidor do Skype for Business 2019 ou 2015+ ou do Lync 2013+ no local.</span><span class="sxs-lookup"><span data-stu-id="7f12e-202">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="7f12e-203">Já temos orientações abrangentes para as organizações migrarem de servidores locais para o Teams e isso deve ser seguido para esses cenários.</span><span class="sxs-lookup"><span data-stu-id="7f12e-203">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="7f12e-204">Essa orientação é específica para o cenário em que o Teams é o primeiro aplicativo que você usa no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f12e-204">This guidance is specific to the scenario that Teams is the first application you utilize in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="7f12e-205">A tabela a seguir detalha a configuração de alto nível e os recursos de usuário final do Teams para serviços principais.</span><span class="sxs-lookup"><span data-stu-id="7f12e-205">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="7f12e-206">Item</span><span class="sxs-lookup"><span data-stu-id="7f12e-206">Item</span></span></th>
<th><span data-ttu-id="7f12e-207">Observações</span><span class="sxs-lookup"><span data-stu-id="7f12e-207">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="7f12e-208">Configuração do Tenant Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-208">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="7f12e-209">Modo de ilhas.</span><span class="sxs-lookup"><span data-stu-id="7f12e-209">Islands mode.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-210">Chat/Comunicação Externa no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-210">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="7f12e-211">Interna somente em seu próprio locatário, a comunicação externa (federação) é por meio da implantação do servidor skype for Business ou do Lync.</span><span class="sxs-lookup"><span data-stu-id="7f12e-211">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7f12e-212">Criar e exibir reuniões no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-212">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="7f12e-213">Capaz de criar reuniões internas e externas por meio do complemento do Outlook.</span><span class="sxs-lookup"><span data-stu-id="7f12e-213">Able to create internal and external meetings via Outlook add-in.</span></span></p>
<p><span data-ttu-id="7f12e-214">O recurso Discagem PSTN e Discagem está disponível com as licenças de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7f12e-214">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span></p>
<p><span data-ttu-id="7f12e-215">O acesso ao calendário do Teams requer o Exchange 2016 CU3+ local implantado com o Exchange híbrido estabelecido:</span><span class="sxs-lookup"><span data-stu-id="7f12e-215">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="7f12e-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Crie uma implantação híbrida com o assistente de Configuração Híbrida.</a></span><span class="sxs-lookup"><span data-stu-id="7f12e-216">
<a href="/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard.</a></span></span></p>
<p><span data-ttu-id="7f12e-217">O administrador pode controlar o complemento do Skype for Business Outlook por meio do atributo PreferredMeetingProviderForIslandsMode da política de reunião do Teams:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span><span class="sxs-lookup"><span data-stu-id="7f12e-217">Administrator can control the Skype for Business Outlook add-in via the Teams meeting policy’s PreferredMeetingProviderForIslandsMode attribute:<a href="/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps"> set-csteamsmeetingpolicy</a>.</span></span></p> 
</td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-218">Recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="7f12e-218">Calling Features</span></span><br />
<span data-ttu-id="7f12e-219">VoIP/PSTN no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="7f12e-220">O VoIP internamente para o locatário está disponível.</span><span class="sxs-lookup"><span data-stu-id="7f12e-220">VoIP internally to the tenant is available.</span></span></p>
<p><span data-ttu-id="7f12e-221">Os serviços PSTN ou Plano de Chamada não estarão disponíveis até que o usuário seja movido para a experiência Somente do Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7f12e-222">Colaboração de equipes e canais no Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="7f12e-223">Para ter uma experiência completa, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="7f12e-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="7f12e-224">A migração de sites locais existentes do SharePoint não é necessária.</span><span class="sxs-lookup"><span data-stu-id="7f12e-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-225">OneDrive for Business (compartilhamento de arquivos P2P)</span><span class="sxs-lookup"><span data-stu-id="7f12e-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="7f12e-226">O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="7f12e-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="7f12e-227">Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</span><span class="sxs-lookup"><span data-stu-id="7f12e-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="7f12e-228">Plataforma de aplicativos</span><span class="sxs-lookup"><span data-stu-id="7f12e-228">Application platform</span></span></td>
<td><span data-ttu-id="7f12e-229">Os usuários poderão usar os aplicativos designados disponíveis para eles de acordo com as políticas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="7f12e-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="7f12e-230">Saiba mais aqui: <a href="/microsoftteams/admin-settings">Configurações de administrador para aplicativos no Teams</a></span><span class="sxs-lookup"><span data-stu-id="7f12e-230">Learn more here: <a href="/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="7f12e-231">Recursos de segurança e conformidade</span><span class="sxs-lookup"><span data-stu-id="7f12e-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="7f12e-232">As políticas de retenção estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7f12e-232">Retention policies are available.</span></span></p></li>
<li><p><span data-ttu-id="7f12e-233">Há suporte para a Descoberta EDiscovery e a Responsabilidade Legal para conformidade em mensagens de canal.</span><span class="sxs-lookup"><span data-stu-id="7f12e-233">eDiscovery and Legal Hold for compliance on channel messages is supported.</span></span></p></li>
<li><p><span data-ttu-id="7f12e-234">As políticas de Prevenção contra Perda de Dados (DLP) estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7f12e-234">Data Loss Prevention policies (DLP) are available.</span></span></p></li>
</ul>
<p><span data-ttu-id="7f12e-235">Conjunto de recursos completo disponível com o Exchange Online; O Exchange local oferece suporte à maioria desses recursos.</span><span class="sxs-lookup"><span data-stu-id="7f12e-235">Full feature set available with Exchange Online; Exchange on-premises supports most of these features.</span></span> <span data-ttu-id="7f12e-236">Para uma lista completa, consulte <a href="/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem.</a></span><span class="sxs-lookup"><span data-stu-id="7f12e-236">For a complete list, see <a href="/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact.</a></span></span></p>
<ul>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="7f12e-237">Etapas de habilitação para organizações com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7f12e-237">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="7f12e-238">Atender a pré-requisitos detalhados na seção Iniciar aqui acima.</span><span class="sxs-lookup"><span data-stu-id="7f12e-238">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="7f12e-239">Alternar locatário para o modo Ilhas (para locatários provisionados APÓS 1/9/2019, entre em contato com o suporte para fazer essa alteração)</span><span class="sxs-lookup"><span data-stu-id="7f12e-239">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact support to make this change)</span></span>  
    [<span data-ttu-id="7f12e-240">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="7f12e-240">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="7f12e-241">Configurar seu locatário de acordo com as políticas de negócios/empresa da sua empresa</span><span class="sxs-lookup"><span data-stu-id="7f12e-241">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="7f12e-242">Gerenciar as configurações do Microsoft Teams para sua organização</span><span class="sxs-lookup"><span data-stu-id="7f12e-242">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="7f12e-243">Implantar o cliente do Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-243">Deploy the Teams client</span></span>  
    [<span data-ttu-id="7f12e-244">Obter clientes para o Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-244">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="7f12e-245">Conduzir seu programa de adoção</span><span class="sxs-lookup"><span data-stu-id="7f12e-245">Drive your adoption program</span></span>  
    [<span data-ttu-id="7f12e-246">Adotar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-246">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)<br/>
    [<span data-ttu-id="7f12e-247">Lista de verificação de início rápido da adoção do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-247">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="7f12e-248">Comece a planejar a movimentação de outras cargas de trabalho para o Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="7f12e-248">Begin planning moving other workloads to Microsoft 365 or Office 365</span></span>

7.  <span data-ttu-id="7f12e-249">Estabeleça o Skype for Business híbrido e siga os caminhos de atualização recomendados para servidores Skype for Business e Lync</span><span class="sxs-lookup"><span data-stu-id="7f12e-249">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="7f12e-250">Atualizar do Skype for Business local para o Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-250">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="7f12e-251">Instrução Closing</span><span class="sxs-lookup"><span data-stu-id="7f12e-251">Closing statement</span></span>

<span data-ttu-id="7f12e-252">O Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, funcionários de informações e funcionários da Linha de Frente em uma única plataforma.</span><span class="sxs-lookup"><span data-stu-id="7f12e-252">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Frontline workers, together on a single platform.</span></span> <span data-ttu-id="7f12e-253">Você pode [começar hoje.](https://products.office.com/microsoft-teams/group-chat-software)</span><span class="sxs-lookup"><span data-stu-id="7f12e-253">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="7f12e-254">Você pode manter contato com todos os nossos comunicados mais recentes e atualizações mensais de produtos [aqui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span><span class="sxs-lookup"><span data-stu-id="7f12e-254">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="7f12e-255">Além disso, como as empresas em todo o mundo estão gerenciando a situação atual do COVID-19, criamos uma série de conteúdos que ajudarão você a utilizar o Teams para o impacto máximo em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f12e-255">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="7f12e-256">Nosso [compromisso com os clientes durante o COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="7f12e-256">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="7f12e-257">2 semanas em: o que aprendemos sobre o trabalho remoto</span><span class="sxs-lookup"><span data-stu-id="7f12e-257">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="7f12e-258">Entrega de reuniões e eventos online</span><span class="sxs-lookup"><span data-stu-id="7f12e-258">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="7f12e-259">Ajudar empresas pequenas e de médio porte a trabalhar remotamente com o Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-259">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="7f12e-260">Transformação digital de eventos ao vivo: observações de Bob Bejan da linha de frente</span><span class="sxs-lookup"><span data-stu-id="7f12e-260">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="7f12e-261">As 9 principais maneiras que o TI da Microsoft está possibilitando o trabalho remoto para seus funcionários</span><span class="sxs-lookup"><span data-stu-id="7f12e-261">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="7f12e-262">Trabalhar remotamente, manter-se seguro– dicas para CISOs</span><span class="sxs-lookup"><span data-stu-id="7f12e-262">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="7f12e-263">Ajudar professores e alunos a mudar para o aprendizado remoto</span><span class="sxs-lookup"><span data-stu-id="7f12e-263">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="7f12e-264">Manter-se produtivo enquanto trabalha remotamente com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-264">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="7f12e-265">Referência dos Serviços de Suporte</span><span class="sxs-lookup"><span data-stu-id="7f12e-265">Support Services reference</span></span>

<span data-ttu-id="7f12e-266">O Teams depende do Exchange Online, do SharePoint Online, do OneDrive for Business e dos Grupos do Microsoft 365 para fornecer aos usuários uma experiência totalmente integrada do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7f12e-266">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Microsoft 365 Groups to provide your users with a fully integrated Microsoft 365 or Office 365 experience.</span></span> <span data-ttu-id="7f12e-267">Conforme mencionado acima, o Teams funcionará sem a implantação completa desses serviços – com recursos limitados.</span><span class="sxs-lookup"><span data-stu-id="7f12e-267">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="7f12e-268">Você pode ler mais sobre o Teams e seus pré-requisitos aqui: [Bem-vindo ao Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7f12e-268">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="7f12e-269">Para detalhes sobre cada um dos serviços listados acima, siga os links abaixo:</span><span class="sxs-lookup"><span data-stu-id="7f12e-269">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="7f12e-270">O Exchange Online é usado para recursos de calendário e armazenamento de mensagens ponto a ponto no Teams.</span><span class="sxs-lookup"><span data-stu-id="7f12e-270">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="7f12e-271">Para saber mais, leia [Como o Exchange e o Teams interagem](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-271">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f12e-272">Para a interopção do Teams com o Exchange local, você deve configurar o novo protocolo de autenticação OAuth do Exchange, conforme descrito em [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="7f12e-272">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="7f12e-273">O SharePoint é usado para compartilhamento de arquivos em canais, enquanto /OneDrive for Business é usado para compartilhamento de arquivos em 1:1 ou chat em grupo.</span><span class="sxs-lookup"><span data-stu-id="7f12e-273">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="7f12e-274">Para saber mais, leia [Como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams.](sharepoint-onedrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="7f12e-274">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="7f12e-275">[Os Grupos do Microsoft 365](office-365-groups.md) são usados para criação/gerenciamento de equipe e canal.</span><span class="sxs-lookup"><span data-stu-id="7f12e-275">[Microsoft 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="7f12e-276">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7f12e-276">Related topics</span></span>

[<span data-ttu-id="7f12e-277">Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-277">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="7f12e-278">Planejar conectividade híbrida entre o Skype for Business Server e o Office 365</span><span class="sxs-lookup"><span data-stu-id="7f12e-278">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="7f12e-279">Dar suporte a funcionários remotos usando o Teams</span><span class="sxs-lookup"><span data-stu-id="7f12e-279">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="7f12e-280">Trabalhar remotamente com o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7f12e-280">Work remotely with Microsoft 365</span></span>](https://aka.ms/remote-work)