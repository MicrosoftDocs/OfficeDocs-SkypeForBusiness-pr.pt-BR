---
title: Implantar e configurar a mobilidade para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artigo o levará pelas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço mobility, permitindo que seus dispositivos móveis sejam capazes de aproveitar os recursos do Skype for Business Server Mobility.
ms.openlocfilehash: 420d34dcf1406df776e438e01007770e515c0d4a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820891"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="0e53e-103">Implantar e configurar a mobilidade para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e53e-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="0e53e-104">Este artigo o levará pelas etapas para configurar uma instalação existente do Skype for Business Server para usar o serviço mobility, permitindo que seus dispositivos móveis sejam capazes de aproveitar os recursos do Skype for Business Server Mobility.</span><span class="sxs-lookup"><span data-stu-id="0e53e-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="0e53e-105">Após analisar o artigo Plano de Mobilidade para [o Skype for Business Server,](../plan-your-deployment/mobility.md) você deve estar pronto para prosseguir com as etapas abaixo para implantar a Mobilidade em seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e53e-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="0e53e-106">As etapas são as seguintes (e estamos incluindo nesta tabela uma lista de permissões):</span><span class="sxs-lookup"><span data-stu-id="0e53e-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="0e53e-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="0e53e-107">**Phase**</span></span>|<span data-ttu-id="0e53e-108">**Permissões**</span><span class="sxs-lookup"><span data-stu-id="0e53e-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0e53e-109">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="0e53e-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="0e53e-110">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="0e53e-110">Domain Admins</span></span>  <br/> <span data-ttu-id="0e53e-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="0e53e-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="0e53e-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="0e53e-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="0e53e-113">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="0e53e-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="0e53e-114">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="0e53e-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="0e53e-115">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="0e53e-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="0e53e-116">Configurar a Descoberta Automática para Mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="0e53e-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="0e53e-117">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="0e53e-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="0e53e-118">Testar sua implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0e53e-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="0e53e-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0e53e-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="0e53e-120">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="0e53e-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="0e53e-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0e53e-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="0e53e-122">Configurar política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0e53e-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="0e53e-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0e53e-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="0e53e-124">Todas as seções a seguir contêm etapas que presumem que você tenha lido o tópico Planejamento.</span><span class="sxs-lookup"><span data-stu-id="0e53e-124">All the following sections contain steps that assume you've read the Planning topic.</span></span> <span data-ttu-id="0e53e-125">Se algo estiver confuso, sinta-se à vontade para conferir as informações lá.</span><span class="sxs-lookup"><span data-stu-id="0e53e-125">If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="0e53e-126">O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0e53e-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0e53e-127">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="0e53e-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0e53e-128">Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="0e53e-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="0e53e-129">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="0e53e-129">Create DNS records</span></span>
<span data-ttu-id="0e53e-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="0e53e-130"><a name="CreateDNSRec"> </a></span></span>

<span data-ttu-id="0e53e-131">Você pode já ter esses registros como parte do seu ambiente do Skype for Business Server, mas precisa criar os seguintes registros para que a Descoberta Automática funcione:</span><span class="sxs-lookup"><span data-stu-id="0e53e-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="0e53e-132">Um registro DNS interno para dar suporte a usuários móveis que estão se conectando de dentro da rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0e53e-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="0e53e-133">Um registro DNS externo (ou público) para dar suporte a usuários móveis que estão se conectando de fora da rede da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0e53e-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="0e53e-134">Esses registros podem ser nomes A (host) ou registros CNAME (você não precisa fazer ambos, estamos apenas incluindo as etapas para tudo aqui).</span><span class="sxs-lookup"><span data-stu-id="0e53e-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="0e53e-135">Criar um registro CNAME de DNS interno</span><span class="sxs-lookup"><span data-stu-id="0e53e-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="0e53e-136">Faça logoff em um servidor DNS em sua  rede que seja membro do grupo Administradores de Domínio ou do **grupo DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="0e53e-137">Clique **em** Iniciar , Escolher Ferramentas  Administrativas **(talvez** seja necessário pesquisar se não for uma opção do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo dns.</span><span class="sxs-lookup"><span data-stu-id="0e53e-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="0e53e-138">No painel esquerdo da janela do console, você precisará ir para o domínio que é a página principal para os Servidores front-end do Skype for Business Server e expandir as **Zonas** de Busca Encaminhar.</span><span class="sxs-lookup"><span data-stu-id="0e53e-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="0e53e-139">Tire um tempo para ver quais das seguintes informações você tem:</span><span class="sxs-lookup"><span data-stu-id="0e53e-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0e53e-140">Qualquer registro de host A ou AAAA para seu servidor front-end (Standard ou Enterprise) ou pool(s) de front-end.</span><span class="sxs-lookup"><span data-stu-id="0e53e-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0e53e-141">Qualquer registro A ou AAAA de host para um Diretor ou pool de Diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0e53e-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="0e53e-142">Depois que você anotou isso, clique com o botão direito do mouse no nome de domínio SIP e escolha Novo **Alias (CNAME)** no menu.</span><span class="sxs-lookup"><span data-stu-id="0e53e-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="0e53e-143">Na caixa **de texto Alias nome,** digite lyncdiscoverinternal para o nome do host, para a URL interna do serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0e53e-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="0e53e-144">No **FQDN (nome** de domínio totalmente qualificado para o host de destino), você precisará digitar ou navegar até o FQDN dos Serviços Web internos do pool de Front-End (ou servidor front-end único, pool de Diretores ou Diretores), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="0e53e-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="0e53e-145">Clique em OK quando for inserido.</span><span class="sxs-lookup"><span data-stu-id="0e53e-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="0e53e-146">Você precisará criar um novo registro CNAME de Descoberta Automática na zona de busca de encaminhamento para cada domínio SIP com suporte em seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e53e-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="0e53e-147">Criar um registro CNAME dns externo</span><span class="sxs-lookup"><span data-stu-id="0e53e-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="0e53e-148">Essas etapas são genéricas, porque não sabemos qual provedor DNS público você pode estar usando, mas ainda queremos ajudá-lo. Faça logoff em seu provedor DNS público com uma conta que poderá fazer novos registros DNS lá.</span><span class="sxs-lookup"><span data-stu-id="0e53e-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="0e53e-149">Neste momento, já deve existir um domínio SIP para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e53e-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="0e53e-150">Expanda **a Zona de Busca** Encaminhada para este domínio SIP ou abra-a.</span><span class="sxs-lookup"><span data-stu-id="0e53e-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="0e53e-151">Tire um tempo para ver quais das seguintes informações você tem:</span><span class="sxs-lookup"><span data-stu-id="0e53e-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0e53e-152">Qualquer registro de host A ou AAAA para seu servidor front-end (Standard ou Enterprise) ou pool(s) de front-end.</span><span class="sxs-lookup"><span data-stu-id="0e53e-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0e53e-153">Qualquer registro A ou AAAA de host para um Diretor ou pool de Diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0e53e-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="0e53e-154">Depois de obter essas informações, você poderá selecionar uma opção para criar um **novo alias (CNAME).**</span><span class="sxs-lookup"><span data-stu-id="0e53e-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="0e53e-155">Agora você deve ser capaz de inserir um Nome de **Alias**, você precisa inserir lyncdiscover aqui para a URL externa do serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0e53e-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="0e53e-156">Em seguida, deve haver uma área para inserir em um **FQDN** para o host de destino, será necessário ser o FQDN para seu pool de Front-End (ou servidor front-end único, pool de Diretores ou Diretores), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="0e53e-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="0e53e-157">Talvez seja necessário salvar aqui, ou se precisar criar registros CNAME adicionais na zona de busca de encaminhamento de cada domínio SIP em seu ambiente do Skype for Business Server, faça isso, mas quando estiver pronto, salve seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e53e-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="0e53e-158">Criar um registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="0e53e-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="0e53e-159">Faça logoff em um servidor DNS em sua  rede que seja membro do grupo Administradores de Domínio ou do **grupo DnsAdmins.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="0e53e-160">Clique **em** Iniciar , Escolher Ferramentas  Administrativas **(talvez** seja necessário pesquisar se não for uma opção do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo dns.</span><span class="sxs-lookup"><span data-stu-id="0e53e-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="0e53e-161">No painel esquerdo da janela do console, você precisará ir para o domínio que é a página principal para os Servidores front-end do Skype for Business Server e expandir as **Zonas** de Busca Encaminhar.</span><span class="sxs-lookup"><span data-stu-id="0e53e-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="0e53e-162">Tire um tempo para ver quais das seguintes informações você tem:</span><span class="sxs-lookup"><span data-stu-id="0e53e-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0e53e-163">Qualquer registro de host A ou AAAA para seu servidor front-end (Standard ou Enterprise) ou pool(s) de front-end.</span><span class="sxs-lookup"><span data-stu-id="0e53e-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0e53e-164">Qualquer registro A ou AAAA de host para um Diretor ou pool de Diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0e53e-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="0e53e-165">Depois que você anotou isso, clique com o botão direito do mouse no nome de domínio SIP e escolha Novo **Host (A ou AAAA)** no menu.</span><span class="sxs-lookup"><span data-stu-id="0e53e-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="0e53e-166">Na caixa de texto **Nome,** digite lyncdiscoverinternal para seu nome de host, para a URL interna do serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0e53e-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="0e53e-167">Na caixa de texto Endereço **IP,** digite o endereço IP dos Serviços Web internos para seu pool de Front-End (ou servidor front-end único, pool de Diretores ou Diretores), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="0e53e-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="0e53e-168">Quando isso for feito, clique **em Adicionar Host** e em **OK.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="0e53e-169">Você precisará criar novos registros A ou AAAA de Descoberta Automática na zona de busca de encaminhamento para cada domínio SIP com suporte em seu ambiente do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e53e-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="0e53e-170">Para fazer isso, repita as etapas de 6 a 8 quantas vezes for necessário.</span><span class="sxs-lookup"><span data-stu-id="0e53e-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="0e53e-171">Quando terminar, clique em **Done**.</span><span class="sxs-lookup"><span data-stu-id="0e53e-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="0e53e-172">Criar um registro DNS A externo</span><span class="sxs-lookup"><span data-stu-id="0e53e-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="0e53e-173">Essas etapas são genéricas, porque não sabemos qual provedor DNS público você pode estar usando, mas ainda queremos ajudá-lo. Faça logoff em seu provedor DNS público com uma conta que poderá fazer novos registros DNS lá.</span><span class="sxs-lookup"><span data-stu-id="0e53e-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="0e53e-174">Neste momento, já deve existir um domínio SIP para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e53e-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="0e53e-175">Expanda **a Zona de Busca** Encaminhada para este domínio SIP ou abra-a.</span><span class="sxs-lookup"><span data-stu-id="0e53e-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="0e53e-176">Tire um tempo para ver quais das seguintes informações você tem:</span><span class="sxs-lookup"><span data-stu-id="0e53e-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0e53e-177">Qualquer registro de host A ou AAAA para seu servidor front-end (Standard ou Enterprise) ou pool(s) de front-end.</span><span class="sxs-lookup"><span data-stu-id="0e53e-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0e53e-178">Qualquer registro A ou AAAA de host para um Diretor ou pool de Diretores (uma configuração opcional que você pode ter em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0e53e-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="0e53e-179">Depois de obter essas informações, você poderá selecionar uma opção para criar um **novo host A ou AAAA**.</span><span class="sxs-lookup"><span data-stu-id="0e53e-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="0e53e-180">Agora você deve ser capaz de inserir um **Nome**, você precisa inserir lyncdiscover aqui para a URL do serviço de Descoberta Automática externa.</span><span class="sxs-lookup"><span data-stu-id="0e53e-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="0e53e-181">Em seguida, deve haver uma área para inserir em um endereço **IP,** que precisará ser o IP para seu pool de Front-End (ou servidor front-end único, ou pool de Diretores ou Diretores), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="0e53e-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="0e53e-182">Talvez seja necessário salvar aqui, ou se precisar criar registros A ou AAAA adicionais na zona de busca de encaminhamento de cada domínio SIP para seu ambiente do Skype for Business Server, faça isso, mas quando estiver pronto, salve seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e53e-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="0e53e-183">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="0e53e-183">Modify certificates</span></span>
<span data-ttu-id="0e53e-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="0e53e-184"><a name="ModCerts"> </a></span></span>

<span data-ttu-id="0e53e-185">Se você tiver dúvidas sobre o planejamento de certificados, documentamos isso no artigo Sobre o Plano de Mobilidade [do Skype for Business Server.](../plan-your-deployment/mobility.md)</span><span class="sxs-lookup"><span data-stu-id="0e53e-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="0e53e-186">Depois que você revisar isso, vamos dar um passo a passo para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0e53e-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="0e53e-187">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="0e53e-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="0e53e-188">Solicitando novos certificados de sua Autoridade de Certificação (CA).</span><span class="sxs-lookup"><span data-stu-id="0e53e-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="0e53e-189">Atualizando seus certificados in-locar com as substituições usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e53e-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="0e53e-190">Verificação dos certificados usando o snap-in Certificados no Console de Gerenciamento Microsoft (MMC).</span><span class="sxs-lookup"><span data-stu-id="0e53e-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="0e53e-191">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="0e53e-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="0e53e-192">Primeiro, talvez seja necessário verificar e ver quais certificados estão no local e se eles têm ou não as entradas de que você precisa.</span><span class="sxs-lookup"><span data-stu-id="0e53e-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="0e53e-193">Para fazer isso, você precisará entrar em seu Skype for Business Server com uma conta que seja um Administrador local.</span><span class="sxs-lookup"><span data-stu-id="0e53e-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="0e53e-194">Essa conta também pode precisar ter direitos para a autoridade de certificação (CA) em emissão, para algumas dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="0e53e-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="0e53e-195">Abra o Shell de Gerenciamento do Skype for Business Server (você pode usar a Pesquisa para encontrá-lo se não o tiver fixado no menu Iniciar ou na barra de tarefas).</span><span class="sxs-lookup"><span data-stu-id="0e53e-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="0e53e-196">Será essencial saber quais certificados foram atribuídos antes de tentar adicionar um certificado atualizado.</span><span class="sxs-lookup"><span data-stu-id="0e53e-196">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate.</span></span> <span data-ttu-id="0e53e-197">Portanto, no comando, digite:</span><span class="sxs-lookup"><span data-stu-id="0e53e-197">So at the command, type:</span></span>
    
   ```powershell
   Get-CsCertificate
   ```

4. <span data-ttu-id="0e53e-198">As informações da Etapa 3 serão exclusivas para você.</span><span class="sxs-lookup"><span data-stu-id="0e53e-198">The information from Step 3 will be unique to you.</span></span> <span data-ttu-id="0e53e-199">Você precisa procurar para determinar se você tem um único certificado que foi atribuído para várias coisas ou se você tem um certificado diferente atribuído para os diferentes componentes que precisam deles.</span><span class="sxs-lookup"><span data-stu-id="0e53e-199">You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them.</span></span> <span data-ttu-id="0e53e-200">O **parâmetro Use** dirá como um certificado está sendo usado, e o parâmetro **Thumbprint** dirá se é todo o mesmo certificado ou vários certificados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-200">The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="0e53e-201">Se você tiver as entradas SAN recomendadas em nossa seção de Planejamento, você está bem.</span><span class="sxs-lookup"><span data-stu-id="0e53e-201">If you have the SAN entries recommended in our Planning section, you're good.</span></span> <span data-ttu-id="0e53e-202">Caso não seja, você precisará solicitar um novo certificado ou vários certificados (dependendo da configuração) da Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="0e53e-202">If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="0e53e-203">Solicitar um novo certificado ou certificados à autoridade de certificação (CA)</span><span class="sxs-lookup"><span data-stu-id="0e53e-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="0e53e-204">Depois de verificar quais entradas SAN você tem, você sabe que tem um único certificado **(depois** de verificar as etapas acima) e aprendeu que não tem todas as entradas necessárias.</span><span class="sxs-lookup"><span data-stu-id="0e53e-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="0e53e-205">Uma nova solicitação de certificado precisa ser feita à sua AC.</span><span class="sxs-lookup"><span data-stu-id="0e53e-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="0e53e-206">Abra o PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0e53e-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="0e53e-207">Para um SAN ausente do Serviço de Descoberta Automática (substituindo o parâmetro -Ca por seu próprio caminho de Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0e53e-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="0e53e-208">Agora, se você tiver vários domínios SIP, não poderá usar o parâmetro AllSipDomain como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="0e53e-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="0e53e-209">Em vez disso, você precisará usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="0e53e-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="0e53e-210">E quando você usa o parâmetro DomainName, precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="0e53e-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="0e53e-211">Um exemplo seria (substituindo o parâmetro -Ca pelo seu próprio caminho de Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0e53e-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="0e53e-212">Ou, depois de verificar quais entradas SAN você tem, você descobriu que tem vários **certificados** que não têm todas as entradas de que precisa.</span><span class="sxs-lookup"><span data-stu-id="0e53e-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="0e53e-213">Uma nova solicitação de certificado precisa ser feita à sua AC.</span><span class="sxs-lookup"><span data-stu-id="0e53e-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="0e53e-214">Abra o PowerShell do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0e53e-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="0e53e-215">Para um SAN ausente do Serviço de Descoberta Automática (substituindo o parâmetro -Ca por seu próprio caminho de Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0e53e-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="0e53e-216">Agora, se você tiver vários domínios SIP, não poderá usar o parâmetro AllSipDomain como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="0e53e-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="0e53e-217">Em vez disso, você precisará usar o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="0e53e-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="0e53e-218">E quando você usa o parâmetro DomainName, precisa definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="0e53e-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="0e53e-219">Exemplos seriam (substituindo o parâmetro -Ca pelo seu próprio caminho de Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0e53e-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="0e53e-220">Depois que os novos certificados foram gerados pela AC, você precisará atribuí-los.</span><span class="sxs-lookup"><span data-stu-id="0e53e-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0e53e-221">Atribuir certificados usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e53e-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="0e53e-222">Dependendo do que você encontrou na seção Do I need new certifications above, você precisa executar **um** dos seguintes.</span><span class="sxs-lookup"><span data-stu-id="0e53e-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="0e53e-223">Se você tiver um único certificado para tudo (as impressões digitais são idênticas), será necessário executar isto:</span><span class="sxs-lookup"><span data-stu-id="0e53e-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="0e53e-224">Se você tiver certificados diferentes para coisas (as impressões digitais são diferentes), execute isto em vez disso:</span><span class="sxs-lookup"><span data-stu-id="0e53e-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="0e53e-225">Exibindo certificados no Console de Gerenciamento Microsoft (MMC)</span><span class="sxs-lookup"><span data-stu-id="0e53e-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="0e53e-226">Você tem uma opção para ver seus certificados usando o snap-in Certificados para o MMC.</span><span class="sxs-lookup"><span data-stu-id="0e53e-226">You have an option to look at your certificates using the Certificates snap-in for the MMC.</span></span> <span data-ttu-id="0e53e-227">Basta digitar O MMC na pesquisa e ele deve aparecer como uma opção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0e53e-227">Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="0e53e-228">Para adicionar o snap-in Certificados, você precisará clicar em Arquivo e, em seguida, **Adicionar/Remover Snap-In...** (ou o atalho de teclado **Ctrl+M** também funcionaria).</span><span class="sxs-lookup"><span data-stu-id="0e53e-228">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work).</span></span> <span data-ttu-id="0e53e-229">**Os certificados** serão uma opção no painel à esquerda, selecione-os e, em seguida, a Conta do Computador na janela pop-up e, em seguida, **Em Seguida.** </span><span class="sxs-lookup"><span data-stu-id="0e53e-229">**Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="0e53e-230">Ainda na janela pop-up, é muito provável que você esteja fazendo isso no computador que é a página principal dos certificados que você precisa ver, portanto, deixe a seleção no Computador **Local,** se for isso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="0e53e-231">Se você estiver trabalhando em um computador remoto, altere o botão de opção para Outro  Computador e insira o FQDN do computador ou use o botão Procurar para procurar esse computador por meio do AD. </span><span class="sxs-lookup"><span data-stu-id="0e53e-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="0e53e-232">Depois de selecionar o computador,  você precisará clicar em Concluir quando estiver pronto e, em seguida, **OK** para adicionar o snap-in ao MMC.</span><span class="sxs-lookup"><span data-stu-id="0e53e-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="0e53e-233">Expanda **a seção Certificados** no painel esquerdo do MMC.</span><span class="sxs-lookup"><span data-stu-id="0e53e-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="0e53e-234">Expanda **também a** pasta Pessoal e selecione **Certificados.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="0e53e-235">Isso permite que você veja os certificados neste armazenamento.</span><span class="sxs-lookup"><span data-stu-id="0e53e-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="0e53e-236">Você precisa localizar o certificado que deseja exibir, clicar com o botão direito do mouse nele e escolher **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0e53e-237">Como você sabe qual é o certificado?</span><span class="sxs-lookup"><span data-stu-id="0e53e-237">How do you know what certificate this is?</span></span> <span data-ttu-id="0e53e-238">Ele deve ser o único certificado atribuído a tudo em seu farm ou você pode ter vários certificados para coisas diferentes, como Padrão, Serviços Web Internos etc., nesse caso, talvez seja necessário procurar vários certificados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="0e53e-239">Vários certificados terão a mesma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="0e53e-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="0e53e-240">Depois de chegar ao exibição **Certificado,** escolha **Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-240">Once you've gotten to the **Certificate** view, choose **Details**.</span></span> <span data-ttu-id="0e53e-241">Isso permitirá que você veja o nome do assunto do certificado quando selecionar **Assunto,** e o nome da assunto atribuído e as propriedades associadas são mostrados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-241">This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="0e53e-242">Você também precisará verificar as entradas de Nome **Alternativo** da Assunto.</span><span class="sxs-lookup"><span data-stu-id="0e53e-242">You'll also need to check the **Subject Alternate Name** entries.</span></span> <span data-ttu-id="0e53e-243">Você encontrará um ou mais dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="0e53e-243">You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="0e53e-244">O nome do pool para este pool ou o nome do servidor único se não for um pool.</span><span class="sxs-lookup"><span data-stu-id="0e53e-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="0e53e-245">O nome do servidor ao que o certificado está atribuído.</span><span class="sxs-lookup"><span data-stu-id="0e53e-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="0e53e-246">Registros de URL simples, geralmente reunir e discar.</span><span class="sxs-lookup"><span data-stu-id="0e53e-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="0e53e-247">Nomes externos dos Serviços Web e internos dos Serviços Web (por exemplo, webpool01.contoso.net, webpool01.contoso.com), com base nas escolhas feitas no Construtor de Topologias e nas seleções de Serviços Web sobrecarecidos.</span><span class="sxs-lookup"><span data-stu-id="0e53e-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="0e53e-248">Se já tiver sido atribuído, a descoberta lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0e53e-248">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="0e53e-249">e lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0e53e-249">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="0e53e-250">records.</span><span class="sxs-lookup"><span data-stu-id="0e53e-250">records.</span></span>
    
     <span data-ttu-id="0e53e-251">Você precisará verificar vários certificados se tiver mais de um atribuído (verifique a Observação acima).</span><span class="sxs-lookup"><span data-stu-id="0e53e-251">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="0e53e-252">Portanto, se você encontrar lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0e53e-252">So, if you find lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="0e53e-253">e lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0e53e-253">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="0e53e-254">records, you've got this configured already.</span><span class="sxs-lookup"><span data-stu-id="0e53e-254">records, you've got this configured already.</span></span> <span data-ttu-id="0e53e-255">Você pode fechar o MMC.</span><span class="sxs-lookup"><span data-stu-id="0e53e-255">You can close the MMC.</span></span>
    
9. <span data-ttu-id="0e53e-256">Se elas não foram atribuídas, você precisará fazer uma nova solicitação de certificado (descrita acima) ou instalá-las pós-solicitação (recomendamos o Seguinte PowerShell acima para isso).</span><span class="sxs-lookup"><span data-stu-id="0e53e-256">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="0e53e-257">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="0e53e-257">Configure the reverse proxy</span></span>
<span data-ttu-id="0e53e-258"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="0e53e-258"><a name="ConfigRP"> </a></span></span>

<span data-ttu-id="0e53e-259">As etapas abaixo não devem ser seguidas exatamente.</span><span class="sxs-lookup"><span data-stu-id="0e53e-259">The steps below are not meant to be followed exactly.</span></span> <span data-ttu-id="0e53e-260">Isso acontece porque nas versões anteriores do produto, nós o explicamos, por exemplo, configurando o TMG (Gateway de Gerenciamento de Ameaças) e, se você não estivesse usando isso, precisaria trabalhar sua própria versão a partir daí.</span><span class="sxs-lookup"><span data-stu-id="0e53e-260">That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="0e53e-261">O TMG não está mais sendo oferecido pela Microsoft como um produto e, se você ainda precisar configurá-lo, poderá ver as etapas do [Lync Server 2013.](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0e53e-261">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="0e53e-262">Mas as informações a seguir se destinam a ser mais úteis em geral, mesmo que não haja como fornecer etapas passo a passo específicas para cada proxy reverso lá fora.</span><span class="sxs-lookup"><span data-stu-id="0e53e-262">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="0e53e-263">Temos duas coisas principais a considerar:</span><span class="sxs-lookup"><span data-stu-id="0e53e-263">We have two main things to consider:</span></span>
  
- <span data-ttu-id="0e53e-264">Você fará sua solicitação inicial de Descoberta Automática sobre HTTPS (o que recomendamos)?</span><span class="sxs-lookup"><span data-stu-id="0e53e-264">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="0e53e-265">Se você tiver uma regra de publicação na Web, precisará modificá-la.</span><span class="sxs-lookup"><span data-stu-id="0e53e-265">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="0e53e-266">Se você ainda não tiver uma regra de publicação na Web, será necessário crie-a.</span><span class="sxs-lookup"><span data-stu-id="0e53e-266">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="0e53e-267">Se você estiver fazendo sua solicitação inicial de Descoberta Automática sobre HTTP, precisará criar ou modificar essa regra também.</span><span class="sxs-lookup"><span data-stu-id="0e53e-267">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0e53e-268">**Importante** Um valor de tempo-out de proxy é um número que varia de implantação para implantação.</span><span class="sxs-lookup"><span data-stu-id="0e53e-268">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="0e53e-269">Você deve monitorar sua implantação e modificar o valor para a melhor experiência para os clientes.</span><span class="sxs-lookup"><span data-stu-id="0e53e-269">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="0e53e-270">Talvez seja possível definir o valor como 200.</span><span class="sxs-lookup"><span data-stu-id="0e53e-270">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="0e53e-271">Se estiver dando suporte a clientes móveis do Lync em seu ambiente, você deve definir o valor como 960 para permitir tempos-out de notificação por push do Office 365, que têm um valor de tempo de tempo de 900.</span><span class="sxs-lookup"><span data-stu-id="0e53e-271">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="0e53e-272">É muito provável que você tenha que aumentar o valor de tempo-out para evitar desconectar clientes quando o valor for muito baixo ou diminuir o número se as conexões por meio do proxy não se desconectarem, mas se desconectarem muito depois que o cliente se desconectar.</span><span class="sxs-lookup"><span data-stu-id="0e53e-272">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="0e53e-273">Monitorar e basear o que é comum para seu ambiente é a única maneira precisa de determinar a configuração apropriada para esse valor.</span><span class="sxs-lookup"><span data-stu-id="0e53e-273">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="0e53e-274">Modificar a regra de publicação na Web existente para a SAN e a URL externas de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="0e53e-274">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="0e53e-275">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-275">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="0e53e-276">Você precisará localizar a regra de publicação na Web e escolher a opção Editar (ela pode estar em um menu ou guia, dependendo da configuração do proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="0e53e-276">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="0e53e-277">Deve haver uma área que declara a que se aplica essa regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="0e53e-277">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="0e53e-278">Você precisa modificar essa regra para sites de entrada ou solicitações de sites.</span><span class="sxs-lookup"><span data-stu-id="0e53e-278">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="0e53e-279">Você adicionará **uma** nova entrada.</span><span class="sxs-lookup"><span data-stu-id="0e53e-279">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="0e53e-280">Digite o nome do seu site de Descoberta Automática (o exemplo que vamos usar é lyncdiscover.contoso.com) e clique em **OK** ou **Salvar,** dependendo do formato do seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-280">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="0e53e-281">Você pode ter um novo certificado que tenha a entrada SAN de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0e53e-281">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="0e53e-282">Isso também precisa ser instalado e configurado para uso de acordo com as configurações do seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-282">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="0e53e-283">Certifique-se de salvar tudo quando a configuração for concluída.</span><span class="sxs-lookup"><span data-stu-id="0e53e-283">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="0e53e-284">Se o proxy reverso tiver **uma funcionalidade** de teste, faça uso dele para garantir que tudo está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="0e53e-284">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="0e53e-285">Agora, talvez seja necessário repetir essas etapas se você tiver um Diretor ou pool de Diretores em seu ambiente (isso significa que você tem uma segunda regra).</span><span class="sxs-lookup"><span data-stu-id="0e53e-285">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="0e53e-286">Criar uma regra de publicação na Web para a URL externa de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="0e53e-286">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="0e53e-287">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-287">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="0e53e-288">Você precisará localizar onde na interface criar suas regras de publicação  na  Web e escolher a opção Novo ou Criar (pode estar em um menu ou guia, dependendo da configuração do proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="0e53e-288">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="0e53e-289">Você está procurando a opção para criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="0e53e-289">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="0e53e-290">Normalmente, você precisará inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0e53e-290">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="0e53e-291">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="0e53e-291">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="0e53e-292">**Ação de** regra: nesse caso, é uma regra **permitir,** você está permitindo que algo passe pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-292">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="0e53e-293">A **regra de** publicação ou a opção que você está escolhendo seria um único site da Web ou **balanceador de carga.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-293">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="0e53e-294">Isso precisa ser **SSL** para acesso externo, escolha essa opção.</span><span class="sxs-lookup"><span data-stu-id="0e53e-294">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="0e53e-295">Você precisará publicar um caminho para Publicação Interna e inserir o FQDN dos Serviços Web externos no balanceador de carga do pool de Front-End (ou o FQDN do balanceador de carga do pool de Diretores, se você tiver um), um exemplo seria sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="0e53e-295">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="0e53e-296">Você deve digitar _ como o caminho a ser publicado, mas também precisa **/\\** _\*encaminhar o título de host original\*\*.</span><span class="sxs-lookup"><span data-stu-id="0e53e-296">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="0e53e-297">Haverá uma opção para informações ou detalhes de nomes públicos **ou externos.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-297">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="0e53e-298">Este é o local onde você poderá inserir:</span><span class="sxs-lookup"><span data-stu-id="0e53e-298">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="0e53e-299">**Aceitar solicitações,** mas deve ser para o nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="0e53e-299">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="0e53e-300">For the **Name**, you should enter **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-300">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="0e53e-301"><sipdomain> (esta é a URL externa do Serviço de Descoberta Automática).</span><span class="sxs-lookup"><span data-stu-id="0e53e-301"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="0e53e-302">Agora, se você estiver criando uma regra para a URL de Serviços Web externa no pool de Front-End, será necessário digitar o FQDN para os Serviços Web externos em seu pool de Front-End (por exemplo, lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="0e53e-302">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="0e53e-303">Haverá uma opção **de** caminho, e você precisará inserir **/\\** _ aqui.</span><span class="sxs-lookup"><span data-stu-id="0e53e-303">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="0e53e-304">Você precisará selecionar um Ouvinte _ *SSL*\* com seu certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="0e53e-304">You'll need to select a _ *SSL Listener*\* with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="0e53e-305">**A Delegação de** Autenticação deve ser definida como **Nenhuma delegação,** mas a autenticação direta **do cliente deve** ser permitida.</span><span class="sxs-lookup"><span data-stu-id="0e53e-305">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="0e53e-306">A regra deve ser definida como **Todos os usuários.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-306">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="0e53e-307">Essas devem ser todas as informações necessárias para criar essa regra e permitir que você prossiga.</span><span class="sxs-lookup"><span data-stu-id="0e53e-307">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="0e53e-308">Você precisará garantir que o **título do host original** seja encaminhado.</span><span class="sxs-lookup"><span data-stu-id="0e53e-308">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="0e53e-309">As **portas do** Servidor Web também precisarão ser definidas. Você precisará fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0e53e-309">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="0e53e-310">**Redirecionar solicitações para a porta HTTP** e o número da porta deve ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="0e53e-310">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="0e53e-311">**Redirecionar solicitações para a porta SSL** e o número da porta deve ser **4443.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-311">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="0e53e-312">Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, testar a regra.</span><span class="sxs-lookup"><span data-stu-id="0e53e-312">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="0e53e-313">Criar uma regra de publicação na Web para a porta 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="0e53e-313">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="0e53e-314">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-314">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="0e53e-315">Você precisará localizar onde na interface criar suas regras de publicação  na  Web e escolher a opção Novo ou Criar (pode estar em um menu ou guia, dependendo da configuração do proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="0e53e-315">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="0e53e-316">Você está procurando a opção para criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="0e53e-316">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="0e53e-317">Normalmente, você precisará inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0e53e-317">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="0e53e-318">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="0e53e-318">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="0e53e-319">**Ação de** regra: nesse caso, é uma regra **permitir,** você está permitindo que algo passe pelo proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0e53e-319">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="0e53e-320">A **regra de** publicação ou a opção que você está escolhendo seria um único site da Web ou **balanceador de carga.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-320">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="0e53e-321">Isso precisa ser uma conexão não segura para se conectar ao **servidor Web ou farm publicado.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-321">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="0e53e-322">Você precisará publicar um caminho para Publicação Interna e inserir o FQDN do endereço **VIP** do balanceador de carga do seu pool de Front-End, um exemplo seria sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="0e53e-322">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="0e53e-323">Você deve digitar _ como o caminho a ser publicado, mas também precisa **/\\** _\*encaminhar o título de host original\*\*.</span><span class="sxs-lookup"><span data-stu-id="0e53e-323">You should type **/\\** _ as the path to be published, but you also need to _\*forward the original host header\*\*.</span></span>
    
   - <span data-ttu-id="0e53e-324">Haverá uma opção para informações ou detalhes de nomes públicos **ou externos.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-324">There will be an option for **public or external name** details or information.</span></span> <span data-ttu-id="0e53e-325">Este é o local onde você poderá inserir:</span><span class="sxs-lookup"><span data-stu-id="0e53e-325">This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="0e53e-326">**Aceitar solicitações,** mas deve ser para o nome de domínio.</span><span class="sxs-lookup"><span data-stu-id="0e53e-326">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="0e53e-327">For the **Name**, you should enter **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-327">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="0e53e-328"><sipdomain> (esta é a URL externa do Serviço de Descoberta Automática).</span><span class="sxs-lookup"><span data-stu-id="0e53e-328"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="0e53e-329">Haverá uma opção **de** caminho, e você precisará inserir **/\\** _ aqui.</span><span class="sxs-lookup"><span data-stu-id="0e53e-329">There will be a **Path** option, and you'll need to enter **/\\** _ here.</span></span>
    
   - <span data-ttu-id="0e53e-330">Você precisará selecionar um ouvinte da Web ou permitir que seu proxy reverso crie um para você.</span><span class="sxs-lookup"><span data-stu-id="0e53e-330">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="0e53e-331">_ *Delegação de* Autenticação \* deve ser definida como **Nenhuma delegação,** mas a autenticação direta do cliente **não deve** ser permitida.</span><span class="sxs-lookup"><span data-stu-id="0e53e-331">_ *Authentication Delegation*\* should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="0e53e-332">A regra deve ser definida como **Todos os usuários.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-332">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="0e53e-333">Essas devem ser todas as informações necessárias para criar essa regra e permitir que você prossiga.</span><span class="sxs-lookup"><span data-stu-id="0e53e-333">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="0e53e-334">As **portas do Servidor Web** precisarão ser definidas. Você precisará fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0e53e-334">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="0e53e-335">**Redirecionar solicitações para a porta HTTP** e o número da porta deve ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="0e53e-335">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="0e53e-336">**Redirecionar solicitações para a porta SSL** e o número da porta deve ser **4443.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-336">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="0e53e-337">Quando tudo estiver configurado, você precisará salvá-los ou aplicá-los e, em seguida, testar a regra.</span><span class="sxs-lookup"><span data-stu-id="0e53e-337">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="0e53e-338">Configurar a Descoberta Automática para Mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="0e53e-338">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="0e53e-339"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="0e53e-339"><a name="ConfigAutoD"> </a></span></span>

<span data-ttu-id="0e53e-340">Ambientes híbridos no Skype for Business Server são ambientes que combinam um ambiente local e o O365.</span><span class="sxs-lookup"><span data-stu-id="0e53e-340">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="0e53e-341">Quando você tem o Skype for Business Server trabalhando em um ambiente híbrido, o serviço descoberta automática precisa ser capaz de localizar um usuário de qualquer um desses ambientes.</span><span class="sxs-lookup"><span data-stu-id="0e53e-341">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="0e53e-342">Para permitir que os clientes móveis descubram onde um usuário está localizado, o serviço de Descoberta Automática precisa ser configurado com uma nova URL.</span><span class="sxs-lookup"><span data-stu-id="0e53e-342">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL).</span></span> <span data-ttu-id="0e53e-343">As etapas são:</span><span class="sxs-lookup"><span data-stu-id="0e53e-343">The steps are:</span></span>
  
1. <span data-ttu-id="0e53e-344">Abra o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e53e-344">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="0e53e-345">Execute o seguinte para obter o valor do atributo **ProxyFQDN** para seu ambiente do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0e53e-345">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```powershell
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="0e53e-346">Em seguida, ainda na janela do shell, execute:</span><span class="sxs-lookup"><span data-stu-id="0e53e-346">Then, still in the shell window, run:</span></span>
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="0e53e-347">Onde [identidade] é substituído pelo nome do domínio do espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="0e53e-347">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="0e53e-348">Testar sua implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0e53e-348">Test your Mobility deployment</span></span>
<span data-ttu-id="0e53e-349"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="0e53e-349"><a name="TestMobility"> </a></span></span>

<span data-ttu-id="0e53e-350">Depois de ter implantado o Skype for Business Server Mobility Service e o Serviço de Descoberta Automática do Skype for Business Server, você vai querer executar uma transação de teste, para garantir que sua implantação está funcionando responsabilidade.</span><span class="sxs-lookup"><span data-stu-id="0e53e-350">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="0e53e-351">Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários criarem, ingressarem e se comunicarem em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="0e53e-351">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="0e53e-352">Você precisará de dois usuários (reais ou de teste) e suas credenciais completas para fazer esse teste.</span><span class="sxs-lookup"><span data-stu-id="0e53e-352">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="0e53e-353">Esse comando funcionará tanto para clientes do Skype for Business quanto para clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e53e-353">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="0e53e-354">Para clientes do Lync Server 2010 no Skype for Business Server 2015, você precisará executar **Test-CsMcxP2PIM** para testar.</span><span class="sxs-lookup"><span data-stu-id="0e53e-354">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="0e53e-355">Seus usuários do Lync Server 2010 ainda precisarão ser usuários reais ou usuários de teste predefinidos, e você precisará das credenciais de senha deles.</span><span class="sxs-lookup"><span data-stu-id="0e53e-355">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="0e53e-356">O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0e53e-356">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0e53e-357">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="0e53e-357">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0e53e-358">Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="0e53e-358">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="0e53e-359">Testar a conferência para clientes móveis do Skype for Business e do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0e53e-359">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="0e53e-360">Faça logon como membro da **função CsAdministrator** em qualquer computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-360">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-361">Inicie o **Shell de Gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou ir para Todos os **Programas** e escolher).</span><span class="sxs-lookup"><span data-stu-id="0e53e-361">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="0e53e-362">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="0e53e-362">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="0e53e-363">Também é possível definir credenciais em um script e passá-las para o cmdlet de teste.</span><span class="sxs-lookup"><span data-stu-id="0e53e-363">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="0e53e-364">Temos um exemplo disso abaixo.</span><span class="sxs-lookup"><span data-stu-id="0e53e-364">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="0e53e-365">Testar a conferência para clientes móveis do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0e53e-365">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="0e53e-366">O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0e53e-366">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="0e53e-367">Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="0e53e-367">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="0e53e-368">Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="0e53e-368">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="0e53e-369">Faça logon como membro da **função CsAdministrator** em qualquer computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-369">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-370">Inicie o **Shell de Gerenciamento do Skype for Business Server** (você pode digitar o nome na pesquisa ou ir para Todos os **Programas** e escolher).</span><span class="sxs-lookup"><span data-stu-id="0e53e-370">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="0e53e-371">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="0e53e-371">At the command line, enter:</span></span>
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="0e53e-372">Também é possível definir credenciais em um script e passá-las para o cmdlet de teste.</span><span class="sxs-lookup"><span data-stu-id="0e53e-372">It's also possible to set credentials in a script and pass them to the test cmdlet.</span></span> <span data-ttu-id="0e53e-373">Temos um exemplo disso abaixo.</span><span class="sxs-lookup"><span data-stu-id="0e53e-373">We have an example of this below.</span></span>
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="0e53e-374">Para revisar ainda mais os procedimentos de comando, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0e53e-374">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="0e53e-375">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="0e53e-375">Configure for push notifications</span></span>
<span data-ttu-id="0e53e-376"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="0e53e-376"><a name="ConfigPush"> </a></span></span>

<span data-ttu-id="0e53e-377">As notificações por push, na forma de selos, ícones ou alertas, podem ser enviadas a um dispositivo móvel mesmo quando o aplicativo Skype ou Lync está inativo.</span><span class="sxs-lookup"><span data-stu-id="0e53e-377">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="0e53e-378">Mas o que são notificações por push?</span><span class="sxs-lookup"><span data-stu-id="0e53e-378">But what are push notifications?</span></span> <span data-ttu-id="0e53e-379">São alertas de eventos, como um convite de IM novo ou perdido ou para uma caixa postal recebida.</span><span class="sxs-lookup"><span data-stu-id="0e53e-379">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="0e53e-380">O serviço Mobilidade do Skype for Business Server envia essas notificações para o Serviço de Notificação por Push do Skype for Business Server baseado em nuvem, que envia as notificações para o Microsoft Push Notification Service (MSNS) para usuários do Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="0e53e-380">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="0e53e-381">Essa funcionalidade não foi alterada do Lync Server 2013, mas se você tiver um Skype for Business Server, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0e53e-381">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="0e53e-382">Para um Servidor de Borda do Skype for Business Server, adicione um novo provedor de hospedagem, o Microsoft Skype for Business Online, e, em seguida, configurar a federação do provedor de hospedagem entre sua organização e o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="0e53e-382">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="0e53e-383">Habilita as notificações por push executando o cmdlet **Set-CsPushNotificationConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-383">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="0e53e-384">Por padrão, as notificações por push estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="0e53e-384">By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="0e53e-385">Teste a configuração de federação e as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="0e53e-385">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="0e53e-386">Configurar o Servidor de Borda do Skype for Business para notificações por push</span><span class="sxs-lookup"><span data-stu-id="0e53e-386">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="0e53e-387">Faça logon, com uma conta que seja membro da função **CsAdministrator,** em um computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-387">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-388">Inicie o **Shell de Gerenciamento do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-388">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0e53e-389">Adicione um provedor de hospedagem online do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e53e-389">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="0e53e-390">Como exemplo:</span><span class="sxs-lookup"><span data-stu-id="0e53e-390">As an example:</span></span>
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="0e53e-391">Não é possível ter mais de um relacionamento de federação com um único provedor de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="0e53e-391">You can't have more than one federation relationship with a single hosting provider.</span></span> <span data-ttu-id="0e53e-392">Portanto, se você já tiver definido um provedor de hospedagem que tenha uma relação de federação com o sipfed.online.lync.com, não adicione outro provedor de hospedagem para ele, mesmo que a identidade do provedor de hospedagem seja algo diferente do SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="0e53e-392">So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="0e53e-393">Configurar a federação do provedor de hospedagem entre sua organização e o Serviço de Notificação por Push no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="0e53e-393">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="0e53e-394">Na linha de comando, você precisará digitar:</span><span class="sxs-lookup"><span data-stu-id="0e53e-394">At the command line, you'll need to type:</span></span>
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="0e53e-395">Habilitar notificações por push</span><span class="sxs-lookup"><span data-stu-id="0e53e-395">Enable push notifications</span></span>

1. <span data-ttu-id="0e53e-396">Faça logon, com uma conta que seja membro da função **CsAdministrator,** em um computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-396">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-397">Inicie o **Shell de Gerenciamento do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-397">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0e53e-398">Habilitar notificações por push:</span><span class="sxs-lookup"><span data-stu-id="0e53e-398">Enable push notifications:</span></span>
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="0e53e-399">Habilitar Federação:</span><span class="sxs-lookup"><span data-stu-id="0e53e-399">Enable Federation:</span></span>
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="0e53e-400">Testar notificações por push e federação</span><span class="sxs-lookup"><span data-stu-id="0e53e-400">Test federation and push notifications</span></span>

1. <span data-ttu-id="0e53e-401">Faça logon, com uma conta que seja membro da função **CsAdministrator,** em um computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-401">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-402">Inicie o **Shell de Gerenciamento do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-402">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0e53e-403">Teste a configuração de federação:</span><span class="sxs-lookup"><span data-stu-id="0e53e-403">Test the federation configuration:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="0e53e-404">Como exemplo:</span><span class="sxs-lookup"><span data-stu-id="0e53e-404">As an example:</span></span>
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="0e53e-405">Teste suas notificações por push:</span><span class="sxs-lookup"><span data-stu-id="0e53e-405">Test your push notifications:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="0e53e-406">Como exemplo:</span><span class="sxs-lookup"><span data-stu-id="0e53e-406">As an example:</span></span>
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="0e53e-407">Configurar política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0e53e-407">Configure Mobility policy</span></span>
<span data-ttu-id="0e53e-408"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="0e53e-408"><a name="ConfigMob"> </a></span></span>

<span data-ttu-id="0e53e-409">Você pode com o Skype for Business Server determinar quem pode usar seu serviço de Mobilidade, Telefonar via Trabalho, VoIP ou vídeo, bem como se o WiFi será necessário para VoIP ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="0e53e-409">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="0e53e-410">A Chamada via Trabalho permite que um usuário móvel use seu número de telefone comercial, em vez de seu número de telefone celular, ao fazer e receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="0e53e-410">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="0e53e-411">A pessoa na outra extremidade da linha não verá o número de telefone celular desse usuário móvel e permite que o usuário móvel evite cobranças de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="0e53e-411">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="0e53e-412">Quando VoIP e vídeo são definidos, os usuários podem fazer chamadas VoIP e vídeo.</span><span class="sxs-lookup"><span data-stu-id="0e53e-412">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="0e53e-413">As configurações de uso de WiFi determinam se o dispositivo móvel de um usuário será necessário para usar uma rede WiFi em uma rede de dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="0e53e-413">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="0e53e-414">Mobilidade, Telefonar via Trabalho, VoIP e recursos de vídeo estão habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="0e53e-414">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="0e53e-415">A configuração para exigir WiFi para VoIP e vídeo está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="0e53e-415">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="0e53e-416">Um administrador tem a capacidade de alterar isso, globalmente, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="0e53e-416">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="0e53e-417">Para poder usar os recursos de Mobilidade e Telefonar via Trabalho, os usuários precisam ser:</span><span class="sxs-lookup"><span data-stu-id="0e53e-417">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="0e53e-418">Habilitado para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e53e-418">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="0e53e-419">Habilitado para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0e53e-419">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="0e53e-420">Atribuída uma política de mobilidade que tem a **opção EnableMobility** definida como **True**.</span><span class="sxs-lookup"><span data-stu-id="0e53e-420">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="0e53e-421">Para que os usuários sejam capazes de usar a Chamada via Trabalho, eles também precisarão ser:</span><span class="sxs-lookup"><span data-stu-id="0e53e-421">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="0e53e-422">Foi atribuída uma política de voz que tem a **opção Habilitar toque simultâneo de telefones** selecionada.</span><span class="sxs-lookup"><span data-stu-id="0e53e-422">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="0e53e-423">Atribuída uma política de mobilidade que tem **o EnableOutsideVoice** definido como **True**.</span><span class="sxs-lookup"><span data-stu-id="0e53e-423">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0e53e-424">Os usuários que não estão habilitados para o Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas VoIP do Skype para Skype ou podem ingressar em conferências usando o link Clique para Ingressar enquanto estão em seus dispositivos móveis, se as opções apropriadas estão definidas para a política de voz à que estão associados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-424">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with.</span></span> <span data-ttu-id="0e53e-425">Há mais detalhes no tópico PLANEJAMENTO.</span><span class="sxs-lookup"><span data-stu-id="0e53e-425">There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="0e53e-426">Modificar a política de mobilidade global</span><span class="sxs-lookup"><span data-stu-id="0e53e-426">Modify global Mobility policy</span></span>

1. <span data-ttu-id="0e53e-427">Faça logon, com uma conta que seja membro da função **CsAdministrator,** em um computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-428">Inicie o **Shell de Gerenciamento do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0e53e-429">Desativar o acesso à Mobilidade e Telefonar via Trabalho globalmente digitando:</span><span class="sxs-lookup"><span data-stu-id="0e53e-429">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="0e53e-430">Você pode desativar a Chamada via Trabalho sem desativar o acesso ao Mobility.</span><span class="sxs-lookup"><span data-stu-id="0e53e-430">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="0e53e-431">Mas você não pode desativar a Mobilidade sem também desativar a Chamada via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e53e-431">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="0e53e-432">Para obter mais informações, consulte [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0e53e-432">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="0e53e-433">Modificar política de mobilidade por site</span><span class="sxs-lookup"><span data-stu-id="0e53e-433">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="0e53e-434">Faça logon, com uma conta que seja membro da função **CsAdministrator,** em um computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-434">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-435">Inicie o **Shell de Gerenciamento do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-435">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0e53e-436">Você pode criar uma política de nível de site, desativar VoIP e vídeo, habilitar Exigir WiFi para Áudio IP e Exigir WiFi para Vídeo IP por site.</span><span class="sxs-lookup"><span data-stu-id="0e53e-436">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site.</span></span> <span data-ttu-id="0e53e-437">Tipo:</span><span class="sxs-lookup"><span data-stu-id="0e53e-437">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="0e53e-438">Saiba mais em [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0e53e-438">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="0e53e-439">Modificar a política de mobilidade por usuário</span><span class="sxs-lookup"><span data-stu-id="0e53e-439">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="0e53e-440">Faça logon, com uma conta que seja membro da função **CsAdministrator,** em um computador onde o Shell de Gerenciamento do **Skype for Business Server** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0e53e-440">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0e53e-441">Inicie o **Shell de Gerenciamento do Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="0e53e-441">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0e53e-442">Crie políticas de mobilidade em nível de usuário e desligue Mobility e Telefonar via Trabalho por usuário.</span><span class="sxs-lookup"><span data-stu-id="0e53e-442">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="0e53e-443">Tipo:</span><span class="sxs-lookup"><span data-stu-id="0e53e-443">Type:</span></span>
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="0e53e-444">Mais um exemplo com dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="0e53e-444">A further example with sample data:</span></span>
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="0e53e-445">Você pode desativar a Chamada via Trabalho sem desativar o acesso ao Mobility.</span><span class="sxs-lookup"><span data-stu-id="0e53e-445">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="0e53e-446">Mas você não pode desativar a Mobilidade sem também desativar a Chamada via Trabalho.</span><span class="sxs-lookup"><span data-stu-id="0e53e-446">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

