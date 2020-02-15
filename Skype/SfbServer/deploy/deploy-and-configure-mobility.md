---
title: Implantar e configurar o Mobility para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artigo irá orientá-lo nas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço de mobilidade, permitindo que os dispositivos móveis aproveitem os recursos de mobilidade do Skype for Business Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029062"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="88f1b-103">Implantar e configurar o Mobility para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="88f1b-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="88f1b-104">Este artigo irá orientá-lo nas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço de mobilidade, permitindo que os dispositivos móveis aproveitem os recursos de mobilidade do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="88f1b-105">Revisou o artigo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , você deve estar pronto para prosseguir com as etapas abaixo para implantar a mobilidade no seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="88f1b-106">As etapas são as seguintes (e estamos incluindo nesta tabela uma lista de permissões):</span><span class="sxs-lookup"><span data-stu-id="88f1b-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="88f1b-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="88f1b-107">**Phase**</span></span>|<span data-ttu-id="88f1b-108">**Permissões**</span><span class="sxs-lookup"><span data-stu-id="88f1b-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="88f1b-109">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="88f1b-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="88f1b-110">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="88f1b-110">Domain Admins</span></span>  <br/> <span data-ttu-id="88f1b-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="88f1b-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="88f1b-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="88f1b-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="88f1b-113">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="88f1b-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="88f1b-114">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="88f1b-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="88f1b-115">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="88f1b-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="88f1b-116">Configurar descoberta automática para mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="88f1b-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="88f1b-117">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="88f1b-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="88f1b-118">Testar sua implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="88f1b-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="88f1b-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="88f1b-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="88f1b-120">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="88f1b-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="88f1b-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="88f1b-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="88f1b-122">Configurar a política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="88f1b-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="88f1b-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="88f1b-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="88f1b-124">Todas as seções a seguir contêm etapas que pressupõem que você leu o tópico de planejamento.</span><span class="sxs-lookup"><span data-stu-id="88f1b-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="88f1b-125">Se alguma coisa for confusa, sinta-se à vontade para fazer o check-out das informações.</span><span class="sxs-lookup"><span data-stu-id="88f1b-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="88f1b-126">O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="88f1b-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="88f1b-127">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="88f1b-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="88f1b-128">Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="88f1b-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="88f1b-129">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="88f1b-129">Create DNS records</span></span>
<span data-ttu-id="88f1b-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="88f1b-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="88f1b-131">Talvez você já tenha isso como parte do seu ambiente do Skype for Business Server, mas é necessário criar os seguintes registros para que a descoberta automática funcione:</span><span class="sxs-lookup"><span data-stu-id="88f1b-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="88f1b-132">Um registro DNS interno para dar suporte a usuários móveis que estão se conectando dentro da rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="88f1b-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="88f1b-133">Um registro DNS externo (ou público) para dar suporte a usuários móveis que estão se conectando de fora da rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="88f1b-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="88f1b-134">Esses registros podem ser nomes de (host) ou registros CNAME (você não precisa fazer os dois, estamos apenas incluindo as etapas para tudo aqui).</span><span class="sxs-lookup"><span data-stu-id="88f1b-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="88f1b-135">Criar um registro CNAME de DNS interno</span><span class="sxs-lookup"><span data-stu-id="88f1b-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="88f1b-136">Faça logon em um servidor DNS de sua rede que seja membro do grupo **Administradores de domínio** ou do grupo **DNSAdmins** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="88f1b-137">Clique em **Iniciar**, escolha **Ferramentas administrativas** (talvez seja necessário **procurá** -lo se não houver uma opção no menu Iniciar) e, em seguida, clique em **DNS** para abrir o snap-in administrativo do DNS.</span><span class="sxs-lookup"><span data-stu-id="88f1b-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="88f1b-138">No painel esquerdo da janela do console, você precisará ir para o domínio que está em casa para os servidores front-end do Skype for Business Server e expandir as **zonas de pesquisa direta** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="88f1b-139">Reserve um tempo para ver qual dos seguintes itens você tem:</span><span class="sxs-lookup"><span data-stu-id="88f1b-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="88f1b-140">Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="88f1b-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="88f1b-141">Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="88f1b-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="88f1b-142">Depois de observar isso, clique com o botão direito do mouse no nome do domínio SIP e escolha **novo alias (CNAME)** no menu.</span><span class="sxs-lookup"><span data-stu-id="88f1b-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="88f1b-143">Na caixa de texto **nome do alias** , digite lyncdiscoverinternal para o nome do host, para a URL interna do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="88f1b-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="88f1b-144">No **nome de domínio totalmente qualificado (FQDN para o host de destino**, você precisará digitar ou procurar o FQDN de serviços Web internos para o seu pool de front-ends (ou servidor de front-end único, ou o pool de diretores ou diretor), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="88f1b-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="88f1b-145">Clique em OK quando for inserido.</span><span class="sxs-lookup"><span data-stu-id="88f1b-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="88f1b-146">Você precisará criar um novo registro CNAME de descoberta automática na zona de pesquisa direta para cada domínio SIP suportado em seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="88f1b-147">Criar um registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="88f1b-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="88f1b-148">Essas etapas são genéricas, porque não podemos saber qual provedor de DNS público você pode estar usando, mas ainda queremos ajudá-lo. Conecte-se ao seu provedor de DNS público com uma conta que possa criar novos registros DNS.</span><span class="sxs-lookup"><span data-stu-id="88f1b-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="88f1b-149">Nesse momento, um domínio SIP já deve existir para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="88f1b-150">Expanda a **zona de pesquisa direta** para este domínio SIP ou abra-a.</span><span class="sxs-lookup"><span data-stu-id="88f1b-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="88f1b-151">Reserve um tempo para ver qual dos seguintes itens você tem:</span><span class="sxs-lookup"><span data-stu-id="88f1b-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="88f1b-152">Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="88f1b-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="88f1b-153">Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="88f1b-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="88f1b-154">Depois de ter essas informações, você poderá selecionar uma opção para criar um **novo alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="88f1b-155">Agora você pode digitar um **nome de alias**, é necessário inserir lyncdiscover aqui para a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="88f1b-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="88f1b-156">Em seguida, deve haver uma área para inserir um **FQDN para o host de destino**, que deverá ser o FQDN do seu pool de front-ends (ou servidor front-end único ou o pool ou diretor do diretor), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="88f1b-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="88f1b-157">Talvez seja necessário salvar aqui ou, se você precisar criar registros CNAME adicionais na zona de pesquisa direta de cada domínio SIP no seu ambiente do Skype for Business Server, você deve fazer isso, mas quando estiver pronto, salve o seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="88f1b-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="88f1b-158">Criar um registro de DNS interno</span><span class="sxs-lookup"><span data-stu-id="88f1b-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="88f1b-159">Faça logon em um servidor DNS de sua rede que seja membro do grupo **Administradores de domínio** ou do grupo **DNSAdmins** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="88f1b-160">Clique em **Iniciar**, escolha **Ferramentas administrativas** (talvez seja necessário **procurá** -lo se não houver uma opção no menu Iniciar) e, em seguida, clique em **DNS** para abrir o snap-in administrativo do DNS.</span><span class="sxs-lookup"><span data-stu-id="88f1b-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="88f1b-161">No painel esquerdo da janela do console, você precisará ir para o domínio que está em casa para os servidores front-end do Skype for Business Server e expandir as **zonas de pesquisa direta** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="88f1b-162">Reserve um tempo para ver qual dos seguintes itens você tem:</span><span class="sxs-lookup"><span data-stu-id="88f1b-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="88f1b-163">Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="88f1b-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="88f1b-164">Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="88f1b-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="88f1b-165">Depois de observar isso, clique com o botão direito do mouse no nome do domínio SIP e escolha **novo host (A ou aaaa)** no menu.</span><span class="sxs-lookup"><span data-stu-id="88f1b-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="88f1b-166">Na caixa de texto **nome** , digite lyncdiscoverinternal para o nome do host, para a URL interna do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="88f1b-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="88f1b-167">Na caixa de texto **endereço IP** , digite o endereço IP dos serviços Web internos para seu pool de front-ends (ou servidor front-end único, ou o pool de diretores ou diretor), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="88f1b-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="88f1b-168">Quando isso estiver concluído, clique em **Adicionar host**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="88f1b-169">Você precisará criar um novo registro de descoberta automática ou registros AAAA na zona de pesquisa direta para cada domínio SIP suportado no seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="88f1b-170">Para fazer isso, repita as etapas 6-8 quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="88f1b-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="88f1b-171">Quando terminar, clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="88f1b-172">Criar um registro de DNS externo</span><span class="sxs-lookup"><span data-stu-id="88f1b-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="88f1b-173">Essas etapas são genéricas, porque não podemos saber qual provedor de DNS público você pode estar usando, mas ainda queremos ajudá-lo. Conecte-se ao seu provedor de DNS público com uma conta que possa criar novos registros DNS.</span><span class="sxs-lookup"><span data-stu-id="88f1b-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="88f1b-174">Nesse momento, um domínio SIP já deve existir para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="88f1b-175">Expanda a **zona de pesquisa direta** para este domínio SIP ou abra-a.</span><span class="sxs-lookup"><span data-stu-id="88f1b-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="88f1b-176">Reserve um tempo para ver qual dos seguintes itens você tem:</span><span class="sxs-lookup"><span data-stu-id="88f1b-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="88f1b-177">Qualquer registro de host A ou AAAA do servidor front-end (Standard ou Enterprise) ou pools de front-ends.</span><span class="sxs-lookup"><span data-stu-id="88f1b-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="88f1b-178">Todos os registros de host A ou AAAA de um diretor ou pool de diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="88f1b-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="88f1b-179">Depois de ter essas informações, você poderá selecionar uma opção para criar um **novo host a ou aaaa**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="88f1b-180">Agora você deve ser capaz de inserir um **nome**, você precisa inserir lyncdiscover aqui para a URL externa do serviço de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="88f1b-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="88f1b-181">Em seguida, deve haver uma área para inserir em um **endereço IP**, será necessário ser o IP para seu pool de front-ends (ou servidor front-end único ou o pool ou diretor de diretor), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="88f1b-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="88f1b-182">Talvez seja necessário salvar aqui ou se você precisar criar registros A ou AAAA adicionais na zona de pesquisa direta de cada domínio SIP para seu ambiente do Skype for Business Server, você deve fazer isso, mas quando estiver pronto, salve o seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="88f1b-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="88f1b-183">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="88f1b-183">Modify certificates</span></span>
<span data-ttu-id="88f1b-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="88f1b-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="88f1b-185">Se você tiver dúvidas sobre o planejamento de certificados, documentamos isso em nosso artigo [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="88f1b-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="88f1b-186">Depois de revisar isso, vamos orientá-lo no seguinte:</span><span class="sxs-lookup"><span data-stu-id="88f1b-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="88f1b-187">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="88f1b-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="88f1b-188">Solicitação de novos certificados da autoridade de certificação (AC).</span><span class="sxs-lookup"><span data-stu-id="88f1b-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="88f1b-189">Atualização de seus certificados in-loco com as substituições usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="88f1b-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="88f1b-190">Verificar os certificados usando o snap-in de certificados no console de gerenciamento Microsoft (MMC).</span><span class="sxs-lookup"><span data-stu-id="88f1b-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="88f1b-191">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="88f1b-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="88f1b-192">Primeiro, talvez seja necessário verificar e ver quais certificados estão no local e se eles têm ou não as entradas de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="88f1b-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="88f1b-193">Para fazer isso, você precisará fazer logon no Skype for Business Server com uma conta que seja um administrador local.</span><span class="sxs-lookup"><span data-stu-id="88f1b-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="88f1b-194">Essa conta também pode precisar ter direitos para a autoridade de certificação (CA) de emissão, para algumas dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="88f1b-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="88f1b-195">Abra o Shell de gerenciamento do Skype for Business Server (você pode usar a pesquisa para encontrá-la se não a tiver fixada no menu iniciar ou na barra de tarefas).</span><span class="sxs-lookup"><span data-stu-id="88f1b-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="88f1b-196">Será essencial que você saiba quais certificados foram atribuídos antes de tentar adicionar um certificado atualizado.</span><span class="sxs-lookup"><span data-stu-id="88f1b-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="88f1b-197">Portanto, no comando, digite:</span><span class="sxs-lookup"><span data-stu-id="88f1b-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="88f1b-198">As informações da etapa 3 serão exclusivas para você.</span><span class="sxs-lookup"><span data-stu-id="88f1b-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="88f1b-199">Você precisará procurá-lo para determinar se você tem um único certificado que tenha sido atribuído para várias coisas ou se você tem um certificado diferente atribuído aos diferentes componentes que precisam deles.</span><span class="sxs-lookup"><span data-stu-id="88f1b-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="88f1b-200">O parâmetro **use** informará como um certificado está sendo usado, e o parâmetro **Thumbprint** informará se é todo o mesmo certificado ou vários certificados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="88f1b-201">Se você tiver as entradas de SAN recomendadas em nossa seção de planejamento, você está bom.</span><span class="sxs-lookup"><span data-stu-id="88f1b-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="88f1b-202">Caso contrário, você precisará solicitar um novo certificado ou vários certificados (dependendo da sua configuração) da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="88f1b-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="88f1b-203">Solicitar um novo certificado ou certificados da autoridade de certificação (CA)</span><span class="sxs-lookup"><span data-stu-id="88f1b-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="88f1b-204">Depois de verificar quais entradas de SAN você tem, você sabe que tem um **único certificado** (após verificar as etapas acima) e aprendeu que não tem todas as entradas necessárias.</span><span class="sxs-lookup"><span data-stu-id="88f1b-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="88f1b-205">Uma nova solicitação de certificado precisa ser feita à sua autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="88f1b-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="88f1b-206">Abra seu PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="88f1b-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="88f1b-207">Para uma SAN de serviço de descoberta automática ausente (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):</span><span class="sxs-lookup"><span data-stu-id="88f1b-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="88f1b-208">Agora, se você tiver vários domínios SIP, não será possível usar o parâmetro AllSipDomain como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="88f1b-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="88f1b-209">Em vez disso, você precisará usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="88f1b-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="88f1b-210">E quando você usa o parâmetro DomainName, você precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="88f1b-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="88f1b-211">Um exemplo seria (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):</span><span class="sxs-lookup"><span data-stu-id="88f1b-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="88f1b-212">Ou, depois de verificar quais entradas de SAN você tem, você descobriu que tem **vários certificados** que não possuem todas as entradas necessárias.</span><span class="sxs-lookup"><span data-stu-id="88f1b-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="88f1b-213">Uma nova solicitação de certificado precisa ser feita à sua autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="88f1b-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="88f1b-214">Abra seu PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="88f1b-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="88f1b-215">Para uma SAN de serviço de descoberta automática ausente (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):</span><span class="sxs-lookup"><span data-stu-id="88f1b-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="88f1b-216">Agora, se você tiver vários domínios SIP, não será possível usar o parâmetro AllSipDomain como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="88f1b-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="88f1b-217">Em vez disso, você precisará usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="88f1b-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="88f1b-218">E quando você usa o parâmetro DomainName, você precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="88f1b-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="88f1b-219">Os exemplos seriam (substituindo o parâmetro-CA pelo caminho de sua própria autoridade de certificação):</span><span class="sxs-lookup"><span data-stu-id="88f1b-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="88f1b-220">Depois que os novos certificados tiverem sido gerados pela autoridade de certificação, você precisará atribuí-los.</span><span class="sxs-lookup"><span data-stu-id="88f1b-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="88f1b-221">Atribuir certificados usando o Shell de gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="88f1b-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="88f1b-222">Dependendo do que você encontrar na seção eu preciso de novas certificações, você precisará executar **um** dos seguintes procedimentos.</span><span class="sxs-lookup"><span data-stu-id="88f1b-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="88f1b-223">Se você tiver um único certificado para tudo (as impressões digitais são idênticas), será necessário executar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88f1b-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="88f1b-224">Se você tiver certificados diferentes para as coisas (as impressões digitais são diferentes), execute isto em vez disso:</span><span class="sxs-lookup"><span data-stu-id="88f1b-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="88f1b-225">Exibindo certificados no console de gerenciamento Microsoft (MMC)</span><span class="sxs-lookup"><span data-stu-id="88f1b-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="88f1b-226">Você tem uma opção para examinar seus certificados usando o snap-in de certificados para o MMC.</span><span class="sxs-lookup"><span data-stu-id="88f1b-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="88f1b-227">Basta digitar MMC na pesquisa e ele deverá aparecer como uma opção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="88f1b-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="88f1b-228">Para adicionar o snap-in certificados, você precisará clicar em **arquivo**e **Adicionar/remover snap-in...** (ou atalho de teclado **Ctrl + M** também funcionará).</span><span class="sxs-lookup"><span data-stu-id="88f1b-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="88f1b-229">**Certificados** será uma opção no painel esquerdo, selecione-o e, em seguida, **conta de computador** na janela pop-up e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="88f1b-230">Ainda na janela pop-up, em todas as chances de que você esteja fazendo isso no computador em que você está em casa para os certificados que precisa examinar, deixe a seleção no **computador local** se isso for possível.</span><span class="sxs-lookup"><span data-stu-id="88f1b-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="88f1b-231">Se você estiver trabalhando em um computador remoto, altere o botão de opção para **outro computador** e, em seguida, insira o FQDN desse computador ou use o botão **procurar** para pesquisar o computador pelo AD.</span><span class="sxs-lookup"><span data-stu-id="88f1b-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="88f1b-232">Depois de selecionar o computador, você precisará clicar em **concluir** quando estiver pronto e, em seguida, em **OK** para adicionar o snap-in ao MMC.</span><span class="sxs-lookup"><span data-stu-id="88f1b-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="88f1b-233">Expanda a seção **certificados** no painel esquerdo do MMC.</span><span class="sxs-lookup"><span data-stu-id="88f1b-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="88f1b-234">Expanda também a pasta **pessoal** e, em seguida, selecione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="88f1b-235">Isso permite que você veja os certificados nesse repositório.</span><span class="sxs-lookup"><span data-stu-id="88f1b-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="88f1b-236">Você precisa localizar o certificado que deseja exibir, clicar com o botão direito do mouse nele e escolher **abrir**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="88f1b-237">Como saber qual é o certificado?</span><span class="sxs-lookup"><span data-stu-id="88f1b-237">How do you know what certificate this is?</span></span> <span data-ttu-id="88f1b-238">Deve ser o único certificado atribuído a tudo para o seu farm, ou você pode ter vários certificados para diferentes coisas, como padrão, serviços Web internos, etc., e, nesse caso, talvez seja necessário examinar vários certificados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="88f1b-239">Vários certificados terão a mesma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="88f1b-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="88f1b-240">Depois de obter o modo de exibição de **certificado** , escolha **detalhes**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="88f1b-241">Isso permitirá que você veja o nome da entidade do certificado quando você selecionar **assunto**e o nome de entidade atribuído e as propriedades associadas serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="88f1b-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="88f1b-242">Você também precisará verificar as entradas de **nome alternativo de entidade** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="88f1b-243">Você encontrará uma ou mais das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="88f1b-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="88f1b-244">O nome do pool para este pool ou o nome do servidor único, se não for um pool.</span><span class="sxs-lookup"><span data-stu-id="88f1b-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="88f1b-245">O nome do servidor ao qual o certificado está atribuído.</span><span class="sxs-lookup"><span data-stu-id="88f1b-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="88f1b-246">Registros de URL simples, normalmente atendem e são de discagem.</span><span class="sxs-lookup"><span data-stu-id="88f1b-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="88f1b-247">Nomes internos e externos de serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no construtor de topologias e nas seleções de serviços Web do nas.</span><span class="sxs-lookup"><span data-stu-id="88f1b-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="88f1b-248">Se já tiver sido atribuído, o lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="88f1b-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="88f1b-249">Você precisará verificar vários certificados se tiver mais de um atribuído (verifique a observação acima).</span><span class="sxs-lookup"><span data-stu-id="88f1b-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="88f1b-250">Portanto, se você encontrar lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros, você já configurou isso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="88f1b-251">Você pode fechar o MMC.</span><span class="sxs-lookup"><span data-stu-id="88f1b-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="88f1b-252">Se não forem atribuídas, será necessário fazer uma nova solicitação de certificado (descrita acima) ou você precisará instalar as solicitações post-Request (recomendamos o seguinte para o PowerShell acima).</span><span class="sxs-lookup"><span data-stu-id="88f1b-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="88f1b-253">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="88f1b-253">Configure the reverse proxy</span></span>
<span data-ttu-id="88f1b-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="88f1b-254"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="88f1b-255">As etapas abaixo não devem ser seguidas exatamente.</span><span class="sxs-lookup"><span data-stu-id="88f1b-255">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="88f1b-256">Isso acontece porque nas versões anteriores do produto, gostaríamos de orientá-lo, por exemplo, a configuração da TMG (Threat Management Gateway) e, se você não o estivesse usando, precisará trabalhar com sua própria versão.</span><span class="sxs-lookup"><span data-stu-id="88f1b-256">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="88f1b-257">A TMG não está mais sendo oferecida pela Microsoft como um produto e, se ainda precisar configurá-la, você poderá examinar as [etapas do Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="88f1b-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="88f1b-258">Mas as informações a seguir devem ser mais úteis em geral, mesmo se não houver nenhuma forma de fornecer etapas específicas passo a passo para cada proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="88f1b-259">Temos duas coisas principais a considerar:</span><span class="sxs-lookup"><span data-stu-id="88f1b-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="88f1b-260">Você vai fazer a solicitação de descoberta automática inicial por HTTPS (o que recomendamos)?</span><span class="sxs-lookup"><span data-stu-id="88f1b-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="88f1b-261">Se você tiver uma regra de publicação na Web, precisará modificá-la.</span><span class="sxs-lookup"><span data-stu-id="88f1b-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="88f1b-262">Se você ainda não tem uma regra de publicação na Web, precisa criá-la.</span><span class="sxs-lookup"><span data-stu-id="88f1b-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="88f1b-263">Se você estiver fazendo uma solicitação de descoberta automática inicial por HTTP, você também precisará criar ou modificar essa regra.</span><span class="sxs-lookup"><span data-stu-id="88f1b-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="88f1b-264">**Importante** Um valor de tempo limite de proxy é um número que varia de implantação para implantação.</span><span class="sxs-lookup"><span data-stu-id="88f1b-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="88f1b-265">Você deve monitorar sua implantação e modificar o valor da melhor experiência para os clientes.</span><span class="sxs-lookup"><span data-stu-id="88f1b-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="88f1b-266">É possível definir o valor como baixo como 200.</span><span class="sxs-lookup"><span data-stu-id="88f1b-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="88f1b-267">Se você estiver dando suporte a clientes móveis do Lync em seu ambiente, você deve definir o valor como 960 para permitir o tempo limite de notificação por push do Office 365, que tem um valor de tempo limite de 900.</span><span class="sxs-lookup"><span data-stu-id="88f1b-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="88f1b-268">É muito provável que você tenha que aumentar o valor de tempo limite para evitar que o cliente seja desconectado quando o valor for muito baixo ou diminuir o número se as conexões por meio do proxy não forem desconectadas, mas muito longo após o cliente ter sido desconectado.</span><span class="sxs-lookup"><span data-stu-id="88f1b-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="88f1b-269">O monitoramento e a determinação de desempenho mais comuns para seu ambiente é a única maneira precisa de determinar a configuração apropriada para esse valor.</span><span class="sxs-lookup"><span data-stu-id="88f1b-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="88f1b-270">Modificar a regra de publicação da Web existente para sua SAN e URL de descoberta automática externa</span><span class="sxs-lookup"><span data-stu-id="88f1b-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="88f1b-271">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="88f1b-272">Você precisará localizar sua regra de publicação na Web e escolher a opção Editar (ela pode estar em um menu ou em uma guia, dependendo da sua configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="88f1b-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="88f1b-273">Deve haver uma área à qual essa regra de publicação da Web seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="88f1b-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="88f1b-274">Você precisa modificar essa regra para sites de entrada ou solicitações de sites.</span><span class="sxs-lookup"><span data-stu-id="88f1b-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="88f1b-275">Você **adicionará** uma nova entrada.</span><span class="sxs-lookup"><span data-stu-id="88f1b-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="88f1b-276">Digite o nome do seu site de descoberta automática (o exemplo que usaremos é lyncdiscover.contoso.com) e clique em **OK** ou **salvar**, dependendo do seu formato de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="88f1b-277">Você pode ter um novo certificado que tenha a entrada de SAN de descoberta automática.</span><span class="sxs-lookup"><span data-stu-id="88f1b-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="88f1b-278">Isso também precisa ser instalado e configurado para uso de acordo com as configurações do seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="88f1b-279">Certifique-se de salvar tudo quando a configuração for concluída.</span><span class="sxs-lookup"><span data-stu-id="88f1b-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="88f1b-280">Se o seu proxy reverso tiver uma funcionalidade de **teste** , use-o para garantir que tudo está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="88f1b-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="88f1b-281">Agora, talvez seja necessário repetir essas etapas se você tiver um diretor ou um pool de diretores no seu ambiente (isso significa que você tem uma segunda regra).</span><span class="sxs-lookup"><span data-stu-id="88f1b-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="88f1b-282">Criar uma regra de publicação na Web para a URL externa de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="88f1b-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="88f1b-283">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="88f1b-284">Você precisará localizar onde na interface você cria suas regras de publicação na Web e escolher a opção **novo** ou **criar** (pode estar em um menu ou guia, dependendo da sua configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="88f1b-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="88f1b-285">Você está procurando a opção de criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="88f1b-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="88f1b-286">Normalmente, você precisará inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="88f1b-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="88f1b-287">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="88f1b-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="88f1b-288">**Ação de regra**: nesse caso, é uma regra de **permissão** , você está permitindo que algo passe pelo seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="88f1b-289">A regra de **publicação** ou opção que você está escolhendo seria **um único site ou balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="88f1b-290">Isso precisa ser **SSL** para acesso externo, escolha essa opção.</span><span class="sxs-lookup"><span data-stu-id="88f1b-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="88f1b-291">Você precisará publicar um caminho para **publicação interna**e inserir o FQDN para os serviços Web externos no balanceador de carga do pool de front-ends (ou o FQDN do balanceador de carga do pool de diretores, se tiver um), um exemplo seria sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="88f1b-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="88f1b-292">Você deve digitar \*\* / \*\*\* como o caminho a ser publicado, mas você também precisa **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="88f1b-293">Haverá uma opção para detalhes ou informações de **nome público ou externo** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-293">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="88f1b-294">Este é o local onde você poderá inserir:</span><span class="sxs-lookup"><span data-stu-id="88f1b-294">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="88f1b-295">**Aceitar solicitações**, mas deve ser para o nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="88f1b-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="88f1b-296">Para o **nome**, você deve inserir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="88f1b-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="88f1b-297"><sipdomain>(esta é a URL externa do serviço de descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="88f1b-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="88f1b-298">Agora, se você estiver criando uma regra para a URL de serviços Web externos no pool de front-ends, precisará digitar o FQDN dos serviços Web externos em seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="88f1b-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="88f1b-299">Haverá uma opção de **caminho** , e você precisará inserir \*\* / \*\*\* aqui.</span><span class="sxs-lookup"><span data-stu-id="88f1b-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="88f1b-300">Você precisará selecionar um **ouvinte SSL** com seu certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="88f1b-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="88f1b-301">A **delegação de autenticação** deve ser definida como **sem delegação**, mas a autenticação direta do cliente **deve** ser permitida.</span><span class="sxs-lookup"><span data-stu-id="88f1b-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="88f1b-302">A regra deve ser definida para **todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="88f1b-303">Isso deve ser todas as informações necessárias para criar essa regra e permitir que você continue.</span><span class="sxs-lookup"><span data-stu-id="88f1b-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="88f1b-304">Você precisará garantir que o **cabeçalho do host original** seja encaminhado.</span><span class="sxs-lookup"><span data-stu-id="88f1b-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="88f1b-305">As portas do **servidor Web** também precisarão ser definidas, você precisará fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88f1b-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="88f1b-306">**Redirecionar solicitações para a porta http** e o número da porta deverá ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="88f1b-307">**Redirecione as solicitações para a porta SSL** e o número da porta deve ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="88f1b-308">Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, poderá testar a regra.</span><span class="sxs-lookup"><span data-stu-id="88f1b-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="88f1b-309">Criar uma regra de publicação na Web para a porta 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="88f1b-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="88f1b-310">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="88f1b-311">Você precisará localizar onde na interface você cria suas regras de publicação na Web e escolher a opção **novo** ou **criar** (pode estar em um menu ou guia, dependendo da sua configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="88f1b-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="88f1b-312">Você está procurando a opção de criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="88f1b-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="88f1b-313">Normalmente, você precisará inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="88f1b-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="88f1b-314">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="88f1b-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="88f1b-315">**Ação de regra**: nesse caso, é uma regra de **permissão** , você está permitindo que algo passe pelo seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="88f1b-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="88f1b-316">A regra de **publicação** ou opção que você está escolhendo seria **um único site ou balanceador de carga**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="88f1b-317">Isso precisa ser uma **conexão não segura para se conectar ao servidor Web ou ao farm publicado**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="88f1b-318">Você precisará publicar um caminho para **publicação interna**e inserir o FQDN para o **endereço VIP** do balanceador de carga do seu pool de front-ends, um exemplo seria sfb_pool01. contoso. local.</span><span class="sxs-lookup"><span data-stu-id="88f1b-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="88f1b-319">Você deve digitar \*\* / \*\*\* como o caminho a ser publicado, mas você também precisa **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="88f1b-320">Haverá uma opção para detalhes ou informações de **nome público ou externo** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-320">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="88f1b-321">Este é o local onde você poderá inserir:</span><span class="sxs-lookup"><span data-stu-id="88f1b-321">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="88f1b-322">**Aceitar solicitações**, mas deve ser para o nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="88f1b-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="88f1b-323">Para o **nome**, você deve inserir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="88f1b-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="88f1b-324"><sipdomain>(esta é a URL externa do serviço de descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="88f1b-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="88f1b-325">Haverá uma opção de **caminho** , e você precisará inserir \*\* / \*\*\* aqui.</span><span class="sxs-lookup"><span data-stu-id="88f1b-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="88f1b-326">Você precisará selecionar um ouvinte da Web ou permitir que seu proxy reverso crie um para você.</span><span class="sxs-lookup"><span data-stu-id="88f1b-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="88f1b-327">A **delegação de autenticação** deve ser definida como **sem delegação**, mas a autenticação direta do cliente **não deve** ser permitida.</span><span class="sxs-lookup"><span data-stu-id="88f1b-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="88f1b-328">A regra deve ser definida para **todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="88f1b-329">Isso deve ser todas as informações necessárias para criar essa regra e permitir que você continue.</span><span class="sxs-lookup"><span data-stu-id="88f1b-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="88f1b-330">As portas de **servidor Web** precisarão ser definidas, será necessário fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88f1b-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="88f1b-331">**Redirecionar solicitações para a porta http** e o número da porta deverá ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="88f1b-332">**Redirecione as solicitações para a porta SSL** e o número da porta deve ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="88f1b-333">Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, poderá testar a regra.</span><span class="sxs-lookup"><span data-stu-id="88f1b-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="88f1b-334">Configurar descoberta automática para mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="88f1b-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="88f1b-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="88f1b-335"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="88f1b-336">Ambientes híbridos no Skype for Business Server são ambientes que combinam um ambiente local e do O365.</span><span class="sxs-lookup"><span data-stu-id="88f1b-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="88f1b-337">Quando o Skype for Business Server funciona em um ambiente híbrido, o serviço de descoberta automática precisa ser capaz de localizar um usuário a partir de qualquer um desses ambientes.</span><span class="sxs-lookup"><span data-stu-id="88f1b-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="88f1b-338">Para permitir que clientes móveis descubram onde um usuário está localizado, o serviço de descoberta automática precisa ser configurado com um novo Uniform Resource Locator (URL).</span><span class="sxs-lookup"><span data-stu-id="88f1b-338">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="88f1b-339">As etapas são:</span><span class="sxs-lookup"><span data-stu-id="88f1b-339">The steps are:</span></span>
  
1. <span data-ttu-id="88f1b-340">Abra o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="88f1b-341">Execute o seguinte para obter o valor do atributo **ProxyFQDN** para o seu ambiente do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="88f1b-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="88f1b-342">Em seguida, ainda na janela do Shell, execute:</span><span class="sxs-lookup"><span data-stu-id="88f1b-342">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="88f1b-343">Onde [identidade] é substituído pelo nome do domínio do espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="88f1b-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="88f1b-344">Testar sua implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="88f1b-344">Test your Mobility deployment</span></span>
<span data-ttu-id="88f1b-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="88f1b-345"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="88f1b-346">Depois de implantar o serviço de mobilidade do Skype for Business Server e o serviço de descoberta automática do Skype for Business Server, convém executar uma transação de teste para garantir que o direito de trabalho da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="88f1b-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="88f1b-347">Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários criarem, ingressar e se comunicar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="88f1b-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="88f1b-348">Você precisará de dois usuários (real ou teste) e de suas credenciais completas para fazer este teste.</span><span class="sxs-lookup"><span data-stu-id="88f1b-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="88f1b-349">Este comando funcionará para clientes do Skype for Business, bem como para os clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88f1b-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="88f1b-350">Para clientes do Lync Server 2010 no Skype for Business Server 2015, você precisará executar **Test-CsMcxP2PIM** para testar.</span><span class="sxs-lookup"><span data-stu-id="88f1b-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="88f1b-351">Seus usuários do Lync Server 2010 ainda terão que ser usuários reais ou usuários de teste predefinidos, e você precisará de suas credenciais de senha.</span><span class="sxs-lookup"><span data-stu-id="88f1b-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="88f1b-352">O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="88f1b-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="88f1b-353">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="88f1b-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="88f1b-354">Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="88f1b-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="88f1b-355">Testar a conferência para clientes móveis do Skype for Business e do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="88f1b-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="88f1b-356">Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-357">Inicie o **Shell de gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou ir para **todos os programas** e escolha-o).</span><span class="sxs-lookup"><span data-stu-id="88f1b-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="88f1b-358">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="88f1b-358">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="88f1b-359">Também é possível definir credenciais em um script e passá-las para o cmdlet Test.</span><span class="sxs-lookup"><span data-stu-id="88f1b-359">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="88f1b-360">Temos um exemplo disso abaixo.</span><span class="sxs-lookup"><span data-stu-id="88f1b-360">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="88f1b-361">Testar a conferência para clientes móveis do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="88f1b-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="88f1b-362">O suporte do MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="88f1b-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="88f1b-363">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para suportar mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="88f1b-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="88f1b-364">Os usuários com clientes herdados que usam o MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="88f1b-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="88f1b-365">Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-366">Inicie o **Shell de gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou ir para **todos os programas** e escolha-o).</span><span class="sxs-lookup"><span data-stu-id="88f1b-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="88f1b-367">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="88f1b-367">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="88f1b-368">Também é possível definir credenciais em um script e passá-las para o cmdlet Test.</span><span class="sxs-lookup"><span data-stu-id="88f1b-368">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="88f1b-369">Temos um exemplo disso abaixo.</span><span class="sxs-lookup"><span data-stu-id="88f1b-369">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="88f1b-370">Para examinar os procedimentos de comando mais tarde, confira [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="88f1b-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="88f1b-371">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="88f1b-371">Configure for push notifications</span></span>
<span data-ttu-id="88f1b-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="88f1b-372"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="88f1b-373">As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas para um dispositivo móvel, mesmo quando o aplicativo Skype ou Lync está inativo.</span><span class="sxs-lookup"><span data-stu-id="88f1b-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="88f1b-374">Mas o que são notificações por push?</span><span class="sxs-lookup"><span data-stu-id="88f1b-374">But what are push notifications?</span></span> <span data-ttu-id="88f1b-375">Eles são alertas de eventos, como um convite de IM novo ou perdido ou para uma caixa postal recebida.</span><span class="sxs-lookup"><span data-stu-id="88f1b-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="88f1b-376">O serviço de mobilidade do Skype for Business Server envia essas notificações para o serviço de notificação por push do Skype for Business Server baseado na nuvem, que envia as notificações para o serviço de notificação por push da Microsoft (MSNS) para usuários do Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="88f1b-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="88f1b-377">Essa funcionalidade não é alterada no Lync Server 2013, mas se você tiver um Skype for Business Server, será necessário fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="88f1b-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="88f1b-378">Para um servidor de borda do Skype for Business Server, adicione um novo provedor de hospedagem, o Microsoft Skype for Business Online e configure a Federação do provedor de hospedagem entre sua organização e o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="88f1b-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="88f1b-379">Habilite notificações por push executando o cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="88f1b-379">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="88f1b-380">Por padrão, as notificações por push estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="88f1b-380">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="88f1b-381">Teste sua configuração de Federação e as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="88f1b-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="88f1b-382">Configurar o servidor de borda do Skype for Business para notificações por push</span><span class="sxs-lookup"><span data-stu-id="88f1b-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="88f1b-383">Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-384">Inicie o **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="88f1b-385">Adicionar um provedor de hospedagem online do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="88f1b-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="88f1b-386">Como exemplo:</span><span class="sxs-lookup"><span data-stu-id="88f1b-386">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="88f1b-387">Você não pode ter mais de uma relação de Federação com um único provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="88f1b-387">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="88f1b-388">Portanto, se você já configurou um provedor de hospedagem que tem uma relação de Federação com o sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo que a identidade do provedor de hospedagem seja algo diferente de SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="88f1b-388">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="88f1b-389">Configure a Federação do provedor de hospedagem entre sua organização e o serviço de notificação por push no Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="88f1b-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="88f1b-390">Na linha de comando, você precisará digitar:</span><span class="sxs-lookup"><span data-stu-id="88f1b-390">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="88f1b-391">Habilitar notificações por push</span><span class="sxs-lookup"><span data-stu-id="88f1b-391">Enable push notifications</span></span>

1. <span data-ttu-id="88f1b-392">Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-393">Inicie o **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="88f1b-394">Habilitar notificações por push:</span><span class="sxs-lookup"><span data-stu-id="88f1b-394">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="88f1b-395">Habilitar Federação:</span><span class="sxs-lookup"><span data-stu-id="88f1b-395">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="88f1b-396">Testar a Federação e as notificações por push</span><span class="sxs-lookup"><span data-stu-id="88f1b-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="88f1b-397">Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-398">Inicie o **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="88f1b-399">Teste a configuração da Federação:</span><span class="sxs-lookup"><span data-stu-id="88f1b-399">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="88f1b-400">Como exemplo:</span><span class="sxs-lookup"><span data-stu-id="88f1b-400">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="88f1b-401">Teste suas notificações por push:</span><span class="sxs-lookup"><span data-stu-id="88f1b-401">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="88f1b-402">Como exemplo:</span><span class="sxs-lookup"><span data-stu-id="88f1b-402">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="88f1b-403">Configurar a política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="88f1b-403">Configure Mobility policy</span></span>
<span data-ttu-id="88f1b-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="88f1b-404"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="88f1b-405">Você tem a capacidade com o Skype for Business Server determinar quem pode usar seu serviço de mobilidade, ligar via trabalho, VoIP (voz sobre IP) ou vídeo, bem como se o WiFi será necessário para VoIP ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="88f1b-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="88f1b-406">Call via trabalho permite que um usuário móvel use seu número de telefone comercial, em vez do número de telefone celular, ao colocar e receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="88f1b-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="88f1b-407">A pessoa na outra extremidade da linha não verá o número de telefone celular do usuário móvel e permitirá que o usuário móvel Evite encargos de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="88f1b-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="88f1b-408">Quando VoIP e vídeo são configurados, os usuários podem tomar e fazer chamadas VoIP e vídeo.</span><span class="sxs-lookup"><span data-stu-id="88f1b-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="88f1b-409">As configurações para o uso de WiFi determinam se o dispositivo móvel de um usuário será necessário para usar uma rede WiFi em uma rede de dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="88f1b-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="88f1b-410">Mobilidade, ligar via trabalho e VoIP e recursos de vídeo são habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="88f1b-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="88f1b-411">A configuração para exigir WiFi para VoIP e vídeo está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="88f1b-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="88f1b-412">Um administrador tem a capacidade de alterar isso de forma global, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="88f1b-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="88f1b-413">Para poder usar os recursos de mobilidade e ligar via trabalho, os usuários precisam ser:</span><span class="sxs-lookup"><span data-stu-id="88f1b-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="88f1b-414">Habilitado para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="88f1b-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="88f1b-415">Habilitado para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="88f1b-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="88f1b-416">Atribuída uma política de mobilidade que tem a opção **EnableMobility** definida como **true**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="88f1b-417">Para que os usuários possam usar a chamada via trabalho, eles também precisarão ser:</span><span class="sxs-lookup"><span data-stu-id="88f1b-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="88f1b-418">Atribuída uma política de voz que tem a opção **habilitar toque simultâneo de telefones** selecionada.</span><span class="sxs-lookup"><span data-stu-id="88f1b-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="88f1b-419">Atribuída uma política de mobilidade que tem o **EnableOutsideVoice** definido como **true**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="88f1b-420">Os usuários que não estão habilitados para o Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas do Skype para Skype VoIP ou ingressar em conferências usando o link Clique para entrar em seus dispositivos móveis, se as opções apropriadas estiverem definidas para a política de voz que estão associadas com.</span><span class="sxs-lookup"><span data-stu-id="88f1b-420">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="88f1b-421">Há mais detalhes no tópico planejamento.</span><span class="sxs-lookup"><span data-stu-id="88f1b-421">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="88f1b-422">Modificar a política de mobilidade global</span><span class="sxs-lookup"><span data-stu-id="88f1b-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="88f1b-423">Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-424">Inicie o **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="88f1b-425">Desative o acesso à mobilidade e ligue via trabalho globalmente digitando:</span><span class="sxs-lookup"><span data-stu-id="88f1b-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="88f1b-426">Você pode desativar a chamada via trabalho sem desativar o acesso à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="88f1b-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="88f1b-427">Mas você não pode desativar a mobilidade sem também desativar a chamada via trabalho.</span><span class="sxs-lookup"><span data-stu-id="88f1b-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="88f1b-428">Para obter mais informações, confira [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="88f1b-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="88f1b-429">Modificar política de mobilidade por site</span><span class="sxs-lookup"><span data-stu-id="88f1b-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="88f1b-430">Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-431">Inicie o **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="88f1b-432">Você pode criar uma política de nível de site, desativar VoIP e vídeo, habilitar exigir WiFi para áudio IP e exigir WiFi para vídeo IP por site.</span><span class="sxs-lookup"><span data-stu-id="88f1b-432">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="88f1b-433">Tipo:</span><span class="sxs-lookup"><span data-stu-id="88f1b-433">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="88f1b-434">Saiba mais em [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="88f1b-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="88f1b-435">Modificar política de mobilidade por usuário</span><span class="sxs-lookup"><span data-stu-id="88f1b-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="88f1b-436">Faça logon, com uma conta que seja membro da função **CsAdministrator** , para um computador onde o **Shell de gerenciamento do Skype for Business Server** e o **OCScore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="88f1b-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="88f1b-437">Inicie o **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="88f1b-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="88f1b-438">Crie políticas de mobilidade de nível de usuário e desative a mobilidade e ligue via trabalho por usuário.</span><span class="sxs-lookup"><span data-stu-id="88f1b-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="88f1b-439">Tipo:</span><span class="sxs-lookup"><span data-stu-id="88f1b-439">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="88f1b-440">Um exemplo adicional com dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="88f1b-440">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="88f1b-441">Você pode desativar a chamada via trabalho sem desativar o acesso à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="88f1b-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="88f1b-442">Mas você não pode desativar a mobilidade sem também desativar a chamada via trabalho.</span><span class="sxs-lookup"><span data-stu-id="88f1b-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

