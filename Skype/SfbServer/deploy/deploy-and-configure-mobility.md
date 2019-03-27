---
title: Implantar e configurar mobilidade do Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artigo falaremos as etapas para configurar um Skype existente para instalação do servidor de negócios para usar o serviço de mobilidade, permitindo que seus dispositivos móveis possam tirar vantagem do Skype para recursos de mobilidade do servidor de negócios.
ms.openlocfilehash: c9203bb90f4d4659819a4336c21f08e58785dfde
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884263"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a><span data-ttu-id="174ac-103">Implantar e configurar mobilidade do Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="174ac-103">Deploy and Configure Mobility for Skype for Business Server</span></span>  
 
<span data-ttu-id="174ac-104">Este artigo falaremos as etapas para configurar um Skype existente para instalação do servidor de negócios para usar o serviço de mobilidade, permitindo que seus dispositivos móveis possam tirar vantagem do Skype para recursos de mobilidade do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="174ac-104">This article will walk you through the steps to configure an existing Skype for Business Server installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="174ac-105">Ter analisado o artigo [Planejar para mobilidade para Skype para Business Server](../plan-your-deployment/mobility.md) , você deve estar pronto para prosseguir com as etapas abaixo para implantar a mobilidade em seu Skype para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="174ac-105">Having reviewed the [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server environment.</span></span> <span data-ttu-id="174ac-106">As etapas são as seguintes (e estamos incluindo nesta tabela uma lista de permissões):</span><span class="sxs-lookup"><span data-stu-id="174ac-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="174ac-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="174ac-107">**Phase**</span></span>|<span data-ttu-id="174ac-108">**Permissões**</span><span class="sxs-lookup"><span data-stu-id="174ac-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="174ac-109">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="174ac-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="174ac-110">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="174ac-110">Domain Admins</span></span>  <br/> <span data-ttu-id="174ac-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="174ac-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="174ac-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="174ac-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="174ac-113">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="174ac-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="174ac-114">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="174ac-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="174ac-115">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="174ac-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="174ac-116">Configurar Descoberta Automática para Mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="174ac-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="174ac-117">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="174ac-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="174ac-118">Testar a implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="174ac-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="174ac-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="174ac-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="174ac-120">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="174ac-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="174ac-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="174ac-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="174ac-122">Configurar a política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="174ac-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="174ac-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="174ac-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="174ac-p102">Todas as seções a seguir contêm as etapas que você já deve ter lido no tópico sobre planejamento. Se tiver dúvidas, consulte esse tópico.</span><span class="sxs-lookup"><span data-stu-id="174ac-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>

> [!NOTE]
> <span data-ttu-id="174ac-126">Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="174ac-126">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="174ac-127">Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="174ac-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="174ac-128">Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="174ac-128">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="174ac-129">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="174ac-129">Create DNS records</span></span>
<span data-ttu-id="174ac-130"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="174ac-130"></span></span>

<span data-ttu-id="174ac-131">Você pode já ter isso como parte da sua Skype para ambiente de servidor de negócios, mas você precisa criar os seguintes registros para descoberta automática funcionar:</span><span class="sxs-lookup"><span data-stu-id="174ac-131">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="174ac-132">Um registro DNS interno para dar suporte a usuários móveis que se conectam através da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="174ac-132">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="174ac-133">Um registro DNS externo (ou público) para dar suporte a usuários móveis que se conectam de fora da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="174ac-133">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="174ac-134">Esses registros podem ser nomes A (host) ou registros CNAME (você não precisa criar ambos, essas etapas são gerais).</span><span class="sxs-lookup"><span data-stu-id="174ac-134">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="174ac-135">Para criar um registro CNAME de DNS interno:</span><span class="sxs-lookup"><span data-stu-id="174ac-135">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="174ac-136">Faça logon em um servidor DNS em uma rede que seja membro do grupo **Admins. do Domínio** ou do grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="174ac-136">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="174ac-137">Clique em **Iniciar**, escolha **Ferramentas Administrativas** (talvez você precise **Pesquisar**, se ela for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo do DNS.</span><span class="sxs-lookup"><span data-stu-id="174ac-137">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="174ac-138">No painel esquerdo da janela do console, você precisará ir para o domínio que residencial para seu Skype para servidores Front-End do servidor de negócios e, em seguida, expanda as **Zonas de pesquisa direta** lá.</span><span class="sxs-lookup"><span data-stu-id="174ac-138">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="174ac-139">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="174ac-139">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="174ac-140">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="174ac-140">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="174ac-141">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="174ac-141">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="174ac-142">Depois disso, clique com o botão direito do mouse no nome do domínio SIP e escolha **Novo Alias (CNAME)** no menu.</span><span class="sxs-lookup"><span data-stu-id="174ac-142">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="174ac-143">Na caixa de texto **Nome de alias**, digite lyncdiscoverinternal como nome do host para a URL interna do serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="174ac-143">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="174ac-144">No **nome de domínio totalmente qualificado (FQDN para o host de destino**, você precisará digite ou procure o FQDN de serviços Web internos para seu Front End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="174ac-144">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="174ac-145">Clique em OK depois de inseri-lo.</span><span class="sxs-lookup"><span data-stu-id="174ac-145">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="174ac-146">Você precisará criar um novo registro de Autodiscover CNAME na zona de pesquisa direta para cada domínio SIP suportado em seu Skype para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="174ac-146">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="174ac-147">Criar um registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="174ac-147">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="174ac-148">As etapas aqui apresentadas são genéricas, pois não sabemos qual provedor DNS público você usará, mas vamos ajudá-lo mesmo assim. Faça logon no provedor DNS público com uma conta que aceite a criação de novos registros DNS.</span><span class="sxs-lookup"><span data-stu-id="174ac-148">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="174ac-149">Neste momento, um domínio SIP deve estar presente lá para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="174ac-149">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="174ac-150">Expanda ou abra a **Zona de Pesquisa Direta** desse domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="174ac-150">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="174ac-151">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="174ac-151">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="174ac-152">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="174ac-152">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="174ac-153">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="174ac-153">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="174ac-154">Depois de obter essas informações, você poderá selecionar uma opção para criar um **Novo Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="174ac-154">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="174ac-155">Agora digite um **Nome de Alias**. Você deve digitar lyncdiscover aqui para a URL externa de serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="174ac-155">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="174ac-156">Em seguida, deve haver uma área para entrar em um **FQDN do host de destino**, isso deverá ser o FQDN para seu Front-End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="174ac-156">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="174ac-157">Talvez seja necessário salvar aqui, ou se você precisar criar registros adicionais de CNAME na zona de pesquisa direta de cada domínio SIP em sua Skype para ambiente de servidor de negócios, você deve fazer isso, mas depois que você estiver pronto, salve o seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="174ac-157">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="174ac-158">Criar registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="174ac-158">Create an internal DNS A record</span></span>

1. <span data-ttu-id="174ac-159">Faça logon em um servidor DNS em uma rede que seja membro do grupo **Admins. do Domínio** ou do grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="174ac-159">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="174ac-160">Clique em **Iniciar**, escolha **Ferramentas Administrativas** (talvez você precise **Pesquisar**, se ela for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo do DNS.</span><span class="sxs-lookup"><span data-stu-id="174ac-160">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="174ac-161">No painel esquerdo da janela do console, você precisará ir para o domínio que residencial para seu Skype para servidores Front-End do servidor de negócios e, em seguida, expanda as **Zonas de pesquisa direta** lá.</span><span class="sxs-lookup"><span data-stu-id="174ac-161">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="174ac-162">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="174ac-162">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="174ac-163">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="174ac-163">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="174ac-164">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="174ac-164">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="174ac-165">Depois disso, clique com o botão direito do mouse no nome do domínio SIP e escolha **Novo Host (A ou AAAA)** no menu.</span><span class="sxs-lookup"><span data-stu-id="174ac-165">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="174ac-166">Na caixa de texto **Nome**, digite lyncdiscoverinternal como nome do host para a URL interna do serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="174ac-166">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="174ac-167">Na caixa de texto **Endereço IP** , digite o endereço de IP de serviços Web interno para seu Front End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="174ac-167">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="174ac-168">Ao concluir esse procedimento, clique em **Adicionar Host** e clique **OK**.</span><span class="sxs-lookup"><span data-stu-id="174ac-168">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="174ac-169">Você precisará criar novos registros de Autodiscover A ou AAAA na zona de pesquisa direta para cada domínio SIP suportado em seu Skype para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="174ac-169">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="174ac-170">Para isso, repita as etapas de 6 a 8 quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="174ac-170">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="174ac-171">Ao terminar, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="174ac-171">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="174ac-172">Criar um registro A de DNS externo</span><span class="sxs-lookup"><span data-stu-id="174ac-172">Create an external DNS A record</span></span>

1. <span data-ttu-id="174ac-173">As etapas aqui apresentadas são genéricas, pois não sabemos qual provedor DNS público você usará, mas vamos ajudá-lo mesmo assim. Faça logon no provedor DNS público com uma conta que aceite a criação de novos registros DNS.</span><span class="sxs-lookup"><span data-stu-id="174ac-173">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="174ac-174">Neste momento, um domínio SIP deve estar presente lá para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="174ac-174">At this point in time, a SIP domain should already exist there for Skype for Business Server.</span></span> <span data-ttu-id="174ac-175">Expanda ou abra a **Zona de Pesquisa Direta** desse domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="174ac-175">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="174ac-176">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="174ac-176">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="174ac-177">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="174ac-177">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="174ac-178">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="174ac-178">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="174ac-179">Depois de obter essas informações, você poderá selecionar uma opção para criar um **Novo Host A ou AAAA**.</span><span class="sxs-lookup"><span data-stu-id="174ac-179">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="174ac-180">Agora digite um **Nome**. Você deve digitar lyncdiscover aqui para a URL externa de serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="174ac-180">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="174ac-181">Em seguida, deve haver uma área para entrar em um **Endereço IP**, isso deverá ser o IP para seu Front End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="174ac-181">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="174ac-182">Talvez seja necessário salvar aqui, ou se você precisar criar adicionais A ou AAAA registra na zona de pesquisa direta de cada domínio SIP para sua Skype para ambiente de servidor de negócios, você deverá fazer isso, mas quando estiver pronto, salvar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="174ac-182">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="174ac-183">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="174ac-183">Modify certificates</span></span>
<span data-ttu-id="174ac-184"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="174ac-184"></span></span>

<span data-ttu-id="174ac-185">Se você tiver perguntas sobre planejamento ao redor de certificados, podemos ter documentado que nosso artigo [Planejar para mobilidade para Skype para Business Server](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="174ac-185">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="174ac-186">Depois de você ler esse artigo, continuaremos com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="174ac-186">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="174ac-187">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="174ac-187">Do I need new certificates?</span></span>
    
- <span data-ttu-id="174ac-188">Solicitando novos certificados à AC (Autoridade de Certificação).</span><span class="sxs-lookup"><span data-stu-id="174ac-188">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="174ac-189">Atualizando certificados in-loco por meio de substituições com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="174ac-189">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="174ac-190">Verificando os certificados usando o snap-in de certificados no Console de gerenciamento Microsoft (MMC).</span><span class="sxs-lookup"><span data-stu-id="174ac-190">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="174ac-191">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="174ac-191">Do I need new certificates?</span></span>

1. <span data-ttu-id="174ac-192">Primeiro, você talvez seja necessário verificar e ver quais certificados são in-loco e ou não têm as entradas que necessárias.</span><span class="sxs-lookup"><span data-stu-id="174ac-192">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="174ac-193">Para fazer isso, você precisará efetuar logon no seu Skype para Business Server com uma conta que seja um administrador local.</span><span class="sxs-lookup"><span data-stu-id="174ac-193">To do that, you'll need to log into your Skype for Business Server with an account that's a local Administrator.</span></span> <span data-ttu-id="174ac-194">Essa conta também pode precisar ter direitos à autoridade de certificado emissora (CA), para algumas dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="174ac-194">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="174ac-195">Abra o Skype para Business Server Management Shell (você pode usar Pesquisar para localizá-lo, se você não tivê-lo fixados à barra de menu ou tarefa do início).</span><span class="sxs-lookup"><span data-stu-id="174ac-195">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="174ac-p110">Você precisa saber quais certificados foram atribuídos antes de tentar adicionar um certificado atualizado. Portanto, no comando, digite:</span><span class="sxs-lookup"><span data-stu-id="174ac-p110">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="174ac-p111">As informações da Etapa 3 serão exclusivas para você. É necessário verificar se você tem um certificado único atribuído a vários componentes ou se você tem um certificado para cada componente. O parâmetro **Use** informará como o certificado está sendo usado, e o parâmetro **Thumbprint** informará se todos são o mesmo certificado ou se são vários certificados.</span><span class="sxs-lookup"><span data-stu-id="174ac-p111">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="174ac-p112">Se você tiver as entradas SAN recomendadas na seção de planejamento, você está no caminho certo. Caso contrário, deverá solicitar um novo certificado ou vários certificados (dependendo de sua configuração) à Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="174ac-p112">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="174ac-203">Solicitar um novo certificado ou certificados à AC</span><span class="sxs-lookup"><span data-stu-id="174ac-203">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="174ac-204">Depois de verificar quais entradas SAN possui, você constata que tem um **certificado único** (depois de fazer a verificação seguindo as etapas mencionadas acima) e que não tem todas as entradas necessárias.</span><span class="sxs-lookup"><span data-stu-id="174ac-204">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="174ac-205">Você deve fazer uma nova solicitação de certificado à AC.</span><span class="sxs-lookup"><span data-stu-id="174ac-205">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="174ac-206">Abra sua Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="174ac-206">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="174ac-207">Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="174ac-207">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="174ac-208">Agora, se você tiver vários domínios SIP, você não pode usar o parâmetro AllSipDomain como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="174ac-208">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="174ac-209">Em vez disso, use o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="174ac-209">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="174ac-210">Quando você usar o parâmetro DomainName, deverá definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="174ac-210">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="174ac-211">Um exemplo seria (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="174ac-211">An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="174ac-212">Ou, depois de verificar quais entradas SAN possui, você constata que tem **vários certificados** que não possuem todas as entradas necessárias.</span><span class="sxs-lookup"><span data-stu-id="174ac-212">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="174ac-213">Você deverá solicitar um novo certificado à AC.</span><span class="sxs-lookup"><span data-stu-id="174ac-213">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="174ac-214">Abra sua Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="174ac-214">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="174ac-215">Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="174ac-215">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="174ac-216">Agora, se você tiver vários domínios SIP, você não pode usar o parâmetro AllSipDomain como no exemplo acima.</span><span class="sxs-lookup"><span data-stu-id="174ac-216">Now, if you have multiple SIP domains, you can't use the AllSipDomain parameter as in the example above.</span></span> <span data-ttu-id="174ac-217">Em vez disso, use o parâmetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="174ac-217">You'll need to use the DomainName parameter instead.</span></span> <span data-ttu-id="174ac-218">Quando você usar o parâmetro DomainName, deverá definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="174ac-218">And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="174ac-219">Exemplos seriam (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="174ac-219">Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="174ac-220">Depois que os novos certificados forem gerados pela AC, você deverá atribuí-los.</span><span class="sxs-lookup"><span data-stu-id="174ac-220">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="174ac-221">Atribuir certificados usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="174ac-221">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="174ac-222">Dependendo da resposta obtida na seção "Preciso de novas certificações?", você deverá executar **um** dos seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="174ac-222">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="174ac-223">Se você tiver um certificado único para tudo (as impressões digitais são idênticas), execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="174ac-223">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="174ac-224">Se você tiver diferentes certificados para diferentes funções (as impressões digitais são diferentes), execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="174ac-224">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="174ac-225">Exibindo certificados no MMC (Console de Gerenciamento Microsoft)</span><span class="sxs-lookup"><span data-stu-id="174ac-225">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="174ac-p117">Você pode consultar seus certificados usando o snap-in de certificados do MMC. Basta digitar MMC no campo de pesquisa e ele será exibido como uma opção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="174ac-p117">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="174ac-p118">Para adicionar o snap-in de certificados, clique em **Arquivo** e em **Adicionar/Remover Snap-In...** (ou use o atalho do teclado **Ctrl+M**). A opção **Certificados** aparecerá no painel esquerdo, selecione-a, selecione **Conta de Computador** na janela pop-up e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="174ac-p118">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="174ac-230">Ainda na janela pop-up, se você estiver usando o computador onde estão os certificados que deseja consultar, mantenha a seleção **Computador Local**.</span><span class="sxs-lookup"><span data-stu-id="174ac-230">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="174ac-231">Se estiver trabalhando em um computador remoto, altere o botão de opção para **Outro Computador** e insira o FQDN do computador ou use o botão **Procurar** para procurar esse computador por meio do AD.</span><span class="sxs-lookup"><span data-stu-id="174ac-231">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="174ac-232">Depois de selecionar o computador, você precisará clicar em **Concluir** quando estiver pronto e em seguida **Okey** para adicionar o snap-in ao MMC.</span><span class="sxs-lookup"><span data-stu-id="174ac-232">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="174ac-233">Expanda a seção de **certificados** no painel esquerdo do MMC.</span><span class="sxs-lookup"><span data-stu-id="174ac-233">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="174ac-234">Expanda também a pasta **Pessoal** e selecione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="174ac-234">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="174ac-235">Isso permite que você veja os certificados nesse repositório.</span><span class="sxs-lookup"><span data-stu-id="174ac-235">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="174ac-236">Você deve localizar o certificado que deseja exibir, clicar com o botão direito do mouse nele e selecionar **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="174ac-236">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="174ac-237">Como você sabe qual certificado é por isso?</span><span class="sxs-lookup"><span data-stu-id="174ac-237">How do you know what certificate this is?</span></span> <span data-ttu-id="174ac-238">Ele deve ser o certificado único atribuído a tudo para seu farm, ou você pode ter vários certificados para coisas diferentes, como padrão, serviços Web internos, etc., caso em que você talvez precise olhar sobre os vários certificados.</span><span class="sxs-lookup"><span data-stu-id="174ac-238">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="174ac-239">Vários certificados terá a mesma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="174ac-239">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="174ac-p122">No modo de exibição **Certificado**, selecione **Detalhes**. Isso permitirá que você veja o nome do requerente do certificado quando selecionar **Entidade**, bem como o nome da entidade atribuída e as propriedades associadas.</span><span class="sxs-lookup"><span data-stu-id="174ac-p122">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="174ac-p123">Você também deverá verificar as entradas de **Nome Alternativo da Entidade**. Você encontrará uma ou mais das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="174ac-p123">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="174ac-244">O nome do pool para esse pool ou o nome de servidor único se este não for um pool.</span><span class="sxs-lookup"><span data-stu-id="174ac-244">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="174ac-245">O nome do servidor ao qual o certificado está atribuído.</span><span class="sxs-lookup"><span data-stu-id="174ac-245">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="174ac-246">Registros de URL Simples, normalmente reunir e discar.</span><span class="sxs-lookup"><span data-stu-id="174ac-246">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="174ac-247">Serviços da Web internos e serviços Web externos nomes (por exemplo, webpool01, webpool01.contoso.com), com base em escolhas feitas no construtor de topologias e nas seleções de serviços da Web.</span><span class="sxs-lookup"><span data-stu-id="174ac-247">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="174ac-248">Caso já estejam atribuídos a lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="174ac-248">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
     <span data-ttu-id="174ac-249">Você deverá verificar vários certificados, se tiver mais de um atribuído (consulte a Observação anterior).</span><span class="sxs-lookup"><span data-stu-id="174ac-249">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="174ac-250">Assim, se você encontrar lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros, você acaba de criar isso configurado já.</span><span class="sxs-lookup"><span data-stu-id="174ac-250">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="174ac-251">Você pode fechar o MMC.</span><span class="sxs-lookup"><span data-stu-id="174ac-251">You can close the MMC.</span></span>
    
9. <span data-ttu-id="174ac-252">Se eles não estiverem atribuídos, você deverá fazer uma nova solicitação de certificado (como descrito anteriormente) ou instalá-los após a solicitação (recomendamos usar o PowerShell mencionado anteriormente).</span><span class="sxs-lookup"><span data-stu-id="174ac-252">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="174ac-253">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="174ac-253">Configure the reverse proxy</span></span>
<span data-ttu-id="174ac-254"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="174ac-254"></span></span>

<span data-ttu-id="174ac-p125">As etapas a seguir não precisam ser seguidas à risca. Nas versões anteriores do produto, explicamos, por exemplo, a configuração do TMG (Threat Management Gateway) e, caso você não esteja usando esse recurso, deverá usar essas etapas adaptando-as para sua própria versão.</span><span class="sxs-lookup"><span data-stu-id="174ac-p125">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="174ac-257">Não há mais está sendo oferecido pela Microsoft como um produto do TMG e se você ainda precisar configurá-lo, você pode examinar as [etapas do Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="174ac-257">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="174ac-258">Mas, as seguintes informações do foi projetada para ser mais geralmente úteis, mesmo se não há fornecemos etapas específicas passo a passo para cada proxy reverso lá.</span><span class="sxs-lookup"><span data-stu-id="174ac-258">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="174ac-259">Devemos ter em mente duas considerações importantes:</span><span class="sxs-lookup"><span data-stu-id="174ac-259">We have two main things to consider:</span></span>
  
- <span data-ttu-id="174ac-260">Você fará sua solicitação inicial de Descoberta Automática por HTTPS (recomendável)?</span><span class="sxs-lookup"><span data-stu-id="174ac-260">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="174ac-261">Se você tiver uma regra de publicação na Web, deverá modificá-la.</span><span class="sxs-lookup"><span data-stu-id="174ac-261">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="174ac-262">Se você ainda não tiver uma regra de publicação na Web, deverá criá-la.</span><span class="sxs-lookup"><span data-stu-id="174ac-262">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="174ac-263">Se você estiver fazendo sua solicitação inicial de Descoberta Automática por HTTP, também deverá criar ou modificar essa regra.</span><span class="sxs-lookup"><span data-stu-id="174ac-263">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="174ac-264">**Importante** Um valor de tempo limite do Proxy é um número que vai variar de implantação para implantação.</span><span class="sxs-lookup"><span data-stu-id="174ac-264">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="174ac-265">Monitore a sua implantação e modificar o valor para uma melhor experiência para clientes.</span><span class="sxs-lookup"><span data-stu-id="174ac-265">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="174ac-266">Você poderá definir o valor mais baixo 200.</span><span class="sxs-lookup"><span data-stu-id="174ac-266">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="174ac-267">Caso tenha suporte para clientes móveis do Lync em seu ambiente, você deve definir o valor para 960 para permitir tempos limites de notificação de push do Office 365, que possuem um valor de tempo limite de 900.</span><span class="sxs-lookup"><span data-stu-id="174ac-267">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="174ac-268">É bem provável que você terá de aumentar o valor de tempo limite para evitar o cliente se desconecta quando o valor é muito baixo ou diminuir o número se conexões por meio do proxy não desconecte mas desmarque tempo depois que o cliente desconectado.</span><span class="sxs-lookup"><span data-stu-id="174ac-268">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="174ac-269">Monitoramento e linha de base o usual para seu ambiente é o único modo preciso para determinar a configuração apropriada para esse valor.</span><span class="sxs-lookup"><span data-stu-id="174ac-269">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="174ac-270">Modificar a regra de publicação na Web existente para SAN e URL externa de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="174ac-270">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="174ac-271">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="174ac-271">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="174ac-272">Você precisará localizar sua regra de publicação na web e, em seguida, escolha a opção de editar (pode ser em um menu ou guia, dependendo da configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="174ac-272">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="174ac-273">Deve haver uma área que afirma que essa regra de publicação na web é aplicada.</span><span class="sxs-lookup"><span data-stu-id="174ac-273">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="174ac-274">Você deve modificar essa regra para sites de entrada ou para solicitações a sites.</span><span class="sxs-lookup"><span data-stu-id="174ac-274">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="174ac-275">Você **adicionará** uma nova entrada.</span><span class="sxs-lookup"><span data-stu-id="174ac-275">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="174ac-276">Digite o nome do seu site de descoberta automática (o exemplo, que usaremos é lyncdiscover.contoso.com) e clique em **Okey** ou **Salvar**, dependendo do formato do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="174ac-276">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="174ac-277">Você pode ter um novo certificado que contenha a entrada SAN de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="174ac-277">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="174ac-278">Que precisa ser também instalado e configurado para uso de acordo com as configurações do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="174ac-278">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="174ac-279">Salve tudo após concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="174ac-279">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="174ac-280">Se seu proxy reverso tem uma funcionalidade de **teste** , em seguida, faça uso dele, para assegurar que tudo está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="174ac-280">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="174ac-281">Agora, você pode precisar Repita essas etapas se você tiver um diretor ou diretor pool em seu ambiente (isso significaria você tem uma segunda regra).</span><span class="sxs-lookup"><span data-stu-id="174ac-281">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="174ac-282">Criar uma regra de publicação na web para a URL de descoberta automática externa</span><span class="sxs-lookup"><span data-stu-id="174ac-282">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="174ac-283">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="174ac-283">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="174ac-284">Você precisará localizar onde na interface do você cria suas regras de publicação da web e escolha a opção **novo** ou **criar** (pode ser em um menu ou guia, dependendo da configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="174ac-284">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="174ac-285">Você está procurando a opção para criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="174ac-285">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="174ac-286">Normalmente, você deverá inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="174ac-286">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="174ac-287">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="174ac-287">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="174ac-288">**A ação de regra**: neste caso é uma regra de **permissão** , você estará permitindo algo passar através do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="174ac-288">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="174ac-289">A regra **Publicação** ou opção que você está escolhendo seria **único site da Web ou equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="174ac-289">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="174ac-290">Para acesso externo, deve ser **SSL**, escolha essa opção.</span><span class="sxs-lookup"><span data-stu-id="174ac-290">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="174ac-291">Você vai precisar de um caminho de publicação para **Publicação interna**e digite o FQDN para os serviços Web externos no balanceador de carga do seu pool de Front-End (ou o FQDN do balanceador de carga do Diretor do pool se você tiver um), um exemplo seria sfb_ pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="174ac-291">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="174ac-292">Você deve digitar \*\* / \*\*\* como o caminho a ser publicado, mas você também precisará **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="174ac-292">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="174ac-p131">Haverá uma opção para os detalhes ou informações do **nome público ou externo**. Este é o local onde você poderá inseri-los:</span><span class="sxs-lookup"><span data-stu-id="174ac-p131">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="174ac-295">**Aceitar solicitações**, mas deve ser para o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="174ac-295">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="174ac-296">Para o **Nome**, você deve inserir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="174ac-296">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="174ac-297"><sipdomain>(isto é a URL externa do serviço Descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="174ac-297"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="174ac-298">Agora, se você estiver criando uma regra para a URL externa de serviços Web no pool de Front-End, você precisará digite o FQDN para os serviços Web externos no seu pool de Front-End (por exemplo, lyncwebextpool01).</span><span class="sxs-lookup"><span data-stu-id="174ac-298">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="174ac-299">Haverá uma opção de **caminho** , e você precisará digitar \*\* / \*\*\* aqui.</span><span class="sxs-lookup"><span data-stu-id="174ac-299">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="174ac-300">Você deverá selecionar um **Ouvinte SSL** com o certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="174ac-300">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="174ac-301">
            A opção \*\*Delegação de Autenticação\*\* deve ser definida como \**Sem delegação\*\*, mas a autenticação direta de cliente \*\*deve\*\* ser permitida.</span><span class="sxs-lookup"><span data-stu-id="174ac-301">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="174ac-302">A regra deve ser definida para **Todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="174ac-302">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="174ac-303">Essa deve ser toda a informação que você precisa para criar esta regra e permitir que você continue.</span><span class="sxs-lookup"><span data-stu-id="174ac-303">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="174ac-304">Você deve garantir que o **cabeçalho do host original** seja encaminhado.</span><span class="sxs-lookup"><span data-stu-id="174ac-304">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="174ac-305">As portas do **Web Server** também deverão ser definidas. Para isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="174ac-305">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="174ac-306">**Redirecione as solicitações para a porta HTTP** e o número da porta deverá ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="174ac-306">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="174ac-307">**Redirecione as solicitações para a porta SSL** e o número da porta deverá ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="174ac-307">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="174ac-308">Quando tudo estiver configurado, você deverá salvar ou aplicar a configuração e depois testar a regra.</span><span class="sxs-lookup"><span data-stu-id="174ac-308">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="174ac-309">Para criar uma regra de publicação Web para a porta 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="174ac-309">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="174ac-310">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="174ac-310">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="174ac-311">Você precisará localizar onde na interface do você cria suas regras de publicação da web e escolha a opção **novo** ou **criar** (pode ser em um menu ou guia, dependendo da configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="174ac-311">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="174ac-312">Você está procurando a opção para criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="174ac-312">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="174ac-313">Normalmente, você deverá inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="174ac-313">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="174ac-314">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="174ac-314">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="174ac-315">**A ação de regra**: neste caso é uma regra de **permissão** , você estará permitindo algo passar através do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="174ac-315">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="174ac-316">A regra **Publicação** ou opção que você está escolhendo seria **único site da Web ou equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="174ac-316">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="174ac-317">Esta deve ser uma **conexão não segura para conectar-se à farm de servidores ou ao servidor Web publicado**.</span><span class="sxs-lookup"><span data-stu-id="174ac-317">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="174ac-318">Você vai precisar de um caminho de publicação para **Publicação interna**e digite o FQDN para o **endereço VIP** do balanceador de carga do seu pool de Front-End, um exemplo seria sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="174ac-318">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="174ac-319">Você deve digitar \*\* / \*\*\* como o caminho a ser publicado, mas você também precisará **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="174ac-319">You should type **/\\**\* as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="174ac-p134">Haverá uma opção para os detalhes ou informações do **nome público ou externo**. Este é o local onde você poderá inseri-los:</span><span class="sxs-lookup"><span data-stu-id="174ac-p134">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="174ac-322">**Aceitar solicitações**, mas deve ser para o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="174ac-322">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="174ac-323">Para o **Nome**, você deve inserir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="174ac-323">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="174ac-324"><sipdomain>(isto é a URL externa do serviço Descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="174ac-324"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="174ac-325">Haverá uma opção de **caminho** , e você precisará digitar \*\* / \*\*\* aqui.</span><span class="sxs-lookup"><span data-stu-id="174ac-325">There will be a **Path** option, and you'll need to enter **/\\**\* here.</span></span>
    
   - <span data-ttu-id="174ac-326">Você precisará selecionar um ouvinte da web ou permitir que o proxy reverso para criá-lo para você.</span><span class="sxs-lookup"><span data-stu-id="174ac-326">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="174ac-327">
            A opção \*\*Delegação de Autenticação\*\* deve ser definida como \**Sem delegação\*\*, mas a autenticação direta de cliente \*\*não deve\*\* ser permitida.</span><span class="sxs-lookup"><span data-stu-id="174ac-327">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="174ac-328">A regra deve ser definida para **Todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="174ac-328">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="174ac-329">Essa deve ser toda a informação que você precisa para criar esta regra e permitir que você continue.</span><span class="sxs-lookup"><span data-stu-id="174ac-329">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="174ac-330">As portas do **Web Server** deverão ser definidas. Para isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="174ac-330">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="174ac-331">**Redirecione as solicitações para a porta HTTP** e o número da porta deverá ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="174ac-331">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="174ac-332">**Redirecione as solicitações para a porta SSL** e o número da porta deverá ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="174ac-332">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="174ac-333">Quando tudo estiver configurado, você deverá salvar ou aplicar a configuração e depois testar a regra.</span><span class="sxs-lookup"><span data-stu-id="174ac-333">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="174ac-334">Configurar Descoberta Automática para Mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="174ac-334">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="174ac-335"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="174ac-335"></span></span>

<span data-ttu-id="174ac-336">Ambientes híbridos no Skype para Business Server são ambientes que combinam um local e o ambiente O365.</span><span class="sxs-lookup"><span data-stu-id="174ac-336">Hybrid environments in Skype for Business Server are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="174ac-337">Quando você tiver Skype para Business Server trabalhando em um ambiente híbrido, o serviço Descoberta automática deve ser capaz de localizar um usuário de qualquer um desses ambientes.</span><span class="sxs-lookup"><span data-stu-id="174ac-337">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="174ac-p137">Para permitir que os clientes móveis descubram onde um usuário está localizado, o serviço de Descoberta Automática deve ser configurado com uma nova URL. As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="174ac-p137">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="174ac-340">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="174ac-340">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="174ac-341">Execute o seguinte procedimento para obter o valor do atributo **ProxyFQDN** para sua Skype para ambiente de servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="174ac-341">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
   ```
   Get-CsHostingProvider
   ```

3. <span data-ttu-id="174ac-342">Então, na janela do Shell, excute:</span><span class="sxs-lookup"><span data-stu-id="174ac-342">Then, still in the shell window, run:</span></span>
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    <span data-ttu-id="174ac-343">Onde [identidade] é substituído pelo nome do domínio do espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="174ac-343">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="174ac-344">Testar a implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="174ac-344">Test your Mobility deployment</span></span>
<span data-ttu-id="174ac-345"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="174ac-345"></span></span>

<span data-ttu-id="174ac-346">Depois que você implantou Skype para o serviço de mobilidade do servidor de negócios e Skype para serviço de descoberta automática do servidor de negócios, convém executar uma transação de teste, para certificar-se o trabalho da sua implantação à direita.</span><span class="sxs-lookup"><span data-stu-id="174ac-346">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="174ac-347">Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários de criar, ingressar e se comunicar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="174ac-347">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="174ac-348">Você precisará de dois usuários (reais ou de teste) e de suas respectivas credenciais completas para executar esse teste.</span><span class="sxs-lookup"><span data-stu-id="174ac-348">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="174ac-349">Esse comando funcionará para ambos os Skype para clientes corporativos, bem como os clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="174ac-349">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="174ac-350">Para clientes do Lync Server 2010 em Skype para Business Server 2015, você precisará executar o **Test-CsMcxP2PIM** para testar.</span><span class="sxs-lookup"><span data-stu-id="174ac-350">For Lync Server 2010 clients on Skype for Business Server 2015, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="174ac-351">Os usuários do Lync Server 2010 ainda precisará ser usuários reais ou usuários de teste predefinida e você precisará suas credenciais de senha.</span><span class="sxs-lookup"><span data-stu-id="174ac-351">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="174ac-352">Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="174ac-352">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="174ac-353">Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="174ac-353">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="174ac-354">Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="174ac-354">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="174ac-355">Testar a conferência para clientes móveis do Skype for Business e do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="174ac-355">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="174ac-356">Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-357">Inicie o **Skype do Shell de gerenciamento do servidor de negócios** (você pode digitar o nome na pesquisa ou vá para **Todos os programas** e escolha-).</span><span class="sxs-lookup"><span data-stu-id="174ac-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="174ac-358">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="174ac-358">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="174ac-p141">Também é possível definir as credenciais em um script e enviá-las para o cmdlet de teste. Temos um exemplo disso a seguir.</span><span class="sxs-lookup"><span data-stu-id="174ac-p141">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="174ac-361">Testar a conferência para clientes móveis do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="174ac-361">Test conferencing for Lync 2010 mobile clients</span></span>

> [!NOTE]
> <span data-ttu-id="174ac-362">Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="174ac-362">MCX (Mobility Service) support for legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="174ac-363">Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos.</span><span class="sxs-lookup"><span data-stu-id="174ac-363">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="174ac-364">Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.</span><span class="sxs-lookup"><span data-stu-id="174ac-364">Users with legacy clients using MCX will need to upgrade to a current client.</span></span>

1. <span data-ttu-id="174ac-365">Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-365">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-366">Inicie o **Skype do Shell de gerenciamento do servidor de negócios** (você pode digitar o nome na pesquisa ou vá para **Todos os programas** e escolha-).</span><span class="sxs-lookup"><span data-stu-id="174ac-366">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="174ac-367">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="174ac-367">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="174ac-p143">Também é possível definir as credenciais em um script e enviá-las para o cmdlet de teste. Temos um exemplo disso a seguir.</span><span class="sxs-lookup"><span data-stu-id="174ac-p143">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

<span data-ttu-id="174ac-370">Para examinar melhor os procedimentos de comando, consulte [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="174ac-370">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="174ac-371">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="174ac-371">Configure for push notifications</span></span>
<span data-ttu-id="174ac-372"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="174ac-372"></span></span>

<span data-ttu-id="174ac-373">As notificações por push, na forma de notificações, ícones ou alertas, podem ser enviadas para um dispositivo móvel mesmo quando o aplicativo Skype ou Lync está inativo.</span><span class="sxs-lookup"><span data-stu-id="174ac-373">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="174ac-374">Mas, quais são as notificações por push?</span><span class="sxs-lookup"><span data-stu-id="174ac-374">But what are push notifications?</span></span> <span data-ttu-id="174ac-375">Elas são alertas de evento, como um convite novo ou perdido enviado por mensagem instantânea ou uma mensagem de voz recebida.</span><span class="sxs-lookup"><span data-stu-id="174ac-375">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="174ac-376">O Skype para serviço de mobilidade do servidor comercial envia essas notificações para o Skype baseado em nuvem para negócios Server Push notificação de serviço, que envia notificações para serviço de notificação Push do Microsoft (MSNS) para usuários do Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="174ac-376">The Skype for Business Server Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="174ac-377">Essa funcionalidade é alterada do Lync Server 2013, mas se você tiver um Skype para Business Server, você vai querer fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="174ac-377">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="174ac-378">Para um Skype para servidor de borda do servidor de negócios, adicionar um novo provedor de hospedagem, Microsoft Skype para negócios Online e configurar a federação do provedor entre sua organização e Skype para Business Online de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="174ac-378">For a Skype for Business Server Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="174ac-p145">Habilite notificações por push executando o cmdlet **Set-CsPushNotificationConfiguration**. Por padrão, as notificações por push estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="174ac-p145">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="174ac-381">Teste sua configuração de federação e as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="174ac-381">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="174ac-382">Configurar o Servidor de Borda do Skype for Business para notificações por push</span><span class="sxs-lookup"><span data-stu-id="174ac-382">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="174ac-383">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-384">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="174ac-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="174ac-385">Adicione um Skype para o provedor de hospedagem online Business Server.</span><span class="sxs-lookup"><span data-stu-id="174ac-385">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="174ac-386">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="174ac-386">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="174ac-p146">Não é possível ter mais de um relacionamento de federação com um único provedor de host. Ou seja, se você já tiver configurado um provedor de host que tenha um relacionamento de federação com sipfed.online.lync.com, não adicione outro provedor de host a ele, mesmo se a identidade do provedor de host for diferente de SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="174ac-p146">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="174ac-389">Configure a federação do provedor de hospedagem entre sua organização e o serviço de notificação por Push em Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="174ac-389">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="174ac-390">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="174ac-390">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="174ac-391">Habilitar notificações por push</span><span class="sxs-lookup"><span data-stu-id="174ac-391">Enable push notifications</span></span>

1. <span data-ttu-id="174ac-392">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-392">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-393">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="174ac-393">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="174ac-394">Habilite notificações por push:</span><span class="sxs-lookup"><span data-stu-id="174ac-394">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="174ac-395">Habilite a federação:</span><span class="sxs-lookup"><span data-stu-id="174ac-395">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="174ac-396">Testar a federação e as notificações por push</span><span class="sxs-lookup"><span data-stu-id="174ac-396">Test federation and push notifications</span></span>

1. <span data-ttu-id="174ac-397">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-397">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-398">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="174ac-398">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="174ac-399">Teste a configuração da federação:</span><span class="sxs-lookup"><span data-stu-id="174ac-399">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="174ac-400">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="174ac-400">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="174ac-401">Teste as notificações por push:</span><span class="sxs-lookup"><span data-stu-id="174ac-401">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="174ac-402">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="174ac-402">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="174ac-403">Configurar a política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="174ac-403">Configure Mobility policy</span></span>
<span data-ttu-id="174ac-404"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="174ac-404"></span></span>

<span data-ttu-id="174ac-405">Você tem a capacidade com Skype para Business Server determinar quem pode usar o serviço de mobilidade, chamada via trabalho, voz sobre IP (VoIP) ou vídeo, bem como se WiFi serão necessário para VoIP ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="174ac-405">You have the ability with Skype for Business Server to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="174ac-406">O recurso Telefonar via Trabalho permite que um usuário móvel use o número de seu telefone comercial, em vez de seu número particular, para fazer e receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="174ac-406">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="174ac-407">A pessoa na outra extremidade da linha não vê o número do celular desse usuário móvel, o que permite que o usuário móvel evite cobranças de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="174ac-407">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="174ac-408">Quando VoIP e vídeo são configurados, os usuários podem receber e fazer chamadas VoIP e de vídeo.</span><span class="sxs-lookup"><span data-stu-id="174ac-408">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="174ac-409">As configurações para o uso de WiFi determinam se o dispositivo móvel de um usuário precisa usar WiFi através de uma rede de dados de celular.</span><span class="sxs-lookup"><span data-stu-id="174ac-409">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="174ac-410">Mobilidade, chamada via trabalho e o VoIP e recursos de vídeo estão habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="174ac-410">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="174ac-411">As configurações para exigir WiFi para VoIP e vídeo estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="174ac-411">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="174ac-412">Um administrador pode alterar essas configurações em nível global, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="174ac-412">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="174ac-413">Para poder usar os recursos de mobilidade e chamada via trabalho, os usuários precisam ser:</span><span class="sxs-lookup"><span data-stu-id="174ac-413">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="174ac-414">Habilitado para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="174ac-414">Enabled for Skype for Business Server</span></span>
    
- <span data-ttu-id="174ac-415">Estar habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="174ac-415">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="174ac-416">Atribuída uma política de mobilidade que tem a opção **EnableMobility** definida como **True**.</span><span class="sxs-lookup"><span data-stu-id="174ac-416">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="174ac-417">Para usar o recurso Telefonar via Trabalho, os usuários devem:</span><span class="sxs-lookup"><span data-stu-id="174ac-417">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="174ac-418">Ter uma política de voz atribuída com a opção **Habilitar toques de telefones simultâneos** selecionada.</span><span class="sxs-lookup"><span data-stu-id="174ac-418">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="174ac-419">Atribuída uma política de mobilidade que tem o **EnableOutsideVoice** definida como **True**.</span><span class="sxs-lookup"><span data-stu-id="174ac-419">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="174ac-p150">Usuários não habilitados para Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas VoIP de Skype para Skype ou podem ingressar em conferências usando o link Clique para Ingressar quando estiverem usando dispositivos móveis, se as opções apropriadas estiverem definidas para a política de voz correspondente. Há mais detalhes no tópico PLANEJAMENTO.</span><span class="sxs-lookup"><span data-stu-id="174ac-p150">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="174ac-422">Modificar a política global de mobilidade</span><span class="sxs-lookup"><span data-stu-id="174ac-422">Modify global Mobility policy</span></span>

1. <span data-ttu-id="174ac-423">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-423">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-424">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="174ac-424">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="174ac-425">Desative acesso a mobilidade e telefonar via trabalho globalmente, digitando:</span><span class="sxs-lookup"><span data-stu-id="174ac-425">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="174ac-426">Você pode desativar chamada via trabalho sem desativar acesso a mobilidade.</span><span class="sxs-lookup"><span data-stu-id="174ac-426">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="174ac-427">Mas você não pode desativar mobilidade sem também desativando a chamada via trabalho.</span><span class="sxs-lookup"><span data-stu-id="174ac-427">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="174ac-428">Para obter mais informações, consulte [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="174ac-428">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="174ac-429">Modificar a política de mobilidade por site</span><span class="sxs-lookup"><span data-stu-id="174ac-429">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="174ac-430">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-430">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-431">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="174ac-431">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="174ac-p152">Você pode criar uma política no nível de site, desativar VoIP e vídeo, habilitar Exigir WiFi para Áudio IP e Exigir WiFi para Vídeo IP por site. Digite:</span><span class="sxs-lookup"><span data-stu-id="174ac-p152">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="174ac-434">Saiba mais em [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="174ac-434">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="174ac-435">Modificar a política de mobilidade por usuário</span><span class="sxs-lookup"><span data-stu-id="174ac-435">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="174ac-436">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="174ac-436">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="174ac-437">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="174ac-437">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="174ac-438">Criar políticas de mobilidade de nível de usuário e desativar a mobilidade e a chamada via trabalho por usuário.</span><span class="sxs-lookup"><span data-stu-id="174ac-438">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="174ac-439">Digite:</span><span class="sxs-lookup"><span data-stu-id="174ac-439">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="174ac-440">Mais um exemplo:</span><span class="sxs-lookup"><span data-stu-id="174ac-440">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="174ac-441">Você pode desativar chamada via trabalho sem desativar acesso a mobilidade.</span><span class="sxs-lookup"><span data-stu-id="174ac-441">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="174ac-442">Mas você não pode desativar mobilidade sem também desativando a chamada via trabalho.</span><span class="sxs-lookup"><span data-stu-id="174ac-442">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

