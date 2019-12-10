---
title: Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Resumo: preparar e implementar a desabilitação do TLS 1,0 e do 1,1 em seus ambientes.'
ms.openlocfilehash: f6fa608174bc22bc91512a69cc67a688b9bc7bb9
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919305"
---
# <a name="disable-tls-1011-in-skype-for-business-server-2015"></a><span data-ttu-id="bbbdb-103">Desabilitar TLS 1.0/1.1 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="bbbdb-103">Disable TLS 1.0/1.1 in Skype for Business Server 2015</span></span>

<span data-ttu-id="bbbdb-104">O objetivo deste artigo é fornecer as diretrizes necessárias para se preparar e implementar a desabilitação do TLS 1,0 e do 1,1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-104">The purpose of this article is to provide the necessary guidance for you to prepare for and implement disabling TLS 1.0 and 1.1 in your environments.</span></span> <span data-ttu-id="bbbdb-105">Esse processo requer planejamento e preparação extensivos.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-105">This process requires extensive planning and preparation.</span></span> <span data-ttu-id="bbbdb-106">Revise cuidadosamente todas as informações deste artigo enquanto faz seu plano para desativar o TLS 1,0 e o 1,1 para sua organização.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-106">Please carefully review all of the information in this article as you make your plan to disable TLS 1.0 and 1.1 for your organization.</span></span> <span data-ttu-id="bbbdb-107">Observe que há muitas dependências externas e condições de conectividade que podem ser impactadas ao desabilitar o TLS 1.0/1.1, portanto, o planejamento e o teste extensivos são garantidos.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-107">Note that there are many external dependencies and connectivity conditions that could be impacted by disabling TLS 1.0/1.1, so extensive planning and testing is warranted.</span></span>

## <a name="in-this-article"></a><span data-ttu-id="bbbdb-108">Neste artigo</span><span class="sxs-lookup"><span data-stu-id="bbbdb-108">In this article</span></span>

- [<span data-ttu-id="bbbdb-109">Plano de fundo e escopo</span><span class="sxs-lookup"><span data-stu-id="bbbdb-109">Background and scope</span></span>](#background)
- [<span data-ttu-id="bbbdb-110">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="bbbdb-110">Prerequisites and process</span></span>](#prerequisites-and-process)
- [<span data-ttu-id="bbbdb-111">Cenários de implantação avançados</span><span class="sxs-lookup"><span data-stu-id="bbbdb-111">Advanced deployment scenarios</span></span>](#advanced-deployment-scenarios)

## <a name="background"></a><span data-ttu-id="bbbdb-112">Plano de fundo</span><span class="sxs-lookup"><span data-stu-id="bbbdb-112">Background</span></span>

<span data-ttu-id="bbbdb-113">Os principais drivers para fornecer o TLS 1,0 e o 1,1 Disable support para o Skype for Business Server no local são o Conselho de padrões de segurança da indústria de cartão de pagamento (PCI) e os padrões federais de processamento de informações.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-113">The primary drivers for providing TLS 1.0 and 1.1 disable support for Skype for Business Server On-Premises are Payment Card Industry (PCI) Security Standards Council and Federal Information Processing Standards requirements.</span></span> <span data-ttu-id="bbbdb-114">Mais informações para requisitos de PCI podem ser encontradas [aqui](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-114">More information for PCI requirements can be found [here](https://blog.pcisecuritystandards.org/are-you-ready-for-30-june-2018-sayin-goodbye-to-ssl-early-tls).</span></span>  <span data-ttu-id="bbbdb-115">A Microsoft não pode fornecer orientação sobre a necessidade ou não de sua organização de aderir a esses ou outros requisitos.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-115">Microsoft cannot provide guidance on whether or not your organization is required to adhere to these or other requirements.</span></span> <span data-ttu-id="bbbdb-116">Você deve determinar se é necessário desativar o TLS 1,0 e/ou 1,1 em seus ambientes.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-116">You must determine if it is required for you to disable TLS 1.0 and/or 1.1 in your environments.</span></span>

<span data-ttu-id="bbbdb-117">A Microsoft produziu um White paper sobre o TLS disponível [aqui](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), e também recomendamos a leitura em segundo plano disponível neste [blog do Exchange](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-117">Microsoft has produced a white paper on TLS available [here](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/), and we also recommend the background reading available in this [Exchange blog](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/).</span></span>

## <a name="supportability-scope"></a><span data-ttu-id="bbbdb-118">Escopo de suporte</span><span class="sxs-lookup"><span data-stu-id="bbbdb-118">Supportability Scope</span></span>

<span data-ttu-id="bbbdb-119">*Escopo* refere-se aos limites de suporte.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-119">*Scope* refers to supportability boundaries.</span></span> <span data-ttu-id="bbbdb-120">*Totalmente testado e com suporte* significa que damos suporte e testamos a desativação do TLS 1,0 e do 1,1 para as versões de produto listadas.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-120">*Fully tested and supported* means we fully support and have tested disabling of TLS 1.0 and 1.1 for the listed product versions.</span></span> <span data-ttu-id="bbbdb-121">*Sendo investigado no momento* significa exatamente isso; Estamos investigando ativamente os produtos em escopo para desabilitar o suporte para TLS.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-121">*Currently being investigated* means just that; we are actively investigating bringing these products into scope for TLS disable support.</span></span> <span data-ttu-id="bbbdb-122">*Fora do escopo* significa que essas versões do produto não são compatíveis com a desabilitação do TLS 1,0 ou do 1,1 e não funcionarão com exceções observadas.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-122">*Out of scope* means these product versions do not support disabling TLS 1.0 or 1.1 and will not work, with noted exceptions.</span></span>

### <a name="fully-tested-and-supported-servers"></a><span data-ttu-id="bbbdb-123">Servidores totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="bbbdb-123">Fully tested and supported servers</span></span>

- <span data-ttu-id="bbbdb-124">Skype for Business Server 2019 CU1 17.0.2046.123 (2019 de junho) ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-124">Skype for Business Server 2019 CU1 17.0.2046.123 (June 2019) or higher</span></span>
- <span data-ttu-id="bbbdb-125">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior no Windows Server 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização substituída), 2012 R2 ou 2016.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-125">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), 2012 R2 or 2016.</span></span>
- <span data-ttu-id="bbbdb-126">Atualizado no local o Skype for Business Server 2015, com o CU9 6.0.9319.548 (2019 de maio) ou superior no Windows Server 2008 R2, 2012 (com KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) ou atualização substituta) ou 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-126">In-place Upgraded Skype for Business Server 2015, with CU9 6.0.9319.548 (May 2019) or higher on Windows Server 2008 R2, 2012 (with KB [3140245](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in) or superseding update), or 2012 R2.</span></span>
- <span data-ttu-id="bbbdb-127">Exchange conectividade e Outlook Web App com Exchange Server 2010 SP3 RU19 ou superior, orientação [aqui](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-127">Exchange Connectivity and Outlook Web App with Exchange Server 2010 SP3 RU19 or higher, guidance [here](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)</span></span>
- <span data-ttu-id="bbbdb-128">Aplicativo de ramificação sobreviventes (SBA) com o Skype for Business Server 2015 CU6 HF2 ou superior (confirme com o seu fornecedor se eles empacotaram as atualizações do appropiate e se foram disponibilizados para o seu aparelho)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-128">Survivable Branch Appliance (SBA) with Skype for Business Server 2015 CU6 HF2 or higher (confirm with your vendor that they packaged the appropiate updates and have been made available for your appliance)</span></span>
- <span data-ttu-id="bbbdb-129">Servidor de ramificação sobreviventes (SBS) com o Skype for Business Server 2015 CU6 HF2 ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-129">Survivable Branch Server (SBS) with Skype for Business Server 2015 CU6 HF2 or higher</span></span>
- <span data-ttu-id="bbbdb-130">**Somente função de borda**do Lync Server 2013, isso ocorre porque a função Edge não tem dependência no Windows Fabric 1,0.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-130">Lync Server 2013 **Edge Role Only**, this is because Edge role does not have a dependency on Windows Fabric 1.0.</span></span>

### <a name="fully-tested-and-supported-clients"></a><span data-ttu-id="bbbdb-131">Clientes totalmente testados e com suporte</span><span class="sxs-lookup"><span data-stu-id="bbbdb-131">Fully tested and supported clients</span></span>

- <span data-ttu-id="bbbdb-132">Lync 2013 (Skype for Business) Desktop Client, MSI e C2R, incluindo o [15.0.5023.1000 básico ou superior](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-132">Lync 2013 (Skype for Business) Desktop Client, MSI and C2R, including Basic [15.0.5023.1000 or higher](https://support.microsoft.com/help/4018334/april-3-2018-update-for-skype-for-business-2015-lync-2013-kb4018334)</span></span>
- <span data-ttu-id="bbbdb-133">Cliente de área de trabalho Skype for Business 2016, MSI [16.0.4678.1000 ou superior](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), incluindo básico</span><span class="sxs-lookup"><span data-stu-id="bbbdb-133">Skype for Business 2016 Desktop Client, MSI [16.0.4678.1000 or higher](https://support.microsoft.com/help/4018323/april-3-2018-update-for-skype-for-business-2016-kb4018323), including Basic</span></span>
- <span data-ttu-id="bbbdb-134">Skype for Business 2016 clique em para executar exige as atualizações de [abril de 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) :</span><span class="sxs-lookup"><span data-stu-id="bbbdb-134">Skype for Business 2016 Click to Run Require the [April 2018](https://docs.microsoft.com/officeupdates/release-notes-office365-proplus) Updates:</span></span> 
    - <span data-ttu-id="bbbdb-135">Mensalmente e semidirecionado, 16\.0\.9126\.2152 ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-135">Monthly and Semi-Annual Targeted, 16\.0\.9126\.2152 or higher</span></span>
    - <span data-ttu-id="bbbdb-136">Canal semestral e semiadiado, 16\.0\.8431\.2242 ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-136">Semi-Annual and Deferred Channel, 16\.0\.8431\.2242 or higher</span></span>
- <span data-ttu-id="bbbdb-137">Skype for Business no Mac 16,15 ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-137">Skype for Business on Mac 16.15 or higher</span></span>
- <span data-ttu-id="bbbdb-138">Skype for Business para iOS e Android 6,19 ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-138">Skype for Business for iOS and Android 6.19 or higher</span></span>
- <span data-ttu-id="bbbdb-139">Salas do Microsoft Teams (anteriormente conhecido como Skype Room System v2 SRS v2) 4.0.64.0 (dezembro de 2018) ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-139">Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) 4.0.64.0 (December 2018) or higher</span></span>
- <span data-ttu-id="bbbdb-140">Atualização do Surface Hub para Team Edition com base no KB4499162 (maio de 2019, versão do sistema operacional 15063,1835) ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-140">Surface Hub update for Team edition based on KB4499162 (May 2019, OS Build 15063.1835) or higher</span></span>
- <span data-ttu-id="bbbdb-141">Skype Web App 2015 CU6 HF2 ou superior (fornecido com o servidor)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-141">Skype Web App 2015 CU6 HF2 or higher (ships with Server)</span></span>

### <a name="currently-being-investigated"></a><span data-ttu-id="bbbdb-142">Sendo investigado no momento</span><span class="sxs-lookup"><span data-stu-id="bbbdb-142">Currently being investigated</span></span>

- <span data-ttu-id="bbbdb-143">Painel de qualidade de chamada (nova instalação após o TLS 1,0, o 1,1 foi desabilitado, veja abaixo) \*</span><span class="sxs-lookup"><span data-stu-id="bbbdb-143">Call Quality Dashboard (new install after TLS 1.0, 1.1 have been disabled, see below)\*</span></span>
 
### <a name="out-of-scope"></a><span data-ttu-id="bbbdb-144">Fora do escopo</span><span class="sxs-lookup"><span data-stu-id="bbbdb-144">Out of scope</span></span>

<span data-ttu-id="bbbdb-145">Exceto onde observado, os seguintes produtos não estão no escopo para TLS 1.0/1.1 desabilitar o suporte e não funcionarão em um ambiente em que o TLS 1,0 e o 1,1 foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-145">Except where noted, the following products are not in scope for TLS 1.0/1.1 disable support and will not function in an environment where TLS 1.0 and 1.1 have been disabled.</span></span> <span data-ttu-id="bbbdb-146">O que isso significa: se você ainda usar servidores ou clientes fora do escopo, será necessário atualizar ou removê-los se precisar desabilitar o TLS 1.0/1.1 em qualquer lugar na sua implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-146">What this means: if you still utilize out-of-scope servers or clients, you must update or remove these if you need to disable TLS 1.0/1.1 anywhere in your Skype for Business Server on-premises deployment.</span></span>

- <span data-ttu-id="bbbdb-147">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbbdb-147">Lync Server 2013</span></span>
- <span data-ttu-id="bbbdb-148">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bbbdb-148">Lync Server 2010</span></span>
- <span data-ttu-id="bbbdb-149">Windows Server 2008 ou inferior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-149">Windows Server 2008 or lower</span></span>
- <span data-ttu-id="bbbdb-150">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="bbbdb-150">Lync for Mac 2011</span></span>
- <span data-ttu-id="bbbdb-151">Lync 2013 para celular-iOS, iPad, Android ou Windows Phone</span><span class="sxs-lookup"><span data-stu-id="bbbdb-151">Lync 2013 for Mobile - iOS, iPad, Android or Windows Phone</span></span>
- <span data-ttu-id="bbbdb-152">Cliente da Windows Store "MX" do Lync</span><span class="sxs-lookup"><span data-stu-id="bbbdb-152">Lync "MX" Windows Store client</span></span>
- <span data-ttu-id="bbbdb-153">Sistema de sala do Lync (conhecido como</span><span class="sxs-lookup"><span data-stu-id="bbbdb-153">Lync Room System (a.k.a.</span></span> <span data-ttu-id="bbbdb-154">SRSv1).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-154">SRSv1).</span></span> <span data-ttu-id="bbbdb-155">O LRS atingiu o fim do suporte em 9 de outubro de 2018 e não será atualizado para dar suporte a TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-155">LRS reached end of support on October 9, 2018 and will not be updated to support TLS 1.2.</span></span>
- <span data-ttu-id="bbbdb-156">Todos os clientes do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bbbdb-156">All Lync 2010 clients</span></span>
- <span data-ttu-id="bbbdb-157">Lync Phone Edition – orientação atualizada [aqui](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-157">Lync Phone Edition - updated guidance [here](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Certified-Skype-for-Business-Online-Phones-and-what-this-means/ba-p/120035).</span></span>
- <span data-ttu-id="bbbdb-158">2013 (SBA) ou servidor de ramificação sobreviver (SBS) com base em</span><span class="sxs-lookup"><span data-stu-id="bbbdb-158">2013 based Survivable Branch Appliance (SBA) or Survivable Branch Server (SBS)</span></span>
- <span data-ttu-id="bbbdb-159">Cloud Connector Edition (CCE)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-159">Cloud Connector Edition (CCE)</span></span>
- <span data-ttu-id="bbbdb-160">Skype for Business para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="bbbdb-160">Skype for Business for Windows Phone</span></span>

### <a name="exceptions"></a><span data-ttu-id="bbbdb-161">Exceções</span><span class="sxs-lookup"><span data-stu-id="bbbdb-161">Exceptions</span></span>

#### <a name="lync-server-2013"></a><span data-ttu-id="bbbdb-162">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bbbdb-162">Lync Server 2013</span></span>

<span data-ttu-id="bbbdb-163">O Lync Server 2013 assume uma dependência na versão 1,0 do Windows Fabric.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-163">Lync Server 2013 takes a dependency on Windows Fabric version 1.0.</span></span>  <span data-ttu-id="bbbdb-164">Na fase de design do Lync Server 2013, o Windows Fabric 1,0 foi escolhido para sua arquitetura distribuída atraente e nova para fornecer replicação, alta disponibilidade e tolerância a falhas.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-164">In the design phase for Lync Server 2013, Windows Fabric 1.0 was chosen for its compelling and new distributed architecture to provide replication, high availability, and fault tolerance.</span></span>  <span data-ttu-id="bbbdb-165">Ao longo do tempo, tanto o Skype for Business Server quanto o Windows Fabric melhoraram bastante a arquitetura conjunta, com o redesign significativo nas versões subsequentes.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-165">Over time, both Skype for Business Server and Windows Fabric have greatly improved this joint architecture with significant re-design in subsequent versions.</span></span>  <span data-ttu-id="bbbdb-166">O servidor atual do Skype for Business 2015 usa o Windows Fabric 3,0, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-166">Current Skype for Business 2015 Server uses Windows Fabric 3.0, for example.</span></span>

<span data-ttu-id="bbbdb-167">Infelizmente, o Windows Fabric 1,0 não **é compatível com TLS 1,2.  No entanto, atualizaremos o Lync Server 2013 para funcionar com o TLS 1,2**.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-167">Unfortunately, Windows Fabric 1.0 **does not support TLS 1.2.  However, we will be updating Lync Server 2013 to work with TLS 1.2**.</span></span> <span data-ttu-id="bbbdb-168">Isso estará disponível na próxima atualização cumulativa do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-168">This will be coming in the next Cumulative Update for Lync Server 2013.</span></span>  <span data-ttu-id="bbbdb-169">Estamos fornecendo suporte a TLS 1,2 para habilitar a coexistência, migração, Federação e cenários híbridos.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-169">We're providing TLS 1.2 support to enable co-existence, migration, federation, and hybrid scenarios.</span></span>

<span data-ttu-id="bbbdb-170">Se a sua organização for necessária para desativar o TLS 1,0 e o 1,1, e você estiver usando o Lync Server 2013, recomendamos que você comece seu processo de planejamento, com a possibilidade de poder ter a atualização in-loco ou migração lado a lado (novos grupos, mover usuários) para o Skype para Business Server 2015 ou superior.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-170">If your organization is required to disable TLS 1.0 and 1.1, and you currently use Lync Server 2013, we recommend you begin your planning process, with the possibility you may have to In-place upgrade or Side-by-Side migrate (new pools, move users) to Skype for Business Server 2015 or higher.</span></span>  <span data-ttu-id="bbbdb-171">Ou talvez você queira acelerar a migração para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-171">Or you may want to accelerate migration to Skype for Business Online.</span></span>

#### <a name="call-quality-dashboard"></a><span data-ttu-id="bbbdb-172">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="bbbdb-172">Call Quality Dashboard</span></span>

<span data-ttu-id="bbbdb-173">No momento, o painel de qualidade de chamada no local tem uma dependência no TLS 1,0 durante a nova instalação (primeira instalação nos seus ambientes locais).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-173">On-Premises Call Quality Dashboard currently has a dependency on TLS 1.0 during new install (first time installing into your On-Premises environments).</span></span>  <span data-ttu-id="bbbdb-174">No momento, estamos investigando esse problema e planejamos liberar uma correção em breve.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-174">We are currently investigating this issue and plan to release a fix in the near future.</span></span>  <span data-ttu-id="bbbdb-175">Se você estiver planejando instalar o CQD e também desabilitar o TLS 1,0, recomendamos que conclua a instalação do CQD primeiro e, em seguida, continue com o TLS 1,0 desativando.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-175">If you are planning to install CQD and also disable TLS 1.0, we recommend that you complete CQD installation first, and then proceed with TLS 1.0 disabling.</span></span>

#### <a name="third-party-devices"></a><span data-ttu-id="bbbdb-176">Dispositivos terceirizados</span><span class="sxs-lookup"><span data-stu-id="bbbdb-176">Third-party devices</span></span>

<span data-ttu-id="bbbdb-177">Em dispositivos de terceiros, como telefones 3PIP, videoconferência, proxies inversos e balanceadores de carga, certifique-se de validar a capacidade de suporte do TLS 1,2, teste cuidadosamente e entre em contato com o fornecedor, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-177">On third-party devices such as 3PIP phones, Video conferencing, Reverse Proxies and Load Balancers, be sure to validate TLS 1.2 supportability, test carefully, and contact the vendor if needed.</span></span>

### <a name="federation-considerations-when-disabling-tls-1011-on-edge-servers"></a><span data-ttu-id="bbbdb-178">Considerações de Federação ao desabilitar o TLS 1.0/1.1 em servidores de borda</span><span class="sxs-lookup"><span data-stu-id="bbbdb-178">Federation considerations when disabling TLS 1.0/1.1 on Edge servers</span></span>

<span data-ttu-id="bbbdb-179">Você deve planejar cuidadosamente e considerar o impacto de desabilitar o TLS 1.0/1.1 em seus servidores Edge.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-179">You must carefully plan for and consider the impact of disabling TLS 1.0/1.1 on your Edge servers.</span></span>  <span data-ttu-id="bbbdb-180">Quando o TLS 1,0 e o 1,1 estiverem desativados, você pode descobrir que outras organizações não podem mais se federar à sua organização.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-180">Once TLS 1.0 and 1.1 are disabled, you may find that other organizations are no longer be able to federate with your organization.</span></span>

<span data-ttu-id="bbbdb-181">Você pode optar por manter o TLS 1.0/1.1 habilitado em seus servidores de borda para manter a compatibilidade com versões anteriores de sistemas externos não corrigidos (SfB 2015, Lync 2013) ou mais antigos (2010).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-181">You may opt to keep TLS 1.0/1.1 enabled on your Edge servers to maintain backward compatibility with non-patched (SfB 2015, Lync 2013) or older (2010) external systems.</span></span>

<span data-ttu-id="bbbdb-182">A Microsoft não pode fornecer conselhos nem recomendações sobre se a rede de borda (ou qualquer rede) cai ou não no padrão PCI; Isso deve ser determinado pela empresa individual.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-182">Microsoft cannot provide advice or recommendations on whether or not your Edge network (or any network) falls under PCI standard; that must be determined by the individual company.</span></span>

<span data-ttu-id="bbbdb-183">O Skype for Business Online é capaz de usar o TLS 1,2 hoje, portanto, não é esperado nenhum impacto no híbrido/Federação online.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-183">Skype for Business Online is capable of TLS 1.2 today, so no impact to Hybrid/Federation with Online is expected.</span></span>

<span data-ttu-id="bbbdb-184">PIC (conectividade de IM pública) para o serviço de consumidor da Skype: não esperamos desabilitar o TLS 1.0/1.1 para afetar a [conectividade do Skype](../../deploy/deploy-skype-connectivity.md); Os gateways PIC da Microsoft já são compatíveis com o TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-184">PIC (Public IM Connectivity) to Skype Consumer service: We do not expect disabling TLS 1.0/1.1 to impact [Skype Connectivity](../../deploy/deploy-skype-connectivity.md); Microsoft PIC Gateways are already TLS 1.2 capable.</span></span>

## <a name="prerequisites-and-process"></a><span data-ttu-id="bbbdb-185">Pré-requisitos e processo</span><span class="sxs-lookup"><span data-stu-id="bbbdb-185">Prerequisites and process</span></span>

<span data-ttu-id="bbbdb-186">Exceto onde observado acima, depois que o TLS 1,0 e o 1,1 estiverem desativados, os clientes e dispositivos funcionarão mais corretamente ou de modo algum.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-186">Except where noted above, once TLS 1.0 and 1.1 are disabled out-of-scope servers, clients and devices will longer function properly, or at all.</span></span> <span data-ttu-id="bbbdb-187">Isso pode significar que você precisa pausar e esperar por diretrizes atualizadas da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-187">This may mean you need to pause and wait for updated guidance from Microsoft.</span></span> <span data-ttu-id="bbbdb-188">Quando tiver certeza de que atende a todos os requisitos e tiver um plano para atender às lacunas, continue.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-188">Once you are satisfied that you meet all requirements and have a plan to address gaps, proceed.</span></span>

<span data-ttu-id="bbbdb-189">Em um nível alto, embora o Skype for Business Server 2019 esteja pronto para o procedimento na instalação, o Skype for Business Server 2015 exigirá que você instale o CU9, aplicando atualizações pré-requisitos para .NET e SQL, implantando as chaves de registro de pré-requisito e, por fim, um o arredondamento de atualizações de configuração do sistema operacional (ou seja, desabilitar o TLS 1,0 e 1,1 via importação de arquivo do registro).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-189">At a high level, while Skype for Business Server 2019 is ready for procedure at install, Skype for Business Server 2015 will require that you install CU9, applying pre-requisite updates to .NET and SQL, deploying prerequisite registry keys, and finally a separate round of OS configuration updates (i.e. disabling TLS 1.0 and 1.1 via registry file import).</span></span> <span data-ttu-id="bbbdb-190">É extremamente importante que você conclua a instalação de todos os pré-requisitos, incluindo o Skype for Business Server 2015 CU6 HF2, antes de desabilitar o TLS 1,0 e o 1,1 em qualquer servidor do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-190">It is critically important that you complete installation of all prerequisites, including Skype for Business Server 2015 CU6 HF2, prior to disabling TLS 1.0 and 1.1 on any server in your environment.</span></span> <span data-ttu-id="bbbdb-191">Cada servidor Skype for Business, incluindo função Edge e back-ends SQL, requer as atualizações.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-191">Every Skype for Business server, including Edge role and SQL Backends, requires the updates.</span></span> <span data-ttu-id="bbbdb-192">Além disso, certifique-se de que todos os clientes com suporte (em escopo) foram atualizados para as versões mínimas necessárias.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-192">Also ensure that all supported (in-scope) clients have been updated to the required minimum versions.</span></span> <span data-ttu-id="bbbdb-193">Não se esqueça de atualizar as estações de trabalho de gerenciamento também.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-193">Don’t forget to update management workstations as well.</span></span>

<span data-ttu-id="bbbdb-194">Queremos acompanhar a ordem usual de operações de "Inside Out" para atualizar os servidores do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-194">We want to follow the usual order of operations of "inside out" for upgrading Skype for Business servers.</span></span> <span data-ttu-id="bbbdb-195">Trate pools de directors, chats persistentes e pools emparelhados da mesma forma que normalmente faria.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-195">Treat Director pools, Persistent chat, and Paired Pools in the same manner you normally would.</span></span> <span data-ttu-id="bbbdb-196">O pedido e os métodos de atualização são abordados [aqui](topology.md) e [aqui](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-196">Order and methods for upgrade are covered [here](topology.md) and [here](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>

### <a name="high-level-process"></a><span data-ttu-id="bbbdb-197">Processo de alto nível</span><span class="sxs-lookup"><span data-stu-id="bbbdb-197">High-level process</span></span>

1. <span data-ttu-id="bbbdb-198">Teste todas as etapas em seu laboratório antes de configurar os servidores de produção.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-198">Test all steps in your lab prior to configuring production servers.</span></span>
2. <span data-ttu-id="bbbdb-199">Faça backup e preserve uma cópia do registro exportado em todos os servidores individuais a serem atualizados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-199">Back up and preserve a copy of exported registry on each and every individual server to be updated.</span></span> <span data-ttu-id="bbbdb-200">Não é possível compartilhar registros entre servidores; Elas contêm chaves exclusivas baseadas em máquina.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-200">You cannot share registries between servers; they contain unique machine-based keys.</span></span>
3. <span data-ttu-id="bbbdb-201">Atualize todos os servidores do Skype for Business 2015 para o CU9 ou superior.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-201">Upgrade all Skype for Business 2015 servers to CU9 or higher.</span></span> <span data-ttu-id="bbbdb-202">Para o Skype for Business Server 2019, atualize para o CU1 ou superior.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-202">For Skype for Business Server 2019, upgrade to CU1 or higher.</span></span>
4. <span data-ttu-id="bbbdb-203">Instale todos os pré-requisitos em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-203">Install all prerequisites to all servers.</span></span>
5. <span data-ttu-id="bbbdb-204">Implantar as chaves de registro de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-204">Deploy prerequisite registry keys.</span></span>
6. <span data-ttu-id="bbbdb-205">Certifique-se de que todos os clientes em escopo sejam atualizados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-205">Ensure that all in-scope clients are updated.</span></span>
7. <span data-ttu-id="bbbdb-206">Desabilite o TLS 1,0 e o 1,1 via importação do registro.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-206">Disable TLS 1.0 and 1.1 via registry import.</span></span>
8. <span data-ttu-id="bbbdb-207">Valide se as cargas de trabalho estão funcionando conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-207">Validate that workloads are functioning as expected.</span></span>
    - <span data-ttu-id="bbbdb-208">Se forem encontrados problemas, solucionar e resolver ou</span><span class="sxs-lookup"><span data-stu-id="bbbdb-208">If problems are encountered, troubleshoot and resolve, or</span></span>
    - <span data-ttu-id="bbbdb-209">Restaurar o registro da etapa 2 para habilitar novamente o TLS 1,0 e o 1,1</span><span class="sxs-lookup"><span data-stu-id="bbbdb-209">Restore registry from step 2 to re-enable TLS 1.0 and 1.1</span></span>
9. <span data-ttu-id="bbbdb-210">Valide se apenas o TLS 1,2 está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-210">Validate that only TLS 1.2 is being used.</span></span>

### <a name="install-prerequisites-to-all-servers"></a><span data-ttu-id="bbbdb-211">Instalar pré-requisitos em todos os servidores</span><span class="sxs-lookup"><span data-stu-id="bbbdb-211">Install prerequisites to all servers</span></span>

<span data-ttu-id="bbbdb-212">Uma atualização de dependência extensa é necessária antes de começar a desabilitar o TLS 1,0 e o 1,1 no nível do sistema operacional no Skype for Business Server 2015 implantações.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-212">Extensive dependency updating is required before you begin to disable TLS 1.0 and 1.1 at the operating system level in your Skype for Business Server 2015 deployments.</span></span> <span data-ttu-id="bbbdb-213">Veja a seguir as versões mínimas que podem dar suporte ao TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-213">The following are the minimum versions that can support TLS 1.2.</span></span> <span data-ttu-id="bbbdb-214">Implante todas as atualizações de pré-requisito em cada servidor do Skype for Business em seu ambiente antes de começar a desabilitar o TLS 1,0 e o 1,1.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-214">Deploy all prerequisite updates across every Skype for Business server in your environment before you begin disabling TLS 1.0 and 1.1.</span></span>

- <span data-ttu-id="bbbdb-215">Skype for Business Server 2015 CU9 6.0.9319.548 (2019 de maio) ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-215">Skype for Business Server 2015 CU9 6.0.9319.548 (May 2019) or higher</span></span>
- <span data-ttu-id="bbbdb-216">[.NET Framework 4,7](https://www.microsoft.com/download/details.aspx?id=55167) ou superior com o SchUseStrongCrypto habilitado no registro (fornecido abaixo)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-216">[.NET Framework 4.7](https://www.microsoft.com/download/details.aspx?id=55167) or higher with SchUseStrongCrypto enabled in the registry (provided below)</span></span>
- <span data-ttu-id="bbbdb-217">O SQL deve ser atualizado em todos os servidores do Skype for Business 2015 e nos back-ends.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-217">SQL must be updated on all Skype for Business 2015 servers and backends.</span></span> <span data-ttu-id="bbbdb-218">Atualize o pool de SQL do pool do SQL back ends primeiro e depois o respectivo FEs.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-218">Update Enterprise Edition Pool SQL Backends first, then their respective FEs.</span></span> 
    - <span data-ttu-id="bbbdb-219">[SQL server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926)ou superior/sql Server 2012 SP2 + CU16 ou superior/ [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014)ou superior/SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="bbbdb-219">[SQL Server 2014 SP1 + CU5](https://support.microsoft.com/help/3130926), or higher / SQL Server 2012 SP2 + CU16 or higher / [SQL Server 2014 RTM + CU12](https://support.microsoft.com/help/3130923/cumulative-update-12-for-sql-server-2014), or higher / SQL Server 2014 SP2</span></span>
     - [<span data-ttu-id="bbbdb-220">SQL Server Native Client para SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="bbbdb-220">SQL Server Native Client for SQL Server 2012</span></span>](https://www.microsoft.com/download/details.aspx?id=50402)
     - <span data-ttu-id="bbbdb-221">[Microsoft ODBC Driver 11 para SQL Server](https://www.microsoft.com/download/details.aspx?id=36434)ou superior</span><span class="sxs-lookup"><span data-stu-id="bbbdb-221">[Microsoft ODBC Driver 11 for SQL Server](https://www.microsoft.com/download/details.aspx?id=36434), or higher</span></span>
     - [<span data-ttu-id="bbbdb-222">Objetos de gerenciamento compartilhado para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="bbbdb-222">Shared Management Objects for SQL Server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=53164)
     - [<span data-ttu-id="bbbdb-223">SQLSysClrTypes para SQL Server 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="bbbdb-223">SQLSysClrTypes for SQL server 2014 SP2</span></span>](https://www.microsoft.com/download/details.aspx?id=42295)

### <a name="basic-steps-to-install-pre-requisites-in-recommended-order-of-operations"></a><span data-ttu-id="bbbdb-224">Etapas básicas para instalar pré-requisitos, em ordem de operações recomendada</span><span class="sxs-lookup"><span data-stu-id="bbbdb-224">Basic steps to install pre-requisites, in recommended order of operations</span></span>

1. <span data-ttu-id="bbbdb-225">Instale a atualização do Skype for Business Server CU9 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-225">Install the Skype for Business Server CU9 update to all servers.</span></span> 
    1. <span data-ttu-id="bbbdb-226">Instale a atualização dos componentes usando o atualizador.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-226">Install the update to components using the updater.</span></span>
    2. <span data-ttu-id="bbbdb-227">Atualize bancos de dados de acordo com os procedimentos documentados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-227">Update databases according to documented procedures.</span></span> <span data-ttu-id="bbbdb-228">Para o Skype for Business Server 2015, consulte KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-228">For Skype for Business Server 2015, see KB [3061064](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span>
    3. <span data-ttu-id="bbbdb-229">Valide a funcionalidade do produto na implantação antes de prosseguir com outras alterações.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-229">Validate product functionality in the deployment prior to moving forward with any other changes.</span></span>
2. <span data-ttu-id="bbbdb-230">Baixe o instalador offline do .NET 4,7.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-230">Download .NET 4.7 Offline Installer.</span></span> 
    1. <span data-ttu-id="bbbdb-231">Referencie[https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-231">Reference: [https://www.microsoft.com/download/details.aspx?id=55167](https://www.microsoft.com/download/details.aspx?id=55167)</span></span>
    2. <span data-ttu-id="bbbdb-232">Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-232">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
    3. <span data-ttu-id="bbbdb-233">Referencie[https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-233">Reference: [https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span></span>
    4. <span data-ttu-id="bbbdb-234">Ex (edição padrão):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-234">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
    5. <span data-ttu-id="bbbdb-235">Ex (edição Enterprise):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-235">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    6. <span data-ttu-id="bbbdb-236">Execute o pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-236">Run the installer package.</span></span>
    7. <span data-ttu-id="bbbdb-237">Reinicie o servidor.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-237">Reboot the server.</span></span>
3. <span data-ttu-id="bbbdb-238">Atualize o SQL Express 2014 em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-238">Update SQL Express 2014 on all servers.</span></span> 
    1. <span data-ttu-id="bbbdb-239">Referencie[https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-239">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)</span></span>
    2. <span data-ttu-id="bbbdb-240">Baixar o SQL 2014 SP2</span><span class="sxs-lookup"><span data-stu-id="bbbdb-240">Download SQL 2014 SP2</span></span> 
        - <span data-ttu-id="bbbdb-241">Referencie[https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-241">Reference: [https://www.microsoft.com/download/details.aspx?id=53168](https://www.microsoft.com/download/details.aspx?id=53168)</span></span>
    3. <span data-ttu-id="bbbdb-242">Copiar a mídia de instalação para uma pasta no servidor (por exemplo: C:\ 01_2014SqlSp2)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-242">Copy the installation media to a folder on the server (Ex: C:\01_2014SqlSp2)</span></span>
    4. <span data-ttu-id="bbbdb-243">Garantir que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end</span><span class="sxs-lookup"><span data-stu-id="bbbdb-243">Ensure Skype for Business Server 2015 services are stopped on the Front End server</span></span> 
        - <span data-ttu-id="bbbdb-244">Ex (edição padrão):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-244">Ex (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="bbbdb-245">Ex (edição Enterprise):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-245">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    5. <span data-ttu-id="bbbdb-246">Abrir um prompt de comando de administrador e atualizar todos os componentes e instâncias instalados</span><span class="sxs-lookup"><span data-stu-id="bbbdb-246">Open an Admin Command Prompt, and upgrade all installed components and instances</span></span> 
        - <span data-ttu-id="bbbdb-247">Exemplo: C:\ 01_2014SqlSp2 \SQLServer2014SP2-KB3171021-x64-ENU.exe/qs/IAcceptSQLServerLicenseTerms/Action = Patch/AllInstances</span><span class="sxs-lookup"><span data-stu-id="bbbdb-247">Example: C:\01_2014SqlSp2\SQLServer2014SP2-KB3171021-x64-ENU.exe /qs /IAcceptSQLServerLicenseTerms /Action=Patch /AllInstances</span></span>
4. <span data-ttu-id="bbbdb-248">Atualize o cliente nativo do SQL.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-248">Update SQL Native Client.</span></span> 
    1. <span data-ttu-id="bbbdb-249">Referência: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-249">Reference: [https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server).</span></span>
    2. <span data-ttu-id="bbbdb-250">Baixar de[https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-250">Download from [https://www.microsoft.com/download/details.aspx?id=50402](https://www.microsoft.com/download/details.aspx?id=50402)</span></span>
    3. <span data-ttu-id="bbbdb-251">Assegure-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-251">Ensure Skype for Business Server 2015 services are stopped on the Front End server.</span></span> 
        - <span data-ttu-id="bbbdb-252">Ex (edição padrão):```Stop-CsWindowsServices```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-252">Ex (Standard Edition): ```Stop-CsWindowsServices```</span></span>
        - <span data-ttu-id="bbbdb-253">Ex (edição Enterprise):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-253">Ex (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    4. <span data-ttu-id="bbbdb-254">Parar a execução de instâncias do SQL instaladas</span><span class="sxs-lookup"><span data-stu-id="bbbdb-254">Stop the SQL instances installed from running</span></span> 
        - <span data-ttu-id="bbbdb-255">Estendi```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-255">Ex: ```Get-Service 'MSSQL$RTCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="bbbdb-256">Estendi```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-256">Ex: ```Get-Service 'MSSQL$LYNCLOCAL' | Stop-Service```</span></span>
        - <span data-ttu-id="bbbdb-257">Exemplo (somente a edição padrão):```Get-Service 'MSSQL$RTC' | Stop-Service```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-257">Ex (Standard Edition Only): ```Get-Service 'MSSQL$RTC' | Stop-Service```</span></span>
    5. <span data-ttu-id="bbbdb-258">Atualize a atualização.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-258">Install the update.</span></span>
5. <span data-ttu-id="bbbdb-259">Atualize o ODBC Driver 11 para SQL Server para incluir o suporte para TLS 1,2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-259">Update ODBC Driver 11 for SQL Server to include support for TLS 1.2 (KB [3135244](https://support.microsoft.com/help/3135244/tls-1-2-support-for-microsoft-sql-server)).</span></span>
    1. <span data-ttu-id="bbbdb-260">Baixe o [ODBC Driver 11 para SQL Server-Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-260">Download [ODBC Driver 11 for SQL Server - Windows](https://www.microsoft.com/download/confirmation.aspx?id=36434).</span></span>
    2. <span data-ttu-id="bbbdb-261">Certifique-se de que os serviços do Skype for Business Server 2015 sejam interrompidos no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-261">Ensure that Skype for Business Server 2015 services are stopped on the Front End server.</span></span>
        - <span data-ttu-id="bbbdb-262">Exemplo (edição padrão):```Stop-CsWindowsService```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-262">Example (Standard Edition): ```Stop-CsWindowsService```</span></span>
        - <span data-ttu-id="bbbdb-263">Exemplo (Enterprise Edition):```Invoke-CsComputerFailover```</span><span class="sxs-lookup"><span data-stu-id="bbbdb-263">Example (Enterprise Edition): ```Invoke-CsComputerFailover```</span></span>
    3. <span data-ttu-id="bbbdb-264">Atualize a atualização.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-264">Install the update.</span></span>
6. <span data-ttu-id="bbbdb-265">Implantar as chaves de registro de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-265">Deploy prerequisite registry keys.</span></span>

### <a name="pre-requisite-registry-keys"></a><span data-ttu-id="bbbdb-266">Chaves do registro de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="bbbdb-266">Pre-requisite registry keys</span></span>

<span data-ttu-id="bbbdb-267">Copie/cole o teste a seguir no bloco de notas e renomeie TLSPreReq. reg ou um nome de sua escolha e, em seguida, importe:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-267">Copy/paste the following test into Notepad and rename TLSPreReq.reg or a name of your choice, then import:</span></span>

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

<span data-ttu-id="bbbdb-268">Para os back-ends do SQL para os pools do Enterprise Edition, os pré-requisitos e a desabilitação de TLS devem ser tratados como qualquer atualização do sistema operacional ou SQL. consulte:[https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-268">For SQL back ends for Enterprise Edition Pools, prerequisites and TLS disable should be treated as any SQL or OS updates would; refer to: [https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server](https://docs.microsoft.com/skypeforbusiness/manage/topology/patch-or-update-a-back-end-or-standard-edition-server)</span></span>

<span data-ttu-id="bbbdb-269">Embora o aplicativo de pré-requisito e as etapas de desabilitação de TLS possam ser combinados, recomendamos enfaticamente que todos os pré-requisitos sejam aplicados antes de prosseguir com a desativação do TLS 1,0 e do 1,1 no nível do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-269">While both the prerequisite application and TLS disabling steps can be combined, we strongly recommend all prerequisites be applied before proceeding with disabling of TLS 1.0 and 1.1 at the operating system level.</span></span> <span data-ttu-id="bbbdb-270">A abordagem de práticas recomendadas seria preparar o ambiente implantando todos os pré-requisitos, Validando se todas as cargas de trabalho funcionam corretamente e conforme o esperado e, em seguida, prosseguindo com o TLS 1.0/1.1 desabilitado em um momento posterior.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-270">The best practice approach would be to prepare the environment by deploying all prerequisites, validating that workloads all function correctly and as expected, and then proceeding with TLS 1.0/1.1 disable at a later time.</span></span>

### <a name="disable-tls-10-and-11-via-registry-import"></a><span data-ttu-id="bbbdb-271">Desabilitar o TLS 1,0 e o 1,1 via importação do registro</span><span class="sxs-lookup"><span data-stu-id="bbbdb-271">Disable TLS 1.0 and 1.1 via registry import</span></span>

<span data-ttu-id="bbbdb-272">Antes de prosseguir com as próximas etapas, *Verifique se você concluiu todos os pré-requisitos e os servidores do Skype for Business atualizados*.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-272">Before you proceed with the next steps, *make sure you have completed all prerequisites and updated Skype for Business Servers*.</span></span>

<span data-ttu-id="bbbdb-273">Copie o seguinte texto em um arquivo do bloco de notas e renomeie-o **TLSDisable. reg**:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-273">Copy the following text into a Notepad file and rename it **TLSDisable.reg**:</span></span>

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

<span data-ttu-id="bbbdb-274">Importe o arquivo. reg em cada servidor que você deseja desativar o TLS 1,0 e o 1,1.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-274">Import the .reg file on each server you wish to disable TLS 1.0 and 1.1.</span></span> <span data-ttu-id="bbbdb-275">Reinicie o servidor.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-275">Reboot the server.</span></span> <span data-ttu-id="bbbdb-276">Depois que os serviços voltam a ficar online, mover para o próximo servidor.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-276">Once the services have come back online, move to the next server.</span></span> <span data-ttu-id="bbbdb-277">A abordagem dos pools da edição Enterprise é a mesma que faria para qualquer atualização do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-277">The approach for Enterprise Edition Pools is the same you would take for any OS update.</span></span>

<span data-ttu-id="bbbdb-278">Você pode ter notado que estamos fazendo mais do que simplesmente desabilitar o TLS 1,0 e 1,1 aqui.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-278">You may have noticed we are doing more than just disabling TLS 1.0 and 1.1 here.</span></span> <span data-ttu-id="bbbdb-279">Estamos oferecendo o reordenamento do pacote de codificação (conforme mostrado acima) e a desativação de algumas cifras fracas mais antigas.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-279">We are supporting Cipher Suite re-order (as shown above) and the disabling of some older weak ciphers.</span></span> <span data-ttu-id="bbbdb-280">Esta é a primeira vez que damos suporte a essas alterações para a API SCHANNEL e crypto no Skype for Business Server, e é importante observar que essas alterações são as únicas para as quais damos suporte e que testamos no momento.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-280">This is the first time we have officially supported these changes to SCHANNEL and Crypto API on Skype for Business Server, and it is important to note that these changes are the only ones we support and have tested at this time.</span></span> <span data-ttu-id="bbbdb-281">Podemos considerar configurações adicionais no futuro, mas por enquanto, não modifique o arquivo de importação do registro na sua implementação.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-281">We may consider additional configurations in the future, but for now, please do not modify the registry import file in your implementation.</span></span>

### <a name="validate-that-workloads-are-functioning-as-expected"></a><span data-ttu-id="bbbdb-282">Validar que as cargas de trabalho estão funcionando como esperado</span><span class="sxs-lookup"><span data-stu-id="bbbdb-282">Validate that workloads are functioning as expected</span></span>

<span data-ttu-id="bbbdb-283">Quando o TLS 1,0 e o 1,1 estiverem desabilitados em seu ambiente, certifique-se de que todas as cargas de trabalho principais estejam funcionando como esperado, como mensagens instantâneas & presença, chamadas ponto a ponto, Enterprise Voice etc.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-283">Once TLS 1.0 and 1.1 have been disabled in your environment, ensure that all your main workloads are functioning as expected, such as IM & Presence, P2P calls, Enterprise Voice, etc.</span></span>

<span data-ttu-id="bbbdb-284">**Validar somente o TLS 1,2 está sendo usado**</span><span class="sxs-lookup"><span data-stu-id="bbbdb-284">**Validate only TLS 1.2 is being used**</span></span>

<span data-ttu-id="bbbdb-285">Faça com que sua equipe de segurança realize uma nova auditoria do tráfego do Skype for Business para garantir que os protocolos mais antigos TLS 1,0 e 1,1 não sejam mais usados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-285">Have your Security Team perform a new audit of Skype for Business traffic to ensure that the older protocols TLS 1.0 and 1.1 are no longer in use.</span></span>

<span data-ttu-id="bbbdb-286">Você também pode usar o Internet Explorer para testar conexões de TLS para serviços Web do Skype for Business Server 2015 após a desabilitação do TLS 1,0 e do TLS 1,1.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-286">Alternatively, you can use Internet Explorer to test TLS connections to web services from Skype for Business Server 2015 after TLS 1.0 and TLS 1.1 have been disabled.</span></span>

1. <span data-ttu-id="bbbdb-287">Inicie o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-287">Launch Internet Explorer.</span></span>
2. <span data-ttu-id="bbbdb-288">Selecione **ferramentas** > **Opções da Internet**.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-288">Select **Tools** > **Internet Options**.</span></span>
3. <span data-ttu-id="bbbdb-289">Selecione a guia **avançado** .</span><span class="sxs-lookup"><span data-stu-id="bbbdb-289">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="bbbdb-290">Em **configurações**, role até a parte inferior.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-290">Under **Settings**, scroll to the bottom.</span></span>
5. <span data-ttu-id="bbbdb-291">Verifique se o TLS 1,0, o TLS 1,1 e o TLS 1,2 estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-291">Verify that TLS 1.0, TLS 1.1, and TLS 1.2 are enabled.</span></span>
6. <span data-ttu-id="bbbdb-292">Procure a URL do serviço Web interno do pool do SfB 2015 (deve se conectar com êxito).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-292">Browse the Internal Web Service URL of your SfB 2015 pool (should connect successfully).</span></span>
7. <span data-ttu-id="bbbdb-293">Volte para o Internet Explorer e desabilite a opção para **usar somente TLS 1,2** .</span><span class="sxs-lookup"><span data-stu-id="bbbdb-293">Go back into Internet Explorer and disable the option to **Use TLS 1.2** only.</span></span>
8. <span data-ttu-id="bbbdb-294">Procure a URL do serviço Web interno do pool do SfB 2015 novamente (não deve se conectar).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-294">Browse the Internal Web Service URL of your SfB 2015 pool again (should fail to connect).</span></span>

![Opções da Internet](../../media/internet-options.jpg)

## <a name="advanced-deployment-scenarios"></a><span data-ttu-id="bbbdb-296">Cenários de implantação avançados</span><span class="sxs-lookup"><span data-stu-id="bbbdb-296">Advanced deployment scenarios</span></span>

<span data-ttu-id="bbbdb-297">Como alguns pré-requisitos de dependência são necessários para dar suporte a TLS 1,2 no Skype for Business ser 2015, a instalação a partir da mídia RTM falhará em qualquer sistema em que o TLS 1,0 e o 1,1 tenham sido desabilitados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-297">Because some dependency prerequisites are required to support TLS 1.2 in Skype for Business Ser 2015, installing from RTM media will fail on any system where TLS 1.0 and 1.1 have been disabled.</span></span>

<span data-ttu-id="bbbdb-298">**Implantar novos servidores de edição padrão ou pools da edição Enterprise após a desabilitação do TLS 1,0 e do 1,1 no seu ambiente.**</span><span class="sxs-lookup"><span data-stu-id="bbbdb-298">**Deploying New Standard Edition Servers or Enterprise Edition Pools once TLS 1.0 and 1.1 have been disabled in your environment.**</span></span>

<span data-ttu-id="bbbdb-299">**Opção 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-299">**Option 1:** Use [SmartSetup](../../deploy/install/install-skype-for-business-server.md).</span></span> <span data-ttu-id="bbbdb-300">Observe que estamos atualizando SmartSetup para acomodar os binários do SQL atualizados em uma futura RECOR e atualizar este artigo no futuro.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-300">Note that we are updating SmartSetup to accommodate the updated SQL binaries in a future CU, and will update this article in the future.</span></span>

<span data-ttu-id="bbbdb-301">**Opção 2:** Pré-instalar instâncias do SQL locais (RTCLOCAL e LYNCLOCAL)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-301">**Option 2:** Pre-install local SQL instances (RTCLOCAL and LYNCLOCAL)</span></span>

1. <span data-ttu-id="bbbdb-302">Baixe e copie o SQL Express 2014 SP2 (SQLEXPR_x64. exe) para a pasta local no FE.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-302">Download and copy SQL Express 2014 SP2 (SQLEXPR_x64.exe) to local folder on FE.</span></span> <span data-ttu-id="bbbdb-303">Digamos que o caminho da pasta <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-303">Let’s say folder path <SQL_FOLDER_PATH>.</span></span>
2. <span data-ttu-id="bbbdb-304">Inicie o PowerShell ou prompt de comando e navegue até <SQL_FOLDER_PATH>.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-304">Launch PowerShell or Command Prompt and navigate to <SQL_FOLDER_PATH>.</span></span>
3. <span data-ttu-id="bbbdb-305">Crie a instância do SQL RTCLOCAL executando o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-305">Create the RTCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="bbbdb-306">Aguarde até que o SQLEXPR_x64. exe termine antes de continuar:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-306">Wait until SQLEXPR_x64.exe finishes before proceeding:</span></span>

    <span data-ttu-id="bbbdb-307">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = RTCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = automatizar</span><span class="sxs-lookup"><span data-stu-id="bbbdb-307">SQLEXPR_x64.exe  /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=RTCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automati</span></span>
1. <span data-ttu-id="bbbdb-308">Crie a instância do SQL LYNCLOCAL executando o comando abaixo.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-308">Create the LYNCLOCAL SQL instance by running the command below.</span></span> <span data-ttu-id="bbbdb-309">Aguarde até que o SQLEXPR_x64. exe termine antes de prosseguir para a próxima etapa:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-309">Wait until SQLEXPR_x64.exe finishes before proceeding to the next step:</span></span>

    <span data-ttu-id="bbbdb-310">SQLEXPR_x64. exe/Q/IACCEPTSQLSERVERLICENSETERMS/UPDATEENABLED = 0/HIDECONSOLE/ACTION = INSTALL/FEATURES = SQLEngine, Tools/INSTANCENAME = LYNCLOCAL/TCPENABLED = 1/SQLSVCACCOUNT = "NT AUTHORITY\NetworkService"/SQLSYSADMINACCOUNTS = "Builtin\Administrators"/BROWSERSVCSTARTUPTYPE = "Automatic"/AGTSVCACCOUNT = "NTAUTHORITY\NetworkService"/SQLSVCSTARTUPTYPE = Automatic</span><span class="sxs-lookup"><span data-stu-id="bbbdb-310">SQLEXPR_x64.exe /Q /IACCEPTSQLSERVERLICENSETERMS /UPDATEENABLED=0 /HIDECONSOLE /ACTION=Install /FEATURES=SQLEngine,Tools /INSTANCENAME=LYNCLOCAL /TCPENABLED=1 /SQLSVCACCOUNT="NT AUTHORITY\NetworkService" /SQLSYSADMINACCOUNTS="Builtin\Administrators" /BROWSERSVCSTARTUPTYPE="Automatic" /AGTSVCACCOUNT="NTAUTHORITY\NetworkService" /SQLSVCSTARTUPTYPE=Automatic</span></span>
1. <span data-ttu-id="bbbdb-311">Executar a instalação do Skype for Business Server 2015 RTM.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-311">Run Skype for Business Server 2015 RTM setup.</span></span>
2. <span data-ttu-id="bbbdb-312">Siga as etapas restantes na seção pré-requisitos acima.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-312">Follow the remaining steps from the prerequisites section above.</span></span>

<span data-ttu-id="bbbdb-313">**Opção 3:** Você também pode substituir manualmente os binários em um diretório de mídia de instalação local da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-313">**Option 3:** You may also manually replace binaries in a local installation media directory as follows:</span></span>

1. [<span data-ttu-id="bbbdb-314">Instalar pré-requisitos para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bbbdb-314">Install prerequisites for Skype for Business Server</span></span>](../../deploy/install/install-prerequisites.md)  
2. <span data-ttu-id="bbbdb-315">Instale o .NET 4,7:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-315">Install .NET 4.7:</span></span> 
      - <span data-ttu-id="bbbdb-316">**Observação:** Primeiro, introduzimos o suporte para o .NET 4,7 no Skype for Business Server 2015 CU5 (6.0.9319.281).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-316">**Note:** We first introduced support for .NET 4.7 in Skype for Business Server 2015 CU5 (6.0.9319.281).</span></span> <span data-ttu-id="bbbdb-317">Portanto, em etapas mais adiante abaixo, atualizaremos os componentes principais antes da instalação principal.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-317">Therefore, in later steps below we will be updating Core Components prior to the main install.</span></span>
      - <span data-ttu-id="bbbdb-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-318">Download: https://www.microsoft.com/download/details.aspx?id=55167.</span></span> 
      - <span data-ttu-id="bbbdb-319">Referência: [software que deve ser instalado antes de uma implantação do Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-319">Reference: [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment)</span></span>
3. <span data-ttu-id="bbbdb-320">Copiar arquivos/pastas ISO:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-320">Copy ISO Files/Folders:</span></span> 
    - <span data-ttu-id="bbbdb-321">Com a ISO do Skype for Business Server 2015 anexada, abra o diretório raiz da unidade em que está conectado (ex: D\) : no explorador de arquivos).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-321">With the Skype for Business Server 2015 ISO attached, open the root directory of the drive it is attached as (Ex: D:\) in File Explorer.</span></span>
    - <span data-ttu-id="bbbdb-322">Copiar todas as pastas e arquivos para uma pasta em um disco local (por exemplo: C:\SkypeForBusiness2015ISO).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-322">Copy all folders and files to a folder on a local disk (Ex: C:\SkypeForBusiness2015ISO).</span></span>
    - <span data-ttu-id="bbbdb-323">**Observação:** Antes de instalar os componentes, alguns arquivos precisarão ser atualizados para dar suporte ao TLS 1,2.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-323">**Note:** Prior to installing components, some files will need to be updated for support of TLS 1.2.</span></span>
4. <span data-ttu-id="bbbdb-324">Substituir pacotes MSI/EXE:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-324">Replace MSI/EXE Packages:</span></span> 
    - <span data-ttu-id="bbbdb-325">Substitua os pacotes MSI e EXE existentes na pasta/Setup/AMD64/da mídia de instalação no computador local.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-325">Replace the existing MSI and EXE packages in the /Setup/amd64/ folder of the installation media on the local machine.</span></span>
    - <span data-ttu-id="bbbdb-326">SQL 2014 SP2 Express:https://www.microsoft.com/en-us/download/details.aspx?id=53167</span><span class="sxs-lookup"><span data-stu-id="bbbdb-326">SQL 2014 SP2 Express: https://www.microsoft.com/en-us/download/details.aspx?id=53167</span></span> 
        - <span data-ttu-id="bbbdb-327">Renomeie para SQLEXPR_x64 na máquina local e substitua o arquivo existente na pasta Setup/AMD64/da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-327">Rename to SQLEXPR_x64 on the local machine, and replace the existing file in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="bbbdb-328">Cliente SQL Native:https://www.microsoft.com/en-us/download/details.aspx?id=50402</span><span class="sxs-lookup"><span data-stu-id="bbbdb-328">SQL Native Client: https://www.microsoft.com/en-us/download/details.aspx?id=50402</span></span> 
        - <span data-ttu-id="bbbdb-329">**Observação:** Renomeie isso se necessário para sqlncli. msi e substitua o arquivo existente que existe na mídia de instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-329">**Note:** Rename this if necessary to sqlncli.msi, and then replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="bbbdb-330">Objetos de gerenciamento do SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="bbbdb-330">SQL Management Objects: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="bbbdb-331">**Observação:** O pacote de recursos terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-331">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="bbbdb-332">Selecione para baixar o SharedManagementObjects. msi apenas.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-332">Select to download SharedManagementObjects.msi only.</span></span>
        - <span data-ttu-id="bbbdb-333">**Observação:** Substitua o arquivo existente que existe na mídia de instalação/amd64/pasta da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-333">**Note:** Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
    - <span data-ttu-id="bbbdb-334">Tipos CLR SQL:https://www.microsoft.com/en-us/download/details.aspx?id=53164</span><span class="sxs-lookup"><span data-stu-id="bbbdb-334">SQL CLR Types: https://www.microsoft.com/en-us/download/details.aspx?id=53164</span></span> 
        - <span data-ttu-id="bbbdb-335">**Observação:** O pacote de recursos terá muitos itens que podem ser baixados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-335">**Note:** The Feature pack will have a lot of items that can be downloaded.</span></span> <span data-ttu-id="bbbdb-336">Selecione para baixar o CQLSysClrTypes. msi somente</span><span class="sxs-lookup"><span data-stu-id="bbbdb-336">Select to download CQLSysClrTypes.msi only</span></span>
        - <span data-ttu-id="bbbdb-337">**Observação**: substitua o arquivo existente que existe na pasta Setup/AMD64/da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-337">**Note**: Replace the existing file that exists in the Setup/amd64/ folder of the installation media.</span></span>
5. <span data-ttu-id="bbbdb-338">Instale os componentes principais:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-338">Install Core Components:</span></span> 
    - <span data-ttu-id="bbbdb-339">Execute setup. exe a partir da pasta Setup/AMD64/da mídia de instalação.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-339">Run Setup.exe from the Setup/amd64/ folder of the installation media.</span></span> <span data-ttu-id="bbbdb-340">Siga as instruções para instalar os componentes principais</span><span class="sxs-lookup"><span data-stu-id="bbbdb-340">Follow the instructions to install Core Components</span></span>
    - <span data-ttu-id="bbbdb-341">Feche os componentes principais.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-341">Close Core Components.</span></span>
6. <span data-ttu-id="bbbdb-342">Atualize os componentes principais:</span><span class="sxs-lookup"><span data-stu-id="bbbdb-342">Update Core Components:</span></span> 
    - <span data-ttu-id="bbbdb-343">Baixe o instalador da atualização do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-343">Download the Skype for Business Update Installer.</span></span>
    - <span data-ttu-id="bbbdb-344">Execute o instalador para atualizar os componentes principais e instalar os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-344">Run the installer to update Core Components and install the performance counters.</span></span>
    - <span data-ttu-id="bbbdb-345">**Observação:** Desde o lançamento do CU6HF2, o recurso de atualização automática atualmente só será instalado no CU6.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-345">**Note:** As of the release of CU6HF2, the auto-update feature currently only will install up to CU6.</span></span> <span data-ttu-id="bbbdb-346">Portanto, o atualizador deve ser executado separadamente para atualizar os componentes principais para o 6.0.9319.516.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-346">Therefore, the updater must be run separately to update Core Components to 6.0.9319.516.</span></span>
    - <span data-ttu-id="bbbdb-347">Referenciehttps://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span><span class="sxs-lookup"><span data-stu-id="bbbdb-347">Reference: https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015</span></span>
7. <span data-ttu-id="bbbdb-348">Instalar ferramentas administrativas (opcional):</span><span class="sxs-lookup"><span data-stu-id="bbbdb-348">Install Administrative Tools (Optional):</span></span> 
    - <span data-ttu-id="bbbdb-349">Isso instalará os tipos de Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64) e Microsoft System CLR para SQL Server 2014 (x64) usando os arquivos atualizados.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-349">This will install the Microsoft SQL Server 2012 Native Client, SQL Server 2014 Management Objects (x64), and Microsoft System CLR Types for SQL Server 2014 (x64) using the updated files.</span></span> <span data-ttu-id="bbbdb-350">Além disso, o construtor de topologia do Skype for Business Server 2015 e o painel de controle estarão disponíveis no computador local.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-350">Additionally, the Skype for Business Server 2015 Topology Builder and Control Panel will be available on the local machine.</span></span>
8. <span data-ttu-id="bbbdb-351">Instale o repositório de configuração local (etapa 1):</span><span class="sxs-lookup"><span data-stu-id="bbbdb-351">Install Local Configuration Store (Step 1):</span></span> 
     - <span data-ttu-id="bbbdb-352">Abra o assistente de implantação, clique em instalar ou atualizar o sistema do Skype for Business Server e clique em **executar** na etapa 1: instalar o repositório de configuração local.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-352">Open the Deployment Wizard, click Install or Update Skype for Business Server System, and click on **Run** at Step 1: Install Local Configuration Store.</span></span>
     - <span data-ttu-id="bbbdb-353">Clique em **Avançar** na caixa de diálogo **instalar repositório de configuração local** .</span><span class="sxs-lookup"><span data-stu-id="bbbdb-353">Click **Next** in the **Install Local Configuration Store** dialog box.</span></span>
     <span data-ttu-id="bbbdb-354">![Caixa de diálogo instalar repositório de configuração local](../../media/local-configuration-store.png)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-354">![Install Local Configuration Store dialog box](../../media/local-configuration-store.png)</span></span>
     - <span data-ttu-id="bbbdb-355">Examine os resultados e certifique-se de que o status da tarefa seja concluído.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-355">Review the results, and ensure that the Task Status is Completed.</span></span> <span data-ttu-id="bbbdb-356">Examine o arquivo de log resultante clicando em **Exibir log**.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-356">Review the resulting log file by clicking **View Log**.</span></span>
     <span data-ttu-id="bbbdb-357">![O status da tarefa é exibido como concluído](../../media/local-configuration-task-completed.png)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-357">![Task status shows as Completed](../../media/local-configuration-task-completed.png)</span></span>
     - <span data-ttu-id="bbbdb-358">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-358">Click **Finish**.</span></span>
9. <span data-ttu-id="bbbdb-359">Configurar ou remover componentes do Skype for Business Server (etapa 2):</span><span class="sxs-lookup"><span data-stu-id="bbbdb-359">Set up or remove Skype for Business Server Components (Step 2):</span></span>
    - <span data-ttu-id="bbbdb-360">Abra o assistente de implantação, clique em **instalar ou atualizar o sistema do Skype for Business Server**e clique em **executar** na etapa 2: configurar ou remover componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bbbdb-360">Open the Deployment Wizard, click **Install or Update Skype for Business Server System**, and click **Run** at Step 2: Set up or Remove Skype for Business Server Components</span></span>
    - <span data-ttu-id="bbbdb-361">Clique em **Avançar** na caixa de diálogo Configurar componentes do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-361">Click **Next** in the Set Up Skype for Business Server Components dialog box.</span></span>
    <span data-ttu-id="bbbdb-362">![a janela Configurar o Skype for Business Server Components](../../media/set-up-skype-for-business-server-components-window.png)</span><span class="sxs-lookup"><span data-stu-id="bbbdb-362">![the Set Up Skype for Business Server Components window](../../media/set-up-skype-for-business-server-components-window.png)</span></span>
    - <span data-ttu-id="bbbdb-363">Examine o log usando o log de exibição e valide se a configuração foi concluída sem problemas.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-363">Review the log using View Log, and validate that setup completed without issues.</span></span> 
    - <span data-ttu-id="bbbdb-364">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="bbbdb-364">Click **Finish**.</span></span>
10. <span data-ttu-id="bbbdb-365">Prossiga com a instalação e a configuração adicionais conforme necessário (você pode retomar os procedimentos de instalação normal neste ponto).</span><span class="sxs-lookup"><span data-stu-id="bbbdb-365">Proceed with additional installation and configuration as required (you can resume normal installation procedures at this point).</span></span>
