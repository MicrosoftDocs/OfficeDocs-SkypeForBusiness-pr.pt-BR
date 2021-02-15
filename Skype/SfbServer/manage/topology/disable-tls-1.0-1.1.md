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
description: 'Resumo: prepare e implemente a desabilitação do TLS 1.0 e 1.1 em seus ambientes.'
ms.openlocfilehash: da76280540f9d18435ed929aace6cf6fc439a4cf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826391"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="d8499-103">Desabilitar o TLS 1.0/1.1 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d8499-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="d8499-104">O objetivo deste artigo é fornecer as orientações necessárias para que você se prepare e implemente a desabilitação do TLS 1.0 e 1.1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="d8499-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="d8499-105">Esse processo requer planejamento e preparação abrangentes.</span><span class="sxs-lookup"><span data-stu-id="d8499-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="d8499-106">Revise cuidadosamente todas as informações neste artigo ao planejar desabilitar o TLS 1.0 e 1.1 para sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8499-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="d8499-107">Observe que há muitas dependências externas e condições de conectividade que podem ser impactadas desabilitando o TLS 1.0/1.1, portanto, é preciso planejar e testar extensivamente.</span><span class="sxs-lookup"><span data-stu-id="d8499-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="d8499-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="d8499-108">In this article</span></span>

- [<span data-ttu-id="d8499-109">Plano de fundo e escopo</span><span class="sxs-lookup"><span data-stu-id="d8499-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="d8499-110">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="d8499-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="d8499-111">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="d8499-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="d8499-112">Histórico</span><span class="sxs-lookup"><span data-stu-id="d8499-112">Background</span></span>

<span data-ttu-id="d8499-113">Os principais fatores para o fornecimento do TLS 1.0 e 1.1 desabilitam o suporte para o Skype for Business Server Local são o Conselho de Padrões de Segurança PCI (Payment Card Industry) e os requisitos dos Padrões Federais de Processamento de Informações.</span><span class="sxs-lookup"><span data-stu-id="d8499-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="d8499-114">Mais informações sobre os requisitos de PCI podem ser [encontradas aqui.](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)</span><span class="sxs-lookup"><span data-stu-id="d8499-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="d8499-115">A Microsoft não pode fornecer orientações sobre se a sua organização deve ou não cumprir esses ou outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="d8499-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="d8499-116">Você deve determinar se é necessário desabilitar o TLS 1.0 e/ou 1.1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="d8499-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="d8499-117">A Microsoft produziu um white paper sobre o TLS disponível [aqui,](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)e também recomendamos a leitura de plano de fundo disponível neste [blog do Exchange.](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="d8499-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="d8499-118">Escopo de suporte</span><span class="sxs-lookup"><span data-stu-id="d8499-118">Supportability Scope</span></span>

<span data-ttu-id="d8499-119">*O escopo* refere-se aos limites de suporte.</span><span class="sxs-lookup"><span data-stu-id="d8499-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="d8499-120">*Totalmente testado e com* suporte significa que damos suporte total e testamos a desabilitação do TLS 1.0 e 1.1 para as versões do produto listadas.</span><span class="sxs-lookup"><span data-stu-id="d8499-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="d8499-121">*Atualmente sendo investigado significa* apenas que; Estamos investigando ativamente para colocar esses produtos no escopo para que o TLS desabilite o suporte.</span><span class="sxs-lookup"><span data-stu-id="d8499-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="d8499-122">*Fora do* escopo significa que essas versões do produto não suportam a desabilitação do TLS 1.0 ou 1.1 e não funcionarão, com exceções notadas.</span><span class="sxs-lookup"><span data-stu-id="d8499-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="d8499-123">Servidores totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="d8499-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="d8499-124">Skype for Business Server 2019 CU1 17.0.2046.123 (junho de 2019) ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="d8499-125">Skype for Business Server 2015 CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização de sobressedida), 2012 R2 ou 2016.</span><span class="sxs-lookup"><span data-stu-id="d8499-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="d8499-126">Skype for Business Server 2015 atualizado in-place, com CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização de sobressedido) ou 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="d8499-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="d8499-127">Conectividade do Exchange e Outlook Web App com o Exchange Server 2010 SP3 RU19 ou superior, [orientações aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="d8499-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="d8499-128">Aparelho de Filial Confiável (SBA) com Skype for Business Server 2015 CU6 HF2 ou superior (confirme com seu fornecedor que eles empacotam as atualizações apropriadas e foram disponibilizadas para seu dispositivo)</span><span class="sxs-lookup"><span data-stu-id="d8499-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="d8499-129">Servidor de FilialVivável (SBS) com Skype for Business Server 2015 CU6 HF2 ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="d8499-130">Somente função de borda do Lync Server 2013 , isso acontece porque a função de Borda não tem uma dependência no Windows Fabric 1.0.</span><span class="sxs-lookup"><span data-stu-id="d8499-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="d8499-131">Clientes totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="d8499-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="d8499-132">Lync 2013 (Skype for Business) Desktop Client, MSI e C2R, incluindo Basic [15.0.5023.1000 ou superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="d8499-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="d8499-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 ou superior,](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323)incluindo Básico</span><span class="sxs-lookup"><span data-stu-id="d8499-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="d8499-134">O Clique para Executar do Skype for Business 2016 requer as atualizações de [abril de 2018:](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus)</span><span class="sxs-lookup"><span data-stu-id="d8499-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="d8499-135">Mensal e Semi-Annual Direcionado, 16 \. 0 \. 9126 \. 2152 ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="d8499-136">Semi-Annual e Canal Adiado, 16 \. 0 \. 8431 \. 2242 ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="d8499-137">Skype for Business no Mac 16.15 ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="d8499-138">Skype for Business para iOS e Android 6.19 ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="d8499-139">Salas do Microsoft Teams (anteriormente conhecidas como Sistema de Salas Skype V2 SRS V2) 4.0.64.0 (dezembro de 2018) ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="d8499-140">Atualização do Surface Hub para a edição Team com base no KB4499162 (maio de 2019, com build 15063.1835 do sistema operacional) ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="d8499-141">Skype Web App 2015 CU6 HF2 ou superior (acompanha o Servidor)</span><span class="sxs-lookup"><span data-stu-id="d8499-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="d8499-142">Atualmente sendo investigado</span><span class="sxs-lookup"><span data-stu-id="d8499-142">Currently being investigated</span></span>

- <span data-ttu-id="d8499-143">Painel de Qualidade da Chamada (nova instalação após o TLS 1.0, 1.1 ter sido desabilitado, veja abaixo)\*</span><span class="sxs-lookup"><span data-stu-id="d8499-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="d8499-144">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="d8499-144">Out of scope</span></span>

<span data-ttu-id="d8499-145">Exceto quando anotou, os produtos a seguir não estão no escopo para o TLS 1.0/1.1 desabilitam o suporte e não funcionarão em um ambiente onde o TLS 1.0 e 1.1 foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="d8499-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="d8499-146">Isso significa que, se você ainda utilizar servidores ou clientes fora do escopo, deverá atualizá-los ou removê-los se precisar desabilitar o TLS 1.0/1.1 em qualquer lugar na implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8499-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="d8499-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8499-147">Lync Server 2013</span></span>
- <span data-ttu-id="d8499-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d8499-148">Lync Server 2010</span></span>
- <span data-ttu-id="d8499-149">Windows Server 2008 ou inferior</span><span class="sxs-lookup"><span data-stu-id="d8499-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="d8499-150">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d8499-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="d8499-151">Lync 2013 para celular - iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d8499-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="d8499-152">Cliente Lync "MX" da Windows Store</span><span class="sxs-lookup"><span data-stu-id="d8499-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="d8499-153">Sistema de Sala do Lync (ou seja,</span><span class="sxs-lookup"><span data-stu-id="d8499-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="d8499-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="d8499-154">SRSv1).</span></span> <span data-ttu-id="d8499-155">O LRS atingiu o fim do suporte em 9 de outubro de 2018 e não será atualizado para dar suporte ao TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d8499-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="d8499-156">Todos os clientes do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d8499-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="d8499-157">Lync Phone Edition - orientações [atualizadas aqui.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035)</span><span class="sxs-lookup"><span data-stu-id="d8499-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="d8499-158">Aparelho de Filial Sobrevivência (SBA) baseado em 2013 ou Servidor de Filial Survivable (SBS)</span><span class="sxs-lookup"><span data-stu-id="d8499-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="d8499-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="d8499-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="d8499-160">Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d8499-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="d8499-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="d8499-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="d8499-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d8499-162">Lync Server 2013</span></span>

<span data-ttu-id="d8499-163">O Lync Server 2013 depende do Windows Fabric versão 1.0.</span><span class="sxs-lookup"><span data-stu-id="d8499-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="d8499-164">Na fase de design do Lync Server 2013, o Windows Fabric 1.0 foi escolhido por sua nova arquitetura distribuída atraente e atraente para fornecer replicação, alta disponibilidade e tolerância a falhas.</span><span class="sxs-lookup"><span data-stu-id="d8499-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="d8499-165">Com o tempo, o Skype for Business Server e o Windows Fabric melhoraram significativamente essa arquitetura conjunta com um re-design significativo em versões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="d8499-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="d8499-166">O Skype for Business Server 2015 server atual usa o Windows Fabric 3.0, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="d8499-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="d8499-167">Infelizmente, o Windows Fabric 1.0 **não dá suporte a TLS 1.2.  No entanto, atualizaremos o Lync Server 2013 para trabalhar com o TLS 1.2.**</span><span class="sxs-lookup"><span data-stu-id="d8499-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="d8499-168">Isso estará presente na próxima Atualização Cumulativa do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d8499-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="d8499-169">Estamos fornecendo suporte a TLS 1.2 para habilitar a co-existência, migração, federação e cenários híbridos.</span><span class="sxs-lookup"><span data-stu-id="d8499-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="d8499-170">Se sua organização precisar desabilitar o TLS 1.0 e 1.1, e você usar o Lync Server 2013 no momento, recomendamos que você comece o processo de planejamento, com a possibilidade de ter que fazer uma atualização in-loco ou migrar lado a lado (novos pools, mover usuários) para o Skype for Business Server 2015 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d8499-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="d8499-171">Ou talvez você queira acelerar a migração para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="d8499-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="d8499-172">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="d8499-172">Call Quality Dashboard</span></span>

<span data-ttu-id="d8499-173">O Painel de Qualidade de Chamada Local atualmente depende do TLS 1.0 durante a nova instalação (instalação pela primeira vez em seus ambientes locais).</span><span class="sxs-lookup"><span data-stu-id="d8499-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="d8499-174">No momento, estamos investigando esse problema e planejamos lançar uma correção em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="d8499-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="d8499-175">Se você estiver planejando instalar o CQD e também desabilitar o TLS 1.0, recomendamos que você conclua a instalação do CQD primeiro e continue com a desabilitação do TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="d8499-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="d8499-176">Gerenciador SDN do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d8499-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="d8499-177">O Gerenciador de SDN do Skype for Business usando o SQL tem uma dependência do TLS 1.0 durante a nova instalação.</span><span class="sxs-lookup"><span data-stu-id="d8499-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="d8499-178">Se você planeja instalar o Gerenciador de SDN do Skype for Business usando um banco de dados do SQL e também desabilitar o TLS 1.0, recomendamos concluir o Gerenciador de SDN do Skype for Business primeiro e, em seguida, continuar com a desabilitação do TLS 1.0.</span><span class="sxs-lookup"><span data-stu-id="d8499-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="d8499-179">Caso o TLS 1.0 tenha sido desabilitado antes da instalação, você deve habilitar temporariamente o TLS 1.0 de volta no servidor back-end do SQL Server que será usado para hospedar o banco de dados SQL do Gerenciador de SDN do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d8499-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="d8499-180">Dispositivos de terceiros</span><span class="sxs-lookup"><span data-stu-id="d8499-180">Third-party devices</span></span>

<span data-ttu-id="d8499-181">Em dispositivos de terceiros, como telefones 3PIP, Videoconferência, Proxies Reversos e Balanceadores de Carga, certifique-se de validar a capacidade de suporte do TLS 1.2, teste cuidadosamente e contate o fornecedor, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d8499-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="d8499-182">Considerações de federação ao desabilitar o TLS 1.0/1.1 em servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="d8499-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="d8499-183">Você deve planejar cuidadosamente e considerar o impacto da desabilitação do TLS 1.0/1.1 em seus servidores de Borda.</span><span class="sxs-lookup"><span data-stu-id="d8499-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="d8499-184">Depois que o TLS 1.0 e 1.1 são desabilitados, você pode descobrir que outras organizações não podem mais federar com sua organização.</span><span class="sxs-lookup"><span data-stu-id="d8499-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="d8499-185">Você pode optar por manter o TLS 1.0/1.1 habilitado em seus servidores de Borda para manter a compatibilidade com versões mais antigas com sistemas externos não patches (SfB 2015, Lync 2013) ou mais antigos (2010).</span><span class="sxs-lookup"><span data-stu-id="d8499-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="d8499-186">A Microsoft não pode fornecer conselhos ou recomendações sobre se a rede de Borda (ou qualquer rede) está ou não no padrão PCI; que deve ser determinado pela empresa individual.</span><span class="sxs-lookup"><span data-stu-id="d8499-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="d8499-187">O Skype for Business Online é capaz de ter o TLS 1.2 hoje, portanto, não se espera nenhum impacto no híbrido/federação com o Online.</span><span class="sxs-lookup"><span data-stu-id="d8499-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="d8499-188">PIC (Conectividade pública de IM) para o serviço de consumidor do Skype: não esperamos que a desabilitação do TLS 1.0/1.1 acarta a conectividade do [Skype;](../../deploy/deploy-skype-connectivity.md) Os Gateways de PIC da Microsoft já têm capacidade para TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d8499-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="d8499-189">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="d8499-189">Prerequisites and process</span></span>

<span data-ttu-id="d8499-190">Exceto quando mencionado acima, uma vez que os TLS 1.0 e 1.1 estão desabilitados para servidores fora do escopo, os clientes e dispositivos funcionarão mais corretamente ou de forma alguma.</span><span class="sxs-lookup"><span data-stu-id="d8499-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="d8499-191">Isso pode significar que você precisa pausar e aguardar por orientações atualizadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d8499-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="d8499-192">Quando tiver a satisfação de atender a todos os requisitos e tiver um plano para solucionar lacunas, prossiga.</span><span class="sxs-lookup"><span data-stu-id="d8499-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="d8499-193">Em um nível alto, enquanto o Skype for Business Server 2019 está pronto para o procedimento durante a instalação, o Skype for Business Server 2015 exigirá que você instale a CU9, aplicando atualizações de pré-requisitos ao .NET e SQL, implantando chaves de registro de pré-requisitos e, finalmente, uma série separada de atualizações de configuração do sistema operacional (ou seja, desabilitando o TLS 1.0 e 1.1 por meio da importação de arquivos do Registro).</span><span class="sxs-lookup"><span data-stu-id="d8499-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="d8499-194">É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo o Skype for Business Server 2015 CU6 HF2, antes de desabilitar o TLS 1.0 e 1.1 em qualquer servidor em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d8499-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="d8499-195">Todos os servidores do Skype for Business, incluindo a função de Borda e back-end sql, exigem as atualizações.</span><span class="sxs-lookup"><span data-stu-id="d8499-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="d8499-196">Verifique também se todos os clientes com suporte (no escopo) foram atualizados para as versões mínimas necessárias.</span><span class="sxs-lookup"><span data-stu-id="d8499-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="d8499-197">Não se esqueça de atualizar as estações de trabalho de gerenciamento também.</span><span class="sxs-lookup"><span data-stu-id="d8499-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="d8499-198">Queremos seguir a ordem usual de operações de "dentro para fora" para atualizar os servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d8499-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="d8499-199">Trate pools de Diretores, Chat Persistente e Pools Emparelhados da mesma maneira que faria normalmente.</span><span class="sxs-lookup"><span data-stu-id="d8499-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="d8499-200">A ordem e os métodos de atualização são abordados [aqui](topology.md) e [aqui.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="d8499-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="d8499-201">Processo de alto nível</span><span class="sxs-lookup"><span data-stu-id="d8499-201">High-level process</span></span>

1. <span data-ttu-id="d8499-202">Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="d8499-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="d8499-203">Fazer o back up e preservar uma cópia do Registro exportado em cada servidor individual a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="d8499-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="d8499-204">Não é possível compartilhar registros entre servidores; eles contêm chaves exclusivas baseadas em máquina.</span><span class="sxs-lookup"><span data-stu-id="d8499-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="d8499-205">Atualize todos os servidores do Skype for Business 2015 para CU9 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d8499-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="d8499-206">Para o Skype for Business Server 2019, atualize para CU1 ou superior.</span><span class="sxs-lookup"><span data-stu-id="d8499-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="d8499-207">Instale todos os pré-requisitos em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="d8499-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="d8499-208">Implantar chaves do Registro de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="d8499-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="d8499-209">Certifique-se de que todos os clientes no escopo sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="d8499-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="d8499-210">Desabilite o TLS 1.0 e 1.1 por meio da importação do Registro.</span><span class="sxs-lookup"><span data-stu-id="d8499-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="d8499-211">Valide se as cargas de trabalho estão funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="d8499-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="d8499-212">Se problemas são encontrados, solução de problemas ou</span><span class="sxs-lookup"><span data-stu-id="d8499-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="d8499-213">Restaurar o Registro da etapa 2 para reabilitar o TLS 1.0 e 1.1</span><span class="sxs-lookup"><span data-stu-id="d8499-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="d8499-214">Valide que apenas o TLS 1.2 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="d8499-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="d8499-215">Instalar pré-requisitos em todos os servidores</span><span class="sxs-lookup"><span data-stu-id="d8499-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="d8499-216">A atualização de dependência extensiva é necessária antes de você começar a desabilitar o TLS 1.0 e 1.1 no nível do sistema operacional em suas implantações do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d8499-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="d8499-217">A seguir estão as versões mínimas que podem dar suporte a TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d8499-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="d8499-218">Implante todas as atualizações de pré-requisitos em todos os servidores do Skype for Business em seu ambiente antes de começar a desabilitar o TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="d8499-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="d8499-219">Skype for Business Server 2015 CU9 6.0.9319.548 (maio de 2019) ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="d8499-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) ou superior com SchUseStrongCrypto habilitado no Registro (fornecido abaixo)</span><span class="sxs-lookup"><span data-stu-id="d8499-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="d8499-221">O SQL deve ser atualizado em todos os servidores e back-ends do Skype for Business 2015.</span><span class="sxs-lookup"><span data-stu-id="d8499-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="d8499-222">Atualize primeiro os back-ends SQL do pool do Enterprise Edition e, em seguida, seus respectivos FEs.</span><span class="sxs-lookup"><span data-stu-id="d8499-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="d8499-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)ou superior / SQL Server 2012 SP2 + CU16 ou superior / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)ou superior / SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d8499-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="d8499-224">SQL Server Native Client para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="d8499-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="d8499-225">[Microsoft ODBC Driver 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)ou superior</span><span class="sxs-lookup"><span data-stu-id="d8499-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="d8499-226">Objetos de Gerenciamento Compartilhados para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d8499-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="d8499-227">SQLSysClrTypes para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d8499-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="d8499-228">Etapas básicas para instalar os pré-requisitos, em ordem recomendada de operações</span><span class="sxs-lookup"><span data-stu-id="d8499-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="d8499-229">Instale a atualização do Skype for Business Server CU9 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="d8499-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="d8499-230">Instale a atualização nos componentes usando o atualizador.</span><span class="sxs-lookup"><span data-stu-id="d8499-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="d8499-231">Atualize os bancos de dados de acordo com os procedimentos documentados.</span><span class="sxs-lookup"><span data-stu-id="d8499-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="d8499-232">Para o Skype for Business Server 2015, consulte kb [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="d8499-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="d8499-233">Valide a funcionalidade do produto na implantação antes de continuar com quaisquer outras alterações.</span><span class="sxs-lookup"><span data-stu-id="d8499-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="d8499-234">Baixe o Instalador Offline do .NET 4.7.</span><span class="sxs-lookup"><span data-stu-id="d8499-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="d8499-235">Referência: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="d8499-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="d8499-236">Verifique se os serviços do Skype for Business Server 2015 foram interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d8499-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="d8499-237">Referência: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="d8499-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="d8499-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d8499-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="d8499-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d8499-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="d8499-240">Execute o pacote do instalador.</span><span class="sxs-lookup"><span data-stu-id="d8499-240">Run the installer package.</span></span>
    7. <span data-ttu-id="d8499-241">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="d8499-241">Reboot the server.</span></span>
3. <span data-ttu-id="d8499-242">Atualize o SQL Express 2014 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="d8499-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="d8499-243">Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="d8499-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="d8499-244">Baixar o SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="d8499-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="d8499-245">Referência: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="d8499-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="d8499-246">Copie a mídia de instalação em uma pasta no servidor (ex: C:\01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="d8499-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="d8499-247">Garantir que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end</span><span class="sxs-lookup"><span data-stu-id="d8499-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="d8499-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d8499-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="d8499-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d8499-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="d8499-250">Abra um Prompt de Comando do Administrador e atualize todos os componentes e instâncias instalados</span><span class="sxs-lookup"><span data-stu-id="d8499-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="d8499-251">Exemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span><span class="sxs-lookup"><span data-stu-id="d8499-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="d8499-252">Atualize o SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="d8499-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="d8499-253">Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="d8499-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="d8499-254">Baixar de [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="d8499-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="d8499-255">Verifique se os serviços do Skype for Business Server 2015 foram interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d8499-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="d8499-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="d8499-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="d8499-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d8499-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="d8499-258">Interromper a execução das instâncias SQL instaladas</span><span class="sxs-lookup"><span data-stu-id="d8499-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="d8499-259">Por ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d8499-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="d8499-260">Por ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d8499-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="d8499-261">Ex (Somente Standard Edition): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="d8499-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="d8499-262">Instale a atualização.</span><span class="sxs-lookup"><span data-stu-id="d8499-262">Install the update.</span></span>
5. <span data-ttu-id="d8499-263">Atualize o driver ODBC 11 para SQL Server para incluir suporte para TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="d8499-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="d8499-264">Baixe [o driver ODBC 11 para SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="d8499-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="d8499-265">Verifique se os serviços do Skype for Business Server 2015 foram interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="d8499-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="d8499-266">Exemplo (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="d8499-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="d8499-267">Exemplo (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="d8499-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="d8499-268">Instale a atualização.</span><span class="sxs-lookup"><span data-stu-id="d8499-268">Install the update.</span></span>
6. <span data-ttu-id="d8499-269">Implantar chaves do Registro de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="d8499-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="d8499-270">Chaves de registro de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="d8499-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="d8499-271">Copie/copie/copie o teste a seguir no Bloco de Notas e renomeie TLSPreReq.reg ou um nome de sua escolha e importe:</span><span class="sxs-lookup"><span data-stu-id="d8499-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="d8499-272">Para back-ends do SQL para Pools Enterprise Edition, os pré-requisitos e a desabilitação do TLS devem ser tratados como qualquer atualização do SQL ou do sistema operacional; consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="d8499-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="d8499-273">Embora as etapas de desabilitação do aplicativo de pré-requisito e do TLS possam ser combinadas, recomendamos que todos os pré-requisitos sejam aplicados antes de prosseguir com a desabilitação do TLS 1.0 e 1.1 no nível do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d8499-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="d8499-274">A melhor abordagem seria preparar o ambiente implantando todos os pré-requisitos, validando que as cargas de trabalho funcionem corretamente e conforme o esperado e, em seguida, continuar com o TLS 1.0/1.1 desabilitar posteriormente.</span><span class="sxs-lookup"><span data-stu-id="d8499-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="d8499-275">Desabilitar o TLS 1.0 e 1.1 por meio da importação do Registro</span><span class="sxs-lookup"><span data-stu-id="d8499-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="d8499-276">Antes de prosseguir com as próximas etapas, certifique-se de ter concluído todos os *pré-requisitos* e atualizado os Servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d8499-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="d8499-277">Copie o texto a seguir em um arquivo do Bloco de Notas e renomeie-o **como TLSDisable.reg:**</span><span class="sxs-lookup"><span data-stu-id="d8499-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="d8499-278">Importe o arquivo .reg em cada servidor que você deseja desabilitar o TLS 1.0 e 1.1.</span><span class="sxs-lookup"><span data-stu-id="d8499-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="d8499-279">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="d8499-279">Reboot the server.</span></span> <span data-ttu-id="d8499-280">Depois que os serviços voltarem a ficar online, vá para o próximo servidor.</span><span class="sxs-lookup"><span data-stu-id="d8499-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="d8499-281">A abordagem para Pools Enterprise Edition é a mesma que você faria para qualquer atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="d8499-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="d8499-282">Você deve ter notado que estamos fazendo mais do que desabilitar apenas o TLS 1.0 e 1.1 aqui.</span><span class="sxs-lookup"><span data-stu-id="d8499-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="d8499-283">Estamos dando suporte à reorganização do Cipher Suite (conforme mostrado acima) e à desabilitação de algumas codificações fracas mais antigas.</span><span class="sxs-lookup"><span data-stu-id="d8499-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="d8499-284">Esta é a primeira vez que oficialmente suportamos essas alterações no SCHANNEL e na API de Criptografia no Skype for Business Server, e é importante observar que essas alterações são as únicas que suportamos e testamos no momento.</span><span class="sxs-lookup"><span data-stu-id="d8499-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="d8499-285">Podemos considerar configurações adicionais no futuro, mas, por enquanto, não modifique o arquivo de importação do Registro em sua implementação.</span><span class="sxs-lookup"><span data-stu-id="d8499-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="d8499-286">Validar se as cargas de trabalho estão funcionando conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="d8499-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="d8499-287">Depois que o TLS 1.0 e 1.1 tiver sido desabilitado em seu ambiente, verifique se todas as cargas de trabalho principais estão funcionando conforme o esperado, como presença de IM &, chamadas P2P, Enterprise Voice etc.</span><span class="sxs-lookup"><span data-stu-id="d8499-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="d8499-288">**Validar se apenas o TLS 1.2 está sendo usado**</span><span class="sxs-lookup"><span data-stu-id="d8499-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="d8499-289">Faça com que sua equipe de segurança execute uma nova auditoria do tráfego do Skype for Business para garantir que os protocolos mais antigos TLS 1.0 e 1.1 não estão mais em uso.</span><span class="sxs-lookup"><span data-stu-id="d8499-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="d8499-290">Como alternativa, você pode usar o Internet Explorer para testar conexões TLS com serviços Web do Skype for Business Server 2015 após a desabilitação do TLS 1.0 e do TLS 1.1.</span><span class="sxs-lookup"><span data-stu-id="d8499-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="d8499-291">Iniciar o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="d8499-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="d8499-292">Selecione **Ferramentas Opções** da  >  **Internet.**</span><span class="sxs-lookup"><span data-stu-id="d8499-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="d8499-293">Selecione a **guia** Avançado.</span><span class="sxs-lookup"><span data-stu-id="d8499-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="d8499-294">Em **Configurações,** role até a parte inferior.</span><span class="sxs-lookup"><span data-stu-id="d8499-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="d8499-295">Verifique se o TLS 1.0, o TLS 1.1 e o TLS 1.2 estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="d8499-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="d8499-296">Procure a URL do Serviço Web Interno do seu pool do SfB 2015 (deve se conectar com êxito).</span><span class="sxs-lookup"><span data-stu-id="d8499-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="d8499-297">Volte para o Internet Explorer e desabilite a opção **Usar somente TLS 1.2.**</span><span class="sxs-lookup"><span data-stu-id="d8499-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="d8499-298">Navegue novamente pela URL do Serviço Web Interno do pool do SfB 2015 (deve não conseguir se conectar).</span><span class="sxs-lookup"><span data-stu-id="d8499-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="d8499-300">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="d8499-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="d8499-301">Como alguns pré-requisitos de dependência são necessários para dar suporte ao TLS 1.2 no Skype for Business Server 2015, a instalação de mídia RTM falhará em qualquer sistema em que o TLS 1.0 e 1.1 tenham sido desabilitados.</span><span class="sxs-lookup"><span data-stu-id="d8499-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="d8499-302">**Implantação de novos servidores Standard Edition ou pools enterprise edition depois que o TLS 1.0 e 1.1 foram desabilitados em seu ambiente.**</span><span class="sxs-lookup"><span data-stu-id="d8499-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="d8499-303">**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="d8499-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="d8499-304">Observe que estamos atualizando o SmartSetup para acomodar os binários SQL atualizados em uma atualização automática futura e atualizaremos este artigo no futuro.</span><span class="sxs-lookup"><span data-stu-id="d8499-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="d8499-305">**Opção 2:** Pré-instalar instâncias LOCAIS do SQL (RTCLOCAL e LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="d8499-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="d8499-306">Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64.exe) para a pasta local no FE.</span><span class="sxs-lookup"><span data-stu-id="d8499-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="d8499-307">Digamos que o caminho da pasta <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="d8499-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="d8499-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="d8499-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="d8499-309">Crie a instância SQL RTCLOCAL executando o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="d8499-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d8499-310">Aguarde até SQLEXPR_x64.exe terminar antes de prosseguir:</span><span class="sxs-lookup"><span data-stu-id="d8499-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="d8499-311">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span><span class="sxs-lookup"><span data-stu-id="d8499-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="d8499-312">Crie a instância SQL LYNCLOCAL executando o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="d8499-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="d8499-313">Aguarde até SQLEXPR_x64.exe terminar antes de prosseguir para a próxima etapa:</span><span class="sxs-lookup"><span data-stu-id="d8499-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="d8499-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span><span class="sxs-lookup"><span data-stu-id="d8499-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="d8499-315">Execute a configuração do Skype for Business Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="d8499-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="d8499-316">Siga as etapas restantes da seção de pré-requisitos acima.</span><span class="sxs-lookup"><span data-stu-id="d8499-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="d8499-317">**Opção 3:** Você também pode substituir manualmente binários em um diretório de mídia de instalação local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d8499-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="d8499-318">Instalar pré-requisitos para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d8499-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="d8499-319">Instale o .NET 4.7:</span><span class="sxs-lookup"><span data-stu-id="d8499-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="d8499-320">**Observação:** Apresentamos primeiro o suporte para o .NET 4.7 no Skype for Business Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="d8499-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="d8499-321">Portanto, nas etapas posteriores abaixo, atualizaremos os Componentes Principais antes da instalação principal.</span><span class="sxs-lookup"><span data-stu-id="d8499-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="d8499-322">Baixe: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="d8499-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="d8499-323">Referência: [Software que deve ser instalado antes de uma implantação do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="d8499-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="d8499-324">Copie arquivos/pastas ISO:</span><span class="sxs-lookup"><span data-stu-id="d8499-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="d8499-325">Com o ISO do Skype for Business Server 2015 anexado, abra o diretório raiz da unidade em que ele está anexado como (Ex: D: \) no Explorador de Arquivos.</span><span class="sxs-lookup"><span data-stu-id="d8499-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="d8499-326">Copie todas as pastas e arquivos para uma pasta em um disco local (Ex: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="d8499-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="d8499-327">**Observação:** Antes de instalar componentes, alguns arquivos precisarão ser atualizados para dar suporte ao TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="d8499-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="d8499-328">Substitua pacotes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="d8499-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="d8499-329">Substitua os pacotes MSI e EXE existentes na pasta /Setup/amd64/ da mídia de instalação no computador local.</span><span class="sxs-lookup"><span data-stu-id="d8499-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="d8499-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="d8499-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="d8499-331">Renomeie para SQLEXPR_x64 no computador local e substitua o arquivo existente na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="d8499-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d8499-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="d8499-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="d8499-333">**Observação:** Renomeie isso se necessário para sqlncli.msi e substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="d8499-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d8499-334">Objetos de gerenciamento SQL: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d8499-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d8499-335">**Observação:** O feature pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="d8499-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d8499-336">Selecione para baixar SharedManagementObjects.msi somente.</span><span class="sxs-lookup"><span data-stu-id="d8499-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="d8499-337">**Observação:** Substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="d8499-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="d8499-338">Tipos DE CLR SQL: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="d8499-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="d8499-339">**Observação:** O feature pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="d8499-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="d8499-340">Selecione para baixar CQLSysClrTypes.msi somente</span><span class="sxs-lookup"><span data-stu-id="d8499-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="d8499-341">**Observação:** substitua o arquivo existente que existe na pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="d8499-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="d8499-342">Instalar componentes principais:</span><span class="sxs-lookup"><span data-stu-id="d8499-342">Install Core Components:</span></span> 
    - <span data-ttu-id="d8499-343">Execute Setup.exe da pasta Setup/amd64/ da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="d8499-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="d8499-344">Siga as instruções para instalar componentes principais</span><span class="sxs-lookup"><span data-stu-id="d8499-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="d8499-345">Feche os componentes principais.</span><span class="sxs-lookup"><span data-stu-id="d8499-345">Close Core Components.</span></span>
6. <span data-ttu-id="d8499-346">Atualizar componentes principais:</span><span class="sxs-lookup"><span data-stu-id="d8499-346">Update Core Components:</span></span> 
    - <span data-ttu-id="d8499-347">Baixe o Instalador de Atualização do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d8499-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="d8499-348">Execute o instalador para atualizar os Componentes Principais e instalar os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="d8499-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="d8499-349">**Observação:** A partir do lançamento do CU6HF2, o recurso de atualização automática atualmente só será instalado até a CU6.</span><span class="sxs-lookup"><span data-stu-id="d8499-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="d8499-350">Portanto, o atualizador deve ser executado separadamente para atualizar os Componentes Principais para 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="d8499-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="d8499-351">Referência: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="d8499-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="d8499-352">Instalar Ferramentas Administrativas (Opcional):</span><span class="sxs-lookup"><span data-stu-id="d8499-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="d8499-353">Isso instalará o Microsoft SQL Server 2012 Native Client, o SQL Server 2014 Management Objects (x64) e o Microsoft System CLR Types para SQL Server 2014 (x64) usando os arquivos atualizados.</span><span class="sxs-lookup"><span data-stu-id="d8499-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="d8499-354">Além disso, o Construtor de Topologias e o Painel de Controle do Skype for Business Server 2015 estarão disponíveis no computador local.</span><span class="sxs-lookup"><span data-stu-id="d8499-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="d8499-355">Instalar o Armazenamento de Configuração Local (Etapa 1):</span><span class="sxs-lookup"><span data-stu-id="d8499-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="d8499-356">Abra o Assistente de Implantação, clique em Instalar  ou Atualizar o Sistema do Skype for Business Server e clique em Executar na Etapa 1: Instalar o Armazenamento de Configuração Local.</span><span class="sxs-lookup"><span data-stu-id="d8499-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="d8499-357">Clique **em Próximo** na caixa de diálogo Instalar Armazenamento de **Configuração** Local.</span><span class="sxs-lookup"><span data-stu-id="d8499-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="d8499-358">![Instalar a caixa de diálogo Do Armazenamento de Configuração Local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="d8499-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="d8499-359">Revise os resultados e verifique se o Status da Tarefa foi Concluído.</span><span class="sxs-lookup"><span data-stu-id="d8499-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="d8499-360">Revise o arquivo de log resultante clicando em **Exibir Log.**</span><span class="sxs-lookup"><span data-stu-id="d8499-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="d8499-361">![O status da tarefa aparece como Concluído](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="d8499-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="d8499-362">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d8499-362">Click **Finish**.</span></span>
9. <span data-ttu-id="d8499-363">Configurar ou remover componentes do Skype for Business Server (Etapa 2):</span><span class="sxs-lookup"><span data-stu-id="d8499-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="d8499-364">Abra o Assistente de Implantação, clique em Instalar  ou Atualizar o **Sistema do Skype for Business Server** e clique em Executar na Etapa 2: Configurar ou Remover Componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="d8499-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="d8499-365">Clique **em Next** na caixa de diálogo Configurar Componentes do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8499-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="d8499-366">![a janela Configurar Componentes do Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="d8499-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="d8499-367">Revise o log usando Exibir Log e valide se a instalação foi concluída sem problemas.</span><span class="sxs-lookup"><span data-stu-id="d8499-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="d8499-368">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d8499-368">Click **Finish**.</span></span>
10. <span data-ttu-id="d8499-369">Prossiga com a instalação e a configuração adicionais conforme necessário (você pode retomar os procedimentos de instalação normais neste ponto).</span><span class="sxs-lookup"><span data-stu-id="d8499-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
