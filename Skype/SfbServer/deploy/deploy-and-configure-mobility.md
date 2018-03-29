---
title: Implantar e configurar Mobilidade para o Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Este artigo falaremos as etapas para configurar um Skype existente para Business Server 2015 instalação para usar o serviço de mobilidade, permitindo que seus dispositivos móveis possam tirar vantagem do Skype para recursos de mobilidade do servidor de negócios.
ms.openlocfilehash: c23974477ec815fca9c0cd3d78ac7acc0b81912e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server-2015"></a><span data-ttu-id="0039c-103">Implantar e configurar Mobilidade para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0039c-103">Deploy and Configure Mobility for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0039c-104">Este artigo falaremos as etapas para configurar um Skype existente para Business Server 2015 instalação para usar o serviço de mobilidade, permitindo que seus dispositivos móveis possam tirar vantagem do Skype para recursos de mobilidade do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0039c-104">This article will walk you through the steps to configure an existing Skype for Business Server 2015 installation to use the Mobility service, allowing your mobile devices to be able to take advantage of Skype for Business Server Mobility features.</span></span>
  
<span data-ttu-id="0039c-105">Ter analisado o artigo [Planejar para mobilidade para Skype para Business Server 2015](../plan-your-deployment/mobility.md) , você deve estar pronto para prosseguir com as etapas abaixo para implantar a mobilidade em seu Skype para ambiente de negócios Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0039c-105">Having reviewed the [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article, you should be ready to proceed with the steps below to deploy Mobility into your Skype for Business Server 2015 environment.</span></span> <span data-ttu-id="0039c-106">As etapas são as seguintes (e estamos incluindo nesta tabela uma lista de permissões):</span><span class="sxs-lookup"><span data-stu-id="0039c-106">The steps are as follows (and we're including in this table a permissions list):</span></span>
  
|<span data-ttu-id="0039c-107">**Fase**</span><span class="sxs-lookup"><span data-stu-id="0039c-107">**Phase**</span></span>|<span data-ttu-id="0039c-108">**Permissões**</span><span class="sxs-lookup"><span data-stu-id="0039c-108">**Permissions**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0039c-109">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="0039c-109">Create DNS records</span></span>](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |<span data-ttu-id="0039c-110">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="0039c-110">Domain Admins</span></span>  <br/> <span data-ttu-id="0039c-111">DNSAdmins</span><span class="sxs-lookup"><span data-stu-id="0039c-111">DNSAdmins</span></span>  <br/> |
|[<span data-ttu-id="0039c-112">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="0039c-112">Modify certificates</span></span>](deploy-and-configure-mobility.md#ModCerts) <br/> |<span data-ttu-id="0039c-113">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="0039c-113">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="0039c-114">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="0039c-114">Configure the reverse proxy</span></span>](deploy-and-configure-mobility.md#ConfigRP) <br/> |<span data-ttu-id="0039c-115">Administrador Local</span><span class="sxs-lookup"><span data-stu-id="0039c-115">Local Administrator</span></span>  <br/> |
|[<span data-ttu-id="0039c-116">Configurar Descoberta Automática para Mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="0039c-116">Configure Autodiscover for Mobility with hybrid deployments</span></span>](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |<span data-ttu-id="0039c-117">Admins. do Domínio</span><span class="sxs-lookup"><span data-stu-id="0039c-117">Domain Admins</span></span>  <br/> |
|[<span data-ttu-id="0039c-118">Testar a implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0039c-118">Test your Mobility deployment</span></span>](deploy-and-configure-mobility.md#TestMobility) <br/> |<span data-ttu-id="0039c-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0039c-119">CsAdministrator</span></span>  <br/> |
|[<span data-ttu-id="0039c-120">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="0039c-120">Configure for push notifications</span></span>](deploy-and-configure-mobility.md#ConfigPush) <br/> |<span data-ttu-id="0039c-121">RtcUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0039c-121">RtcUniversalServerAdmins</span></span>  <br/> |
|[<span data-ttu-id="0039c-122">Configurar a política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0039c-122">Configure Mobility policy</span></span>](deploy-and-configure-mobility.md#ConfigMob) <br/> |<span data-ttu-id="0039c-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0039c-123">CsAdministrator</span></span>  <br/> |
   
<span data-ttu-id="0039c-p102">Todas as seções a seguir contêm as etapas que você já deve ter lido no tópico sobre planejamento. Se tiver dúvidas, consulte esse tópico.</span><span class="sxs-lookup"><span data-stu-id="0039c-p102">All the following sections contain steps that assume you've read the Planning topic. If anything's confusing you, feel free to check out the information there.</span></span>
  
## <a name="create-dns-records"></a><span data-ttu-id="0039c-126">Criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="0039c-126">Create DNS records</span></span>
<span data-ttu-id="0039c-127"><a name="CreateDNSRec"> </a></span><span class="sxs-lookup"><span data-stu-id="0039c-127"></span></span>

<span data-ttu-id="0039c-128">Você pode já ter isso como parte da sua Skype para ambiente de servidor de negócios, mas você precisa criar os seguintes registros para descoberta automática funcionar:</span><span class="sxs-lookup"><span data-stu-id="0039c-128">You may already have these as part of your Skype for Business Server environment, but you do need to create the following records for Autodiscovery to work:</span></span>
  
- <span data-ttu-id="0039c-129">Um registro DNS interno para dar suporte a usuários móveis que se conectam através da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="0039c-129">An internal DNS record to support mobile users who're connecting from within your organization's network.</span></span>
    
- <span data-ttu-id="0039c-130">Um registro DNS externo (ou público) para dar suporte a usuários móveis que se conectam de fora da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="0039c-130">An external (or public) DNS record to support mobile users who're connecting from outside your organization's network.</span></span>
    
<span data-ttu-id="0039c-131">Esses registros podem ser nomes A (host) ou registros CNAME (você não precisa criar ambos, essas etapas são gerais).</span><span class="sxs-lookup"><span data-stu-id="0039c-131">These records can be either A (host) names or CNAME records (you don't have to make both, we're just including the steps for everything here).</span></span>
  
### <a name="create-an-internal-dns-cname-record"></a><span data-ttu-id="0039c-132">Para criar um registro CNAME de DNS interno:</span><span class="sxs-lookup"><span data-stu-id="0039c-132">Create an internal DNS CNAME record</span></span>

1. <span data-ttu-id="0039c-133">Faça logon em um servidor DNS em uma rede que seja membro do grupo **Admins. do Domínio** ou do grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="0039c-133">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="0039c-134">Clique em **Iniciar**, escolha **Ferramentas Administrativas** (talvez você precise **Pesquisar**, se ela for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo do DNS.</span><span class="sxs-lookup"><span data-stu-id="0039c-134">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="0039c-135">No painel esquerdo da janela do console, você precisará ir para o domínio que residencial para seu Skype para servidores Front-End do servidor de negócios e, em seguida, expanda as **Zonas de pesquisa direta** lá.</span><span class="sxs-lookup"><span data-stu-id="0039c-135">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="0039c-136">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="0039c-136">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0039c-137">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="0039c-137">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0039c-138">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0039c-138">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="0039c-139">Depois disso, clique com o botão direito do mouse no nome do domínio SIP e escolha **Novo Alias (CNAME)** no menu.</span><span class="sxs-lookup"><span data-stu-id="0039c-139">Once you've noted this, right-click your SIP domain name, and then choose **New Alias (CNAME)** from the menu.</span></span>
    
6. <span data-ttu-id="0039c-140">Na caixa de texto **Nome de alias**, digite lyncdiscoverinternal como nome do host para a URL interna do serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0039c-140">In the **Alias name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="0039c-141">No **nome de domínio totalmente qualificado (FQDN para o host de destino**, você precisará digite ou procure o FQDN de serviços Web internos para seu Front End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="0039c-141">In the **Fully qualified domain name (FQDN for target host**, you'll need to type or browse to the internal Web Services FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span> <span data-ttu-id="0039c-142">Clique em OK depois de inseri-lo.</span><span class="sxs-lookup"><span data-stu-id="0039c-142">Click OK when this is entered.</span></span>
    
8. <span data-ttu-id="0039c-143">Você precisará criar um novo registro de Autodiscover CNAME na zona de pesquisa direta para cada domínio SIP suportado em seu Skype para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0039c-143">You'll need to create a new Autodiscover CNAME record in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span>
    
### <a name="create-an-external-dns-cname-record"></a><span data-ttu-id="0039c-144">Criar um registro CNAME de DNS externo</span><span class="sxs-lookup"><span data-stu-id="0039c-144">Create an external DNS CNAME record</span></span>

1. <span data-ttu-id="0039c-145">As etapas aqui apresentadas são genéricas, pois não sabemos qual provedor DNS público você usará, mas vamos ajudá-lo mesmo assim. Faça logon no provedor DNS público com uma conta que aceite a criação de novos registros DNS.</span><span class="sxs-lookup"><span data-stu-id="0039c-145">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="0039c-146">Neste momento, um domínio SIP deve estar presente lá para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0039c-146">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="0039c-147">Expanda ou abra a **Zona de Pesquisa Direta** desse domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="0039c-147">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="0039c-148">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="0039c-148">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0039c-149">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="0039c-149">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0039c-150">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0039c-150">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="0039c-151">Depois de obter essas informações, você poderá selecionar uma opção para criar um **Novo Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="0039c-151">Once you have that information, you should be able to select an option for creating a **New Alias (CNAME)**.</span></span>
    
5. <span data-ttu-id="0039c-152">Agora digite um **Nome de Alias**. Você deve digitar lyncdiscover aqui para a URL externa de serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0039c-152">Now you should be able to enter an **Alias Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="0039c-153">Em seguida, deve haver uma área para entrar em um **FQDN do host de destino**, isso deverá ser o FQDN para seu Front-End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="0039c-153">Next there should be an area to enter in a **FQDN for target host**, this will need to be the FQDN for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="0039c-154">Talvez seja necessário salvar aqui, ou se você precisar criar registros adicionais de CNAME na zona de pesquisa direta de cada domínio SIP em sua Skype para ambiente de servidor de negócios, você deve fazer isso, mas depois que você estiver pronto, salve o seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0039c-154">You may need to save here, or if you need to create additional CNAME records in the forward lookup zone of each SIP domain in your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
### <a name="create-an-internal-dns-a-record"></a><span data-ttu-id="0039c-155">Criar registro A de DNS interno</span><span class="sxs-lookup"><span data-stu-id="0039c-155">Create an internal DNS A record</span></span>

1. <span data-ttu-id="0039c-156">Faça logon em um servidor DNS em uma rede que seja membro do grupo **Admins. do Domínio** ou do grupo **DnsAdmins**.</span><span class="sxs-lookup"><span data-stu-id="0039c-156">Log into a DNS server in your network that's either a member of the **Domain Admins** group or the **DnsAdmins** group.</span></span>
    
2. <span data-ttu-id="0039c-157">Clique em **Iniciar**, escolha **Ferramentas Administrativas** (talvez você precise **Pesquisar**, se ela for uma opção fora do menu Iniciar) e clique em **DNS** para abrir o snap-in administrativo do DNS.</span><span class="sxs-lookup"><span data-stu-id="0039c-157">Click **Start**, Choose **Administrative Tools** (you may need to **Search** for it if it's not an option off the Start menu), and then click **DNS** to open the DNS administrative snap-in.</span></span>
    
3. <span data-ttu-id="0039c-158">No painel esquerdo da janela do console, você precisará ir para o domínio que residencial para seu Skype para servidores Front-End do servidor de negócios e, em seguida, expanda as **Zonas de pesquisa direta** lá.</span><span class="sxs-lookup"><span data-stu-id="0039c-158">In the left-hand pane of the console window, you'll need to go to the domain that's home to your Skype for Business Server's Front End Servers, and expand the **Forward Lookup Zones** there.</span></span>
    
4. <span data-ttu-id="0039c-159">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="0039c-159">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0039c-160">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="0039c-160">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0039c-161">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0039c-161">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
5. <span data-ttu-id="0039c-162">Depois disso, clique com o botão direito do mouse no nome do domínio SIP e escolha **Novo Host (A ou AAAA)** no menu.</span><span class="sxs-lookup"><span data-stu-id="0039c-162">Once you've noted this, right-click your SIP domain name, and then choose **New Host (A or AAAA)** from the menu.</span></span>
    
6. <span data-ttu-id="0039c-163">Na caixa de texto **Nome**, digite lyncdiscoverinternal como nome do host para a URL interna do serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0039c-163">In the **Name** textbox, type lyncdiscoverinternal for your host name, for the internal Autodiscover service URL.</span></span>
    
7. <span data-ttu-id="0039c-164">Na caixa de texto **Endereço IP** , digite o endereço de IP de serviços Web interno para seu Front End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 4 acima.</span><span class="sxs-lookup"><span data-stu-id="0039c-164">In the **IP Address** textbox, type the internal Web Services IP address for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 4 above.</span></span>
    
8. <span data-ttu-id="0039c-165">Ao concluir esse procedimento, clique em **Adicionar Host** e clique **OK**.</span><span class="sxs-lookup"><span data-stu-id="0039c-165">When this is done, click **Add Host**, and then click **OK**.</span></span>
    
9. <span data-ttu-id="0039c-166">Você precisará criar novos registros de Autodiscover A ou AAAA na zona de pesquisa direta para cada domínio SIP suportado em seu Skype para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0039c-166">You'll need to create a new Autodiscover A or AAAA records in the forward lookup zone for each SIP domain supported in your Skype for Business Server environment.</span></span> <span data-ttu-id="0039c-167">Para isso, repita as etapas de 6 a 8 quantas vezes forem necessárias.</span><span class="sxs-lookup"><span data-stu-id="0039c-167">To do this, repeat steps 6-8 as many times as needed.</span></span>
    
10. <span data-ttu-id="0039c-168">Ao terminar, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="0039c-168">When you're done, click **Done**.</span></span>
    
### <a name="create-an-external-dns-a-record"></a><span data-ttu-id="0039c-169">Criar um registro A de DNS externo</span><span class="sxs-lookup"><span data-stu-id="0039c-169">Create an external DNS A record</span></span>

1. <span data-ttu-id="0039c-170">As etapas aqui apresentadas são genéricas, pois não sabemos qual provedor DNS público você usará, mas vamos ajudá-lo mesmo assim. Faça logon no provedor DNS público com uma conta que aceite a criação de novos registros DNS.</span><span class="sxs-lookup"><span data-stu-id="0039c-170">These steps are generic, because we can't tell what public DNS provider you might be using, but we still want to help you out. Please log into your public DNS provider with an account that will be able to make new DNS records there.</span></span>
    
2. <span data-ttu-id="0039c-171">Neste momento, um domínio SIP deve estar presente lá para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0039c-171">At this point in time, a SIP domain should already exist there for Skype for Business Server 2015.</span></span> <span data-ttu-id="0039c-172">Expanda ou abra a **Zona de Pesquisa Direta** desse domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="0039c-172">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise open it up.</span></span>
    
3. <span data-ttu-id="0039c-173">Verifique quais das opções abaixo você tem:</span><span class="sxs-lookup"><span data-stu-id="0039c-173">Take a moment to see which of the following you have:</span></span>
    
   - <span data-ttu-id="0039c-174">Qualquer A ou AAAA registros do host para o servidor Front-End (Standard ou Enterprise) ou o pool de Front-End (s).</span><span class="sxs-lookup"><span data-stu-id="0039c-174">Any host A or AAAA records for your Front End Server (Standard or Enterprise) or Front End pool(s).</span></span>
    
   - <span data-ttu-id="0039c-175">Qualquer uma AAAA registros de host ou de um diretor ou o Diretor do pool (uma configuração opcional que ocorram em sua implantação).</span><span class="sxs-lookup"><span data-stu-id="0039c-175">Any host A or AAAA records for a Director or Director pool (an optional configuration you may have in your deployment).</span></span>
    
4. <span data-ttu-id="0039c-176">Depois de obter essas informações, você poderá selecionar uma opção para criar um **Novo Host A ou AAAA**.</span><span class="sxs-lookup"><span data-stu-id="0039c-176">Once you have that information, you should be able to select an option for creating a **New Host A or AAAA**.</span></span>
    
5. <span data-ttu-id="0039c-177">Agora digite um **Nome**. Você deve digitar lyncdiscover aqui para a URL externa de serviço de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0039c-177">Now you should be able to enter a **Name**, you need to enter lyncdiscover here for the external Autodiscover service URL.</span></span>
    
6. <span data-ttu-id="0039c-178">Em seguida, deve haver uma área para entrar em um **Endereço IP**, isso deverá ser o IP para seu Front End pool (ou único servidor Front-End ou pool de diretores ou diretor), identificado na etapa 3 acima.</span><span class="sxs-lookup"><span data-stu-id="0039c-178">Next there should be an area to enter in a **IP Addresss**, this will need to be the IP for your Front End pool (or single Front End Server, or Director pool or Director), identified in step 3 above.</span></span>
    
7. <span data-ttu-id="0039c-179">Talvez seja necessário salvar aqui, ou se você precisar criar adicionais A ou AAAA registra na zona de pesquisa direta de cada domínio SIP para sua Skype para ambiente de servidor de negócios, você deverá fazer isso, mas quando estiver pronto, salvar seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0039c-179">You may need to save here, or if you need to create additional A or AAAA records in the forward lookup zone of each SIP domain for your Skype for Business Server environment, you should do that, but once you're ready, save your work.</span></span>
    
## <a name="modify-certificates"></a><span data-ttu-id="0039c-180">Modificar certificados</span><span class="sxs-lookup"><span data-stu-id="0039c-180">Modify certificates</span></span>
<span data-ttu-id="0039c-181"><a name="ModCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="0039c-181"></span></span>

<span data-ttu-id="0039c-182">Se você tiver perguntas sobre planejamento ao redor de certificados, podemos ter documentado que nosso artigo [Planejar para mobilidade para Skype para Business Server 2015](../plan-your-deployment/mobility.md) .</span><span class="sxs-lookup"><span data-stu-id="0039c-182">If you have questions about Planning around certificates, we've documented that in our [Plan for Mobility for Skype for Business Server 2015](../plan-your-deployment/mobility.md) article.</span></span> <span data-ttu-id="0039c-183">Depois de você ler esse artigo, continuaremos com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="0039c-183">Once you've reviewed that, we'll walk you through the following:</span></span>
  
- <span data-ttu-id="0039c-184">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="0039c-184">Do I need new certificates?</span></span>
    
- <span data-ttu-id="0039c-185">Solicitando novos certificados à AC (Autoridade de Certificação).</span><span class="sxs-lookup"><span data-stu-id="0039c-185">Requesting new certificates from your Certificate Authority (CA).</span></span>
    
- <span data-ttu-id="0039c-186">Atualizando certificados in-loco por meio de substituições com o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0039c-186">Updating your in-place certificates with the replacements using PowerShell.</span></span>
    
- <span data-ttu-id="0039c-187">Verificando os certificados usando o snap-in de certificados no Console de gerenciamento Microsoft (MMC).</span><span class="sxs-lookup"><span data-stu-id="0039c-187">Checking the certificates using the Certificates snapin in the Microsoft Management Console (MMC).</span></span>
    
### <a name="do-i-need-new-certificates"></a><span data-ttu-id="0039c-188">Preciso de novos certificados?</span><span class="sxs-lookup"><span data-stu-id="0039c-188">Do I need new certificates?</span></span>

1. <span data-ttu-id="0039c-189">Primeiro, você talvez seja necessário verificar e ver quais certificados são in-loco e ou não têm as entradas que necessárias.</span><span class="sxs-lookup"><span data-stu-id="0039c-189">First, you may need to check and see what certificates are in-place, and whether or not they have the entries you need.</span></span> <span data-ttu-id="0039c-190">Para fazer isso, você precisará fazer logon na sua Skype para servidor de Business Server 2015 com uma conta que seja um administrador local.</span><span class="sxs-lookup"><span data-stu-id="0039c-190">To do that, you'll need to log into your Skype for Business Server 2015 server with an account that's a local Administrator.</span></span> <span data-ttu-id="0039c-191">Essa conta também pode precisar ter direitos à autoridade de certificado emissora (CA), para algumas dessas etapas.</span><span class="sxs-lookup"><span data-stu-id="0039c-191">This account may also need to have rights to the issuing Certificate Authority (CA), for some of these steps.</span></span>
    
2. <span data-ttu-id="0039c-192">Abra o Skype para Business Server Management Shell (você pode usar Pesquisar para localizá-lo, se você não tivê-lo fixados à barra de menu ou tarefa do início).</span><span class="sxs-lookup"><span data-stu-id="0039c-192">Open the Skype for Business Server Management Shell (you can use Search to find it if you don't have it pinned to your Start menu or task bar).</span></span>
    
3. <span data-ttu-id="0039c-p109">Você precisa saber quais certificados foram atribuídos antes de tentar adicionar um certificado atualizado. Portanto, no comando, digite:</span><span class="sxs-lookup"><span data-stu-id="0039c-p109">It's going to be essential for you to know what certificates have been assigned before you try adding an updated certificate. So at the command, type:</span></span>
    
   ```
   Get-CsCertificate
   ```

4. <span data-ttu-id="0039c-p110">As informações da Etapa 3 serão exclusivas para você. É necessário verificar se você tem um certificado único atribuído a vários componentes ou se você tem um certificado para cada componente. O parâmetro **Use** informará como o certificado está sendo usado, e o parâmetro **Thumbprint** informará se todos são o mesmo certificado ou se são vários certificados.</span><span class="sxs-lookup"><span data-stu-id="0039c-p110">The information from Step 3 will be unique to you. You need to look it over to determine if you have a single certificate that's been assigned for multiple things, or whether you have a different certificate assigned for the different components that need them. The **Use** parameter will tell you how a certificate's being used, and the **Thumbprint** parameter will tell you if it's all the same certificate, or multiple certs.</span></span>
    
5. <span data-ttu-id="0039c-p111">Se você tiver as entradas SAN recomendadas na seção de planejamento, você está no caminho certo. Caso contrário, deverá solicitar um novo certificado ou vários certificados (dependendo de sua configuração) à Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="0039c-p111">If you have the SAN entries recommended in our Planning section, you're good. If not, you'll need to request a new certificate, or multiple certificates (depending on your configuration) from your Certificate Authority.</span></span>
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a><span data-ttu-id="0039c-200">Solicitar um novo certificado ou certificados à AC</span><span class="sxs-lookup"><span data-stu-id="0039c-200">Request a new certificate, or certificates, from your Certificate Authority (CA)</span></span>

1. <span data-ttu-id="0039c-201">Depois de verificar quais entradas SAN possui, você constata que tem um **certificado único** (depois de fazer a verificação seguindo as etapas mencionadas acima) e que não tem todas as entradas necessárias.</span><span class="sxs-lookup"><span data-stu-id="0039c-201">After you've checked to see what SAN entries you have, you know you have a **single certificate** (after checking via the steps above), and you learned you don't have all the entries you need.</span></span> <span data-ttu-id="0039c-202">Você deve fazer uma nova solicitação de certificado à AC.</span><span class="sxs-lookup"><span data-stu-id="0039c-202">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="0039c-203">Abra sua Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0039c-203">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="0039c-204">Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0039c-204">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="0039c-p113">Agora, se você tiver vários domínios SIP, não poderá usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, use o parâmetro DomainName. Quando você usar o parâmetro DomainName, deverá definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Um exemplo seria (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0039c-p113">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. An example would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. <span data-ttu-id="0039c-209">Ou, depois de verificar quais entradas SAN possui, você constata que tem **vários certificados** que não possuem todas as entradas necessárias.</span><span class="sxs-lookup"><span data-stu-id="0039c-209">Or, after you've checked to see what SAN entries you have, you found you have **multiple certificates** that don't have all the entries you need.</span></span> <span data-ttu-id="0039c-210">Você deverá solicitar um novo certificado à AC.</span><span class="sxs-lookup"><span data-stu-id="0039c-210">A new certificate request needs to be made to your CA.</span></span> <span data-ttu-id="0039c-211">Abra sua Skype para Business Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0039c-211">Open your Skype for Business Server PowerShell:</span></span>
    
   - <span data-ttu-id="0039c-212">Para um SAN de Serviço de Descoberta Automática ausente (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0039c-212">For a missing Autodiscover Service SAN (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - <span data-ttu-id="0039c-p115">Agora, se você tiver vários domínios SIP, não poderá usar o parâmetro AllSipDomain como no exemplo acima. Em vez disso, use o parâmetro DomainName. Quando você usar o parâmetro DomainName, deverá definir o FQDN para os registros lyncdiscoverinternal e lyncdiscover. Exemplos seriam (substituindo o parâmetro -Ca pelo caminho de sua própria Autoridade de Certificação):</span><span class="sxs-lookup"><span data-stu-id="0039c-p115">Now, if you have multiple SIP domains, you can't use the AllSipDomain paramater as in the example above. You'll need to use the DomainName parameter instead. And when you use the DomainName parameter, you've got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records. Examples would be (replacing the -Ca parameter with your own Certificate Authority path):</span></span>
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - <span data-ttu-id="0039c-217">Depois que os novos certificados forem gerados pela AC, você deverá atribuí-los.</span><span class="sxs-lookup"><span data-stu-id="0039c-217">Once the new certificates have been generated by the CA, you're going to need to assign them.</span></span>
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0039c-218">Atribuir certificados usando o Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0039c-218">Assign certificates using Skype for Business Server Management Shell</span></span>

- <span data-ttu-id="0039c-219">Dependendo da resposta obtida na seção "Preciso de novas certificações?", você deverá executar **um** dos seguintes comandos.</span><span class="sxs-lookup"><span data-stu-id="0039c-219">Depending on what you found in the Do I need new certifications section above, you need to run **one** of the following.</span></span>
    
  - <span data-ttu-id="0039c-220">Se você tiver um certificado único para tudo (as impressões digitais são idênticas), execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0039c-220">If you have a single certificate for everything (the thumbprints are identical) then you need to run this:</span></span>
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - <span data-ttu-id="0039c-221">Se você tiver diferentes certificados para diferentes funções (as impressões digitais são diferentes), execute o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0039c-221">If you've got different certificates for things (the thumbprints are all different), run this instead:</span></span>
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a><span data-ttu-id="0039c-222">Exibindo certificados no MMC (Console de Gerenciamento Microsoft)</span><span class="sxs-lookup"><span data-stu-id="0039c-222">Viewing certificates in the Microsoft Management Console (MMC)</span></span>

1. <span data-ttu-id="0039c-p116">Você pode consultar seus certificados usando o snap-in de certificados do MMC. Basta digitar MMC no campo de pesquisa e ele será exibido como uma opção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0039c-p116">You have an option to look at your certificates using the Certificates snap-in for the MMC. Simply type MMC into search and it should pop up as an application option,.</span></span>
    
2. <span data-ttu-id="0039c-p117">Para adicionar o snap-in de certificados, clique em **Arquivo** e em **Adicionar/Remover Snap-In...** (ou use o atalho do teclado **Ctrl+M**). A opção **Certificados** aparecerá no painel esquerdo, selecione-a, selecione **Conta de Computador** na janela pop-up e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="0039c-p117">To add the Certificates snap-in, you'll need to click **File**, and then **Add/Remove Snap-In...** (or keyboard shortcut **Ctrl+M** would also work). **Certificates** will be an option in the left-hand pane, select it and then **Computer Account** in the pop-up window, then **Next**.</span></span>
    
3. <span data-ttu-id="0039c-227">Ainda na janela pop-up, se você estiver usando o computador onde estão os certificados que deseja consultar, mantenha a seleção **Computador Local**.</span><span class="sxs-lookup"><span data-stu-id="0039c-227">Still in the pop-up window, in all likelihood you're doing this on the computer that's home to the certificates you need to look at, so leave the selection on **Local Computer** if that's so.</span></span> <span data-ttu-id="0039c-228">Se estiver trabalhando em um computador remoto, altere o botão de opção para **Outro Computador** e insira o FQDN do computador ou use o botão **Procurar** para procurar esse computador por meio do AD.</span><span class="sxs-lookup"><span data-stu-id="0039c-228">If you're working on a remote machine, change the radio button to **Another Computer** and then either enter that computer's FQDN or use the **Browse** button to search for that computer through AD.</span></span> <span data-ttu-id="0039c-229">Depois de selecionar o computador, você precisará clicar em **Concluir** quando estiver pronto e em seguida **Okey** para adicionar o snap-in ao MMC.</span><span class="sxs-lookup"><span data-stu-id="0039c-229">After selecting the computer, you'll need to click **Finish** when ready, and then **OK** to add the snap-in to the MMC.</span></span>
    
4. <span data-ttu-id="0039c-230">Expanda a seção de **certificados** no painel esquerdo do MMC.</span><span class="sxs-lookup"><span data-stu-id="0039c-230">Expand the **Certificates** section in the MMC's left-hand pane.</span></span> <span data-ttu-id="0039c-231">Expanda também a pasta **Pessoal** e selecione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="0039c-231">Expand the **Personal** folder as well, and then select **Certificates**.</span></span> <span data-ttu-id="0039c-232">Isso permite que você veja os certificados nesse repositório.</span><span class="sxs-lookup"><span data-stu-id="0039c-232">This lets you see the certificates in this store.</span></span>
    
5. <span data-ttu-id="0039c-233">Você deve localizar o certificado que deseja exibir, clicar com o botão direito do mouse nele e selecionar **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="0039c-233">You need to locate the certificate you want to view, right-click on it, and choose **Open**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0039c-234">Como você sabe qual certificado é por isso?</span><span class="sxs-lookup"><span data-stu-id="0039c-234">How do you know what certificate this is?</span></span> <span data-ttu-id="0039c-235">Ele deve ser o certificado único atribuído a tudo para seu farm, ou você pode ter vários certificados para coisas diferentes, como padrão, serviços Web internos, etc., caso em que você talvez precise olhar sobre os vários certificados.</span><span class="sxs-lookup"><span data-stu-id="0039c-235">It should be either the single certificate assigned to everything for your farm, or you may have multiple certificates for different things, like Default, Internal Web Services, etc., in which case you may need to look at multiple certificates.</span></span> <span data-ttu-id="0039c-236">Vários certificados terá a mesma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="0039c-236">Multiple certificates will have the same thumbprint.</span></span> 
  
6. <span data-ttu-id="0039c-p121">No modo de exibição **Certificado**, selecione **Detalhes**. Isso permitirá que você veja o nome do requerente do certificado quando selecionar **Entidade**, bem como o nome da entidade atribuída e as propriedades associadas.</span><span class="sxs-lookup"><span data-stu-id="0039c-p121">Once you've gotten to the **Certificate** view, choose **Details**. This will let you see the certificate subject name when you select **Subject**, and the assigned subject name and associated properties are shown.</span></span>
    
7. <span data-ttu-id="0039c-p122">Você também deverá verificar as entradas de **Nome Alternativo da Entidade**. Você encontrará uma ou mais das opções a seguir:</span><span class="sxs-lookup"><span data-stu-id="0039c-p122">You'll also need to check the **Subject Alternate Name** entries. You'll find one or more of the following:</span></span>
    
   - <span data-ttu-id="0039c-241">O nome do pool para esse pool ou o nome de servidor único se este não for um pool.</span><span class="sxs-lookup"><span data-stu-id="0039c-241">The pool name for this pool, or the single server name if this isn't a pool.</span></span>
    
   - <span data-ttu-id="0039c-242">O nome do servidor ao qual o certificado está atribuído.</span><span class="sxs-lookup"><span data-stu-id="0039c-242">The server name that the certificate is assigned to.</span></span>
    
   - <span data-ttu-id="0039c-243">Registros de URL Simples, normalmente reunir e discar.</span><span class="sxs-lookup"><span data-stu-id="0039c-243">Simple URL records, typically meet and dialin.</span></span>
    
   - <span data-ttu-id="0039c-244">Serviços da Web internos e serviços Web externos nomes (por exemplo, webpool01, webpool01.contoso.com), com base em escolhas feitas no construtor de topologias e nas seleções de serviços da Web.</span><span class="sxs-lookup"><span data-stu-id="0039c-244">Web Services internal and Web Services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden Web Services selections.</span></span>
    
   - <span data-ttu-id="0039c-245">Caso já estejam atribuídos a lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="0039c-245">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="0039c-246">Você deverá verificar vários certificados, se tiver mais de um atribuído (consulte a Observação anterior).</span><span class="sxs-lookup"><span data-stu-id="0039c-246">You'll need to check multiple certificates if you have more than one assigned (check the Note above).</span></span>
    
8. <span data-ttu-id="0039c-247">Assim, se você encontrar lyncdiscover. \<sipdomain\> e lyncdiscoverinternal. \<sipdomain\> registros, você acaba de criar isso configurado já.</span><span class="sxs-lookup"><span data-stu-id="0039c-247">So, if you find lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records, you've got this configured already.</span></span> <span data-ttu-id="0039c-248">Você pode fechar o MMC.</span><span class="sxs-lookup"><span data-stu-id="0039c-248">You can close the MMC.</span></span>
    
9. <span data-ttu-id="0039c-249">Se eles não estiverem atribuídos, você deverá fazer uma nova solicitação de certificado (como descrito anteriormente) ou instalá-los após a solicitação (recomendamos usar o PowerShell mencionado anteriormente).</span><span class="sxs-lookup"><span data-stu-id="0039c-249">If they aren't assigned, you'll either need to make a new certificate request (outlined above) or you need to install them post-request (we recommend the following the PowerShell above for that).</span></span>
    
## <a name="configure-the-reverse-proxy"></a><span data-ttu-id="0039c-250">Configurar o proxy inverso</span><span class="sxs-lookup"><span data-stu-id="0039c-250">Configure the reverse proxy</span></span>
<span data-ttu-id="0039c-251"><a name="ConfigRP"> </a></span><span class="sxs-lookup"><span data-stu-id="0039c-251"></span></span>

<span data-ttu-id="0039c-p124">As etapas a seguir não precisam ser seguidas à risca. Nas versões anteriores do produto, explicamos, por exemplo, a configuração do TMG (Threat Management Gateway) e, caso você não esteja usando esse recurso, deverá usar essas etapas adaptando-as para sua própria versão.</span><span class="sxs-lookup"><span data-stu-id="0039c-p124">The steps below are not meant to be followed exactly. That's because in previous versions of the product, we'd have walked you through, for example, configuring Threat Management Gateway (TMG) and if you weren't using that, you'd need to work out your own version from there.</span></span>
  
<span data-ttu-id="0039c-254">Não há mais está sendo oferecido pela Microsoft como um produto do TMG e se você ainda precisar configurá-lo, você pode examinar as [etapas do Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="0039c-254">TMG is no longer being offered by Microsoft as a product, and if you still need to configure it, you can look at the [Lync Server 2013 steps](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx).</span></span> <span data-ttu-id="0039c-255">Mas, as seguintes informações do foi projetada para ser mais geralmente úteis, mesmo se não há fornecemos etapas específicas passo a passo para cada proxy reverso lá.</span><span class="sxs-lookup"><span data-stu-id="0039c-255">But the following information's intended to be more generally helpful, even if there's no way we can provide specific walkthrough steps for every Reverse proxy out there.</span></span>
  
<span data-ttu-id="0039c-256">Devemos ter em mente duas considerações importantes:</span><span class="sxs-lookup"><span data-stu-id="0039c-256">We have two main things to consider:</span></span>
  
- <span data-ttu-id="0039c-257">Você fará sua solicitação inicial de Descoberta Automática por HTTPS (recomendável)?</span><span class="sxs-lookup"><span data-stu-id="0039c-257">Are you going to be doing your initial Autodiscover request over HTTPS (which we recommend)?</span></span>
    
  - <span data-ttu-id="0039c-258">Se você tiver uma regra de publicação na Web, deverá modificá-la.</span><span class="sxs-lookup"><span data-stu-id="0039c-258">If you have a web publishing rule, you need to modify it.</span></span>
    
  - <span data-ttu-id="0039c-259">Se você ainda não tiver uma regra de publicação na Web, deverá criá-la.</span><span class="sxs-lookup"><span data-stu-id="0039c-259">If you don't have a web publishing rule yet, you need to create it.</span></span>
    
- <span data-ttu-id="0039c-260">Se você estiver fazendo sua solicitação inicial de Descoberta Automática por HTTP, também deverá criar ou modificar essa regra.</span><span class="sxs-lookup"><span data-stu-id="0039c-260">If you're doing your initial Autodiscover request over HTTP, then you'll need to create or modify that rule as well.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0039c-261">**Importante** Um valor de tempo limite do Proxy é um número que vai variar de implantação para implantação.</span><span class="sxs-lookup"><span data-stu-id="0039c-261">**Important** A Proxy time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="0039c-262">Monitore a sua implantação e modificar o valor para uma melhor experiência para clientes.</span><span class="sxs-lookup"><span data-stu-id="0039c-262">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="0039c-263">Você poderá definir o valor mais baixo 200.</span><span class="sxs-lookup"><span data-stu-id="0039c-263">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="0039c-264">Caso tenha suporte para clientes móveis do Lync em seu ambiente, você deve definir o valor para 960 para permitir tempos limites de notificação de push do Office 365, que possuem um valor de tempo limite de 900.</span><span class="sxs-lookup"><span data-stu-id="0039c-264">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notification time-outs from Office 365, which have a time-out value of 900.</span></span> <span data-ttu-id="0039c-265">É bem provável que você terá de aumentar o valor de tempo limite para evitar o cliente se desconecta quando o valor é muito baixo ou diminuir o número se conexões por meio do proxy não desconecte mas desmarque tempo depois que o cliente desconectado.</span><span class="sxs-lookup"><span data-stu-id="0039c-265">It is very likely that you will have to increase the time-out value to avoid client disconnects when the value is too low, or decrease the number if connections through the proxy do not disconnect but clear long after the client has disconnected.</span></span> <span data-ttu-id="0039c-266">Monitoramento e linha de base o usual para seu ambiente é o único modo preciso para determinar a configuração apropriada para esse valor.</span><span class="sxs-lookup"><span data-stu-id="0039c-266">Monitoring and baselining what is usual for your environment is the only accurate way to determine the appropriate setting for this value.</span></span>
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a><span data-ttu-id="0039c-267">Modificar a regra de publicação na Web existente para SAN e URL externa de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="0039c-267">Modify the existing web publishing rule for your external Autodiscover SAN and URL</span></span>

1. <span data-ttu-id="0039c-268">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0039c-268">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="0039c-269">Você precisará localizar sua regra de publicação na web e, em seguida, escolha a opção de editar (pode ser em um menu ou guia, dependendo da configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="0039c-269">You'll need to locate your web publishing rule, and choose the Edit option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span>
    
3. <span data-ttu-id="0039c-270">Deve haver uma área que afirma que essa regra de publicação na web é aplicada.</span><span class="sxs-lookup"><span data-stu-id="0039c-270">There should be an area that states what this web publishing rule is applied to.</span></span> <span data-ttu-id="0039c-271">Você deve modificar essa regra para sites de entrada ou para solicitações a sites.</span><span class="sxs-lookup"><span data-stu-id="0039c-271">You need to modify this rule for incoming sites or requests for sites.</span></span> <span data-ttu-id="0039c-272">Você **adicionará** uma nova entrada.</span><span class="sxs-lookup"><span data-stu-id="0039c-272">You're going to **add** a new entry.</span></span>
    
4. <span data-ttu-id="0039c-273">Digite o nome do seu site de descoberta automática (o exemplo, que usaremos é lyncdiscover.contoso.com) e clique em **Okey** ou **Salvar**, dependendo do formato do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0039c-273">Type the name of your Autodiscover site (the example we'll use is lyncdiscover.contoso.com), and click **OK** or **Save**, depending on your Reverse proxy's format.</span></span>
    
5. <span data-ttu-id="0039c-274">Você pode ter um novo certificado que contenha a entrada SAN de Descoberta Automática.</span><span class="sxs-lookup"><span data-stu-id="0039c-274">You may have a new certificate that has the Autodiscover SAN entry in it.</span></span> <span data-ttu-id="0039c-275">Que precisa ser também instalado e configurado para uso de acordo com as configurações do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0039c-275">That needs to be installed as well and configured for use according to your Reverse proxy's settings.</span></span> <span data-ttu-id="0039c-276">Salve tudo após concluir a configuração.</span><span class="sxs-lookup"><span data-stu-id="0039c-276">Be sure to save everything when the configuration is completed.</span></span>
    
6. <span data-ttu-id="0039c-277">Se seu proxy reverso tem uma funcionalidade de **teste** , em seguida, faça uso dele, para assegurar que tudo está funcionando corretamente.</span><span class="sxs-lookup"><span data-stu-id="0039c-277">If your Reverse proxy has a **Test** functionality, then please make use of it, to ensure everything's working properly.</span></span>
    
7. <span data-ttu-id="0039c-278">Agora, você pode precisar Repita essas etapas se você tiver um diretor ou diretor pool em seu ambiente (isso significaria você tem uma segunda regra).</span><span class="sxs-lookup"><span data-stu-id="0039c-278">Now, you may need to repeat these steps if you have a Director or Director pool in your environment (this would mean you have a second rule).</span></span>
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="0039c-279">Criar uma regra de publicação na web para a URL de descoberta automática externa</span><span class="sxs-lookup"><span data-stu-id="0039c-279">Create a web publishing rule for the external Autodiscover URL</span></span>

1. <span data-ttu-id="0039c-280">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0039c-280">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="0039c-281">Você precisará localizar onde na interface do você cria suas regras de publicação da web e escolha a opção **novo** ou **criar** (pode ser em um menu ou guia, dependendo da configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="0039c-281">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="0039c-282">Você está procurando a opção para criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="0039c-282">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="0039c-283">Normalmente, você deverá inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0039c-283">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="0039c-284">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="0039c-284">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="0039c-285">**A ação de regra**: neste caso é uma regra de **permissão** , você estará permitindo algo passar através do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0039c-285">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="0039c-286">A regra **Publicação** ou opção que você está escolhendo seria **único site da Web ou equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="0039c-286">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="0039c-287">Para acesso externo, deve ser **SSL**, escolha essa opção.</span><span class="sxs-lookup"><span data-stu-id="0039c-287">This needs to be **SSL** for external access, choose that option.</span></span>
    
   - <span data-ttu-id="0039c-288">Você vai precisar de um caminho de publicação para **Publicação interna**e digite o FQDN para os serviços Web externos no balanceador de carga do seu pool de Front-End (ou o FQDN do balanceador de carga do Diretor do pool se você tiver um), um exemplo seria sfb_ pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="0039c-288">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the external Web Services on your Front End pool's load balancer (or the FQDN of the Director pool's load balancer if you have one), an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="0039c-289">Você deve digitar ** / ** conforme o caminho a ser publicado, mas você também precisará **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="0039c-289">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="0039c-p130">Haverá uma opção para os detalhes ou informações do **nome público ou externo**. Este é o local onde você poderá inseri-los:</span><span class="sxs-lookup"><span data-stu-id="0039c-p130">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="0039c-292">**Aceitar solicitações**, mas deve ser para o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="0039c-292">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="0039c-293">Para o **Nome**, você deve inserir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="0039c-293">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="0039c-294"><sipdomain>(isto é a URL externa do serviço Descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="0039c-294"><sipdomain> (this is the external Autodiscover Service URL).</span></span> <span data-ttu-id="0039c-295">Agora, se você estiver criando uma regra para a URL externa de serviços Web no pool de Front-End, você precisará digite o FQDN para os serviços Web externos no seu pool de Front-End (por exemplo, lyncwebextpool01).</span><span class="sxs-lookup"><span data-stu-id="0039c-295">Now, if you're creating a rule for the external Web Services URL on the Front End pool, you'll need to type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
   - <span data-ttu-id="0039c-296">Haverá uma opção de **caminho** , e você precisará digitar ** / ** aqui.</span><span class="sxs-lookup"><span data-stu-id="0039c-296">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="0039c-297">Você deverá selecionar um **Ouvinte SSL** com o certificado público atualizado.</span><span class="sxs-lookup"><span data-stu-id="0039c-297">You'll need to select a **SSL Listener** with your up-to-date public certificate.</span></span>
    
   - <span data-ttu-id="0039c-298">
            A opção **Delegação de Autenticação** deve ser definida como **Sem delegação**, mas a autenticação direta de cliente **deve** ser permitida.</span><span class="sxs-lookup"><span data-stu-id="0039c-298">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should** be allowed.</span></span>
    
   - <span data-ttu-id="0039c-299">A regra deve ser definida para **Todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="0039c-299">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="0039c-300">Essa deve ser toda a informação que você precisa para criar esta regra e permitir que você continue.</span><span class="sxs-lookup"><span data-stu-id="0039c-300">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="0039c-301">Você deve garantir que o **cabeçalho do host original** seja encaminhado.</span><span class="sxs-lookup"><span data-stu-id="0039c-301">You're going to need to ensure that the **original host header** is forwarded.</span></span>
    
5. <span data-ttu-id="0039c-302">As portas do **Web Server** também deverão ser definidas. Para isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0039c-302">The **Web Server** ports will need to be set as well, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="0039c-303">**Redirecione as solicitações para a porta HTTP** e o número da porta deverá ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="0039c-303">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="0039c-304">**Redirecione as solicitações para a porta SSL** e o número da porta deverá ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="0039c-304">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
6. <span data-ttu-id="0039c-305">Quando tudo estiver configurado, você deverá salvar ou aplicar a configuração e depois testar a regra.</span><span class="sxs-lookup"><span data-stu-id="0039c-305">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a><span data-ttu-id="0039c-306">Para criar uma regra de publicação Web para a porta 80 (opcional)</span><span class="sxs-lookup"><span data-stu-id="0039c-306">Create a web publishing rule for port 80 (Optional)</span></span>

1. <span data-ttu-id="0039c-307">Abra sua interface de proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0039c-307">Open your Reverse proxy interface.</span></span>
    
2. <span data-ttu-id="0039c-308">Você precisará localizar onde na interface do você cria suas regras de publicação da web e escolha a opção **novo** ou **criar** (pode ser em um menu ou guia, dependendo da configuração de proxy reverso).</span><span class="sxs-lookup"><span data-stu-id="0039c-308">You'll need to locate where in the interface you create your web publishing rules, and choose the **New** or **Create** option (it may be on a menu or tab, depending on your Reverse proxy configuration).</span></span> <span data-ttu-id="0039c-309">Você está procurando a opção para criar uma nova regra de publicação na Web.</span><span class="sxs-lookup"><span data-stu-id="0039c-309">You are looking for the option to create a new web publishing rule.</span></span>
    
3. <span data-ttu-id="0039c-310">Normalmente, você deverá inserir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="0039c-310">Typically, you will need to enter the following information:</span></span>
    
   - <span data-ttu-id="0039c-311">**Nome**: o nome da regra</span><span class="sxs-lookup"><span data-stu-id="0039c-311">**Name**: the name for your rule</span></span>
    
   - <span data-ttu-id="0039c-312">**A ação de regra**: neste caso é uma regra de **permissão** , você estará permitindo algo passar através do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="0039c-312">**Rule Action**: In this case it's an **Allow** rule, you're letting something pass through your Reverse proxy.</span></span>
    
   - <span data-ttu-id="0039c-313">A regra **Publicação** ou opção que você está escolhendo seria **único site da Web ou equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="0039c-313">The **Publishing** rule or option you're choosing would be **single web site or load balancer**.</span></span>
    
   - <span data-ttu-id="0039c-314">Esta deve ser uma **conexão não segura para conectar-se à farm de servidores ou ao servidor Web publicado**.</span><span class="sxs-lookup"><span data-stu-id="0039c-314">This needs to be a **non-secured connection to connect to the published Web server or farm**.</span></span>
    
   - <span data-ttu-id="0039c-315">Você vai precisar de um caminho de publicação para **Publicação interna**e digite o FQDN para o **endereço VIP** do balanceador de carga do seu pool de Front-End, um exemplo seria sfb_pool01.contoso.local.</span><span class="sxs-lookup"><span data-stu-id="0039c-315">You're going to need to publish a path for **Internal Publishing**, and enter the FQDN for the **VIP address** of your Front End pool's load balancer, an example would be sfb_pool01.contoso.local.</span></span>
    
   - <span data-ttu-id="0039c-316">Você deve digitar ** / ** conforme o caminho a ser publicado, mas você também precisará **encaminhar o cabeçalho de host original**.</span><span class="sxs-lookup"><span data-stu-id="0039c-316">You should type **/\*** as the path to be published, but you also need to **forward the original host header**.</span></span>
    
   - <span data-ttu-id="0039c-p133">Haverá uma opção para os detalhes ou informações do **nome público ou externo**. Este é o local onde você poderá inseri-los:</span><span class="sxs-lookup"><span data-stu-id="0039c-p133">There will be an option for **public or external name** details or information. This is the place where you'll be able to enter:</span></span>
    
   - <span data-ttu-id="0039c-319">**Aceitar solicitações**, mas deve ser para o nome do domínio.</span><span class="sxs-lookup"><span data-stu-id="0039c-319">**Accept requests**, but it should be for the domain name.</span></span>
    
   - <span data-ttu-id="0039c-320">Para o **Nome**, você deve inserir **lyncdiscover.**</span><span class="sxs-lookup"><span data-stu-id="0039c-320">For the **Name**, you should enter **lyncdiscover.**</span></span> <span data-ttu-id="0039c-321"><sipdomain>(isto é a URL externa do serviço Descoberta automática).</span><span class="sxs-lookup"><span data-stu-id="0039c-321"><sipdomain> (this is the external Autodiscover Service URL).</span></span>
    
   - <span data-ttu-id="0039c-322">Haverá uma opção de **caminho** , e você precisará digitar ** / ** aqui.</span><span class="sxs-lookup"><span data-stu-id="0039c-322">There will be a **Path** option, and you'll need to enter **/\*** here.</span></span>
    
   - <span data-ttu-id="0039c-323">Você precisará selecionar um ouvinte da web ou permitir que o proxy reverso para criá-lo para você.</span><span class="sxs-lookup"><span data-stu-id="0039c-323">You'll need to select a web listener, or allow your Reverse proxy to create one for you.</span></span>
    
   - <span data-ttu-id="0039c-324">
            A opção **Delegação de Autenticação** deve ser definida como **Sem delegação**, mas a autenticação direta de cliente **não deve** ser permitida.</span><span class="sxs-lookup"><span data-stu-id="0039c-324">**Authentication Delegation** should be set to **No delegation**, but direct client authentication **should not** be allowed.</span></span>
    
   - <span data-ttu-id="0039c-325">A regra deve ser definida para **Todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="0039c-325">The rule should be set to **All users**.</span></span>
    
   - <span data-ttu-id="0039c-326">Essa deve ser toda a informação que você precisa para criar esta regra e permitir que você continue.</span><span class="sxs-lookup"><span data-stu-id="0039c-326">This should be all the information you need to create this rule and allow you to proceed.</span></span>
    
4. <span data-ttu-id="0039c-327">As portas do **Web Server** deverão ser definidas. Para isso, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0039c-327">The **Web Server** ports will need to be set, you'll need to do the following:</span></span>
    
   - <span data-ttu-id="0039c-328">**Redirecione as solicitações para a porta HTTP** e o número da porta deverá ser **8080**.</span><span class="sxs-lookup"><span data-stu-id="0039c-328">**Redirect requests to HTTP port** and the port number should be **8080**.</span></span>
    
   - <span data-ttu-id="0039c-329">**Redirecione as solicitações para a porta SSL** e o número da porta deverá ser **4443**.</span><span class="sxs-lookup"><span data-stu-id="0039c-329">**Redirect requests to SSL port** and the port number should be **4443**.</span></span>
    
5. <span data-ttu-id="0039c-330">Quando tudo estiver configurado, você deverá salvar ou aplicar a configuração e depois testar a regra.</span><span class="sxs-lookup"><span data-stu-id="0039c-330">When everything's configured, you'll need to save or apply these, and then you'll want to test the rule.</span></span>
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a><span data-ttu-id="0039c-331">Configurar Descoberta Automática para Mobilidade com implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="0039c-331">Configure Autodiscover for Mobility with hybrid deployments</span></span>
<span data-ttu-id="0039c-332"><a name="ConfigAutoD"> </a></span><span class="sxs-lookup"><span data-stu-id="0039c-332"></span></span>

<span data-ttu-id="0039c-333">Ambientes híbridos no Skype para Business Server 2015 são ambientes que combinam um local e o ambiente O365.</span><span class="sxs-lookup"><span data-stu-id="0039c-333">Hybrid environments in Skype for Business Server 2015 are environments that combine an on-premises and O365 environment.</span></span> <span data-ttu-id="0039c-334">Quando você tiver Skype para Business Server trabalhando em um ambiente híbrido, o serviço Descoberta automática deve ser capaz de localizar um usuário de qualquer um desses ambientes.</span><span class="sxs-lookup"><span data-stu-id="0039c-334">When you have Skype for Business Server working in a Hybrid environment, the Autodiscover service needs to be able to locate a user from either of these environments.</span></span>
  
<span data-ttu-id="0039c-p136">Para permitir que os clientes móveis descubram onde um usuário está localizado, o serviço de Descoberta Automática deve ser configurado com uma nova URL. As etapas são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="0039c-p136">To let mobile clients discover where a user's located, the Autodiscover service needs to be configured with a new uniform resource locator (URL). The steps are:</span></span>
  
1. <span data-ttu-id="0039c-337">Abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="0039c-337">Open Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="0039c-338">Execute o seguinte procedimento para obter o valor do atributo **ProxyFQDN** para sua Skype para ambiente de servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="0039c-338">Run the following to get the value of the attribute **ProxyFQDN** for your Skype for Business Server environment:</span></span>
    
  ```
  Get-CsHostingProvider
  ```

3. <span data-ttu-id="0039c-339">Então, na janela do Shell, excute:</span><span class="sxs-lookup"><span data-stu-id="0039c-339">Then, still in the shell window, run:</span></span>
    
  ```
  Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
  ```

    <span data-ttu-id="0039c-340">Onde [identidade] é substituído pelo nome do domínio do espaço de endereço SIP compartilhado.</span><span class="sxs-lookup"><span data-stu-id="0039c-340">Where [identity] is replaced with the domain name of the shared SIP address space.</span></span>
    
## <a name="test-your-mobility-deployment"></a><span data-ttu-id="0039c-341">Testar a implantação de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0039c-341">Test your Mobility deployment</span></span>
<span data-ttu-id="0039c-342"><a name="TestMobility"> </a></span><span class="sxs-lookup"><span data-stu-id="0039c-342"></span></span>

<span data-ttu-id="0039c-343">Depois que você implantou Skype para o serviço de mobilidade do servidor de negócios e Skype para serviço de descoberta automática do servidor de negócios, convém executar uma transação de teste, para certificar-se o trabalho da sua implantação à direita.</span><span class="sxs-lookup"><span data-stu-id="0039c-343">Once you've deployed Skype for Business Server Mobility Service and Skype for Business Server Autodiscover Service, you'll want to run a test transaction, to make sure your deployment's working right.</span></span> <span data-ttu-id="0039c-344">Você pode executar **Test-CsUcwaConference** para testar a capacidade de dois usuários de criar, ingressar e se comunicar em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="0039c-344">You can run **Test-CsUcwaConference** to test the ability of two users to create, join and communicate in a conference.</span></span> <span data-ttu-id="0039c-345">Você precisará de dois usuários (reais ou de teste) e de suas respectivas credenciais completas para executar esse teste.</span><span class="sxs-lookup"><span data-stu-id="0039c-345">You will need two users (real or test) and their full credentials to do this testing.</span></span> <span data-ttu-id="0039c-346">Esse comando funcionará para ambos os Skype para clientes corporativos, bem como os clientes do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0039c-346">This command will work for both Skype for Business clients as well as Lync Server 2013 clients.</span></span>
  
<span data-ttu-id="0039c-347">Para clientes do Lync Server 2010, você precisará executar o **Test-CsMcxP2PIM** para testar.</span><span class="sxs-lookup"><span data-stu-id="0039c-347">For Lync Server 2010 clients, you'll need to run **Test-CsMcxP2PIM** to test.</span></span> <span data-ttu-id="0039c-348">Os usuários do Lync Server 2010 ainda precisará ser usuários reais ou usuários de teste predefinida e você precisará suas credenciais de senha.</span><span class="sxs-lookup"><span data-stu-id="0039c-348">Your Lync Server 2010 users will still have to be actual users, or predefined test users, and you'll need their password credentials.</span></span>
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a><span data-ttu-id="0039c-349">Testar a conferência para clientes móveis do Skype for Business e do Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0039c-349">Test conferencing for Skype for Business and Lync 2013 mobile clients</span></span>

1. <span data-ttu-id="0039c-350">Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-350">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-351">Inicie o **Skype do Shell de gerenciamento do servidor de negócios** (você pode digitar o nome na pesquisa ou vá para **Todos os programas** e escolha-).</span><span class="sxs-lookup"><span data-stu-id="0039c-351">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="0039c-352">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="0039c-352">At the command line, enter:</span></span>
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="0039c-p139">Também é possível definir as credenciais em um script e enviá-las para o cmdlet de teste. Temos um exemplo disso a seguir.</span><span class="sxs-lookup"><span data-stu-id="0039c-p139">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a><span data-ttu-id="0039c-355">Testar a conferência para clientes móveis do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0039c-355">Test conferencing for Lync 2010 mobile clients</span></span>

1. <span data-ttu-id="0039c-356">Faça logon como membro da função **CsAdministrator** em qualquer computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-356">Log on as a member of the **CsAdministrator** role on any computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-357">Inicie o **Skype do Shell de gerenciamento do servidor de negócios** (você pode digitar o nome na pesquisa ou vá para **Todos os programas** e escolha-).</span><span class="sxs-lookup"><span data-stu-id="0039c-357">Start the **Skype for Business Server Management Shell** (you might type the name in search or go to **All Programs** and choose it).</span></span>
    
3. <span data-ttu-id="0039c-358">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="0039c-358">At the command line, enter:</span></span>
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   <span data-ttu-id="0039c-p140">Também é possível definir as credenciais em um script e enviá-las para o cmdlet de teste. Temos um exemplo disso a seguir.</span><span class="sxs-lookup"><span data-stu-id="0039c-p140">It's also possible to set credentials in a script and pass them to the test cmdlet. We have an example of this below.</span></span>
    
  ```
  $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
  $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
  $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
  $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
  Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
  ```

<span data-ttu-id="0039c-361">Para revisar os procedimentos de comando Além disso, pode conferir [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) e [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0039c-361">To review the command procedures further, you can check out [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) and [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).</span></span>
  
## <a name="configure-for-push-notifications"></a><span data-ttu-id="0039c-362">Configurar para notificações por push</span><span class="sxs-lookup"><span data-stu-id="0039c-362">Configure for push notifications</span></span>
<span data-ttu-id="0039c-363"><a name="ConfigPush"> </a></span><span class="sxs-lookup"><span data-stu-id="0039c-363"></span></span>

<span data-ttu-id="0039c-364">As notificações por push, na forma de notificações, ícones ou alertas, podem ser enviadas para um dispositivo móvel mesmo quando o aplicativo Skype ou Lync está inativo.</span><span class="sxs-lookup"><span data-stu-id="0039c-364">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the Skype or Lync app is inactive.</span></span> <span data-ttu-id="0039c-365">Mas o que são notificações por push?</span><span class="sxs-lookup"><span data-stu-id="0039c-365">But what are pusn notifications?</span></span> <span data-ttu-id="0039c-366">Elas são alertas de evento, como um convite novo ou perdido enviado por mensagem instantânea ou uma mensagem de voz recebida.</span><span class="sxs-lookup"><span data-stu-id="0039c-366">They are event alerts, like a new or missed IM invitation, or for a received voicemail.</span></span> <span data-ttu-id="0039c-367">O Skype para serviço de mobilidade do Business Server 2015 envia essas notificações para o Skype baseado em nuvem para negócios Server Push notificação de serviço, que envia notificações para serviço de notificação Push do Microsoft (MSNS) para usuários do Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="0039c-367">The Skype for Business Server 2015 Mobility service sends these notifications to the cloud-based Skype for Business Server Push Notification Service, which then sends the notifications to the Microsoft Push Notification Service (MSNS) for Windows Phone users.</span></span>
  
<span data-ttu-id="0039c-368">Essa funcionalidade é alterada do Lync Server 2013, mas se você tiver um Skype para Business Server, você vai querer fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0039c-368">This functionality is unchanged from Lync Server 2013, but if you have a Skype for Business Server, you'll want to do the following:</span></span>
  
- <span data-ttu-id="0039c-369">Para um Skype para o servidor de borda do Business Server 2015, adicionar um novo provedor de hospedagem, Microsoft Skype para negócios Online e configurar a federação do provedor entre sua organização e Skype para Business Online de hospedagem.</span><span class="sxs-lookup"><span data-stu-id="0039c-369">For a Skype for Business Server 2015 Edge Server, add a new hosting provider, Microsoft Skype for Business Online, and then set up hosting provider federation between your organization and Skype for Business Online.</span></span>
    
- <span data-ttu-id="0039c-p142">Habilite notificações por push executando o cmdlet **Set-CsPushNotificationConfiguration**. Por padrão, as notificações por push estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="0039c-p142">Enable push notifications by running the **Set-CsPushNotificationConfiguration** cmdlet. By default, push notifications are turned off.</span></span>
    
- <span data-ttu-id="0039c-372">Teste sua configuração de federação e as notificações por push.</span><span class="sxs-lookup"><span data-stu-id="0039c-372">Test your federation configuration and push notifications.</span></span>
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a><span data-ttu-id="0039c-373">Configurar o Servidor de Borda do Skype for Business para notificações por push</span><span class="sxs-lookup"><span data-stu-id="0039c-373">Configure your Skype for Business Edge Server for push notifications</span></span>

1. <span data-ttu-id="0039c-374">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-374">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-375">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="0039c-375">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0039c-376">Adicione um Skype para o provedor de hospedagem online Business Server.</span><span class="sxs-lookup"><span data-stu-id="0039c-376">Add a Skype for Business Server online hosting provider.</span></span>
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   <span data-ttu-id="0039c-377">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0039c-377">As an example:</span></span>
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > <span data-ttu-id="0039c-p143">Não é possível ter mais de um relacionamento de federação com um único provedor de host. Ou seja, se você já tiver configurado um provedor de host que tenha um relacionamento de federação com sipfed.online.lync.com, não adicione outro provedor de host a ele, mesmo se a identidade do provedor de host for diferente de SkypeOnline.</span><span class="sxs-lookup"><span data-stu-id="0039c-p143">You can't have more than one federation relationship with a single hosting provider. So, if you've already set up a hosting provider that has a federation relationship with sipfed.online.lync.com, don't add another hosting provider for it, even if the identity of the hosting provider is something other than SkypeOnline.</span></span> 
  
4. <span data-ttu-id="0039c-380">Configure a federação do provedor de hospedagem entre sua organização e o serviço de notificação por Push em Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="0039c-380">Set up the hosting provider federation between your organization and the Push Notification Service at Skype for Business Online.</span></span> <span data-ttu-id="0039c-381">Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="0039c-381">At the command line, you'll need to type:</span></span>
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a><span data-ttu-id="0039c-382">Habilitar notificações por push</span><span class="sxs-lookup"><span data-stu-id="0039c-382">Enable push notifications</span></span>

1. <span data-ttu-id="0039c-383">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-383">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-384">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="0039c-384">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0039c-385">Habilite notificações por push:</span><span class="sxs-lookup"><span data-stu-id="0039c-385">Enable push notifications:</span></span>
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. <span data-ttu-id="0039c-386">Habilite a federação:</span><span class="sxs-lookup"><span data-stu-id="0039c-386">Enable Federation:</span></span>
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a><span data-ttu-id="0039c-387">Testar a federação e as notificações por push</span><span class="sxs-lookup"><span data-stu-id="0039c-387">Test federation and push notifications</span></span>

1. <span data-ttu-id="0039c-388">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-388">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-389">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="0039c-389">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0039c-390">Teste a configuração da federação:</span><span class="sxs-lookup"><span data-stu-id="0039c-390">Test the federation configuration:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    <span data-ttu-id="0039c-391">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0039c-391">As an example:</span></span>
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. <span data-ttu-id="0039c-392">Teste as notificações por push:</span><span class="sxs-lookup"><span data-stu-id="0039c-392">Test your push notifications:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    <span data-ttu-id="0039c-393">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0039c-393">As an example:</span></span>
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a><span data-ttu-id="0039c-394">Configurar a política de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0039c-394">Configure Mobility policy</span></span>
<span data-ttu-id="0039c-395"><a name="ConfigMob"> </a></span><span class="sxs-lookup"><span data-stu-id="0039c-395"></span></span>

<span data-ttu-id="0039c-396">Você tem a capacidade com Skype para 2015 do servidor de negócios determinar quem pode usar o serviço de mobilidade, chamada via trabalho, voz sobre IP (VoIP) ou vídeo, bem como se WiFi serão necessário para VoIP ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="0039c-396">You have the ability with Skype for Business Server 2015 to determine who can use your Mobility service, Call via Work, voice over IP (VoIP), or video, as well as whether WiFi will be required for VoIP or video.</span></span> <span data-ttu-id="0039c-397">O recurso Telefonar via Trabalho permite que um usuário móvel use o número de seu telefone comercial, em vez de seu número particular, para fazer e receber chamadas.</span><span class="sxs-lookup"><span data-stu-id="0039c-397">Call via Work lets a mobile user use their work phone number, instead of their mobile phone number, when placing and receiving calls.</span></span> <span data-ttu-id="0039c-398">A pessoa na outra extremidade da linha não vê o número do celular desse usuário móvel, o que permite que o usuário móvel evite cobranças de chamadas de saída.</span><span class="sxs-lookup"><span data-stu-id="0039c-398">The person on the other end of the line won't see that mobile user's cell phone number, and it lets that mobile user avoid outgoing call charges.</span></span> <span data-ttu-id="0039c-399">Quando VoIP e vídeo são configurados, os usuários podem receber e fazer chamadas VoIP e de vídeo.</span><span class="sxs-lookup"><span data-stu-id="0039c-399">When VoIP and video are set up, users can take and make VoIP calls and video.</span></span> <span data-ttu-id="0039c-400">As configurações para o uso de WiFi determinam se o dispositivo móvel de um usuário precisa usar WiFi através de uma rede de dados de celular.</span><span class="sxs-lookup"><span data-stu-id="0039c-400">The settings for WiFi usage determine whether a user's mobile device will be required to use a WiFi network over a cellular data network.</span></span>
  
<span data-ttu-id="0039c-401">Mobilidade, chamada via trabalho e o VoIP e recursos de vídeo estão habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="0039c-401">Mobility, Call via Work, and the VoIP and video features are all enabled by default.</span></span> <span data-ttu-id="0039c-402">As configurações para exigir WiFi para VoIP e vídeo estão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="0039c-402">The setting to require WiFi for VoIP and video are disabled.</span></span> <span data-ttu-id="0039c-403">Um administrador pode alterar essas configurações em nível global, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="0039c-403">An Admin has the ability to change this, either globally, by site, or by user.</span></span>
  
<span data-ttu-id="0039c-404">Para poder usar os recursos de mobilidade e chamada via trabalho, os usuários precisam ser:</span><span class="sxs-lookup"><span data-stu-id="0039c-404">To be able to use Mobility features and Call via Work, users need to be:</span></span>
  
- <span data-ttu-id="0039c-405">Habilitado para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0039c-405">Enabled for Skype for Business Server 2015</span></span>
    
- <span data-ttu-id="0039c-406">Estar habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="0039c-406">Enabled for Enterprise Voice.</span></span>
    
- <span data-ttu-id="0039c-407">Atribuída uma política de mobilidade que tem a opção **EnableMobility** definida como **True**.</span><span class="sxs-lookup"><span data-stu-id="0039c-407">Assigned a Mobility policy that has the **EnableMobility** option set to **True**.</span></span>
    
<span data-ttu-id="0039c-408">Para usar o recurso Telefonar via Trabalho, os usuários devem:</span><span class="sxs-lookup"><span data-stu-id="0039c-408">For users to be able to use Call via Work, they'll also need to be:</span></span>
  
- <span data-ttu-id="0039c-409">Ter uma política de voz atribuída com a opção **Habilitar toques de telefones simultâneos** selecionada.</span><span class="sxs-lookup"><span data-stu-id="0039c-409">Assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>
    
- <span data-ttu-id="0039c-410">Atribuída uma política de mobilidade que tem o **EnableOutsideVoice** definida como **True**.</span><span class="sxs-lookup"><span data-stu-id="0039c-410">Assigned a Mobility policy that has the **EnableOutsideVoice** set to **True**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="0039c-p147">Usuários não habilitados para Enterprise Voice podem usar seus dispositivos móveis para fazer chamadas VoIP de Skype para Skype ou podem ingressar em conferências usando o link Clique para Ingressar quando estiverem usando dispositivos móveis, se as opções apropriadas estiverem definidas para a política de voz correspondente. Há mais detalhes no tópico PLANEJAMENTO.</span><span class="sxs-lookup"><span data-stu-id="0039c-p147">Users who aren't enabled for Enterprise Voice can use their mobile devices to make Skype to Skype VoIP calls or can join conferences by using the Click to Join link while on their mobile devices, if the appropriate options are set for the Voice policy they're associated with. There's more detail in the PLANNING topic.</span></span> 
  
### <a name="modify-global-mobility-policy"></a><span data-ttu-id="0039c-413">Modificar a política global de mobilidade</span><span class="sxs-lookup"><span data-stu-id="0039c-413">Modify global Mobility policy</span></span>

1. <span data-ttu-id="0039c-414">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-414">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-415">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="0039c-415">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0039c-416">Desative acesso a mobilidade e telefonar via trabalho globalmente, digitando:</span><span class="sxs-lookup"><span data-stu-id="0039c-416">Turn off access to Mobility and Call via Work globally by typing:</span></span>
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > <span data-ttu-id="0039c-417">Você pode desativar chamada via trabalho sem desativar acesso a mobilidade.</span><span class="sxs-lookup"><span data-stu-id="0039c-417">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="0039c-418">Mas você não pode desativar mobilidade sem também desativando a chamada via trabalho.</span><span class="sxs-lookup"><span data-stu-id="0039c-418">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  
    <span data-ttu-id="0039c-419">Para obter mais informações, consulte [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0039c-419">For more info, check out [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-site"></a><span data-ttu-id="0039c-420">Modificar a política de mobilidade por site</span><span class="sxs-lookup"><span data-stu-id="0039c-420">Modify Mobility policy by site</span></span>

1. <span data-ttu-id="0039c-421">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-421">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-422">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="0039c-422">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0039c-p149">Você pode criar uma política no nível de site, desativar VoIP e vídeo, habilitar Exigir WiFi para Áudio IP e Exigir WiFi para Vídeo IP por site. Digite:</span><span class="sxs-lookup"><span data-stu-id="0039c-p149">You can create a site-level policy, turn off VoIP and video, enable Require WiFi for IP Audio, and Require WiFi for IP Video by site. Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    <span data-ttu-id="0039c-425">Saiba mais em [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0039c-425">Learn more at [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).</span></span>
    
### <a name="modify-mobility-policy-by-user"></a><span data-ttu-id="0039c-426">Modificar a política de mobilidade por usuário</span><span class="sxs-lookup"><span data-stu-id="0039c-426">Modify Mobility policy by user</span></span>

1. <span data-ttu-id="0039c-427">Faça logon, com uma conta que seja membro da função **CsAdministrator** , em um computador onde o **Skype do Shell de gerenciamento do servidor de negócios** e o **Ocscore** estão instalados.</span><span class="sxs-lookup"><span data-stu-id="0039c-427">Log on, with an account that's a member of the **CsAdministrator** role, to a computer where **Skype for Business Server Management Shell** and **Ocscore** are installed.</span></span>
    
2. <span data-ttu-id="0039c-428">Inicie o **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="0039c-428">Start the **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0039c-429">Criar políticas de mobilidade de nível de usuário e desativar a mobilidade e a chamada via trabalho por usuário.</span><span class="sxs-lookup"><span data-stu-id="0039c-429">Create user level Mobility policies and turn off Mobility and Call via Work by user.</span></span> <span data-ttu-id="0039c-430">Digite:</span><span class="sxs-lookup"><span data-stu-id="0039c-430">Type:</span></span>
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    <span data-ttu-id="0039c-431">Mais um exemplo:</span><span class="sxs-lookup"><span data-stu-id="0039c-431">A further example with sample data:</span></span>
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > <span data-ttu-id="0039c-432">Você pode desativar chamada via trabalho sem desativar acesso a mobilidade.</span><span class="sxs-lookup"><span data-stu-id="0039c-432">You can turn off Call via Work without turning off access to Mobility.</span></span> <span data-ttu-id="0039c-433">Mas você não pode desativar mobilidade sem também desativando a chamada via trabalho.</span><span class="sxs-lookup"><span data-stu-id="0039c-433">But you can't turn off Mobility without also turning off Call via Work.</span></span> 
  

