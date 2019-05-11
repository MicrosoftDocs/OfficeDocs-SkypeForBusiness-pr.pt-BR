---
title: Desabilitar o TLS 1.0/1.1 no Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: Preparar e implementar desabilitando TLS 1.0 e 1.1 em seus ambientes.'
ms.openlocfilehash: 570d691463f117c2c81c1191d1679db9f70e96b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911897"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="2975b-103">Desabilitar o TLS 1.0/1.1 no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2975b-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="2975b-104">A finalidade deste artigo é fornecer as diretrizes necessárias para você preparar e implementar desabilitando TLS 1.0 e 1.1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="2975b-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="2975b-105">Esse processo exige amplo planejamento e preparação.</span><span class="sxs-lookup"><span data-stu-id="2975b-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="2975b-106">Examine cuidadosamente todas as informações neste artigo à medida que você faz seu plano para desabilitar o TLS 1.0 e 1.1 para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2975b-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="2975b-107">Observe que há muitas dependências externas e condições de conectividade que podem ser afetadas por meio da desabilitação TLS 1.0/1.1, tão extenso de planejamento e teste é garantido.</span><span class="sxs-lookup"><span data-stu-id="2975b-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="2975b-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="2975b-108">In this article</span></span>

- [<span data-ttu-id="2975b-109">Plano de fundo e escopo</span><span class="sxs-lookup"><span data-stu-id="2975b-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="2975b-110">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="2975b-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="2975b-111">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="2975b-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="2975b-112">Plano de fundo</span><span class="sxs-lookup"><span data-stu-id="2975b-112">Background</span></span>

<span data-ttu-id="2975b-113">Os principais fatores para fornecer TLS 1.0 e suporte de disable 1.1 para Skype para Business Server local são os requisitos de conselho de padrões de segurança do setor de cartões de pagamento (PCI) e os padrões de processamento de informações federais.</span><span class="sxs-lookup"><span data-stu-id="2975b-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="2975b-114">Para obter mais informações para os requisitos de PCI podem ser encontradas [aqui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="2975b-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="2975b-115">Não é possível para o Microsoft fornecem orientação sobre ou não a sua organização é obrigada aderir a essas ou outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="2975b-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="2975b-116">Você deve determinar se ele é necessário para desabilitar o TLS 1.0 e/ou 1.1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="2975b-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="2975b-117">Microsoft gerou um white paper sobre TLS disponíveis [aqui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), e também recomendamos o plano de fundo lendo disponíveis neste [blog do Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="2975b-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="2975b-118">Escopo de suporte</span><span class="sxs-lookup"><span data-stu-id="2975b-118">Supportability Scope</span></span>

<span data-ttu-id="2975b-119">*Escopo* refere-se aos limites de suporte.</span><span class="sxs-lookup"><span data-stu-id="2975b-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="2975b-120">Para Skype para Business Server local, *no escopo* significa totalmente suportar e testamos a desabilitação de TLS 1.0 e 1.1 para as versões de produto listado.</span><span class="sxs-lookup"><span data-stu-id="2975b-120">For Skype for Business Server On-Premises, *in scope* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="2975b-121">*Atualmente, sendo investigados* significa apenas que; estamos ativamente investigando trazendo esses produtos para o escopo para desativar o suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="2975b-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="2975b-122">*Fora do escopo* significa dessas versões do produto não suportam desabilitando TLS 1.0 ou 1.1 e não funcionarão, com as exceções indicadas.</span><span class="sxs-lookup"><span data-stu-id="2975b-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="2975b-123">Servidores totalmente testadas e suportadas</span><span class="sxs-lookup"><span data-stu-id="2975b-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="2975b-124">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="2975b-124">Skype for Business Server 2019</span></span>
- <span data-ttu-id="2975b-125">Skype para Business Server 2015 CU6 HF2 6.0.9319.516 ([março 2018 atualizar](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) e superiores em:</span><span class="sxs-lookup"><span data-stu-id="2975b-125">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) and higher on:</span></span> 
    - <span data-ttu-id="2975b-126">Windows Server 2012 (com 3140245 KB ou atualização que substitui), 2012 R2 ou 2016</span><span class="sxs-lookup"><span data-stu-id="2975b-126">Windows Server 2012 (with KB 3140245 or superseding update), 2012 R2 or 2016</span></span>
- <span data-ttu-id="2975b-127">In-loco atualizados Skype para Business Server 2015, com CU6 HF2 e superiores em</span><span class="sxs-lookup"><span data-stu-id="2975b-127">In-place Upgraded Skype for Business Server 2015, with CU6 HF2 and higher on</span></span> 
    - <span data-ttu-id="2975b-128">Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização que substitui) ou 2012 R2</span><span class="sxs-lookup"><span data-stu-id="2975b-128">Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2</span></span>
- <span data-ttu-id="2975b-129">Conectividade do Exchange e Outlook Web App com RU19 do Exchange Server 2010 SP3 ou superior, orientação [aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="2975b-129">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="2975b-130">Aparelho de filial persistente (SBA) com Skype para Business Server 2015 CU6 HF2 ou superior (Confirmar com seu fornecedor que eles empacotados as atualizações apropriado e tenham sido disponibilizados para o seu aparelho)</span><span class="sxs-lookup"><span data-stu-id="2975b-130">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="2975b-131">Servidor de filial persistente (SBS) com Skype para Business Server 2015 CU6 HF2 ou superior</span><span class="sxs-lookup"><span data-stu-id="2975b-131">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="2975b-132">Lync Server 2013 **Apenas função de borda**, é porque a função de borda não possuem uma dependência sobre Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="2975b-132">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>


### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="2975b-133">Clientes totalmente testados e suportados</span><span class="sxs-lookup"><span data-stu-id="2975b-133">Fully tested and supported clients</span></span>

- <span data-ttu-id="2975b-134">O cliente de Desktop do Lync 2013 (Skype for Business), MSI e C2R, incluindo Basic [15.0.5023.1000 e superiores](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="2975b-134">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 and higher](https://support.microsoft.com/en-us/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="2975b-135">Skype para negócios 2016 Desktop Client, MSI [16.0.4678.1000 e superiores](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluindo Basic</span><span class="sxs-lookup"><span data-stu-id="2975b-135">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 and higher](https://support.microsoft.com/en-us/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="2975b-136">Skype para negócios 2016, clique executar exigem as atualizações de [abril 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="2975b-136">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="2975b-137">Mensal e anual delimitadas direcionadas, 16\.0\.9126\.2152 e superiores</span><span class="sxs-lookup"><span data-stu-id="2975b-137">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 and higher</span></span>
    - <span data-ttu-id="2975b-138">Anual delimitadas e canal adiada, 16\.0\.8431\.2242 e superiores</span><span class="sxs-lookup"><span data-stu-id="2975b-138">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 and higher</span></span>
- <span data-ttu-id="2975b-139">Skype for Business no Mac 16.15 e superior</span><span class="sxs-lookup"><span data-stu-id="2975b-139">Skype for Business on Mac 16.15 and higher</span></span>
- <span data-ttu-id="2975b-140">Skype para empresas para iOS e Android 6.19 e superior</span><span class="sxs-lookup"><span data-stu-id="2975b-140">Skype for Business for iOS and Android 6.19 and higher</span></span>
- <span data-ttu-id="2975b-141">Skype Web App 2015 CU6 HF2 e superior (fornecido com o servidor)</span><span class="sxs-lookup"><span data-stu-id="2975b-141">Skype Web App 2015 CU6 HF2 and higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="2975b-142">Atualmente, sendo investigados</span><span class="sxs-lookup"><span data-stu-id="2975b-142">Currently being investigated</span></span>

#### <a name="devices"></a><span data-ttu-id="2975b-143">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="2975b-143">Devices</span></span>

- <span data-ttu-id="2975b-144">O sistema de sala do Lync (também conhecido como</span><span class="sxs-lookup"><span data-stu-id="2975b-144">Lync Room System (a.k.a.</span></span> <span data-ttu-id="2975b-145">SRSv1)</span><span class="sxs-lookup"><span data-stu-id="2975b-145">SRSv1)</span></span>
- <span data-ttu-id="2975b-146">Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2975b-146">Microsoft Teams Rooms</span></span>
- <span data-ttu-id="2975b-147">Surface Hub</span><span class="sxs-lookup"><span data-stu-id="2975b-147">Surface Hub</span></span>
- <span data-ttu-id="2975b-148">2015 baseados aparelho de filial persistente (SBA) ou o servidor de filial persistente (SBS)</span><span class="sxs-lookup"><span data-stu-id="2975b-148">2015 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>

#### <a name="other"></a><span data-ttu-id="2975b-149">Outro</span><span class="sxs-lookup"><span data-stu-id="2975b-149">Other</span></span>

- <span data-ttu-id="2975b-150">Painel de controle de qualidade de chamada (nova instalação após TLS 1.0, 1.1 foram desabilitadas, veja abaixo) \*</span><span class="sxs-lookup"><span data-stu-id="2975b-150">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="2975b-151">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="2975b-151">Out of scope</span></span>

<span data-ttu-id="2975b-152">Exceto onde observado, os produtos a seguir não estão no escopo para suporte a TLS 1.0/1.1 disable e não funcionarão em um ambiente onde TLS 1.0 e 1.1 foram desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="2975b-152">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span>  <span data-ttu-id="2975b-153">O que isso significa: se você ainda utiliza clientes ou servidores fora do escopo, você deve atualizar ou removê-los a se você precisar desativar TLS 1.0/1.1 em qualquer lugar no seu Skype para Business Server implantação local.</span><span class="sxs-lookup"><span data-stu-id="2975b-153">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="2975b-154">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2975b-154">Lync Server 2013</span></span>
- <span data-ttu-id="2975b-155">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2975b-155">Lync Server 2010</span></span>
- <span data-ttu-id="2975b-156">Windows Server 2008 e inferior</span><span class="sxs-lookup"><span data-stu-id="2975b-156">Windows Server 2008 and lower</span></span>
- <span data-ttu-id="2975b-157">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="2975b-157">Lync for Mac 2011</span></span>
- <span data-ttu-id="2975b-158">Lync 2013 para dispositivos móveis - iOS, iPad, Android ou do Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2975b-158">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="2975b-159">Cliente do Lync "MX" Windows Store</span><span class="sxs-lookup"><span data-stu-id="2975b-159">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="2975b-160">Todos os clientes do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2975b-160">All Lync 2010 clients</span></span>
- <span data-ttu-id="2975b-161">Lync Phone Edition - atualizada a orientação [aqui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="2975b-161">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="2975b-162">Aparelho de filial persistente (SBA) ou o servidor de filial persistente (SBS) com base em 2013</span><span class="sxs-lookup"><span data-stu-id="2975b-162">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="2975b-163">Conector de nuvem Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="2975b-163">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="2975b-164">Skype for Business para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="2975b-164">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="2975b-165">Exceções</span><span class="sxs-lookup"><span data-stu-id="2975b-165">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="2975b-166">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2975b-166">Lync Server 2013</span></span>

<span data-ttu-id="2975b-167">Lync Server 2013 assume uma dependência versão 1.0 do Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="2975b-167">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="2975b-168">Na fase de design do Lync Server 2013, Windows Fabric 1.0 foi escolhido para sua arquitetura distribuída nova e atraente fornecer replicação, alta disponibilidade e tolerância a falhas.</span><span class="sxs-lookup"><span data-stu-id="2975b-168">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="2975b-169">Ao longo do tempo, ambos os Skype para Business Server e Windows Fabric melhoraram muito essa arquitetura conjunta com significativo refaça o projeto em versões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="2975b-169">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="2975b-170">Skype atual para o Business 2015 Server usa o Windows Fabric 3.0, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="2975b-170">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="2975b-171">Infelizmente, o Windows Fabric 1.0 **não oferece suporte a TLS 1.2.  No entanto, atualizaremos Lync Server 2013 para trabalhar com o TLS 1.2**.</span><span class="sxs-lookup"><span data-stu-id="2975b-171">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="2975b-172">Isso estará disponível na próxima atualização cumulativa para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2975b-172">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="2975b-173">Estamos fornecendo suporte a TLS 1.2 para permitir que os cenários de coexistência, migração, Federação e híbrida.</span><span class="sxs-lookup"><span data-stu-id="2975b-173">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="2975b-174">Se sua organização é obrigada para desabilitar o TLS 1.0 e 1.1 e Lync Server 2013 atualmente em uso, é recomendável começar o processo de planejamento, com a possibilidade talvez seja necessário atualização in-loco ou lado a lado migrar (novos pools, mover usuários) para Skype para Servidor de negócios 2015 ou superior.</span><span class="sxs-lookup"><span data-stu-id="2975b-174">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="2975b-175">Ou talvez você queira acelerar a migração para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="2975b-175">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="2975b-176">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="2975b-176">Call Quality Dashboard</span></span>

<span data-ttu-id="2975b-177">Painel de qualidade de chamada local atualmente tem uma dependência em TLS 1.0 durante a nova instalação (primeira vez instalando em seus ambientes de local).</span><span class="sxs-lookup"><span data-stu-id="2975b-177">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="2975b-178">Estamos atualmente investigando esse problema e planeje liberar uma correção no futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="2975b-178">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="2975b-179">Se você estiver planejando instalar CQD e também desabilitar TLS 1.0, recomendamos que você concluir a instalação de CQD primeiro e, em seguida, continue com a desativação de TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="2975b-179">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="2975b-180">Dispositivos de terceiros</span><span class="sxs-lookup"><span data-stu-id="2975b-180">Third-party devices</span></span>

<span data-ttu-id="2975b-181">Em dispositivos de terceiros, como telefones 3PIP, conferência de vídeo, Proxies reversos e balanceadores de carga, certifique-se validar o suporte de TLS 1.2, teste cuidadoso e contate o fornecedor, se necessário.</span><span class="sxs-lookup"><span data-stu-id="2975b-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="2975b-182">Considerações sobre a federação desabilitando TLS 1.0/1.1 nos servidores de borda</span><span class="sxs-lookup"><span data-stu-id="2975b-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="2975b-183">Cuidadosamente, você deve planejar e considerar o impacto da desativação TLS 1.0/1.1 em seus servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="2975b-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="2975b-184">Depois que o TLS 1.0 e 1.1 estiverem desativados, você pode descobrir que outras organizações estão deixará de ser capaz de estabelecer uma federação com sua organização.</span><span class="sxs-lookup"><span data-stu-id="2975b-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="2975b-185">Você pode optar por manter o TLS 1.0/1.1 estiver habilitada nos servidores de borda para manter a compatibilidade com versões anteriores com não-corrigidas (SfB 2015, Lync 2013) ou mais antigos sistemas externos de (2010).</span><span class="sxs-lookup"><span data-stu-id="2975b-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="2975b-186">Microsoft não pode fornecer conselhos ou recomendações no ou não a sua rede de borda (ou qualquer rede) cai sob padrão; PCI que deve ser determinado pela empresa individual.</span><span class="sxs-lookup"><span data-stu-id="2975b-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="2975b-187">Skype para Business Online é capaz de TLS 1.2 atualmente, portanto, nenhum impacto híbrida/federação com Online é esperado.</span><span class="sxs-lookup"><span data-stu-id="2975b-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="2975b-188">PIC (conectividade de IM pública) ao serviço de consumidor do Skype: não esperamos desabilitando TLS 1.0/1.1 para que possam afetar a [Conectividade do Skype](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways já estão TLS 1.2 capaz.</span><span class="sxs-lookup"><span data-stu-id="2975b-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="2975b-189">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="2975b-189">Prerequisites and process</span></span>

<span data-ttu-id="2975b-190">Exceto quando observado acima, depois que o TLS 1.0 e 1.1 são desabilitados fora do escopo de servidores, clientes e dispositivos mais funcionará corretamente, ou.</span><span class="sxs-lookup"><span data-stu-id="2975b-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="2975b-191">Isso pode significar que você precisa fazer uma pausa e aguarde atualizada a orientação da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2975b-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="2975b-192">Quando você estiver satisfeito que atender a todos os requisitos e ter um plano para intervalos de endereço, continue.</span><span class="sxs-lookup"><span data-stu-id="2975b-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="2975b-193">Em um alto nível, embora Skype para Business Server 2019 está pronta para o procedimento de instalação, Skype para Business Server 2015 exigirá que você instale CU6 HF2, aplicando atualizações de pré-requisito .NET e SQL, implantando chaves de registro de pré-requisito e finalmente um separado atualizações de ida da configuração do sistema operacional (isto é, desabilitando TLS 1.0 e 1.1 por meio da importação do arquivo de registro).</span><span class="sxs-lookup"><span data-stu-id="2975b-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU6 HF2, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="2975b-194">É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo Skype para Business Server 2015 CU6 HF2, antes da desativação TLS 1.0 e 1.1 em qualquer servidor em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="2975b-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="2975b-195">Cada Skype para Business server, incluindo a função de borda e SQL back-ends, requer as atualizações.</span><span class="sxs-lookup"><span data-stu-id="2975b-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="2975b-196">Além disso, certifique-se de que todos os clientes suportados de (no escopo) foram atualizados com as versões mínimas necessárias.</span><span class="sxs-lookup"><span data-stu-id="2975b-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="2975b-197">Não se esqueça de atualizar estações de trabalho de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="2975b-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="2975b-198">Queremos seguem a ordem usual de operações do "dentro para fora" para atualizar o Skype para servidores de negócios.</span><span class="sxs-lookup"><span data-stu-id="2975b-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="2975b-199">Trate os pools de diretor, bate-papo persistente e Pools emparelhada da mesma maneira que faria normalmente.</span><span class="sxs-lookup"><span data-stu-id="2975b-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="2975b-200">Ordem e métodos de atualização são abordados [aqui](topology.md) e [aqui](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="2975b-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="2975b-201">Processo de alto nível</span><span class="sxs-lookup"><span data-stu-id="2975b-201">High-level process</span></span>

1. <span data-ttu-id="2975b-202">Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="2975b-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="2975b-203">Fazer backup e preservar uma cópia do registro exportado em cada servidor individual a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="2975b-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="2975b-204">Não é possível compartilhar registros entre servidores; elas contêm teclas exclusivas baseada na máquina.</span><span class="sxs-lookup"><span data-stu-id="2975b-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="2975b-205">Atualize todos os Skype para servidores de negócios 2015 para CU6 HF2 ou superior.</span><span class="sxs-lookup"><span data-stu-id="2975b-205">Upgrade all Skype for Business 2015 servers to CU6 HF2 or higher.</span></span> <span data-ttu-id="2975b-206">(Para Skype para Business Server 2019, nenhuma CU é necessária)</span><span class="sxs-lookup"><span data-stu-id="2975b-206">(For Skype for Business Server 2019, no CU is needed)</span></span>
4. <span data-ttu-id="2975b-207">Instale todos os pré-requisitos para todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="2975b-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="2975b-208">Implante chaves do registro de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="2975b-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="2975b-209">Certifique-se de que todos os clientes no escopo serão atualizados.</span><span class="sxs-lookup"><span data-stu-id="2975b-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="2975b-210">Desabilite o TLS 1.0 e 1.1 por meio da importação do registro.</span><span class="sxs-lookup"><span data-stu-id="2975b-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="2975b-211">Valide que as cargas de trabalho estão funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="2975b-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="2975b-212">Se forem encontrados problemas, solucionar e resolver, ou</span><span class="sxs-lookup"><span data-stu-id="2975b-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="2975b-213">Restaurar o registro da etapa 2 para reabilitar o TLS 1.0 e 1.1</span><span class="sxs-lookup"><span data-stu-id="2975b-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="2975b-214">Valide que apenas o TLS 1.2 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="2975b-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="2975b-215">Instalar os pré-requisitos para todos os servidores</span><span class="sxs-lookup"><span data-stu-id="2975b-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="2975b-216">A atualização de dependência extensiva é necessária antes de começar a desativar o TLS 1.0 e 1.1 no nível do sistema operacional no seu Skype para implantações de negócios Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2975b-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="2975b-217">Estas são as versões mínimas que podem oferecer suporte a TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2975b-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="2975b-218">Implante todas as atualizações de pré-requisito em cada Skype para Business server no seu ambiente antes de começar desabilitando TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="2975b-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="2975b-219">Skype para Business Server 2015 CU6 HF2 6.0.9319.516 ([atualização de março 2018](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) ou superior</span><span class="sxs-lookup"><span data-stu-id="2975b-219">Skype for Business Server 2015 CU6 HF2 6.0.9319.516 ([March 2018 update](https://support.microsoft.com/en-us/help/4086059/march-2018-cumulative-update-6-0-9319-516-for-skype-for-business)) or higher</span></span>
- <span data-ttu-id="2975b-220">[4.7 do .NET framework](https://www.microsoft.com/en-us/download/details.aspx?id=55167) ou superior com SchUseStrongCrypto habilitada no registro (fornecido abaixo)</span><span class="sxs-lookup"><span data-stu-id="2975b-220">[.NET Framework 4.7](https://www.microsoft.com/en-us/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="2975b-221">SQL deve ser atualizado em todos os Skype para servidores de negócios 2015 e back-ends.</span><span class="sxs-lookup"><span data-stu-id="2975b-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="2975b-222">Atualize back-ends Enterprise Edition Pool SQL em primeiro lugar, em seguida, seus respectivos FEs.</span><span class="sxs-lookup"><span data-stu-id="2975b-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="2975b-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)) ou superior / SQL Server 2012 SP2 + CU16 ou superior / RTM do SQL Server 2014 + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) ou superior / 2014 do SQL Server SP2</span><span class="sxs-lookup"><span data-stu-id="2975b-223">SQL Server 2014 SP1 + CU5 ([link](https://support.microsoft.com/help/3130926)), or higher / SQL Server 2012 SP2 + CU16 or higher/ SQL Server 2014 RTM + CU12 ([link](https://support.microsoft.com/en-us/help/3130923/cumulative-update-12-for-sql-server-2014)) or higher / SQL Server 2014 SP2</span></span>
    - <span data-ttu-id="2975b-224">SQL Server Native Client para SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span><span class="sxs-lookup"><span data-stu-id="2975b-224">SQL Server Native Client for SQL Server 2012 ([link](https://www.microsoft.com/en-us/download/details.aspx?id=50402))</span></span>
    - <span data-ttu-id="2975b-225">Microsoft ODBC Driver 11 para o SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)) ou superior</span><span class="sxs-lookup"><span data-stu-id="2975b-225">Microsoft ODBC Driver 11 for SQL Server ([link](https://www.microsoft.com/en-us/download/details.aspx?id=36434)), or higher</span></span>
    - <span data-ttu-id="2975b-226">Objetos de gerenciamento compartilhado para o SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="2975b-226">Shared Management Objects for SQL Server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>
    - <span data-ttu-id="2975b-227">SQLSysClrTypes para o SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span><span class="sxs-lookup"><span data-stu-id="2975b-227">SQLSysClrTypes for SQL server 2014 SP2 ([link](https://www.microsoft.com/en-in/download/details.aspx?id=42295))</span></span>

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="2975b-228">Etapas básicas para instalar os pré-requisitos, na ordem recomendada de operações</span><span class="sxs-lookup"><span data-stu-id="2975b-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="2975b-229">Instale o Skype para Business Server CU6HF2 (6.0.9319.516) atualizar a todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="2975b-229">Install the Skype for Business Server CU6HF2 (6.0.9319.516) update to all servers.</span></span> 
    1. <span data-ttu-id="2975b-230">Instale a atualização para os componentes usando o atualizador.</span><span class="sxs-lookup"><span data-stu-id="2975b-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="2975b-231">Atualize bancos de dados de acordo com os procedimentos documentados.</span><span class="sxs-lookup"><span data-stu-id="2975b-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="2975b-232">Instruções são documentadas em [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="2975b-232">Instructions are documented at [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="2975b-233">Valide a funcionalidade do produto na implantação antes de continuar com qualquer outra alteração.</span><span class="sxs-lookup"><span data-stu-id="2975b-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="2975b-234">Baixe o .NET 4.7 instalador Offline.</span><span class="sxs-lookup"><span data-stu-id="2975b-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="2975b-235">Referência:[https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="2975b-235">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=55167](https://www.microsoft.com/en-us/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="2975b-236">Certifique-se de que o Skype para serviços de Business Server 2015 são interrompidos no servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="2975b-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="2975b-237">Referência:[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="2975b-237">Reference: [https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="2975b-238">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="2975b-238">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
    5. <span data-ttu-id="2975b-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span><span class="sxs-lookup"><span data-stu-id="2975b-239">Ex (Enterprise Edition): Invoke-CsComputerFailover</span></span>
    6. <span data-ttu-id="2975b-240">Execute o pacote do instalador.</span><span class="sxs-lookup"><span data-stu-id="2975b-240">Run the installer package.</span></span>
    7. <span data-ttu-id="2975b-241">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="2975b-241">Reboot the server.</span></span>
3. <span data-ttu-id="2975b-242">Atualize o SQL Express 2014 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="2975b-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="2975b-243">Referência:[https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="2975b-243">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="2975b-244">Baixe o SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="2975b-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="2975b-245">Referência:[https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="2975b-245">Reference: [https://www.microsoft.com/en-us/download/details.aspx?id=53168](https://www.microsoft.com/en-us/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="2975b-246">Copie a mídia de instalação para uma pasta no servidor (ex.: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="2975b-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="2975b-247">Certifique-se de Skype para os serviços são interrompidos em servidor Front-End do Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2975b-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="2975b-248">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2975b-248">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="2975b-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="2975b-249">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    5. <span data-ttu-id="2975b-250">Abra um Prompt de comando do administrador e atualizar todos os componentes instalados e instâncias</span><span class="sxs-lookup"><span data-stu-id="2975b-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="2975b-251">Exemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action = Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="2975b-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="2975b-252">Atualize o SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="2975b-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="2975b-253">Referência: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="2975b-253">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="2975b-254">Baixar a partir[https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="2975b-254">Download from [https://www.microsoft.com/en-us/download/details.aspx?id=50402](https://www.microsoft.com/en-us/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="2975b-255">Certifique-se Skype para os serviços são interrompidos em servidor Front-End do Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="2975b-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="2975b-256">Ex (Standard Edition): Stop-CsWindowsServices</span><span class="sxs-lookup"><span data-stu-id="2975b-256">Ex (Standard Edition): Stop-CsWindowsServices</span></span>
        - <span data-ttu-id="2975b-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="2975b-257">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="2975b-258">Pare as instâncias do SQL instaladas sejam executados</span><span class="sxs-lookup"><span data-stu-id="2975b-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="2975b-259">Ex.: Get-Service 'MSSQL$ RTCLOCAL' | STOP-serviço</span><span class="sxs-lookup"><span data-stu-id="2975b-259">Ex: Get-Service 'MSSQL$RTCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="2975b-260">Ex.: Get-Service 'MSSQL$ LYNCLOCAL' | STOP-serviço</span><span class="sxs-lookup"><span data-stu-id="2975b-260">Ex: Get-Service 'MSSQL$LYNCLOCAL' | Stop-Servic</span></span>
        - <span data-ttu-id="2975b-261">Ex (Standard Edition apenas): Get-Service 'MSSQL$ RTC' | STOP-serviço</span><span class="sxs-lookup"><span data-stu-id="2975b-261">Ex (Standard Edition Only): Get-Service 'MSSQL$RTC' | Stop-Servic</span></span>
    5. <span data-ttu-id="2975b-262">Atualize a atualização.</span><span class="sxs-lookup"><span data-stu-id="2975b-262">Install the update.</span></span>
5. <span data-ttu-id="2975b-263">Atualize o Driver ODBC 11 para o SQL Server.</span><span class="sxs-lookup"><span data-stu-id="2975b-263">Update ODBC Driver 11 for SQL Server.</span></span> 
    1. <span data-ttu-id="2975b-264">Referência: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="2975b-264">Reference: [https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/en-us/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="2975b-265">Baixar a partir[https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span><span class="sxs-lookup"><span data-stu-id="2975b-265">Download from [https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434](https://www.microsoft.com/en-us/download/confirmation.aspx?id=36434)</span></span>
    3. <span data-ttu-id="2975b-266">Certifique-se de que o Skype para serviços de Business Server 2015 são interrompidos no servidor Front-End</span><span class="sxs-lookup"><span data-stu-id="2975b-266">Ensure that Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="2975b-267">Ex (Standard Edition): Stop-CsWindowsService</span><span class="sxs-lookup"><span data-stu-id="2975b-267">Ex (Standard Edition): Stop-CsWindowsService</span></span>
        - <span data-ttu-id="2975b-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span><span class="sxs-lookup"><span data-stu-id="2975b-268">Ex (Enterprise Edition): Invoke-CsComputerFailove</span></span>
    4. <span data-ttu-id="2975b-269">Atualize a atualização.</span><span class="sxs-lookup"><span data-stu-id="2975b-269">Install the update.</span></span>
6. <span data-ttu-id="2975b-270">Implante chaves do registro de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="2975b-270">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="2975b-271">Chaves do registro de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="2975b-271">Pre-requisite registry keys</span></span>

<span data-ttu-id="2975b-272">Copiar/colar o seguinte teste no bloco de notas e renomeie TLSPreReq.reg ou um nome de sua escolha, importar:</span><span class="sxs-lookup"><span data-stu-id="2975b-272">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v2.0.50727]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]

"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp]

"DefaultSecureProtocols"=dword:00000AA0

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server]

"DisabledByDefault"=dword:00000000

"Enabled"=dword:00000001
```

<span data-ttu-id="2975b-273">Para o SQL back ends para Pools do Enterprise Edition, os pré-requisitos e TLS desabilitar deve ser tratado como faria com quaisquer atualizações SQL ou o sistema operacional; Consulte o artigo:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="2975b-273">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="2975b-274">Enquanto o aplicativo de pré-requisito e o TLS desabilitando etapas podem ser combinadas, é altamente recomendável que todos os pré-requisitos a ser aplicado antes de prosseguir com a desativação de TLS 1.0 e 1.1 no nível do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2975b-274">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="2975b-275">A abordagem de prática recomendada seria preparar o ambiente implantando todos os pré-requisitos, validando que todas as cargas de trabalho funcionam corretamente e conforme o esperado, e então prosseguir com TLS 1.0/1.1 desabilitar mais tarde.</span><span class="sxs-lookup"><span data-stu-id="2975b-275">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="2975b-276">Desabilitar o TLS 1.0 e 1.1 por meio da importação de registro</span><span class="sxs-lookup"><span data-stu-id="2975b-276">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="2975b-277">Antes que você prosseguir com as próximas etapas, *Certifique-se de ter concluído a todos os pré-requisitos e atualizado Skype para servidores de negócios*.</span><span class="sxs-lookup"><span data-stu-id="2975b-277">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="2975b-278">Copie o seguinte texto em um arquivo do bloco de notas e renomeie- **TLSDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="2975b-278">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Cryptography\Configuration\SSL\00010002]

"Functions"="TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256_P256,TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256_P256,TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384,TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256,TLS_RSA_WITH_AES_256_GCM_SHA384,TLS_RSA_WITH_AES_128_GCM_SHA256,TLS_RSA_WITH_AES_256_CBC_SHA256,TLS_RSA_WITH_AES_128_CBC_SHA256"

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL]

"AllowInsecureRenegoClients"=dword:00000000

"AllowInsecureRenegoServers"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 128/128]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\AES 256/256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\DES 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\NULL]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC2 56/56]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 128/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 40/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 56/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\RC4 64/128]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Ciphers\Triple DES 168]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\MD5]

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA256]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA384]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Hashes\SHA512]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\Diffie-Hellman]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\ECDH]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\KeyExchangeAlgorithms\PKCS]

"Enabled"=dword:FFFFFFFF

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\Multi-Protocol Unified Hello\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\PCT 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 3.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.0\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1]

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Client]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.1\Server]

"DisabledByDefault"=dword:00000001

"Enabled"=dword:00000000
```

<span data-ttu-id="2975b-279">Importe o arquivo. reg em cada servidor que você deseja desativar o TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="2975b-279">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="2975b-280">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="2975b-280">Reboot the server.</span></span> <span data-ttu-id="2975b-281">Uma vez que os serviços tenham online novamente, mova para o próximo servidor.</span><span class="sxs-lookup"><span data-stu-id="2975b-281">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="2975b-282">A abordagem para Pools do Enterprise Edition é a mesma que você percorreria para qualquer atualização de sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="2975b-282">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="2975b-283">Você deve ter percebido que fazemos mais do que apenas desabilitando TLS 1.0 e 1.1 aqui.</span><span class="sxs-lookup"><span data-stu-id="2975b-283">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="2975b-284">Podemos suporte para conjunto de codificação reordenar (conforme mostrado acima) e a desativação de alguns codificações fracas mais antigas.</span><span class="sxs-lookup"><span data-stu-id="2975b-284">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="2975b-285">Esta é a primeira vez em que podemos oficialmente suportada essas alterações SCHANNEL e a API de criptografia no Skype para Business Server, e é importante observar que essas alterações são as únicas, podemos suportar e testado neste momento.</span><span class="sxs-lookup"><span data-stu-id="2975b-285">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="2975b-286">Ainda considerarem configurações adicionais no futuro, mas no momento, não modifique o arquivo de importação do registro na sua implementação.</span><span class="sxs-lookup"><span data-stu-id="2975b-286">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="2975b-287">Validar que cargas de trabalho estão funcionando conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="2975b-287">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="2975b-288">Depois que o TLS 1.0 e 1.1 foram desabilitadas em seu ambiente, certifique-se de que todas as suas cargas de trabalho principais estão funcionando conforme o esperado, como mensagens Instantâneas & presença, chamadas de P2P, Enterprise Voice, etc.</span><span class="sxs-lookup"><span data-stu-id="2975b-288">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="2975b-289">**Validar apenas TLS 1.2 está sendo usado.**</span><span class="sxs-lookup"><span data-stu-id="2975b-289">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="2975b-290">Ter sua equipe de segurança para realizar uma auditoria nova do Skype para tráfego de negócios para garantir que a antiguidade protocolos TLS 1.0 e 1.1 não estão mais em uso.</span><span class="sxs-lookup"><span data-stu-id="2975b-290">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="2975b-291">Como alternativa, você pode usar o Internet Explorer para testar conexões TLS aos serviços web do Skype Business Server 2015 depois 1.0 TLS e TLS 1.1 foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="2975b-291">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="2975b-292">Inicie o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2975b-292">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="2975b-293">Selecione **Ferramentas** > **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="2975b-293">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="2975b-294">Selecione a guia **Avançado** .</span><span class="sxs-lookup"><span data-stu-id="2975b-294">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="2975b-295">Em **configurações**, navegue até o fim.</span><span class="sxs-lookup"><span data-stu-id="2975b-295">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="2975b-296">Verificar se o TLS 1.0, 1.1 TLS e TLS 1.2 estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="2975b-296">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="2975b-297">Procure a URL interna do serviço Web do seu pool SfB 2015 (deve se conectar com êxito).</span><span class="sxs-lookup"><span data-stu-id="2975b-297">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="2975b-298">Volte para o Internet Explorer e desabilite a opção para **Usar TLS 1.2** apenas.</span><span class="sxs-lookup"><span data-stu-id="2975b-298">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="2975b-299">Procure a URL interna do serviço Web do seu pool SfB 2015 novamente (deve Falha na conexão).</span><span class="sxs-lookup"><span data-stu-id="2975b-299">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="2975b-301">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="2975b-301">Advanced deployment scenarios</span></span>

<span data-ttu-id="2975b-302">Pois alguns pré-requisitos de dependência são necessárias para dar suporte a TLS 1.2 no Skype para negócios Ser 2015, instalando da mídia RTM falhará em qualquer sistema onde TLS 1.0 e 1.1 foram desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="2975b-302">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="2975b-303">**Implantando os novos servidores do Standard Edition ou Enterprise Edition Pools depois que o TLS 1.0 e 1.1 foram desabilitadas em seu ambiente.**</span><span class="sxs-lookup"><span data-stu-id="2975b-303">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="2975b-304">**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="2975b-304">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="2975b-305">Observe que estiver atualizando SmartSetup para acomodar os binários atualizados do SQL em um futuro CU e atualizará este artigo no futuro.</span><span class="sxs-lookup"><span data-stu-id="2975b-305">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="2975b-306">**Opção 2:** Pré-instalar instâncias SQL locais (RTCLOCAL e LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="2975b-306">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="2975b-307">Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64.exe) para uma pasta local na FE.</span><span class="sxs-lookup"><span data-stu-id="2975b-307">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="2975b-308">Digamos que <SQL_FOLDER_PATH> de caminho da pasta.</span><span class="sxs-lookup"><span data-stu-id="2975b-308">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="2975b-309">Inicialize o PowerShell ou o Prompt de comando e navegue até <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="2975b-309">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="2975b-310">Crie a instância SQL RTCLOCAL executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="2975b-310">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="2975b-311">Aguarde até que o SQLEXPR_x64.exe é concluída antes de prosseguir:</span><span class="sxs-lookup"><span data-stu-id="2975b-311">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="2975b-312">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Install/recursos = SQLEngine, ferramentas /INSTANCENAME = RTCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT\NETWORKSERVICE" /SQLSYSADMINACCOUNTS = "Builtin\ Os administradores"/BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT"Automática"="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automáti</span><span class="sxs-lookup"><span data-stu-id="2975b-312">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="2975b-313">Crie a instância SQL LYNCLOCAL executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="2975b-313">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="2975b-314">Aguarde até que o SQLEXPR_x64.exe é concluída antes de prosseguir para a próxima etapa:</span><span class="sxs-lookup"><span data-stu-id="2975b-314">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="2975b-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED = 0 /HIDECONSOLE /ACTION = Install/recursos = SQLEngine, ferramentas /INSTANCENAME = LYNCLOCAL /TCPENABLED = 1 /SQLSVCACCOUNT = "NT\NETWORKSERVICE" /SQLSYSADMINACCOUNTS = "Builtin\ Os administradores"/BROWSERSVCSTARTUPTYPE = /AGTSVCACCOUNT"Automática"="NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automático</span><span class="sxs-lookup"><span data-stu-id="2975b-315">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="2975b-316">Execute Skype para instalação Business Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="2975b-316">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="2975b-317">Siga as etapas restantes da seção pré-requisitos acima.</span><span class="sxs-lookup"><span data-stu-id="2975b-317">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="2975b-318">**Opção 3:** Você pode substituir também manualmente binários em um diretório de mídia de instalação local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2975b-318">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="2975b-319">Instalar os pré-requisitos para Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="2975b-319">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. 2. <span data-ttu-id="2975b-320">Instale o .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="2975b-320">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="2975b-321">**Observação:** Podemos introduzidos suporte para .NET 4.7 no Skype para Business Server 2015 CU5 + (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="2975b-321">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5+ (6.0.9319.281).</span></span> <span data-ttu-id="2975b-322">Portanto, nas etapas posteriores abaixo atualizaremos componentes principais antes da instalação principal.</span><span class="sxs-lookup"><span data-stu-id="2975b-322">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="2975b-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="2975b-323">Download: https://www.microsoft.com/en-us/download/details.aspx?id=55167.</span></span>
      - <span data-ttu-id="2975b-324">Referência: [Software que deve ser instalado antes de um Skype para implantação Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="2975b-324">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="2975b-325">Copie os arquivos/pastas de ISO:</span><span class="sxs-lookup"><span data-stu-id="2975b-325">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="2975b-326">Com o Skype para Business Server 2015 ISO anexado, abra o diretório raiz da unidade do qual ele está conectado como (ex.: D:\) no Gerenciador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2975b-326">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="2975b-327">Copie todos os arquivos e pastas em uma pasta em um disco local (ex.: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="2975b-327">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="2975b-328">**Observação:** Antes de instalar os componentes, alguns arquivos precisarão ser atualizadas para oferecer suporte a TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="2975b-328">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="2975b-329">Substitua os pacotes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="2975b-329">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="2975b-330">Substitua os pacotes MSI e EXE existentes na pasta/amd64//Setup da mídia de instalação na máquina local.</span><span class="sxs-lookup"><span data-stu-id="2975b-330">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="2975b-331">SQL Express Edition SP2 de 2014:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="2975b-331">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="2975b-332">Renomeie para SQLEXPR_x64 na máquina local e substituir o arquivo existente na instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="2975b-332">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2975b-333">O SQL Native Client:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="2975b-333">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="2975b-334">**Observação:** Renomear isso se necessário, para SQLNCLI e, em seguida, substituir o arquivo existente que existe na instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="2975b-334">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2975b-335">Objetos de gerenciamento de SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="2975b-335">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="2975b-336">**Observação:** Feature pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="2975b-336">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="2975b-337">Selecione esta opção para baixar SharedManagementObjects.msi somente.</span><span class="sxs-lookup"><span data-stu-id="2975b-337">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="2975b-338">**Observação:** Substituir o arquivo existente que existe na instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="2975b-338">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="2975b-339">Tipos CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="2975b-339">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="2975b-340">**Observação:** Feature pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="2975b-340">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="2975b-341">Selecione essa opção para baixar CQLSysClrTypes.msi apenas</span><span class="sxs-lookup"><span data-stu-id="2975b-341">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="2975b-342">**Observação**: substituir o arquivo existente que existe na instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="2975b-342">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="2975b-343">Instale os componentes principais:</span><span class="sxs-lookup"><span data-stu-id="2975b-343">Install Core Components:</span></span> 
    - <span data-ttu-id="2975b-344">Executar Setup.exe a partir do programa de instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="2975b-344">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="2975b-345">Siga as instruções para instalar os componentes principais</span><span class="sxs-lookup"><span data-stu-id="2975b-345">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="2975b-346">Feche componentes principais.</span><span class="sxs-lookup"><span data-stu-id="2975b-346">Close Core Components.</span></span>
6. <span data-ttu-id="2975b-347">Atualize componentes principais:</span><span class="sxs-lookup"><span data-stu-id="2975b-347">Update Core Components:</span></span> 
    - <span data-ttu-id="2975b-348">Baixe o Skype para o instalador da atualização de negócios.</span><span class="sxs-lookup"><span data-stu-id="2975b-348">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="2975b-349">Execute o instalador para atualizar os componentes principais e instalar os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="2975b-349">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="2975b-350">**Observação:** Desde o lançamento do CU6HF2, o recurso de atualização automática atualmente apenas instalará até CU6.</span><span class="sxs-lookup"><span data-stu-id="2975b-350">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="2975b-351">Portanto, o atualizador deve ser executado separadamente para atualizar os componentes principais para 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="2975b-351">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="2975b-352">Referência:https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="2975b-352">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="2975b-353">Instale as ferramentas administrativas (opcionais):</span><span class="sxs-lookup"><span data-stu-id="2975b-353">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="2975b-354">Isso instalará o Microsoft SQL Server 2012 Native Client, objetos de gerenciamento 2014 (x64) do SQL Server e Microsoft System CLR Types for SQL Server 2014 (x64) usando os arquivos atualizados.</span><span class="sxs-lookup"><span data-stu-id="2975b-354">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="2975b-355">Além disso, o Skype para painel de controle e o construtor de topologias do Business Server 2015 estarão disponível na máquina local.</span><span class="sxs-lookup"><span data-stu-id="2975b-355">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="2975b-356">Repositório de configuração Local Install (etapa 1):</span><span class="sxs-lookup"><span data-stu-id="2975b-356">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="2975b-357">Abrir o Assistente de implantação, clique em instalar ou atualizar Skype para Business Server System e clique em **Executar** na etapa 1: instalar repositório de configuração Local.</span><span class="sxs-lookup"><span data-stu-id="2975b-357">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="2975b-358">Clique em **Avançar** na caixa de diálogo **Instalar repositório de configuração Local** .</span><span class="sxs-lookup"><span data-stu-id="2975b-358">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="2975b-359">![Caixa de diálogo instalar repositório de configuração Local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="2975b-359">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="2975b-360">Revise os resultados e certifique-se de que o Status da tarefa é concluído.</span><span class="sxs-lookup"><span data-stu-id="2975b-360">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="2975b-361">Revise o arquivo de log resultante clicando em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="2975b-361">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="2975b-362">![Status da tarefa mostra como concluído](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="2975b-362">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="2975b-363">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2975b-363">Click **Finish**.</span></span>
9. <span data-ttu-id="2975b-364">Configurar ou remover Skype para componentes de servidor de negócios (etapa 2):</span><span class="sxs-lookup"><span data-stu-id="2975b-364">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="2975b-365">Abrir o Assistente de implantação, clique em **instalar ou atualização Skype para Business Server System**e clique em **Executar** na etapa 2: configurar ou remover Skype para componentes de servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="2975b-365">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="2975b-366">Clique em **Avançar** na definir backup Skype para caixa de diálogo de componentes de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="2975b-366">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="2975b-367">![a definir backup Skype para a janela de componentes de servidor de negócios](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="2975b-367">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="2975b-368">Examine o log usando o modo de exibição de Log e validar a instalação efetuada sem problemas.</span><span class="sxs-lookup"><span data-stu-id="2975b-368">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="2975b-369">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="2975b-369">Click **Finish**.</span></span>
10. <span data-ttu-id="2975b-370">Prossiga com adicionais de instalação e configuração conforme necessário (você pode retomar procedimentos de instalação normal nesse momento).</span><span class="sxs-lookup"><span data-stu-id="2975b-370">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
