---
title: Implantar o Microsoft Teams primeiro
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
description: Use esta orientação para implementar o Microsoft Teams como sua primeira carga de trabalho do Office 365.
ROBOTS: NOINDEX, NOFOLLOW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79607004c8f750ceed0325733c8c52a4873e9cdc
ms.sourcegitcommit: 89a7c0427a5abbef838a17ae7eac6934c6176a35
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2020
ms.locfileid: "42982148"
---
# <a name="roll-out-microsoft-teams-first"></a><span data-ttu-id="40267-103">Implantar o Microsoft Teams primeiro</span><span class="sxs-lookup"><span data-stu-id="40267-103">Roll out Microsoft Teams First</span></span>

<span data-ttu-id="40267-104">O Microsoft Teams pode ajudar seus funcionários a ficar conectados e colaborar uns com os outros, especialmente no momento atual sem precedentes, em que o trabalho remoto é uma realidade dos funcionários do mundo todo.</span><span class="sxs-lookup"><span data-stu-id="40267-104">Microsoft Teams can help your employees stay connected and collaborate with each other, especially in the current unprecedented time where remote work is a reality of employees around the world.</span></span> <span data-ttu-id="40267-105">Poder conversar, fazer reuniões com vídeo e colaborar em documentos do Office dentro do teams pode ajudar as empresas a se manterem produtivas.</span><span class="sxs-lookup"><span data-stu-id="40267-105">Being able to chat, do video meetings and collaborate on Office documents within Teams can help companies stay productive.</span></span> <span data-ttu-id="40267-106">Seja você uma pequena empresa, uma organização sem fins lucrativos ou de grande porte, você pode começar a usar o Microsoft Teams como a primeira carga de trabalho do pacote do Office 365 antes de implantar qualquer outro aplicativo ou serviço do Office.</span><span class="sxs-lookup"><span data-stu-id="40267-106">Whether you are a small business, a non-profit or a large organization, you can get started with Teams as the first workload within Office 365 suite before deploying any other Office app or service.</span></span>

<span data-ttu-id="40267-107">Este artigo detalha as considerações que você deve fazer com a abordagem "Teams First".</span><span class="sxs-lookup"><span data-stu-id="40267-107">This article details the considerations you must make with the "Teams First" approach.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40267-108">Embora as equipes possam ser a primeira carga de trabalho implantada na nuvem da sua organização, a implantação de equipes deve fazer parte da estratégia geral de implantação de nuvem.</span><span class="sxs-lookup"><span data-stu-id="40267-108">While Teams can be your organization's first cloud deployed workload, deploying Teams should be part of your overall cloud deployment strategy.</span></span>

<span data-ttu-id="40267-109">Se você já tiver feito outros serviços do Office 365 e o Teams for a sua próxima carga de trabalho a ser distribuída (em vez do primeiro), comece com [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="40267-109">If you have already rolled out other Office 365 services and Teams is your next workload to roll out (instead of the first), start with [How to roll out  Teams](How-to-roll-out-teams.md).</span></span>

## <a name="start-here"></a><span data-ttu-id="40267-110">Comece aqui</span><span class="sxs-lookup"><span data-stu-id="40267-110">Start here</span></span>

<span data-ttu-id="40267-111">Para começar a usar sua primeira implantação do Microsoft Teams, você precisará atender a pelo menos alguns pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="40267-111">To get started with your Teams First deployment you will need to meet at minimum some pre-requisites.</span></span> <span data-ttu-id="40267-112">A lista a seguir mostrará o que você deve ter em vigor para a sua organização para que as equipes possam ser habilitadas:</span><span class="sxs-lookup"><span data-stu-id="40267-112">The following list will show what you must have in place for your organization before Teams can be enabled:</span></span>

1.  <span data-ttu-id="40267-113">Um locatário do Office 365 configurado com seu nome de domínio</span><span class="sxs-lookup"><span data-stu-id="40267-113">An Office 365 tenant configured with your domain name</span></span>

2.  <span data-ttu-id="40267-114">Conectividade do Azure Active Directory (AAD Connect) ou solução de sincronização de identidade de nuvem semelhante – com todos os atributos necessários sincronizados com seu locatário</span><span class="sxs-lookup"><span data-stu-id="40267-114">Azure Active Directory connectivity (AAD connect) or similar cloud identity sync solution – with all required attributes synched with your tenant</span></span>  
    <span data-ttu-id="40267-115">Para entender os atributos sincronizados com a sincronização do AAD, leia a [sincronização do Azure ad Connect: atributos sincronizados com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span><span class="sxs-lookup"><span data-stu-id="40267-115">To understand the attributes synchronized with AAD sync, read [Azure AD Connect sync: Attributes synchronized to Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)</span></span>

3.  <span data-ttu-id="40267-116">Licenças de usuário adequadas atribuídas para Teams</span><span class="sxs-lookup"><span data-stu-id="40267-116">Appropriate user licenses assigned for Teams</span></span>  
    <span data-ttu-id="40267-117">Para entender o licenciamento do Teams, leia [o licenciamento do Office 365 para Microsoft Teams](office-365-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="40267-117">To understand Teams licensing, read [Office 365 licensing for Microsoft Teams](office-365-licensing.md)</span></span>

4.  <span data-ttu-id="40267-118">Rede da organização preparada para equipes</span><span class="sxs-lookup"><span data-stu-id="40267-118">Organization's network prepared for Teams</span></span>  
    <span data-ttu-id="40267-119">Para entender a preparação da rede, leia [preparar a rede da sua organização para equipes](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="40267-119">To understand network preparation, read [Prepare your organization's network for Teams](prepare-network.md).</span></span>

5.  <span data-ttu-id="40267-120">Permitir o acesso à rede para o Exchange, SharePoint e OneDrive for Business no Office 365: [URLs e intervalos de endereços IP do office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="40267-120">Allow network access to Exchange, Sharepoint, and OneDrive for Business in Office 365: [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

> [!NOTE]
> <span data-ttu-id="40267-121">Os locatários criados após 1º de setembro de 2019 são provisionados no modo somente Teams.</span><span class="sxs-lookup"><span data-stu-id="40267-121">Tenants created after September 1, 2019 are provisioned in Teams Only mode.</span></span>
> 
> [!IMPORTANT]
> <span data-ttu-id="40267-122">Se você tiver o Skype for Business Server implantado e seu locatário tiver sido provisionado após 1º de setembro de 2019, entre em contato com o suporte Premier para habilitar os recursos de coexistência do teams.</span><span class="sxs-lookup"><span data-stu-id="40267-122">If you have Skype for Business Server deployed, and your tenant was provisioned AFTER September 1, 2019, please contact premier support to enable coexistence capabilities for Teams.</span></span> <span data-ttu-id="40267-123">Verifique se a "política de atualização da organização" está definida como ' Island Mode ' <span class="underline">antes</span> de atribuir licenças de equipe a um usuário.</span><span class="sxs-lookup"><span data-stu-id="40267-123">Make sure your 'Organization wide upgrade policy' is set to 'Island mode' <span class="underline">before</span> you assign any Teams licenses to a user.</span></span>

## <a name="migration-starting-points"></a><span data-ttu-id="40267-124">Pontos de partida de migração</span><span class="sxs-lookup"><span data-stu-id="40267-124">Migration Starting points</span></span>

<span data-ttu-id="40267-125">Sua jornada ao Office 365 e recursos disponíveis no Microsoft Teams, dependendo do seu ponto de partida e da existência do Skype for Business ou do Lync Server local.</span><span class="sxs-lookup"><span data-stu-id="40267-125">Your journey to Office 365 and features available in Teams depending on your starting point and the existence of on premises Skype for Business or Lync server.</span></span> <span data-ttu-id="40267-126">As seções a seguir detalham os recursos básicos e as opções de configuração, além dos pré-requisitos anteriores.</span><span class="sxs-lookup"><span data-stu-id="40267-126">The following sections will detail basic capabilities and configuration options in addition to the pre-requisites above.</span></span> <span data-ttu-id="40267-127">Dividimos os cenários de ponto de partida nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="40267-127">We have broken down the starting point scenarios to the following topics:</span></span>

<span data-ttu-id="40267-128">**Configuração de equipes de locatário**: os modos locatário e usuário são usados para controlar o comportamento do destinatário.</span><span class="sxs-lookup"><span data-stu-id="40267-128">**Tenant Teams Configuration**: Tenant and user modes are used to control the recipient's behavior.</span></span> <span data-ttu-id="40267-129">Essas configurações podem ser atribuídas no nível do locatário ou no nível do usuário em uma organização.</span><span class="sxs-lookup"><span data-stu-id="40267-129">These settings can be assigned on the tenant level or the user level in an organization.</span></span> <span data-ttu-id="40267-130">Para saber mais, leia [coexistência com o Skype for Business](coexistence-chat-calls-presence.md).</span><span class="sxs-lookup"><span data-stu-id="40267-130">To learn more, read [Coexistence with Skype for Business](coexistence-chat-calls-presence.md).</span></span>

<span data-ttu-id="40267-131">**Chat/comunicação externa no Teams**: os serviços de chat fazem referência a conversas de chat ponto a ponto ou em grupo dentro e organização ou externamente à organização.</span><span class="sxs-lookup"><span data-stu-id="40267-131">**Chat / External communication in Teams**: Chat services refer to peer to peer or group chat conversations within and organization or externally to the organization.</span></span> <span data-ttu-id="40267-132">A comunicação externa também é conhecida como Federação no Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="40267-132">External communication is also referred to as federation in Skype for Business.</span></span>

<span data-ttu-id="40267-133">**Criar e exibir reuniões no Microsoft Teams**: um usuário sempre pode criar reuniões online por meio do suplemento do Outlook Teams e do dial-in PSTN está disponível em todos os cenários depois que o usuário é licenciado.</span><span class="sxs-lookup"><span data-stu-id="40267-133">**Create and view meetings in Teams**: A user can always create online meetings via the Outlook Teams add-in and PSTN dial-in is available in all scenarios once the user is licensed.</span></span> <span data-ttu-id="40267-134">Teams e informações de calendário do Skype for Business Store na caixa de correio do Exchange do usuário.</span><span class="sxs-lookup"><span data-stu-id="40267-134">Teams and Skype for Business store calendaring information in the user's Exchange mailbox.</span></span> <span data-ttu-id="40267-135">No Exchange Server local, o Exchange Server 2016 CU3 ou superior para o cliente do teams deve ser capaz de interagir com a caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="40267-135">On premises Exchange server must be Exchange Server 2016 CU3 or above for the Teams client to be able to interact with the user's mailbox.</span></span> <span data-ttu-id="40267-136">Sem acesso à caixa de correio do Exchange o ícone de calendário no Teams não será exibido e ele não poderá exibir, criar ou modificar reuniões no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="40267-136">Without Exchange mailbox access the Calendar icon in Teams will not appear and they user will not be able to view, create or modify meetings in the Teams client.</span></span>

<span data-ttu-id="40267-137">**Recursos de chamada VoIP/PSTN no Teams**: as chamadas podem ser VoIP ou rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="40267-137">**Calling features VoIP / PSTN in Teams**: Calling can be Voice over IP (VoIP) or Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="40267-138">A conectividade de VoIP acontece nativamente entre clientes do Teams, enquanto a conectividade PSTN ocorre quando um usuário disca para um número de telefone externo.</span><span class="sxs-lookup"><span data-stu-id="40267-138">VoIP connectivity happens natively between Teams clients, while PSTN connectivity happen when a user dials an outside phone number.</span></span>  

<span data-ttu-id="40267-139">O Microsoft Teams dá suporte a dois tipos de conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="40267-139">Teams support two types of PSTN connectivity.</span></span> <span data-ttu-id="40267-140">Plano de chamadas da Microsoft, quando a Microsoft fornece uma infraestrutura de telefonia, incluindo o número de telefone de um usuário ou configuração de roteamento direto, em que o cliente fornece a conectividade de telefonia em um controlador de borda de sessão (SBC) para o usuário do teams.</span><span class="sxs-lookup"><span data-stu-id="40267-140">Microsoft Calling Plan, when Microsoft provides telephony infrastructure including the phone number for a user, or Direct Routing configuration, where the customer provides the telephony connectivity over a Session Border Controller (SBC) for the Teams user.</span></span>  
<span data-ttu-id="40267-141">Para saber mais, leia [qual plano de chamadas é ideal para você?](calling-plan-landing-page.md) e [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="40267-141">To learn more, read [Which Calling Plan is right for you?](calling-plan-landing-page.md) and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

<span data-ttu-id="40267-142">**Colaboração entre equipes e canais no Teams**: no Teams, o Teams é um grupo de pessoas reunidas para trabalho, projetos ou interesses comuns.</span><span class="sxs-lookup"><span data-stu-id="40267-142">**Teams and Channels collaboration in Teams**: In Teams, teams are groups of people brought together for work, projects, or common interests.</span></span> <span data-ttu-id="40267-143">As equipes são compostas de canais.</span><span class="sxs-lookup"><span data-stu-id="40267-143">Teams are made up of channels.</span></span> <span data-ttu-id="40267-144">Cada canal é criado em torno de um tópico, como "eventos da equipe", um nome de departamento ou apenas para diversão.</span><span class="sxs-lookup"><span data-stu-id="40267-144">Each channel is built around a topic, like "Team Events," a department name, or just for fun.</span></span> <span data-ttu-id="40267-145">Os canais são onde você mantém reuniões, têm conversas e trabalham em arquivos juntos.</span><span class="sxs-lookup"><span data-stu-id="40267-145">Channels are where you hold meetings, have conversations, and work on files together.</span></span> <span data-ttu-id="40267-146">Durante a colaboração</span><span class="sxs-lookup"><span data-stu-id="40267-146">During collaboration</span></span>

<span data-ttu-id="40267-147">**Onedrive for Business (compartilhamento de arquivos P2P) no Teams**: fora de equipes e canais, os usuários do teams podem compartilhar arquivos ponto a ponto usando o onedrive for Business ou outros programas de compartilhamento ponto a ponto, como arquivos Citrix, Dropbox, Box e Google Drive.</span><span class="sxs-lookup"><span data-stu-id="40267-147">**OneDrive for Business (P2P file sharing) in Teams**: Outside of Teams and Channels, Teams users can share files peer-to-peer using OneDrive for business or other P2P sharing file programs such as Citrix Files, DropBox, Box and Google Drive.</span></span> <span data-ttu-id="40267-148">Para o OneDrive for Business, um usuário deve ter uma licença do SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="40267-148">For OneDrive for business a user must have SharePoint Online license assigned.</span></span>

<span data-ttu-id="40267-149">**Plataforma do aplicativo**: os aplicativos fornecem ferramentas de ponta de tudo para a sua organização para tirar o máximo proveito do teams.</span><span class="sxs-lookup"><span data-stu-id="40267-149">**Application Platform**: Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="40267-150">Esses aplicativos combinam a funcionalidade de guias, extensões de mensagens, conectores e bots fornecidos pela Microsoft, criados por um terceiro ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="40267-150">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="40267-151">**Recursos de segurança e conformidade:** O Teams tem uma ampla gama de informações para ajudá-lo com áreas de conformidade, incluindo políticas de retenção, proteção contra perda de dados (DLP), descoberta eletrônica e retenção legal para canais, chats e arquivos, pesquisa de logs de auditoria.</span><span class="sxs-lookup"><span data-stu-id="40267-151">**Security and Compliance features:** Teams has a wide range of information to help you with compliance areas, including retention policies, Data Loss Protection (DLP), eDiscovery and legal hold for channels, chats and files, audit log search.</span></span> <span data-ttu-id="40267-152">Para saber mais, leia sobre [segurança e conformidade no Microsoft Teams](security-compliance-overview.md).</span><span class="sxs-lookup"><span data-stu-id="40267-152">To learn more, read [Security and compliance in Microsoft Teams](security-compliance-overview.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="40267-153">Os recursos avançados de descoberta eletrônica exigem licenciamento e5.</span><span class="sxs-lookup"><span data-stu-id="40267-153">Advance eDiscovery features require E5 licensing.</span></span>

<span data-ttu-id="40267-154">[Compare as opções de licenciamento](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span><span class="sxs-lookup"><span data-stu-id="40267-154">[Compare licensing options](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).</span></span>

<span data-ttu-id="40267-155">Saiba [como o Exchange e o Microsoft Teams interagem](exchange-teams-interact.md) para saber quais recursos de conformidade estão disponíveis no seu cenário.</span><span class="sxs-lookup"><span data-stu-id="40267-155">Read [How Exchange and Microsoft Teams interact](exchange-teams-interact.md) to learn which compliance features are available in your scenario.</span></span>

## <a name="organizations-span-classunderlinewithoutspan-skype-for-business-or-lync-server"></a><span data-ttu-id="40267-156">Organizações **<span class="underline">sem</span>** o Skype for Business ou o Lync Server</span><span class="sxs-lookup"><span data-stu-id="40267-156">Organizations **<span class="underline">without</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="40267-157">Este ponto de partida pressupõe que sua organização não use o Skype for Business ou o Lync Server atualmente, e o Teams será o seu primeiro aplicativo no Office 365.</span><span class="sxs-lookup"><span data-stu-id="40267-157">This starting point assumes that your organization does not utilize Skype for Business or Lync server currently and Teams will be your first application in Office 365.</span></span> <span data-ttu-id="40267-158">A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final do teams para serviços essenciais.</span><span class="sxs-lookup"><span data-stu-id="40267-158">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="40267-159">Item</span><span class="sxs-lookup"><span data-stu-id="40267-159">Item</span></span></th>
<th><span data-ttu-id="40267-160">Observações</span><span class="sxs-lookup"><span data-stu-id="40267-160">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="40267-161">Configuração de equipes de locatários</span><span class="sxs-lookup"><span data-stu-id="40267-161">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="40267-162">Modo somente equipes, todos os recursos de chat e chamadas estão apenas nas equipes</span><span class="sxs-lookup"><span data-stu-id="40267-162">Teams Only mode, all chat and calling features are in Teams Only</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-163">Chat/comunicação externa no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-163">Chat / External Communication in Teams</span></span></td>
<td><p><span data-ttu-id="40267-164">O locatário interno (intra Office 365) e a comunicação de chat externa possíveis do teams</span><span class="sxs-lookup"><span data-stu-id="40267-164">Internal (intra Office 365 tenant) and external chat communication possible from Teams</span></span></p>
<p><span data-ttu-id="40267-165"><em>Observação: as entradas DNS devem ser configuradas para acesso externo.</span><span class="sxs-lookup"><span data-stu-id="40267-165"><em>Note: DNS entries must be configured for external access.</span></span> <span data-ttu-id="40267-166">Os registros DNS do Skype for Business são necessários, mesmo que você não tenha o Skype for Business no local ou o Office 365 para permitir a Federação com ambientes do Lync e do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="40267-166">Skype for Business DNS records are needed even though you don't have Skype for Business on-premises or in Office 365 to allow federation with Lync and Skype for Business environments.</span></span><br /><span data-ttu-id="40267-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">Registros de sistema de nome de domínio externo do Office 365</a></em></span><span class="sxs-lookup"><span data-stu-id="40267-167">
<a href="https://docs.microsoft.com/office365/enterprise/external-domain-name-system-records">External Domain Name System records for Office 365</a></em></span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="40267-168"><em>Criar e exibir reuniões no Microsoft Teams</em></span><span class="sxs-lookup"><span data-stu-id="40267-168"><em>Create and view Meetings in Teams</em></span></span></td>
<td><p><span data-ttu-id="40267-169"><em>Capaz de criar reuniões via suplemento do Outlook</em></span><span class="sxs-lookup"><span data-stu-id="40267-169"><em>Able to create meetings via Outlook add-in</em></span></span></p>
<p><span data-ttu-id="40267-170"><em>O recurso de discagem PSTN e conexão discada está disponível com as licenças de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="40267-170"><em>PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="40267-171">Observação: o acesso ao calendário do teams requer o Exchange 2016 CU3 implantado no local com o Exchange Hybrid establishs: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">criar uma implantação híbrida com o assistente de configuração híbrida</a></span><span class="sxs-lookup"><span data-stu-id="40267-171">Note: Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established: <a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span><br />
<span data-ttu-id="40267-172">Além da configuração híbrida do Exchange, estabelecer a autenticação OAuth do Exchange: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configurar a autenticação OAuth entre organizações Exchange e Exchange Online</a></em></span><span class="sxs-lookup"><span data-stu-id="40267-172">In addition to Exchange hybrid configuration, establish Exchange OAuth authentication: <a href="https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help">Configure OAuth authentication between Exchange and Exchange Online organizations</a></em></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-173">Recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="40267-173">Calling Features</span></span><br />
<span data-ttu-id="40267-174">VoIP/PSTN no Teams</span><span class="sxs-lookup"><span data-stu-id="40267-174">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="40267-175">VoIP interna e externamente para o locatário está disponível</span><span class="sxs-lookup"><span data-stu-id="40267-175">VoIP internally and externally to the tenant is available</span></span></p>
<p><span data-ttu-id="40267-176">Os serviços PSTN podem ser configurados pelo sistema telefônico da Microsoft, além de adicionar um plano de chamadas da Microsoft ou roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="40267-176">PSTN services can be configured via Microsoft Phone System, plus adding a Microsoft Calling Plan or Direct Routing.</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="40267-177">Colaboração entre equipes e canais no Teams</span><span class="sxs-lookup"><span data-stu-id="40267-177">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="40267-178">Para ter experiência total, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="40267-178">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="40267-179">A migração de sites do SharePoint locais existentes não é necessária.</span><span class="sxs-lookup"><span data-stu-id="40267-179">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-180">OneDrive for Business (compartilhamento de arquivos P2P)</span><span class="sxs-lookup"><span data-stu-id="40267-180">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="40267-181">O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="40267-181">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="40267-182">Sem essa licença, o compartilhamento de arquivos ponto a ponto não será possível.</span><span class="sxs-lookup"><span data-stu-id="40267-182">Without this license peer-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="40267-183">Plataforma do aplicativo</span><span class="sxs-lookup"><span data-stu-id="40267-183">Application platform</span></span></td>
<td><span data-ttu-id="40267-184">Os usuários poderão usar os aplicativos designados para eles de acordo com as políticas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="40267-184">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="40267-185">Saiba mais aqui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configurações de administrador para aplicativos no Microsoft Teams</a></span><span class="sxs-lookup"><span data-stu-id="40267-185">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-186">Recursos de segurança e conformidade</span><span class="sxs-lookup"><span data-stu-id="40267-186">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="40267-187">Políticas de retenção estão disponíveis</span><span class="sxs-lookup"><span data-stu-id="40267-187">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="40267-188">a descoberta eletrônica e a retenção legal para conformidade com mensagens de canal são aceitas</span><span class="sxs-lookup"><span data-stu-id="40267-188">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="40267-189">Políticas de prevenção contra perda de dados (DLP) estão disponíveis</span><span class="sxs-lookup"><span data-stu-id="40267-189">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="40267-190">Conjunto de recursos completo disponível com o Exchange Online, o Exchange local oferece suporte para a maioria desses recursos, consulte</span><span class="sxs-lookup"><span data-stu-id="40267-190">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="40267-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem</a></span><span class="sxs-lookup"><span data-stu-id="40267-191"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<p><span data-ttu-id="40267-192">para obter uma lista completa</span><span class="sxs-lookup"><span data-stu-id="40267-192">for full list</span></span></p></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-without-skype-for-business-or-lync-server"></a><span data-ttu-id="40267-193">Etapas de capacitação para organizações sem o Skype for Business ou o Lync Server</span><span class="sxs-lookup"><span data-stu-id="40267-193">Enablement steps for organizations without Skype for Business or Lync Server</span></span>

1.  <span data-ttu-id="40267-194">Conheça pré-requisitos detalhados descritos na seção iniciar aqui acima</span><span class="sxs-lookup"><span data-stu-id="40267-194">Meet pre-requisites detailed in the Start Here section above</span></span>

2.  <span data-ttu-id="40267-195">Alternar locatário para o modo somente do Teams (somente para locatários existentes): [Configurando suas configurações de coexistência e atualização](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="40267-195">Switch tenant into Teams Only mode (for existing tenants only): [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

3.  <span data-ttu-id="40267-196">Configure seu locatário de acordo com as políticas de negócios/empresa da sua empresa: [gerenciar as configurações do Microsoft Teams para sua organização](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="40267-196">Configure your tenant in accordance with your company's business/company policies: [Manage Microsoft Teams settings for your organization](enable-features-office-365.md).</span></span>

4.  <span data-ttu-id="40267-197">Implantar o cliente do teams para seus usuários: [obter clientes para Teams](get-clients.md)</span><span class="sxs-lookup"><span data-stu-id="40267-197">Deploy the Teams client to your users: [Get clients for Teams](get-clients.md)</span></span>

5.  <span data-ttu-id="40267-198">Orientar o programa de adoção</span><span class="sxs-lookup"><span data-stu-id="40267-198">Drive your adoption program</span></span>  
    [<span data-ttu-id="40267-199">Adotar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-199">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="40267-200">Lista de verificação de início rápido da adoção do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-200">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="40267-201">Começar a mover outras cargas de trabalho para o Office 365</span><span class="sxs-lookup"><span data-stu-id="40267-201">Begin planning moving other workloads to Office 365</span></span>

## <a name="organizations-span-classunderlinewithspan-skype-for-business-or-lync-server"></a><span data-ttu-id="40267-202">Organizações **<span class="underline">com</span>** o Skype for Business ou o Lync Server</span><span class="sxs-lookup"><span data-stu-id="40267-202">Organizations **<span class="underline">with</span>** Skype for Business or Lync server</span></span>

<span data-ttu-id="40267-203">Este ponto de partida pressupõe que sua organização utilize o Skype for Business 2019 ou 2015 + ou o Lync 2013 + Server no local.</span><span class="sxs-lookup"><span data-stu-id="40267-203">This starting point assumes that your organization utilizes Skype for Business 2019 or 2015+ or Lync 2013+ server on premises.</span></span> <span data-ttu-id="40267-204">Já temos uma ampla orientação para as organizações que migram de servidores locais para o Microsoft Teams e devem ser seguidas nesses cenários.</span><span class="sxs-lookup"><span data-stu-id="40267-204">We already have extensive guidance for organizations migrating from on premises servers to Teams and it should be followed for these scenarios.</span></span> <span data-ttu-id="40267-205">Esta orientação é específica do cenário que o Microsoft Teams é o primeiro aplicativo que você usa no Office 365.</span><span class="sxs-lookup"><span data-stu-id="40267-205">This guidance is specific to the scenario that Teams is the first application you utilize in Office 365.</span></span> <span data-ttu-id="40267-206">A tabela a seguir detalha a configuração de alto nível e os recursos do usuário final do teams para serviços essenciais.</span><span class="sxs-lookup"><span data-stu-id="40267-206">The following table details high level configuration and end user capabilities for Teams for core services.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="40267-207">Item</span><span class="sxs-lookup"><span data-stu-id="40267-207">Item</span></span></th>
<th><span data-ttu-id="40267-208">Observações</span><span class="sxs-lookup"><span data-stu-id="40267-208">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="40267-209">Configuração de equipes de locatários</span><span class="sxs-lookup"><span data-stu-id="40267-209">Tenant Teams configuration</span></span></td>
<td><span data-ttu-id="40267-210">Modo de ilhas</span><span class="sxs-lookup"><span data-stu-id="40267-210">Islands mode</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-211">Chat/comunicação externa no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-211">Chat / External Communication in Teams</span></span></td>
<td><span data-ttu-id="40267-212">Interno somente dentro de seu próprio locatário, a comunicação externa (Federação) está via sua implantação do Skype for Business ou do Lync Server</span><span class="sxs-lookup"><span data-stu-id="40267-212">Internal within your own tenant only, external communication (federation) is via your Skype for Business or Lync server deployment</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="40267-213">Criar e exibir reuniões no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-213">Create and view Meetings in Teams</span></span></td>
<td><p><span data-ttu-id="40267-214">Capaz de criar reuniões via suplemento do Outlook</span><span class="sxs-lookup"><span data-stu-id="40267-214">Able to create meetings via Outlook add-in</span></span></p>
<p><span data-ttu-id="40267-215">O recurso de discagem PSTN e conexão discada está disponível com as licenças de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="40267-215">PSTN Dial in and Dial out capability is available with the Audio Conferencing licenses.</span></span><br />
<span data-ttu-id="40267-216">O acesso ao calendário de equipes requer o Exchange 2016 CU3 local instalado com o Exchange Hybrid estabelecido:</span><span class="sxs-lookup"><span data-stu-id="40267-216">Teams calendar access requires Exchange 2016 CU3+ on-premises deployed with Exchange hybrid established:</span></span><br /><span data-ttu-id="40267-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Criar uma implantação híbrida com o assistente de configuração híbrida</a></span><span class="sxs-lookup"><span data-stu-id="40267-217">
<a href="https://docs.microsoft.com/exchange/hybrid-deployment/deploy-hybrid">Create a hybrid deployment with the Hybrid Configuration wizard</a></span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-218">Recursos de chamada</span><span class="sxs-lookup"><span data-stu-id="40267-218">Calling Features</span></span><br />
<span data-ttu-id="40267-219">VoIP/PSTN no Teams</span><span class="sxs-lookup"><span data-stu-id="40267-219">VoIP / PSTN in Teams</span></span></td>
<td><p><span data-ttu-id="40267-220">VoIP internamente para o locatário está disponível</span><span class="sxs-lookup"><span data-stu-id="40267-220">VoIP internally to the tenant is available</span></span></p>
<p><span data-ttu-id="40267-221">Os serviços de PSTN ou de plano de chamada não estão disponíveis até que o usuário seja movido para a experiência apenas com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-221">PSTN or Calling Plan services are not available until the user is moved to Teams Only experience</span></span></p></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="40267-222">Colaboração entre equipes e canais no Teams</span><span class="sxs-lookup"><span data-stu-id="40267-222">Teams and Channels collaboration in Teams</span></span></td>
<td><p><span data-ttu-id="40267-223">Para ter experiência total, incluindo recursos de conformidade, uma licença do SharePoint Online precisa ser atribuída ao usuário.</span><span class="sxs-lookup"><span data-stu-id="40267-223">For full experience, including compliance features, a SharePoint Online license need to be assigned to the user.</span></span></p>
<p><span data-ttu-id="40267-224">A migração de sites do SharePoint locais existentes não é necessária.</span><span class="sxs-lookup"><span data-stu-id="40267-224">Migration of existing on-premises SharePoint sites is not required.</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-225">OneDrive for Business (compartilhamento de arquivos P2P)</span><span class="sxs-lookup"><span data-stu-id="40267-225">OneDrive for Business (P2P file sharing)</span></span></td>
<td><span data-ttu-id="40267-226">O OneDrive for Business exige que um usuário tenha uma licença do SharePoint Online atribuída.</span><span class="sxs-lookup"><span data-stu-id="40267-226">OneDrive for Business requires a user to have a SharePoint Online license assigned.</span></span> <span data-ttu-id="40267-227">Sem essa licença, o compartilhamento de arquivos por ponto não será possível.</span><span class="sxs-lookup"><span data-stu-id="40267-227">Without this license per-to-peer file sharing will not be possible.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="40267-228">Plataforma do aplicativo</span><span class="sxs-lookup"><span data-stu-id="40267-228">Application platform</span></span></td>
<td><span data-ttu-id="40267-229">Os usuários poderão usar os aplicativos designados para eles de acordo com as políticas da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="40267-229">Users will be able to use the apps that are designated available for them according to your company policies.</span></span><br />
<span data-ttu-id="40267-230">Saiba mais aqui: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">configurações de administrador para aplicativos no Microsoft Teams</a></span><span class="sxs-lookup"><span data-stu-id="40267-230">Learn more here: <a href="https://docs.microsoft.com/microsoftteams/admin-settings">Admin settings for apps in Teams</a></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="40267-231">Recursos de segurança e conformidade</span><span class="sxs-lookup"><span data-stu-id="40267-231">Security and Compliance features</span></span></td>
<td><ul>
<li><p><span data-ttu-id="40267-232">Políticas de retenção estão disponíveis</span><span class="sxs-lookup"><span data-stu-id="40267-232">Retention policies are available</span></span></p></li>
<li><p><span data-ttu-id="40267-233">a descoberta eletrônica e a retenção legal para conformidade com mensagens de canal são aceitas</span><span class="sxs-lookup"><span data-stu-id="40267-233">eDiscovery and Legal Hold for compliance on channel messages is supported</span></span></p></li>
<li><p><span data-ttu-id="40267-234">Políticas de prevenção contra perda de dados (DLP) estão disponíveis</span><span class="sxs-lookup"><span data-stu-id="40267-234">Data Loss Prevention policies (DLP) are available</span></span></p></li>
</ul>
<p><span data-ttu-id="40267-235">Conjunto de recursos completo disponível com o Exchange Online, o Exchange local oferece suporte para a maioria desses recursos, consulte</span><span class="sxs-lookup"><span data-stu-id="40267-235">Full feature set available with Exchange Online, Exchange on-premises supports most of these features, see</span></span></p>
<p><span data-ttu-id="40267-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">Como o Exchange e o Teams interagem</a></span><span class="sxs-lookup"><span data-stu-id="40267-236"><a href="https://docs.microsoft.com/MicrosoftTeams/exchange-teams-interact">How Exchange and Teams interact</a></span></span></p>
<ul>
<li><p><span data-ttu-id="40267-237">para obter uma lista completa</span><span class="sxs-lookup"><span data-stu-id="40267-237">for full list</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

### <a name="enablement-steps-for-organizations-with-skype-for-business-server"></a><span data-ttu-id="40267-238">Etapas de capacitação para organizações com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="40267-238">Enablement steps for organizations with Skype for Business Server</span></span>  

1.  <span data-ttu-id="40267-239">Conheça pré-requisitos detalhados na seção início aqui.</span><span class="sxs-lookup"><span data-stu-id="40267-239">Meet pre-requisites detailed in the Start Here section above.</span></span>

2.  <span data-ttu-id="40267-240">Alternar o locatário para o modo de ilhas (para locatários provisionados após 9/1/2019, entre em contato com o suporte Premier para fazer essa alteração)</span><span class="sxs-lookup"><span data-stu-id="40267-240">Switch tenant into Islands mode (for tenants provisioned AFTER 9/1/2019, please contact premier support to make this change)</span></span>  
    [<span data-ttu-id="40267-241">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="40267-241">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

3.  <span data-ttu-id="40267-242">Configurar seu locatário de acordo com as políticas de negócios/empresa da empresa</span><span class="sxs-lookup"><span data-stu-id="40267-242">Configure your tenant in accordance with your company's business/company policies</span></span>  
    [<span data-ttu-id="40267-243">Gerenciar as configurações do Microsoft Teams para sua organização</span><span class="sxs-lookup"><span data-stu-id="40267-243">Manage Microsoft Teams settings for your organization</span></span>](enable-features-office-365.md)

4.  <span data-ttu-id="40267-244">Implantar o cliente do teams</span><span class="sxs-lookup"><span data-stu-id="40267-244">Deploy the Teams client</span></span>  
    [<span data-ttu-id="40267-245">Obter clientes para o Teams</span><span class="sxs-lookup"><span data-stu-id="40267-245">Get clients for Teams</span></span>](get-clients.md)

5.   <span data-ttu-id="40267-246">Orientar o programa de adoção</span><span class="sxs-lookup"><span data-stu-id="40267-246">Drive your adoption program</span></span>  
    [<span data-ttu-id="40267-247">Adotar o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-247">Adopt Microsoft Teams</span></span>](adopt-microsoft-teams-landing-page.md)
    
    [<span data-ttu-id="40267-248">Lista de verificação de início rápido da adoção do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-248">Microsoft Teams adoption quick start checklist</span></span>](teams-adoption-quick-start-checklist.md)

6.  <span data-ttu-id="40267-249">Começar a mover outras cargas de trabalho para o Office 365</span><span class="sxs-lookup"><span data-stu-id="40267-249">Begin planning moving other workloads to Office 365</span></span>

7.  <span data-ttu-id="40267-250">Estabeleça o Skype for Business Hybrid e siga os caminhos de atualização recomendados para o Skype for Business e para os servidores Lync</span><span class="sxs-lookup"><span data-stu-id="40267-250">Establish Skype for Business hybrid and follow the recommended upgrade paths for Skype for Business and Lync servers</span></span>  
    [<span data-ttu-id="40267-251">Atualize o Skype for Business no local para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-251">Upgrade from Skype for Business on-premises to Teams</span></span>](upgrade-to-teams-execute-skypeforbusinesshybridonprem.md)

## <a name="closing-statement"></a><span data-ttu-id="40267-252">Instrução de fechamento</span><span class="sxs-lookup"><span data-stu-id="40267-252">Closing statement</span></span>

<span data-ttu-id="40267-253">O Microsoft Teams pode ser um habilitador para sua organização reunir todos os funcionários, operadores de informações e trabalhadores de primeira mão, juntos em uma única plataforma.</span><span class="sxs-lookup"><span data-stu-id="40267-253">Microsoft Teams can be an enabler for your organization to bring all the employees, information workers and Firstline workers, together on a single platform.</span></span> <span data-ttu-id="40267-254">Você pode [começar](https://products.office.com/microsoft-teams/group-chat-software) hoje mesmo.</span><span class="sxs-lookup"><span data-stu-id="40267-254">You can [get started](https://products.office.com/microsoft-teams/group-chat-software) today.</span></span> <span data-ttu-id="40267-255">Você pode manter contato com todos os nossos comunicados mais recentes e atualizações de produtos mensais [aqui](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span><span class="sxs-lookup"><span data-stu-id="40267-255">You can keep in touch with all our latest announcements and monthly product updates [here](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog).</span></span>

<span data-ttu-id="40267-256">Além disso, como as empresas de todo o mundo estão gerenciando a situação COVID-19 atual, criamos uma série de conteúdo que ajudará você a usar o Microsoft Teams para obter o máximo de impacto em sua organização.</span><span class="sxs-lookup"><span data-stu-id="40267-256">Additionally, as companies around the world are managing the current COVID-19 situation, we have created a series of content that will help you utilize Teams for the maximum impact in your organization.</span></span>

  - <span data-ttu-id="40267-257">Nosso [compromisso com os clientes durante a COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span><span class="sxs-lookup"><span data-stu-id="40267-257">Our [commitment to customers during COVID-19](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/05/our-commitment-to-customers-during-covid-19/)</span></span>

  - [<span data-ttu-id="40267-258">duas semanas em: o que aprendemos sobre o trabalho remoto</span><span class="sxs-lookup"><span data-stu-id="40267-258">2 weeks in: what we've learned about remote work</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/18/making-the-switch-to-remote-work-5-things-weve-learned/)

  - [<span data-ttu-id="40267-259">Fornecendo reuniões e eventos online</span><span class="sxs-lookup"><span data-stu-id="40267-259">Delivering online meetings and events</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/delivering-online-meetings-events/)

  - [<span data-ttu-id="40267-260">Ajudar empresas de pequeno e médio porte a trabalhar remotamente com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-260">Helping small and medium-sized businesses work remotely with Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/17/helping-smb-customers-work-remotely-microsoft-teams/)

  - [<span data-ttu-id="40267-261">Transformação digital de eventos dinâmicos: Bob Bejan observações do Frontline</span><span class="sxs-lookup"><span data-stu-id="40267-261">Digital transformation of live events: Bob Bejan's observations from the frontline</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/13/digital-transformation-live-events-bob-bejans-observations-frontline/)

  - [<span data-ttu-id="40267-262">As nove formas mais importantes para a ti da Microsoft ao habilitar o trabalho remoto para seus funcionários</span><span class="sxs-lookup"><span data-stu-id="40267-262">The top 9 ways Microsoft IT is enabling remote work for its employees</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/top-9-ways-microsoft-it-enabling-remote-work-employees/)

  - [<span data-ttu-id="40267-263">Trabalhe remotamente, fique seguro — dicas para CISOs</span><span class="sxs-lookup"><span data-stu-id="40267-263">Work remotely, stay secure—tips for CISOs</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/12/work-remotely-stay-secure-ciso-tips/)

  - [<span data-ttu-id="40267-264">Ajudando professores e alunos a fazer a mudança para o aprendizado remoto</span><span class="sxs-lookup"><span data-stu-id="40267-264">Helping teachers and students make the switch to remote learning</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/11/helping-teachers-students-switch-remote-learning/)

  - [<span data-ttu-id="40267-265">Manter-se produtivo enquanto trabalha remotamente com o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-265">Staying productive while working remotely with Microsoft Teams</span></span>](https://www.microsoft.com/en-us/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/)

## <a name="support-services-reference"></a><span data-ttu-id="40267-266">Referência de serviços de suporte</span><span class="sxs-lookup"><span data-stu-id="40267-266">Support Services reference</span></span>

<span data-ttu-id="40267-267">O Microsoft Teams depende dos grupos do Exchange Online, do SharePoint Online, do OneDrive for Business e do Office 365 para fornecer aos usuários uma experiência totalmente integrada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="40267-267">Teams relies on Exchange Online, SharePoint Online, OneDrive for Business and Office 365 Groups to provide your users with a fully integrated Office 365 experience.</span></span> <span data-ttu-id="40267-268">Conforme observado acima, o Microsoft Teams funciona sem a implantação completa desses serviços – com recursos limitados.</span><span class="sxs-lookup"><span data-stu-id="40267-268">As noted above, Teams will work without full deploying these services – with limited capabilities.</span></span> <span data-ttu-id="40267-269">Você pode ler mais sobre o Teams e seus pré-requisitos aqui: [Bem-vindo ao Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="40267-269">You can read more about Teams and its pre-requisites here: [Welcome to Teams](teams-overview.md).</span></span>

<span data-ttu-id="40267-270">Para ver especificações sobre cada um dos serviços listados acima, siga os links abaixo:</span><span class="sxs-lookup"><span data-stu-id="40267-270">For specifics on each of the services listed above, please follow the links below:</span></span>

  - <span data-ttu-id="40267-271">O Exchange Online é usado para recursos de calendário e armazenamento de mensagens ponto a ponto no Teams.</span><span class="sxs-lookup"><span data-stu-id="40267-271">Exchange Online is used for calendaring features and storing peer to peer messages in Teams.</span></span> <span data-ttu-id="40267-272">Para saber mais, leia [como o Exchange e as equipes interagem](exchange-teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="40267-272">To learn more, read [How Exchange and Teams interact](exchange-teams-interact.md)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="40267-273">Para a interoperabilidade do teams com o Exchange no local, você deve configurar o novo protocolo de autenticação OAuth do Exchange, conforme descrito em [Configurar a autenticação OAuth entre organizações Exchange e Exchange Online](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="40267-273">For Teams interop with Exchange on-premises, you must configure the new Exchange OAuth authentication protocol as described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help).</span></span>

  - <span data-ttu-id="40267-274">O SharePoint é usado para compartilhamento de arquivos em canais, enquanto o/OneDrive for Business é usado para compartilhamento de arquivos no 1:1 ou em um chat em grupo.</span><span class="sxs-lookup"><span data-stu-id="40267-274">SharePoint is used for file sharing in channels, while /OneDrive for Business is used for file sharing in 1:1 or group chat.</span></span> <span data-ttu-id="40267-275">Para saber mais, leia [como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](sharepoint-onedrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="40267-275">To learn more, read [How SharePoint Online and OneDrive for Business interact with Microsoft Teams](sharepoint-onedrive-interact.md).</span></span>

  - <span data-ttu-id="40267-276">Os [grupos do Office 365](office-365-groups.md) são usados para criação/gerenciamento de equipes e canais.</span><span class="sxs-lookup"><span data-stu-id="40267-276">[Office 365 Groups](office-365-groups.md) are used for team and channel creation/management.</span></span>


## <a name="related-topics"></a><span data-ttu-id="40267-277">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="40267-277">Related topics</span></span>

[<span data-ttu-id="40267-278">Cartazes de soluções de telefonia e arquitetura de TI do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40267-278">Microsoft Teams IT architecture and telephony solutions posters</span></span>](teams-architecture-solutions-posters.md#teams-as-part-of-microsoft-365)

[<span data-ttu-id="40267-279">Planejar conectividade híbrida entre o Skype for Business Server e o Office 365</span><span class="sxs-lookup"><span data-stu-id="40267-279">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)

[<span data-ttu-id="40267-280">Suporte a trabalhadores remotos usando o Teams</span><span class="sxs-lookup"><span data-stu-id="40267-280">Support remote workers using Teams</span></span>](support-remote-work-with-teams.md)

[<span data-ttu-id="40267-281">Trabalhe remotamente com o Office 365</span><span class="sxs-lookup"><span data-stu-id="40267-281">Work remotely with Office 365</span></span>](https://aka.ms/remote-work)