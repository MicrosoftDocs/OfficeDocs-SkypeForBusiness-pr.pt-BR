---
title: Desabilitar o TLS 1.0/1.1 no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: Preparar e implementar a desabilitação do TLS 1.0 e 1.1 em seus ambientes.
ms.openlocfilehash: 214605f80c79d7ecb334aeca49d29210e888b511
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726392"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="3c0f4-103">Desabilitar o TLS 1.0/1.1 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3c0f4-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="3c0f4-104">Este artigo ajuda você a se preparar e implementar a desabilitação de TLS 1.0 e 1.1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-104">This article helps you prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="3c0f4-105">Esse processo requer planejamento e preparação abrangentes.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="3c0f4-106">Revise cuidadosamente todas as informações deste artigo ao planejar desabilitar o TLS 1.0 e 1.1 para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-106">Carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="3c0f4-107">Há muitas dependências externas e condições de conectividade que podem ser impactadas desabilitando o TLS 1.0/1.1, portanto, é preciso planejar e testar extensivamente.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-107">There are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

- [<span data-ttu-id="3c0f4-108">Plano de fundo e escopo</span><span class="sxs-lookup"><span data-stu-id="3c0f4-108">Background and scope</span></span>](#background-and-scope)
- [<span data-ttu-id="3c0f4-109">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="3c0f4-109">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="3c0f4-110">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="3c0f4-110">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background-and-scope"></a><span data-ttu-id="3c0f4-111">Plano de fundo e escopo</span><span class="sxs-lookup"><span data-stu-id="3c0f4-111">Background and scope</span></span>

<span data-ttu-id="3c0f4-112">Os principais drivers para fornecer o TLS 1.0 e 1.1 desabilitam o suporte para o Skype for Business Server local são o Pci (Payment Card Industry) Security Standards Council e federal Information Processing Standards requirements.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-112">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="3c0f4-113">Mais informações sobre os requisitos pci podem ser encontradas [aqui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-113">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="3c0f4-114">A Microsoft não pode fornecer orientações sobre se sua organização precisa ou não aderir a esses ou outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-114">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="3c0f4-115">Você deve determinar se é necessário desabilitar o TLS 1.0 e/ou 1.1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-115">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="3c0f4-116">A Microsoft produziu um white paper no TLS disponível aqui [e](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)também recomendamos a leitura em segundo plano disponível neste blog [do Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-116">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="3c0f4-117">Escopo de suporte</span><span class="sxs-lookup"><span data-stu-id="3c0f4-117">Supportability Scope</span></span>

<span data-ttu-id="3c0f4-118">*Escopo* refere-se aos limites de suporte.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-118">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="3c0f4-119">*Totalmente testado e suportado* significa que suportamos totalmente e testamos a desabilitação do TLS 1.0 e 1.1 para as versões do produto listadas.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-119">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="3c0f4-120">*Atualmente sendo investigado significa* exatamente isso; estamos investigando ativamente a possibilidade de colocar esses produtos no escopo para que o TLS desabilite o suporte.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-120">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="3c0f4-121">*Fora do escopo,* essas versões do produto não suportam desabilitar o TLS 1.0 ou 1.1 e não funcionarão, com exceções notadas.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-121">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="3c0f4-122">Servidores totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="3c0f4-122">Fully tested and supported servers</span></span>

- <span data-ttu-id="3c0f4-123">Skype for Business Server 2019 CU1 17.0.2046.123 (junho de 2019) ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-123">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="3c0f4-124">Skype for Business Server 2015 CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização de superação), 2012 R2 ou 2016.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-124">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="3c0f4-125">Skype for Business Server 2015 atualizado in-place, com CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização sobressedida) ou 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-125">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="3c0f4-126">Conectividade do Exchange e Outlook Web App com Exchange Server 2010 SP3 RU19 ou superior, [orientações aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-126">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="3c0f4-127">Aparelho de Filial Desavivável (SBA) com Skype for Business Server 2015 CU6 HF2 ou superior (confirme com o fornecedor que eles empacotou as atualizações apropriadas e foram disponibilizadas para o seu dispositivo)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-127">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="3c0f4-128">Servidor de Filial Desavivável (SBS) com Skype for Business Server 2015 CU6 HF2 ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-128">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="3c0f4-129">Somente função de borda do Lync Server 2013 , isso acontece porque a função De borda não tem uma dependência do Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-129">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="3c0f4-130">Clientes totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="3c0f4-130">Fully tested and supported clients</span></span>

- <span data-ttu-id="3c0f4-131">Cliente de área de trabalho do Lync 2013 (Skype for Business), MSI e C2R, incluindo Basic [15.0.5023.1000 ou superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-131">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="3c0f4-132">Cliente de área de trabalho do Skype for Business 2016, MSI [16.0.4678.1000 ou superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluindo Basic</span><span class="sxs-lookup"><span data-stu-id="3c0f4-132">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="3c0f4-133">Clique para executar o Skype for Business 2016 Exigir as Atualizações de abril de [2018:](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-133">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="3c0f4-134">Mensal e Semi-Annual Direcionado, 16 \. 0 \. 9126 \. 2152 ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-134">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="3c0f4-135">Semi-Annual e Canal Adiado, 16 \. 0 \. 8431 \. 2242 ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-135">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="3c0f4-136">Skype for Business no Mac 16.15 ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-136">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="3c0f4-137">Skype for Business para iOS e Android 6.19 ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-137">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="3c0f4-138">Salas do Microsoft Teams (anteriormente conhecidas como Skype Room System V2 SRS V2) 4.0.64.0 (dezembro de 2018) ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-138">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="3c0f4-139">Atualização do Surface Hub para a edição team com base em KB4499162 (maio de 2019, com build do sistema operacional 15063.1835) ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-139">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="3c0f4-140">Skype Web App 2015 CU6 HF2 ou superior (acompanha o Server)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-140">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="3c0f4-141">Atualmente sendo investigado</span><span class="sxs-lookup"><span data-stu-id="3c0f4-141">Currently being investigated</span></span>

- <span data-ttu-id="3c0f4-142">Painel de Qualidade de Chamada (nova instalação após o TLS 1.0, 1.1 ter sido desabilitado, consulte abaixo)\*</span><span class="sxs-lookup"><span data-stu-id="3c0f4-142">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="3c0f4-143">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="3c0f4-143">Out of scope</span></span>

<span data-ttu-id="3c0f4-144">Exceto quando notado, os produtos a seguir não estão no escopo para o TLS 1.0/1.1 desabilitar o suporte e não funcionarão em um ambiente em que o TLS 1.0 e 1.1 foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-144">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="3c0f4-145">O que isso significa: se você ainda utilizar servidores ou clientes fora do escopo, deverá atualizá-los ou removê-los se precisar desabilitar o TLS 1.0/1.1 em qualquer lugar em sua implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-145">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="3c0f4-146">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c0f4-146">Lync Server 2013</span></span>
- <span data-ttu-id="3c0f4-147">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3c0f4-147">Lync Server 2010</span></span>
- <span data-ttu-id="3c0f4-148">Windows Server 2008 ou inferior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-148">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="3c0f4-149">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="3c0f4-149">Lync for Mac 2011</span></span>
- <span data-ttu-id="3c0f4-150">Lync 2013 para Celular - iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3c0f4-150">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="3c0f4-151">Cliente Lync "MX" da Windows Store</span><span class="sxs-lookup"><span data-stu-id="3c0f4-151">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="3c0f4-152">Lync Room System (também conhecido como .</span><span class="sxs-lookup"><span data-stu-id="3c0f4-152">Lync Room System (a.k.a.</span></span> <span data-ttu-id="3c0f4-153">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-153">SRSv1).</span></span> <span data-ttu-id="3c0f4-154">O LRS atingiu o fim do suporte em 9 de outubro de 2018 e não será atualizado para dar suporte ao TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-154">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="3c0f4-155">Todos os clientes do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="3c0f4-155">All Lync 2010 clients</span></span>
- <span data-ttu-id="3c0f4-156">Lync Phone Edition - diretrizes atualizadas [aqui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-156">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="3c0f4-157">Dispositivo de Filial (SBA) baseado em 2013 ou SBS (Servidor de Filial Desavivável)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-157">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="3c0f4-158">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-158">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="3c0f4-159">Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3c0f4-159">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="3c0f4-160">Exceptions</span><span class="sxs-lookup"><span data-stu-id="3c0f4-160">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="3c0f4-161">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c0f4-161">Lync Server 2013</span></span>

<span data-ttu-id="3c0f4-162">O Lync Server 2013 tem uma dependência do Windows Fabric versão 1.0.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-162">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="3c0f4-163">Na fase de design do Lync Server 2013, o Windows Fabric 1.0 foi escolhido por sua nova arquitetura distribuída atraente para fornecer replicação, alta disponibilidade e tolerância a falhas.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-163">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="3c0f4-164">Com o passar do tempo, o Skype for Business Server e o Windows Fabric melhoraram muito essa arquitetura conjunta com um re-design significativo nas versões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-164">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="3c0f4-165">O Servidor Atual do Skype for Business 2015 usa o Windows Fabric 3.0, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-165">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="3c0f4-166">Infelizmente, o Windows Fabric 1.0 **não dá suporte ao TLS 1.2.  No entanto, atualizaremos o Lync Server 2013 para trabalhar com o TLS 1.2**.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-166">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="3c0f4-167">Isso estará chegando na próxima Atualização Cumulativa do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-167">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="3c0f4-168">Estamos fornecendo suporte ao TLS 1.2 para habilitar cenários de co-existência, migração, federação e híbridos.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-168">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="3c0f4-169">Se sua organização for necessária para desabilitar o TLS 1.0 e 1.1, e você usar o Lync Server 2013 no momento, recomendamos que você inicie seu processo de planejamento, com a possibilidade de ter que atualizar in-loco ou migrar lado a lado (novos pools, mover usuários) para o Skype for Business Server 2015 ou superior.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-169">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="3c0f4-170">Ou talvez você queira acelerar a migração para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-170">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="3c0f4-171">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="3c0f4-171">Call Quality Dashboard</span></span>

<span data-ttu-id="3c0f4-172">No momento, o Painel de Qualidade de Chamada Local tem uma dependência do TLS 1.0 durante a nova instalação (primeira vez que você instala seus ambientes locais).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-172">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="3c0f4-173">No momento, estamos investigando esse problema e planejamos liberar uma correção em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-173">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="3c0f4-174">Se você estiver planejando instalar o CQD e também desabilitar o TLS 1.0, recomendamos que você conclua a instalação do CQD primeiro e prossiga com a desabilitação do TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-174">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="3c0f4-175">Gerente do SDN do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3c0f4-175">Skype for Business SDN Manager</span></span>

<span data-ttu-id="3c0f4-176">O Gerenciador de SDN do Skype for Business usando SQL um banco de dados tem uma dependência do TLS 1.0 durante a nova instalação.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-176">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="3c0f4-177">Se você estiver planejando instalar o Gerenciador de SDN do Skype for Business usando SQL um banco de dados e também desabilitar o TLS 1.0, recomendamos que você conclua o Gerenciador de SDN do Skype for Business primeiro e prossiga com a desabilitação do TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-177">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="3c0f4-178">Caso o TLS 1.0 tenha sido desabilitado antes da instalação, você deve habilitar temporariamente o TLS 1.0 de volta no servidor back-end do SQL Server que será usado para hospedar o banco de dados do Gerenciador de SDN do Skype for Business SQL.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-178">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="3c0f4-179">Dispositivos de terceiros</span><span class="sxs-lookup"><span data-stu-id="3c0f4-179">Third-party devices</span></span>

<span data-ttu-id="3c0f4-180">Em dispositivos de terceiros, como telefones 3PIP, Videoconferência, Proxies Reversos e Balanceadores de Carga, certifique-se de validar a capacidade de suporte do TLS 1.2, teste cuidadosamente e contate o fornecedor, se necessário.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-180">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="3c0f4-181">Considerações de federação ao desabilitar o TLS 1.0/1.1 em servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="3c0f4-181">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="3c0f4-182">Você deve planejar cuidadosamente e considerar o impacto da desabilitação do TLS 1.0/1.1 em seus servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-182">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="3c0f4-183">Depois que o TLS 1.0 e o 1.1 são desabilitados, você pode descobrir que outras organizações não podem mais se federar com sua organização.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-183">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="3c0f4-184">Você pode optar por manter o TLS 1.0/1.1 habilitado em seus servidores de Borda para manter a compatibilidade com versões regressivas com sistemas externos não corrigidas (SfB 2015, Lync 2013) ou mais antigos (2010).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-184">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="3c0f4-185">A Microsoft não pode fornecer conselhos ou recomendações sobre se sua rede de Borda (ou qualquer rede) está ou não em conformidade com o padrão PCI; que deve ser determinado pela empresa individual.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-185">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="3c0f4-186">O Skype for Business Online é capaz de TLS 1.2 hoje, portanto, não é esperado impacto para o Híbrido/Federação com o Online.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-186">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="3c0f4-187">PIC (Conectividade de IM Pública) para o serviço do Skype Consumer: não esperamos desabilitar o TLS 1.0/1.1 para afetar a conectividade do [Skype;](../../deploy/deploy-skype-connectivity.md) Os Gateways PIC da Microsoft já são TLS 1.2 capazes.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-187">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="3c0f4-188">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="3c0f4-188">Prerequisites and process</span></span>

<span data-ttu-id="3c0f4-189">Exceto quando mencionado acima, uma vez que o TLS 1.0 e 1.1 são desabilitados servidores fora do escopo, clientes e dispositivos funcionarão corretamente ou em tudo.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-189">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="3c0f4-190">Isso pode significar que você precisa pausar e aguardar orientações atualizadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-190">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="3c0f4-191">Depois de atender a todos os requisitos e ter um plano para resolver lacunas, prossiga.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-191">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="3c0f4-192">Em um nível alto, enquanto o Skype for Business Server 2019 está pronto para o procedimento na instalação, o Skype for Business Server 2015 exigirá que você instale o CU9, aplicando atualizações pré-requisitos ao .NET e ao SQL, implantando chaves de registro de pré-requisitos e, finalmente, uma rodada separada de atualizações de configuração do sistema operacional (ou seja, desabilitando o TLS 1.0 e 1.1 por meio da importação de arquivos do Registro).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-192">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="3c0f4-193">É fundamental que você conclua a instalação de todos os pré-requisitos, incluindo o Skype for Business Server 2015 CU6 HF2, antes de desabilitar o TLS 1.0 e 1.1 em qualquer servidor em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-193">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="3c0f4-194">Todos os servidores do Skype for Business, incluindo a função de borda e SQL Backends, exigem as atualizações.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-194">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="3c0f4-195">Verifique também se todos os clientes com suporte (no escopo) foram atualizados para as versões mínimas necessárias.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-195">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="3c0f4-196">Não se esqueça de atualizar as estações de trabalho de gerenciamento também.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-196">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="3c0f4-197">Queremos seguir a ordem usual de operações de "de dentro para fora" para atualizar servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-197">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="3c0f4-198">Trate pools de diretores, chat persistente e pools emparelhados da mesma maneira que normalmente faria.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-198">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="3c0f4-199">A ordem e os métodos de atualização são abordados [aqui](topology.md) e [aqui.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-199">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="3c0f4-200">Processo de alto nível</span><span class="sxs-lookup"><span data-stu-id="3c0f4-200">High-level process</span></span>

1. <span data-ttu-id="3c0f4-201">Teste todas as etapas em seu laboratório antes de configurar servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-201">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="3c0f4-202">Fazer o back-up e preservar uma cópia do Registro exportado em cada servidor individual a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-202">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="3c0f4-203">Não é possível compartilhar registros entre servidores; eles contêm chaves exclusivas baseadas em máquina.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-203">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="3c0f4-204">Atualize todos os servidores do Skype for Business 2015 para CU9 ou superior.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-204">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="3c0f4-205">Para o Skype for Business Server 2019, atualize para CU1 ou superior.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-205">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="3c0f4-206">Instale todos os pré-requisitos em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-206">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="3c0f4-207">Implantar chaves de registro de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-207">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="3c0f4-208">Certifique-se de que todos os clientes no escopo sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-208">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="3c0f4-209">Desabilite o TLS 1.0 e 1.1 por meio da importação do Registro.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-209">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="3c0f4-210">Valide se as cargas de trabalho estão funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-210">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="3c0f4-211">Se os problemas são encontrados, solução de problemas e solução ou</span><span class="sxs-lookup"><span data-stu-id="3c0f4-211">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="3c0f4-212">Restaurar o Registro da etapa 2 para habilitar o TLS 1.0 e 1.1</span><span class="sxs-lookup"><span data-stu-id="3c0f4-212">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="3c0f4-213">Valide se apenas o TLS 1.2 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-213">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="3c0f4-214">Instalar pré-requisitos em todos os servidores</span><span class="sxs-lookup"><span data-stu-id="3c0f4-214">Install prerequisites to all servers</span></span>

<span data-ttu-id="3c0f4-215">A atualização de dependência extensiva é necessária antes de começar a desabilitar o TLS 1.0 e 1.1 no nível do sistema operacional em suas implantações do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-215">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="3c0f4-216">A seguir estão as versões mínimas que podem dar suporte ao TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-216">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="3c0f4-217">Implante todas as atualizações de pré-requisito em todos os servidores do Skype for Business em seu ambiente antes de começar a desabilitar o TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-217">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="3c0f4-218">Skype for Business Server 2015 CU9 6.0.9319.548 (maio de 2019) ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-218">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="3c0f4-219">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) ou superior com SchUseStrongCrypto habilitado no Registro (fornecido abaixo)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-219">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="3c0f4-220">SQL deve ser atualizado em todos os servidores e back-ends do Skype for Business 2015.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-220">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="3c0f4-221">Atualize o Pool enterprise edition SQL backends primeiro e, em seguida, seus respectivos FEs.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-221">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="3c0f4-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), ou superior /SQL Server 2012 SP2 + CU16 ou superior [/SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), ou superior /SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3c0f4-222">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="3c0f4-223">SQL Server cliente nativo para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="3c0f4-223">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="3c0f4-224">[Microsoft ODBC Driver 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), ou superior</span><span class="sxs-lookup"><span data-stu-id="3c0f4-224">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="3c0f4-225">Objetos de gerenciamento compartilhados para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3c0f4-225">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="3c0f4-226">SQLSysClrTypes para SQL server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3c0f4-226">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="3c0f4-227">Etapas básicas para instalar pré-requisitos, em ordem recomendada de operações</span><span class="sxs-lookup"><span data-stu-id="3c0f4-227">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="3c0f4-228">Instale a atualização cu9 do Skype for Business Server para todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-228">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="3c0f4-229">Instale a atualização em componentes usando o atualizador.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-229">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="3c0f4-230">Atualize os bancos de dados de acordo com os procedimentos documentados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-230">Update databases according to documented procedures.</span></span> <span data-ttu-id="3c0f4-231">Para o Skype for Business Server 2015, consulte KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-231">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="3c0f4-232">Valide a funcionalidade do produto na implantação antes de avançar com quaisquer outras alterações.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-232">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="3c0f4-233">Baixe o Instalador Offline do .NET 4.7.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-233">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="3c0f4-234">Referência: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-234">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="3c0f4-235">Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-235">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="3c0f4-236">Referência: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-236">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="3c0f4-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-237">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="3c0f4-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-238">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="3c0f4-239">Execute o pacote do instalador.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-239">Run the installer package.</span></span>
    7. <span data-ttu-id="3c0f4-240">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-240">Reboot the server.</span></span>
3. <span data-ttu-id="3c0f4-241">Atualize SQL Express 2014 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-241">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="3c0f4-242">Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-242">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="3c0f4-243">Baixar SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="3c0f4-243">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="3c0f4-244">Referência: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-244">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="3c0f4-245">Copie a mídia de instalação para uma pasta no servidor (Ex: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-245">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="3c0f4-246">Garantir que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end</span><span class="sxs-lookup"><span data-stu-id="3c0f4-246">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="3c0f4-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-247">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="3c0f4-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-248">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="3c0f4-249">Abra um Prompt de Comando de Administrador e atualize todos os componentes e instâncias instalados</span><span class="sxs-lookup"><span data-stu-id="3c0f4-249">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="3c0f4-250">Exemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="3c0f4-250">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="3c0f4-251">Atualizar SQL Cliente Nativo.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-251">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="3c0f4-252">Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="3c0f4-252">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="3c0f4-253">Baixar do [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-253">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="3c0f4-254">Verifique se os serviços do Skype for Business Server 2015 são interrompidos no servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-254">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="3c0f4-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-255">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="3c0f4-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-256">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="3c0f4-257">Impedir que SQL instâncias instaladas em execução</span><span class="sxs-lookup"><span data-stu-id="3c0f4-257">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="3c0f4-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-258">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="3c0f4-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-259">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="3c0f4-260">Ex (Somente Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-260">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="3c0f4-261">Instale a atualização.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-261">Install the update.</span></span>
5. <span data-ttu-id="3c0f4-262">Atualizar ODBC Driver 11 para SQL Server incluir suporte para TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-262">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="3c0f4-263">Baixe [ODBC Driver 11 para SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-263">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="3c0f4-264">Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-264">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="3c0f4-265">Exemplo (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-265">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="3c0f4-266">Exemplo (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="3c0f4-266">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="3c0f4-267">Instale a atualização.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-267">Install the update.</span></span>
6. <span data-ttu-id="3c0f4-268">Implantar chaves de registro de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-268">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="3c0f4-269">Chaves de Registro de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="3c0f4-269">Pre-requisite registry keys</span></span>

<span data-ttu-id="3c0f4-270">Copie/colar o teste a seguir no Bloco de Notas e renomeie TLSPreReq.reg ou um nome de sua escolha e importe:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-270">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

```console
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

<span data-ttu-id="3c0f4-271">Para SQL back-ends para Pools Enterprise Edition, os pré-requisitos e a desabilitação de TLS devem ser tratados como qualquer SQL ou atualizações do sistema operacional seriam; consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-271">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="3c0f4-272">Embora o aplicativo de pré-requisito e as etapas de desabilitação TLS possam ser combinadas, recomendamos que todos os pré-requisitos sejam aplicados antes de prosseguir com a desabilitação do TLS 1.0 e 1.1 no nível do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-272">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="3c0f4-273">A abordagem de prática ideal seria preparar o ambiente implantando todos os pré-requisitos, validando que todas as cargas de trabalho funcionem corretamente e conforme o esperado e, em seguida, continuar com o TLS 1.0/1.1 desabilitado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-273">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="3c0f4-274">Desabilitar o TLS 1.0 e 1.1 por meio da importação do Registro</span><span class="sxs-lookup"><span data-stu-id="3c0f4-274">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="3c0f4-275">Antes de prosseguir com as próximas etapas, certifique-se de ter concluído todos os *pré-requisitos* e atualizado o Skype for Business Servers .</span><span class="sxs-lookup"><span data-stu-id="3c0f4-275">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="3c0f4-276">Copie o seguinte texto em um arquivo bloco de notas e **renomeie-o TLSDisable.reg**:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-276">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

```console
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

<span data-ttu-id="3c0f4-277">Importe o arquivo .reg em cada servidor que você deseja desabilitar TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-277">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="3c0f4-278">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-278">Reboot the server.</span></span> <span data-ttu-id="3c0f4-279">Depois que os serviços voltarem online, mova-se para o próximo servidor.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-279">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="3c0f4-280">A abordagem para Pools Enterprise Edition é a mesma que você faria para qualquer atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-280">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="3c0f4-281">Você deve ter percebido que estamos desabilitando mais do que desabilitar o TLS 1.0 e 1.1 aqui.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-281">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="3c0f4-282">Estamos dando suporte à re-ordem do Cipher Suite (conforme mostrado acima) e à desabilitação de algumas codificações fracas mais antigas.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-282">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="3c0f4-283">Esta é a primeira vez que suportamos oficialmente essas alterações na API SCHANNEL e Crypto no Skype for Business Server, e é importante observar que essas alterações são as únicas que suportamos e testamos no momento.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-283">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="3c0f4-284">Podemos considerar configurações adicionais no futuro, mas, por enquanto, não modifique o arquivo de importação do Registro em sua implementação.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-284">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="3c0f4-285">Validar se as cargas de trabalho estão funcionando conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="3c0f4-285">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="3c0f4-286">Depois que o TLS 1.0 e o 1.1 foram desabilitados em seu ambiente, verifique se todas as suas cargas de trabalho principais estão funcionando conforme o esperado, como IM & Presence, chamadas P2P, Enterprise Voice, etc.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-286">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="3c0f4-287">**Validar apenas o TLS 1.2 está sendo usado**</span><span class="sxs-lookup"><span data-stu-id="3c0f4-287">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="3c0f4-288">Faça com que sua Equipe de Segurança execute uma nova auditoria do tráfego do Skype for Business para garantir que os protocolos mais antigos TLS 1.0 e 1.1 não sejam mais em uso.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-288">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="3c0f4-289">Como alternativa, você pode usar o Internet Explorer para testar as conexões TLS aos serviços Web do Skype for Business Server 2015 depois que o TLS 1.0 e o TLS 1.1 foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-289">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="3c0f4-290">Iniciar o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-290">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="3c0f4-291">Selecione **Ferramentas Opções** da  >  **Internet**.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-291">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="3c0f4-292">Selecione a **guia** Avançado.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-292">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="3c0f4-293">Em **Configurações,** role até a parte inferior.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-293">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="3c0f4-294">Verifique se o TLS 1.0, o TLS 1.1 e o TLS 1.2 estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-294">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="3c0f4-295">Navegue pela URL do Serviço Web Interno do pool do SfB 2015 (deve se conectar com êxito).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-295">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="3c0f4-296">Volte para o Internet Explorer e desabilite a opção **para Usar somente o TLS 1.2.**</span><span class="sxs-lookup"><span data-stu-id="3c0f4-296">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="3c0f4-297">Navegue novamente pela URL do Serviço Web Interno do pool do SfB 2015 (deve falhar ao se conectar).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-297">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="3c0f4-299">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="3c0f4-299">Advanced deployment scenarios</span></span>

<span data-ttu-id="3c0f4-300">Como alguns pré-requisitos de dependência são necessários para dar suporte ao TLS 1.2 no Skype for Business Server 2015, a instalação da mídia RTM falhará em qualquer sistema em que o TLS 1.0 e 1.1 foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-300">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="3c0f4-301">**Implantando Novos Servidores Standard Edition ou Pools Enterprise Edition depois que o TLS 1.0 e o 1.1 foram desabilitados em seu ambiente.**</span><span class="sxs-lookup"><span data-stu-id="3c0f4-301">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="3c0f4-302">**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-302">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="3c0f4-303">Observe que estamos atualizando o SmartSetup para acomodar SQL binários atualizados em uma CU futura e atualizaremos este artigo no futuro.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-303">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="3c0f4-304">**Opção 2:** Pré-instalar instâncias SQL locais (RTCLOCAL e LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-304">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="3c0f4-305">Baixe e copie SQL Express 2014 SP2 (SQLEXPR_x64.exe) para a pasta local no FE.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-305">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="3c0f4-306">Digamos que o caminho da pasta <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-306">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="3c0f4-307">Iniciar o PowerShell ou o Prompt de Comando e navegue até <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-307">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="3c0f4-308">Crie a instância RTCLOCAL SQL executando o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-308">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="3c0f4-309">Aguarde até SQLEXPR_x64.exe finalize antes de prosseguir:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-309">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="3c0f4-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="3c0f4-310">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="3c0f4-311">Crie a instância LYNCLOCAL SQL executando o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-311">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="3c0f4-312">Aguarde até SQLEXPR_x64.exe finalize antes de prosseguir para a próxima etapa:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-312">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="3c0f4-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="3c0f4-313">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="3c0f4-314">Execute a configuração RTM do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-314">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="3c0f4-315">Siga as etapas restantes da seção pré-requisitos acima.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-315">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="3c0f4-316">**Opção 3:** Você também pode substituir binários manualmente em um diretório de mídia de instalação local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-316">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="3c0f4-317">Instalar pré-requisitos para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3c0f4-317">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="3c0f4-318">Instale o .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-318">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="3c0f4-319">**Observação:** Apresentamos pela primeira vez o suporte para o .NET 4.7 no Skype for Business Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-319">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="3c0f4-320">Portanto, nas etapas posteriores abaixo, atualizaremos Componentes Principais antes da instalação principal.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-320">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="3c0f4-321">Download: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="3c0f4-321">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="3c0f4-322">Referência: [software que deve ser instalado antes de uma implantação do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-322">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="3c0f4-323">Copiar arquivos/pastas ISO:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-323">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="3c0f4-324">Com o ISO do Skype for Business Server 2015 anexado, abra o diretório raiz da unidade anexada como (Ex: D: \) no Explorador de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-324">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="3c0f4-325">Copie todas as pastas e arquivos para uma pasta em um disco local (Ex: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-325">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="3c0f4-326">**Observação:** Antes de instalar componentes, alguns arquivos precisarão ser atualizados para dar suporte ao TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-326">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="3c0f4-327">Substitua pacotes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-327">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="3c0f4-328">Substitua os pacotes MSI e EXE existentes na pasta /Setup/amd64/ da mídia de instalação no computador local.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-328">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="3c0f4-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="3c0f4-329">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="3c0f4-330">Renomeie para SQLEXPR_x64 no computador local e substitua o arquivo existente na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-330">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="3c0f4-331">SQL cliente nativo: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="3c0f4-331">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="3c0f4-332">**Observação:** Renomeie isso se necessário para sqlncli.msi e substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-332">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="3c0f4-333">SQL Objetos de Gerenciamento: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="3c0f4-333">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="3c0f4-334">**Observação:** O Feature pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-334">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="3c0f4-335">Selecione para baixar SharedManagementObjects.msi somente.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-335">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="3c0f4-336">**Observação:** Substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-336">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="3c0f4-337">SQL clr tipos: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="3c0f4-337">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="3c0f4-338">**Observação:** O Feature pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-338">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="3c0f4-339">Selecione para baixar CQLSysClrTypes.msi somente</span><span class="sxs-lookup"><span data-stu-id="3c0f4-339">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="3c0f4-340">**Observação**: Substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-340">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="3c0f4-341">Instalar componentes principais:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-341">Install Core Components:</span></span> 
    - <span data-ttu-id="3c0f4-342">Execute Setup.exe da pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-342">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="3c0f4-343">Siga as instruções para instalar Componentes Principais</span><span class="sxs-lookup"><span data-stu-id="3c0f4-343">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="3c0f4-344">Fechar Componentes Principais.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-344">Close Core Components.</span></span>
6. <span data-ttu-id="3c0f4-345">Atualizar Componentes Principais:</span><span class="sxs-lookup"><span data-stu-id="3c0f4-345">Update Core Components:</span></span> 
    - <span data-ttu-id="3c0f4-346">Baixe o Instalador de Atualização do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-346">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="3c0f4-347">Execute o instalador para atualizar Os Componentes Principais e instalar os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-347">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="3c0f4-348">**Observação:** A partir do lançamento do CU6HF2, o recurso de atualização automática atualmente só instalará até CU6.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-348">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="3c0f4-349">Portanto, o atualizador deve ser executado separadamente para atualizar Componentes Principais para 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-349">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="3c0f4-350">Referência: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="3c0f4-350">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="3c0f4-351">Instalar Ferramentas Administrativas (Opcional):</span><span class="sxs-lookup"><span data-stu-id="3c0f4-351">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="3c0f4-352">Isso instalará o cliente nativo do Microsoft SQL Server 2012, os objetos de gerenciamento do SQL Server 2014 (x64) e os Tipos de CLR do Microsoft System para SQL Server 2014 (x64) usando os arquivos atualizados.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-352">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="3c0f4-353">Além disso, o Painel de Controle e Construtor de Topologias do Skype for Business Server 2015 estará disponível no computador local.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-353">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="3c0f4-354">Instalar o Armazenamento de Configuração Local (Etapa 1):</span><span class="sxs-lookup"><span data-stu-id="3c0f4-354">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="3c0f4-355">Abra o Assistente de Implantação, clique em Instalar ou Atualizar o Sistema do Skype for Business Server e clique em **Executar** na Etapa 1: Instalar o Armazenamento de Configuração Local.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-355">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="3c0f4-356">Clique **em Próximo** na caixa de diálogo Instalar o Armazenamento de **Configuração** Local.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-356">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="3c0f4-357">![Caixa de diálogo Instalar o Armazenamento de Configuração Local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-357">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="3c0f4-358">Revise os resultados e verifique se o Status da Tarefa foi Concluído.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-358">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="3c0f4-359">Revise o arquivo de log resultante clicando em **Exibir Log**.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-359">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="3c0f4-360">![O status da tarefa mostra como Concluído](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-360">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="3c0f4-361">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-361">Click **Finish**.</span></span>
9. <span data-ttu-id="3c0f4-362">Configurar ou remover componentes do Skype for Business Server (Etapa 2):</span><span class="sxs-lookup"><span data-stu-id="3c0f4-362">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="3c0f4-363">Abra o Assistente de Implantação, clique em Instalar  ou Atualizar o Sistema do **Skype for Business Server** e clique em Executar na Etapa 2: Configurar ou Remover Componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3c0f4-363">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="3c0f4-364">Clique **em Próximo** na caixa de diálogo Configurar Componentes do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-364">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="3c0f4-365">![a janela Configurar Componentes do Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="3c0f4-365">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="3c0f4-366">Revise o log usando o Log de Exibição e valide essa configuração concluída sem problemas.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-366">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="3c0f4-367">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="3c0f4-367">Click **Finish**.</span></span>
10. <span data-ttu-id="3c0f4-368">Prossiga com a instalação e a configuração adicionais conforme necessário (você pode retomar os procedimentos normais de instalação neste ponto).</span><span class="sxs-lookup"><span data-stu-id="3c0f4-368">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
