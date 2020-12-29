---
title: Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: Prepare-se e implemente a desabilitação de TLS 1,0 e 1,1 em seus ambientes.'
ms.openlocfilehash: 06ebc3f5821e8daa1c80633b25140a852f72097d
ms.sourcegitcommit: 4143ce9bd62e67ba09f89cedadfd65803bda5361
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/28/2020
ms.locfileid: "49734289"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="fb925-103">Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fb925-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="fb925-104">O objetivo deste artigo é fornecer as diretrizes necessárias para preparar e implementar a desabilitação de TLS 1,0 e 1,1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="fb925-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="fb925-105">Esse processo requer planejamento e preparação abrangentes.</span><span class="sxs-lookup"><span data-stu-id="fb925-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="fb925-106">Revise cuidadosamente todas as informações deste artigo ao fazer seu plano para desabilitar o TLS 1,0 e 1,1 para sua organização.</span><span class="sxs-lookup"><span data-stu-id="fb925-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="fb925-107">Observe que há muitas dependências externas e condições de conectividade que podem ser impactadas desabilitando o TLS 1.0/1.1, portanto, o planejamento e o teste extensivos são garantidos.</span><span class="sxs-lookup"><span data-stu-id="fb925-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="fb925-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="fb925-108">In this article</span></span>

- [<span data-ttu-id="fb925-109">Plano de fundo e escopo</span><span class="sxs-lookup"><span data-stu-id="fb925-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="fb925-110">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="fb925-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="fb925-111">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="fb925-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="fb925-112">Histórico</span><span class="sxs-lookup"><span data-stu-id="fb925-112">Background</span></span>

<span data-ttu-id="fb925-113">Os principais drivers de fornecimento de TLS 1,0 e 1,1 desabilitar o suporte para o Skype for Business Server no local são os padrões de segurança do setor de cartão de pagamento PCI e os requisitos de padrões federais de processamento de informações.</span><span class="sxs-lookup"><span data-stu-id="fb925-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="fb925-114">É [possível encontrar mais](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls)informações sobre os requisitos de PCI.</span><span class="sxs-lookup"><span data-stu-id="fb925-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="fb925-115">A Microsoft não pode fornecer orientações sobre a necessidade ou não de sua organização para cumprir estes ou outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="fb925-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="fb925-116">Você deve determinar se é necessário desabilitar o TLS 1,0 e/ou 1,1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="fb925-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="fb925-117">A Microsoft produziu um White paper sobre o TLS disponível [aqui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)e também recomendamos a leitura em segundo plano disponível neste [blog do Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="fb925-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="fb925-118">Escopo de capacidade de suporte</span><span class="sxs-lookup"><span data-stu-id="fb925-118">Supportability Scope</span></span>

<span data-ttu-id="fb925-119">O *escopo* se refere aos limites de capacidade de suporte.</span><span class="sxs-lookup"><span data-stu-id="fb925-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="fb925-120">*Totalmente testado e com suporte* significa que oferecemos suporte para a desabilitação de TLS 1,0 e 1,1 para as versões de produto listadas.</span><span class="sxs-lookup"><span data-stu-id="fb925-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="fb925-121">*Sendo investigado no momento* significa apenas isso; Estamos investigando ativamente os produtos em escopo para habilitar o suporte a TLS.</span><span class="sxs-lookup"><span data-stu-id="fb925-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="fb925-122">*Fora do escopo* significa que essas versões do produto não dão suporte à desabilitação de TLS 1,0 ou 1,1 e não funcionarão, com exceções anotadas.</span><span class="sxs-lookup"><span data-stu-id="fb925-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="fb925-123">Servidores totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="fb925-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="fb925-124">Skype for Business Server 2019 CU1 17.0.2046.123 (junho de 2019) ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="fb925-125">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior no Windows Server 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização substituindo), 2012 R2 ou 2016.</span><span class="sxs-lookup"><span data-stu-id="fb925-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="fb925-126">Atualizado no local o Skype for Business Server 2015, com o CU9 6.0.9319.548 (maio de 2019) ou superior no Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização de substituição) ou 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="fb925-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="fb925-127">Conectividade do Exchange e Outlook Web App com o Exchange Server 2010 SP3 RU19 ou superior, orientação [aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="fb925-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="fb925-128">Aparelho de filial persistente (SBA) com o Skype for Business Server 2015 CU6 HF2 ou superior (confirme com seu fornecedor que eles empacotaram as atualizações apropriadas e foram disponibilizados para seu dispositivo)</span><span class="sxs-lookup"><span data-stu-id="fb925-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropriate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="fb925-129">Servidor de ramificação persistente (SBS) com o Skype for Business Server 2015 CU6 HF2 ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="fb925-130">**Somente função de borda** do Lync Server 2013, isso ocorre porque a função de borda não tem uma dependência no Windows Fabric 1,0.</span><span class="sxs-lookup"><span data-stu-id="fb925-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="fb925-131">Clientes totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="fb925-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="fb925-132">Lync 2013 (Skype for Business) Desktop Client, MSI e C2R, incluindo o [15.0.5023.1000 básico ou superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="fb925-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="fb925-133">Cliente de área de trabalho do Skype for Business 2016, MSI [16.0.4678.1000 ou superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluindo básico</span><span class="sxs-lookup"><span data-stu-id="fb925-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="fb925-134">Skype for Business 2016 clique para executar exigir as atualizações de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="fb925-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="fb925-135">Mensal e Semi-Annual direcionados, 16 \. 0 \. 9126 \. 2152 ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="fb925-136">Canal Semi-Annual e adiado, 16 \. 0 \. 8431 \. 2242 ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="fb925-137">Skype for Business no Mac 16,15 ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="fb925-138">Skype for Business para iOS e Android 6,19 ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="fb925-139">Salas do Microsoft Teams (anteriormente conhecido como Skype Room System v2 SRS v2) 4.0.64.0 (dezembro de 2018) ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="fb925-140">Atualização do Surface Hub para Team Edition com base no KB4499162 (maio de 2019, compilação de sistema operacional 15063,1835) ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="fb925-141">Skype Web App 2015 CU6 HF2 ou superior (fornecido com o servidor)</span><span class="sxs-lookup"><span data-stu-id="fb925-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="fb925-142">Sendo investigado no momento</span><span class="sxs-lookup"><span data-stu-id="fb925-142">Currently being investigated</span></span>

- <span data-ttu-id="fb925-143">Painel de qualidade de chamada (nova instalação após TLS 1,0, 1,1 foram desabilitadas, veja abaixo) \*</span><span class="sxs-lookup"><span data-stu-id="fb925-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="fb925-144">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="fb925-144">Out of scope</span></span>

<span data-ttu-id="fb925-145">Exceto onde observado, os seguintes produtos não estão no escopo para TLS 1.0/1.1 desabilitam o suporte e não funcionarão em um ambiente em que o TLS 1,0 e 1,1 foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="fb925-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="fb925-146">O que isso significa: se você ainda utilizar servidores ou clientes fora do escopo, deverá atualizar ou remover estes se precisar desabilitar o TLS 1.0/1.1 em qualquer lugar em sua implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb925-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="fb925-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb925-147">Lync Server 2013</span></span>
- <span data-ttu-id="fb925-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fb925-148">Lync Server 2010</span></span>
- <span data-ttu-id="fb925-149">Windows Server 2008 ou inferior</span><span class="sxs-lookup"><span data-stu-id="fb925-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="fb925-150">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="fb925-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="fb925-151">Lync 2013 para Mobile-iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="fb925-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="fb925-152">Cliente da Windows Store "MX" do Lync</span><span class="sxs-lookup"><span data-stu-id="fb925-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="fb925-153">Sistema de salas do Lync (conhecido como</span><span class="sxs-lookup"><span data-stu-id="fb925-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="fb925-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="fb925-154">SRSv1).</span></span> <span data-ttu-id="fb925-155">O LRS atingiu o fim do suporte em 9 de outubro de 2018 e não será atualizado para suportar o TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="fb925-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="fb925-156">Todos os clientes do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="fb925-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="fb925-157">Lync Phone Edition – orientações atualizadas [aqui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="fb925-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="fb925-158">SBA (aparelho de filial persistente com base em 2013) ou servidor de filial persistente (SBS)</span><span class="sxs-lookup"><span data-stu-id="fb925-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="fb925-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="fb925-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="fb925-160">Skype for Business para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="fb925-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="fb925-161">Exceptions</span><span class="sxs-lookup"><span data-stu-id="fb925-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="fb925-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb925-162">Lync Server 2013</span></span>

<span data-ttu-id="fb925-163">O Lync Server 2013 tem uma dependência no Windows Fabric versão 1,0.</span><span class="sxs-lookup"><span data-stu-id="fb925-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="fb925-164">Na fase de design do Lync Server 2013, o Windows Fabric 1,0 foi escolhido por sua arquitetura distribuída e nova, para fornecer replicação, alta disponibilidade e tolerância a falhas.</span><span class="sxs-lookup"><span data-stu-id="fb925-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="fb925-165">Com o tempo, tanto o Skype for Business Server quanto o Windows Fabric melhoraram muito essa arquitetura conjunta com um novo design significativo nas versões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="fb925-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="fb925-166">O servidor atual do Skype for Business 2015 usa o Windows Fabric 3,0, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="fb925-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="fb925-167">Infelizmente, o Windows Fabric 1,0 não **oferece suporte a TLS 1,2.  No entanto, atualizaremos o Lync Server 2013 para funcionar com TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="fb925-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="fb925-168">Isso será disponibilizado na próxima atualização cumulativa para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fb925-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="fb925-169">Estamos fornecendo suporte a TLS 1,2 para habilitar a coexistência, migração, Federação e cenários híbridos.</span><span class="sxs-lookup"><span data-stu-id="fb925-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="fb925-170">Se sua organização for necessária para desabilitar o TLS 1,0 e 1,1, e você usar o Lync Server 2013 no momento, recomendamos que você inicie o processo de planejamento, com a possibilidade de que você possa ter a atualização in-loco ou migrar lado a lado (novos pools, mover usuários) para o Skype for Business Server 2015 ou superior.</span><span class="sxs-lookup"><span data-stu-id="fb925-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="fb925-171">Ou talvez você queira acelerar a migração para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="fb925-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="fb925-172">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="fb925-172">Call Quality Dashboard</span></span>

<span data-ttu-id="fb925-173">No momento, o painel de qualidade de chamada local tem uma dependência no TLS 1,0 durante a nova instalação (primeira vez em que é feita a instalação em seus ambientes locais).</span><span class="sxs-lookup"><span data-stu-id="fb925-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="fb925-174">No momento, estamos investigando esse problema e planejamos lançar uma correção em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="fb925-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="fb925-175">Se você estiver planejando instalar o CQD e também desabilitar o TLS 1,0, recomendamos concluir a instalação do CQD primeiro e, em seguida, prosseguir com o TLS 1,0 desabilitando.</span><span class="sxs-lookup"><span data-stu-id="fb925-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="skype-for-business-sdn-manager"></a><span data-ttu-id="fb925-176">Gerenciador de SDN do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="fb925-176">Skype for Business SDN Manager</span></span>

<span data-ttu-id="fb925-177">O Gerenciador de SDN do Skype for Business usando SQL um banco de dados tem uma dependência no TLS 1,0 durante a nova instalação.</span><span class="sxs-lookup"><span data-stu-id="fb925-177">Skype for Business SDN Manager using SQL a database has a dependency on TLS 1.0 during new install.</span></span> <span data-ttu-id="fb925-178">Se estiver planejando instalar o Gerenciador de SDN do Skype for Business usando o SQL a Database e também desabilitar o TLS 1,0, recomendamos que você conclua primeiro o Gerenciador de SDN do Skype for Business e, em seguida, prossiga com o TLS 1,0 desabilitando.</span><span class="sxs-lookup"><span data-stu-id="fb925-178">If you are planning to install Skype for Business SDN Manager using SQL a database and also disable TLS 1.0, we recommend that you complete Skype for Business SDN Manager first, and then proceed with TLS 1.0 disabling.</span></span> <span data-ttu-id="fb925-179">Caso TLS 1,0 foi desabilitado antes da instalação, você deve 1,0 habilitá-lo temporariamente no servidor back-end do SQL Server que será usado para hospedar o banco de dados SQL do Gerenciador de SDN do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fb925-179">In case TLS 1.0 was disabled prior to installation, you should temporarily enabled TLS 1.0 back in SQL Server backend server that will be used to host Skype for Business SDN Manager SQL database.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="fb925-180">Dispositivos de terceiros</span><span class="sxs-lookup"><span data-stu-id="fb925-180">Third-party devices</span></span>

<span data-ttu-id="fb925-181">Em dispositivos de terceiros, como telefones 3PIP, conferência de vídeo, proxies reverso e balanceadores de carga, certifique-se de validar o suporte a TLS 1,2, teste cuidadosamente e entre em contato com o fornecedor, se necessário.</span><span class="sxs-lookup"><span data-stu-id="fb925-181">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="fb925-182">Considerações de Federação ao desabilitar o TLS 1.0/1.1 em servidores de borda</span><span class="sxs-lookup"><span data-stu-id="fb925-182">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="fb925-183">Você deve planejar cuidadosamente e considerar o impacto de desabilitar o TLS 1.0/1.1 nos servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="fb925-183">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="fb925-184">Depois que o TLS 1,0 e 1,1 estiverem desabilitados, você poderá achar que outras organizações não poderão ser federadas com sua organização.</span><span class="sxs-lookup"><span data-stu-id="fb925-184">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="fb925-185">Você pode optar por manter o TLS 1.0/1.1 habilitado em seus servidores de borda para manter a compatibilidade com versões anteriores de sistemas externos não corrigidos (SfB 2015, Lync 2013) ou mais antigos (2010).</span><span class="sxs-lookup"><span data-stu-id="fb925-185">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="fb925-186">A Microsoft não pode fornecer conselhos ou recomendações sobre se a rede de borda (ou qualquer rede) está ou não no padrão PCI; Isso deve ser determinado pela empresa individual.</span><span class="sxs-lookup"><span data-stu-id="fb925-186">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="fb925-187">O Skype for Business Online é capaz de permitir o TLS 1,2 hoje, portanto, não é esperado nenhum impacto no híbrido/Federação online.</span><span class="sxs-lookup"><span data-stu-id="fb925-187">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="fb925-188">PIC (conectividade de IM pública) para o serviço de consumidor do Skype: não esperamos desabilitar o TLS 1.0/1.1 para impactar a [conectividade do Skype](../../deploy/deploy-skype-connectivity.md); Os gateways PIC da Microsoft já são compatíveis com o TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="fb925-188">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="fb925-189">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="fb925-189">Prerequisites and process</span></span>

<span data-ttu-id="fb925-190">Exceto quando observado acima, depois que o TLS 1,0 e 1,1 forem desabilitados servidores fora do escopo, os clientes e dispositivos funcionarão mais corretamente ou de qualquer forma.</span><span class="sxs-lookup"><span data-stu-id="fb925-190">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="fb925-191">Isso pode significar que você precisa pausar e aguardar orientações atualizadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fb925-191">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="fb925-192">Quando estiver satisfeito com a necessidade de atender a todos os requisitos e ter um plano para lidar com as lacunas, continue.</span><span class="sxs-lookup"><span data-stu-id="fb925-192">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="fb925-193">Em um nível alto, enquanto o Skype for Business Server 2019 estiver pronto para o procedimento a ser instalado, o Skype for Business Server 2015 exigirá que você instale o CU9, aplicando atualizações de pré-requisito ao .NET e ao SQL, implantando chaves de registro de pré-requisito e finalmente uma rodada de 1,1 1,0 atualizações de configuração de so.</span><span class="sxs-lookup"><span data-stu-id="fb925-193">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="fb925-194">É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo o Skype for Business Server 2015 CU6 HF2, antes de desabilitar o TLS 1,0 e 1,1 em qualquer servidor do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb925-194">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="fb925-195">Todo o Skype for Business Server, incluindo função de borda e backends SQL, requer as atualizações.</span><span class="sxs-lookup"><span data-stu-id="fb925-195">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="fb925-196">Além disso, certifique-se de que todos os clientes com suporte (em escopo) foram atualizados para as versões mínimas necessárias.</span><span class="sxs-lookup"><span data-stu-id="fb925-196">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="fb925-197">Não se esqueça também de atualizar as estações de trabalho de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="fb925-197">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="fb925-198">Queremos seguir a ordem usual de operações de "Inside Out" para atualizar os servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fb925-198">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="fb925-199">Trate pools de diretores, chat persistente e pools emparelhados da mesma maneira que você faria normalmente.</span><span class="sxs-lookup"><span data-stu-id="fb925-199">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="fb925-200">O pedido e os métodos para atualização são abordados [aqui](topology.md) e [aqui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="fb925-200">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="fb925-201">Processo de alto nível</span><span class="sxs-lookup"><span data-stu-id="fb925-201">High-level process</span></span>

1. <span data-ttu-id="fb925-202">Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="fb925-202">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="fb925-203">Faça backup e preserve uma cópia do registro exportado em cada servidor individual a ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="fb925-203">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="fb925-204">Não é possível compartilhar registros entre servidores; Eles contêm chaves exclusivas baseadas em máquina.</span><span class="sxs-lookup"><span data-stu-id="fb925-204">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="fb925-205">Atualize todos os servidores do Skype for Business 2015 para o CU9 ou superior.</span><span class="sxs-lookup"><span data-stu-id="fb925-205">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="fb925-206">Para o Skype for Business Server 2019, atualize para o CU1 ou superior.</span><span class="sxs-lookup"><span data-stu-id="fb925-206">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="fb925-207">Instale todos os pré-requisitos para todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="fb925-207">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="fb925-208">Implantar chaves de registro de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="fb925-208">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="fb925-209">Verifique se todos os clientes no escopo estão atualizados.</span><span class="sxs-lookup"><span data-stu-id="fb925-209">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="fb925-210">Desabilite o TLS 1,0 e 1,1 via importação do registro.</span><span class="sxs-lookup"><span data-stu-id="fb925-210">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="fb925-211">Validar que as cargas de trabalho estão funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="fb925-211">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="fb925-212">Se forem encontrados problemas, solucionar e resolver, ou</span><span class="sxs-lookup"><span data-stu-id="fb925-212">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="fb925-213">Restaure o registro da etapa 2 para reabilitar o TLS 1,0 e 1,1</span><span class="sxs-lookup"><span data-stu-id="fb925-213">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="fb925-214">Valide que apenas o TLS 1,2 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="fb925-214">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="fb925-215">Instalar pré-requisitos para todos os servidores</span><span class="sxs-lookup"><span data-stu-id="fb925-215">Install prerequisites to all servers</span></span>

<span data-ttu-id="fb925-216">Uma atualização de dependência extensiva é necessária antes de começar a desabilitar o TLS 1,0 e 1,1 no nível do sistema operacional em suas implantações de 2015 do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb925-216">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="fb925-217">Veja a seguir as versões mínimas que podem dar suporte a TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="fb925-217">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="fb925-218">Implante todas as atualizações de pré-requisito em cada Skype for Business Server em seu ambiente antes de começar a desabilitar o TLS 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="fb925-218">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="fb925-219">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-219">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="fb925-220">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) ou superior com o SchUseStrongCrypto habilitado no registro (fornecido abaixo)</span><span class="sxs-lookup"><span data-stu-id="fb925-220">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="fb925-221">O SQL deve ser atualizado em todos os servidores do Skype for Business 2015 e de back-ends.</span><span class="sxs-lookup"><span data-stu-id="fb925-221">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="fb925-222">Atualize o pool de SQL da Enterprise Edition primeiro e depois o respectivo FEs.</span><span class="sxs-lookup"><span data-stu-id="fb925-222">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="fb925-223">[SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)ou superior/sql Server 2012 SP2 + atualização cumulativa 16 ou superior/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)ou superior/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="fb925-223">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="fb925-224">SQL Server Native Client para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="fb925-224">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="fb925-225">[Microsoft ODBC Driver 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)ou superior</span><span class="sxs-lookup"><span data-stu-id="fb925-225">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="fb925-226">Objetos de gerenciamento compartilhado para o SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="fb925-226">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="fb925-227">SQLSysClrTypes para o SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="fb925-227">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="fb925-228">Etapas básicas para instalar os pré-requisitos, em ordem recomendada de operações</span><span class="sxs-lookup"><span data-stu-id="fb925-228">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="fb925-229">Instale a atualização do Skype for Business Server CU9 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="fb925-229">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="fb925-230">Instale a atualização dos componentes usando o atualizador.</span><span class="sxs-lookup"><span data-stu-id="fb925-230">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="fb925-231">Atualizar bancos de dados de acordo com procedimentos documentados.</span><span class="sxs-lookup"><span data-stu-id="fb925-231">Update databases according to documented procedures.</span></span> <span data-ttu-id="fb925-232">Para o Skype for Business Server 2015, confira KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="fb925-232">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="fb925-233">Validar a funcionalidade do produto na implantação antes de prosseguir com outras alterações.</span><span class="sxs-lookup"><span data-stu-id="fb925-233">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="fb925-234">Baixe o instalador offline do .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="fb925-234">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="fb925-235">Indicação [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="fb925-235">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="fb925-236">Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fb925-236">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="fb925-237">Indicação [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="fb925-237">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="fb925-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="fb925-238">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="fb925-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="fb925-239">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="fb925-240">Execute o pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="fb925-240">Run the installer package.</span></span>
    7. <span data-ttu-id="fb925-241">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="fb925-241">Reboot the server.</span></span>
3. <span data-ttu-id="fb925-242">Atualize o SQL Express 2014 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="fb925-242">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="fb925-243">Indicação [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="fb925-243">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="fb925-244">Baixar o SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="fb925-244">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="fb925-245">Indicação [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="fb925-245">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="fb925-246">Copie a mídia de instalação para uma pasta no servidor (ex: C:\ 01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="fb925-246">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="fb925-247">Garantir que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end</span><span class="sxs-lookup"><span data-stu-id="fb925-247">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="fb925-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="fb925-248">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="fb925-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="fb925-249">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="fb925-250">Abrir um prompt de comando do administrador e atualizar todos os componentes e instâncias instalados</span><span class="sxs-lookup"><span data-stu-id="fb925-250">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="fb925-251">Exemplo: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe/QS/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="fb925-251">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="fb925-252">Atualize o SQL Native Client.</span><span class="sxs-lookup"><span data-stu-id="fb925-252">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="fb925-253">Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server) .</span><span class="sxs-lookup"><span data-stu-id="fb925-253">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="fb925-254">Baixar do [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="fb925-254">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="fb925-255">Verifique se os serviços do Skype for Business Server 2015 estão interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fb925-255">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="fb925-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="fb925-256">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="fb925-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="fb925-257">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="fb925-258">Interromper a execução das instâncias SQL instaladas</span><span class="sxs-lookup"><span data-stu-id="fb925-258">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="fb925-259">Ex ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="fb925-259">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="fb925-260">Ex ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="fb925-260">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="fb925-261">Ex (Standard Edition apenas): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="fb925-261">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="fb925-262">Instale a atualização.</span><span class="sxs-lookup"><span data-stu-id="fb925-262">Install the update.</span></span>
5. <span data-ttu-id="fb925-263">Atualize o ODBC Driver 11 para SQL Server para incluir suporte para TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="fb925-263">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="fb925-264">Baixe o [ODBC Driver 11 para SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="fb925-264">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="fb925-265">Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="fb925-265">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="fb925-266">Exemplo (edição Standard): ```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="fb925-266">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="fb925-267">Exemplo (Enterprise Edition): ```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="fb925-267">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="fb925-268">Instale a atualização.</span><span class="sxs-lookup"><span data-stu-id="fb925-268">Install the update.</span></span>
6. <span data-ttu-id="fb925-269">Implantar chaves de registro de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="fb925-269">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="fb925-270">Chaves de registro de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="fb925-270">Pre-requisite registry keys</span></span>

<span data-ttu-id="fb925-271">Copie/cole o teste a seguir no bloco de notas e renomeie o TLSPreReq. reg ou um nome de sua escolha e, em seguida, importe:</span><span class="sxs-lookup"><span data-stu-id="fb925-271">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="fb925-272">Para o SQL back ends para os pools Enterprise Edition, os pré-requisitos e a desabilitação de TLS devem ser tratados como qualquer atualização SQL ou de so; consulte: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="fb925-272">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="fb925-273">Embora o aplicativo de pré-requisito e as etapas de desabilitação de TLS possam ser combinados, é altamente recomendável que todos os pré-requisitos sejam aplicados antes de prosseguir com a desabilitação de TLS 1,0 e 1,1 no nível do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="fb925-273">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="fb925-274">A abordagem de práticas recomendadas seria preparar o ambiente implantando todos os pré-requisitos, Validando que as cargas de trabalho funcionaram corretamente e conforme o esperado e, em seguida, prosseguindo com o TLS 1.0/1.1 desabilitado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="fb925-274">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="fb925-275">Desabilitar o TLS 1,0 e 1,1 via importação do registro</span><span class="sxs-lookup"><span data-stu-id="fb925-275">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="fb925-276">Antes de prosseguir com as próximas etapas, *certifique-se de ter concluído todos os pré-requisitos e os servidores do Skype for Business atualizados*.</span><span class="sxs-lookup"><span data-stu-id="fb925-276">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="fb925-277">Copie o seguinte texto em um arquivo do bloco de notas e renomeie-o **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="fb925-277">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="fb925-278">Importe o arquivo. reg em cada servidor que você deseja desabilitar o TLS 1,0 e 1,1.</span><span class="sxs-lookup"><span data-stu-id="fb925-278">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="fb925-279">Reinicialize o servidor.</span><span class="sxs-lookup"><span data-stu-id="fb925-279">Reboot the server.</span></span> <span data-ttu-id="fb925-280">Depois que os serviços voltarem online, vá para o próximo servidor.</span><span class="sxs-lookup"><span data-stu-id="fb925-280">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="fb925-281">A abordagem para pools Enterprise Edition é o mesmo que você faria para qualquer atualização de sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="fb925-281">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="fb925-282">Você pode ter notado que estamos fazendo mais do que simplesmente desabilitando o TLS 1,0 e 1,1 aqui.</span><span class="sxs-lookup"><span data-stu-id="fb925-282">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="fb925-283">Estamos dando suporte à reordenação do pacote de codificação (conforme mostrado acima) e à desabilitação de algumas cifras fracas mais antigas.</span><span class="sxs-lookup"><span data-stu-id="fb925-283">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="fb925-284">Esta é a primeira vez que suportamos oficialmente essas alterações para a API de criptografia e SCHANNEL no Skype for Business Server, e é importante observar que essas alterações são as únicas que suportamos e testaram no momento.</span><span class="sxs-lookup"><span data-stu-id="fb925-284">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="fb925-285">Podemos considerar configurações adicionais no futuro, mas por enquanto, não modifique o arquivo de importação do registro em sua implementação.</span><span class="sxs-lookup"><span data-stu-id="fb925-285">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="fb925-286">Validar que as cargas de trabalho estão funcionando conforme o esperado</span><span class="sxs-lookup"><span data-stu-id="fb925-286">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="fb925-287">Após o TLS 1,0 e 1,1 ter sido desabilitado em seu ambiente, verifique se todas as cargas de trabalho principais estão funcionando conforme o esperado, como a presença de mensagens instantâneas &, chamadas P2P, Enterprise Voice, etc.</span><span class="sxs-lookup"><span data-stu-id="fb925-287">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="fb925-288">**Validar somente TLS 1,2 está sendo usado**</span><span class="sxs-lookup"><span data-stu-id="fb925-288">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="fb925-289">Faça com que sua equipe de segurança execute uma nova auditoria de tráfego do Skype for Business para garantir que os protocolos mais antigos TLS 1,0 e 1,1 não estejam mais em uso.</span><span class="sxs-lookup"><span data-stu-id="fb925-289">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="fb925-290">Como alternativa, você pode usar o Internet Explorer para testar conexões TLS para serviços Web do Skype for Business Server 2015 após o TLS 1,0 e o TLS 1,1 terem sido desabilitados.</span><span class="sxs-lookup"><span data-stu-id="fb925-290">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="fb925-291">Inicie o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fb925-291">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="fb925-292">Selecione **ferramentas**  >  **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="fb925-292">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="fb925-293">Selecione a guia **avançado** .</span><span class="sxs-lookup"><span data-stu-id="fb925-293">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="fb925-294">Em **configurações**, role até o final.</span><span class="sxs-lookup"><span data-stu-id="fb925-294">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="fb925-295">Verifique se o TLS 1,0, TLS 1,1 e TLS 1,2 estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="fb925-295">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="fb925-296">Procure a URL do serviço Web interno do seu pool do SfB 2015 (deve se conectar com êxito).</span><span class="sxs-lookup"><span data-stu-id="fb925-296">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="fb925-297">Volte para o Internet Explorer e desabilite a opção para **usar somente TLS 1,2** .</span><span class="sxs-lookup"><span data-stu-id="fb925-297">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="fb925-298">Procure a URL do serviço Web interno do pool do SfB 2015 novamente (não deve se conectar).</span><span class="sxs-lookup"><span data-stu-id="fb925-298">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="fb925-300">Cenários de implantação avançada</span><span class="sxs-lookup"><span data-stu-id="fb925-300">Advanced deployment scenarios</span></span>

<span data-ttu-id="fb925-301">Como alguns pré-requisitos de dependência são necessários para dar suporte a TLS 1,2 no Skype for Business Server 2015, a instalação da mídia RTM falhará em qualquer sistema em que o TLS 1,0 e 1,1 tenham sido desabilitados.</span><span class="sxs-lookup"><span data-stu-id="fb925-301">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Server 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="fb925-302">**Implantar novos servidores Standard Edition ou pools Enterprise Edition após o TLS 1,0 e 1,1 ter sido desabilitado em seu ambiente.**</span><span class="sxs-lookup"><span data-stu-id="fb925-302">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="fb925-303">**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="fb925-303">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="fb925-304">Observe que estamos atualizando o SmartSetup para acomodar os binários do SQL atualizados em uma futura CU e atualizar este artigo no futuro.</span><span class="sxs-lookup"><span data-stu-id="fb925-304">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="fb925-305">**Opção 2:** Pré-instalar instâncias do SQL locais (RTCLOCAL e LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="fb925-305">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="fb925-306">Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64.exe) para a pasta local no FE.</span><span class="sxs-lookup"><span data-stu-id="fb925-306">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="fb925-307">Digamos que o caminho da pasta <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="fb925-307">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="fb925-308">Inicie o PowerShell ou prompt de comando e navegue até <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="fb925-308">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="fb925-309">Crie a instância do SQL RTCLOCAL executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="fb925-309">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="fb925-310">Aguarde até que SQLEXPR_x64.exe seja concluída antes de prosseguir:</span><span class="sxs-lookup"><span data-stu-id="fb925-310">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="fb925-311">SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\administradores"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automatizi</span><span class="sxs-lookup"><span data-stu-id="fb925-311">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="fb925-312">Crie a instância do SQL LYNCLOCAL executando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="fb925-312">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="fb925-313">Aguarde até que SQLEXPR_x64.exe seja concluído antes de prosseguir para a próxima etapa:</span><span class="sxs-lookup"><span data-stu-id="fb925-313">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="fb925-314">SQLEXPR_x64.exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\administradores"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="fb925-314">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="fb925-315">Executar a instalação do Skype for Business Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="fb925-315">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="fb925-316">Siga as etapas restantes da seção pré-requisitos acima.</span><span class="sxs-lookup"><span data-stu-id="fb925-316">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="fb925-317">**Opção 3:** Você também pode substituir manualmente os binários em um diretório de mídia de instalação local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fb925-317">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="fb925-318">Instalar pré-requisitos para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb925-318">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="fb925-319">Instale o .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="fb925-319">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="fb925-320">**Observação:** Primeiro, apresentamos suporte para o .NET 4,7 no Skype for Business Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="fb925-320">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="fb925-321">Portanto, nas etapas posteriores abaixo, atualizaremos os componentes principais antes da instalação principal.</span><span class="sxs-lookup"><span data-stu-id="fb925-321">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="fb925-322">Baixar: https://www.microsoft.com/download/details.aspx?id=55167 .</span><span class="sxs-lookup"><span data-stu-id="fb925-322">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="fb925-323">Referência: [software que deve ser instalado antes da implantação do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="fb925-323">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="fb925-324">Copiar arquivos/pastas ISO:</span><span class="sxs-lookup"><span data-stu-id="fb925-324">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="fb925-325">Com o ISO do Skype for Business Server 2015 conectado, abra o diretório raiz da unidade à qual ele está conectado (ex: D: \) no explorador de arquivos.</span><span class="sxs-lookup"><span data-stu-id="fb925-325">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="fb925-326">Copiar todas as pastas e arquivos para uma pasta em um disco local (ex: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="fb925-326">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="fb925-327">**Observação:** Antes de instalar os componentes, alguns arquivos precisarão ser atualizados para o suporte do TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="fb925-327">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="fb925-328">Substituir pacotes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="fb925-328">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="fb925-329">Substitua os pacotes MSI e EXE existentes na pasta/Setup/AMD64/da mídia de instalação no computador local.</span><span class="sxs-lookup"><span data-stu-id="fb925-329">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="fb925-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="fb925-330">SQL 2014 SP2 Express: https://www.microsoft.com/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="fb925-331">Renomeie como SQLEXPR_x64 no computador local e substitua o arquivo existente na instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="fb925-331">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="fb925-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="fb925-332">SQL Native Client: https://www.microsoft.com/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="fb925-333">**Observação:** Renomeie-o se necessário para sqlncli.msi e, em seguida, substitua o arquivo existente que existe na instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="fb925-333">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="fb925-334">Objetos de gerenciamento do SQL: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="fb925-334">SQL Management Objects: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="fb925-335">**Observação:** O Feature Pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="fb925-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="fb925-336">Selecione para baixar somente SharedManagementObjects.msi.</span><span class="sxs-lookup"><span data-stu-id="fb925-336">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="fb925-337">**Observação:** Substitua o arquivo existente que existe na pasta Setup/AMD64/da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="fb925-337">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="fb925-338">Tipos CLR SQL: https://www.microsoft.com/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="fb925-338">SQL CLR Types: https://www.microsoft.com/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="fb925-339">**Observação:** O Feature Pack terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="fb925-339">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="fb925-340">Selecione para baixar somente CQLSysClrTypes.msi</span><span class="sxs-lookup"><span data-stu-id="fb925-340">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="fb925-341">**Observação**: substitua o arquivo existente que existe na pasta Setup/AMD64/da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="fb925-341">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="fb925-342">Instale os componentes principais:</span><span class="sxs-lookup"><span data-stu-id="fb925-342">Install Core Components:</span></span> 
    - <span data-ttu-id="fb925-343">Execute Setup.exe na pasta Setup/AMD64/da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="fb925-343">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="fb925-344">Siga as instruções para instalar os componentes principais</span><span class="sxs-lookup"><span data-stu-id="fb925-344">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="fb925-345">Feche os componentes principais.</span><span class="sxs-lookup"><span data-stu-id="fb925-345">Close Core Components.</span></span>
6. <span data-ttu-id="fb925-346">Atualizar componentes principais:</span><span class="sxs-lookup"><span data-stu-id="fb925-346">Update Core Components:</span></span> 
    - <span data-ttu-id="fb925-347">Baixe o instalador de atualização do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="fb925-347">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="fb925-348">Execute o instalador para atualizar os componentes principais e instalar os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="fb925-348">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="fb925-349">**Observação:** A partir da versão do CU6HF2, o recurso de atualização automática atualmente só instalará até o CU6.</span><span class="sxs-lookup"><span data-stu-id="fb925-349">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="fb925-350">Portanto, o atualizador deve ser executado separadamente para atualizar os componentes principais para o 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="fb925-350">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="fb925-351">Indicação https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="fb925-351">Reference: https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="fb925-352">Instalar ferramentas administrativas (opcional):</span><span class="sxs-lookup"><span data-stu-id="fb925-352">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="fb925-353">Isso instalará o Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR Types for SQL Server 2014 (x64) usando os arquivos atualizados.</span><span class="sxs-lookup"><span data-stu-id="fb925-353">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="fb925-354">Além disso, o construtor de topologias do Skype for Business Server 2015 e o painel de controle estarão disponíveis na máquina local.</span><span class="sxs-lookup"><span data-stu-id="fb925-354">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="fb925-355">Instale o repositório de configuração local (etapa 1):</span><span class="sxs-lookup"><span data-stu-id="fb925-355">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="fb925-356">Abra o assistente de implantação, clique em instalar ou atualizar o sistema do Skype for Business Server e clique em **executar** na etapa 1: instalar o repositório de configuração local.</span><span class="sxs-lookup"><span data-stu-id="fb925-356">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="fb925-357">Clique em **Avançar** na caixa de diálogo **instalar repositório de configuração local** .</span><span class="sxs-lookup"><span data-stu-id="fb925-357">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="fb925-358">![Caixa de diálogo instalar repositório de configuração local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="fb925-358">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="fb925-359">Revise os resultados e verifique se o status da tarefa está concluído.</span><span class="sxs-lookup"><span data-stu-id="fb925-359">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="fb925-360">Examine o arquivo de log resultante clicando em **Exibir log**.</span><span class="sxs-lookup"><span data-stu-id="fb925-360">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="fb925-361">![O status da tarefa é exibido como concluído](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="fb925-361">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="fb925-362">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="fb925-362">Click **Finish**.</span></span>
9. <span data-ttu-id="fb925-363">Configurar ou remover componentes do Skype for Business Server (etapa 2):</span><span class="sxs-lookup"><span data-stu-id="fb925-363">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="fb925-364">Abra o assistente de implantação, clique em **instalar ou atualizar o sistema do Skype for Business Server** e clique em **executar** na etapa 2: configurar ou remover componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fb925-364">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="fb925-365">Clique em **Avançar** na caixa de diálogo Configurar componentes do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb925-365">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="fb925-366">![a janela configurar componentes do Skype for Business Server](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="fb925-366">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="fb925-367">Revise o log usando o log de exibição e valide se a instalação foi concluída sem problemas.</span><span class="sxs-lookup"><span data-stu-id="fb925-367">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="fb925-368">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="fb925-368">Click **Finish**.</span></span>
10. <span data-ttu-id="fb925-369">Prossiga com a instalação e a configuração adicionais, conforme necessário (você pode retomar os procedimentos de instalação normais neste ponto).</span><span class="sxs-lookup"><span data-stu-id="fb925-369">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
