---
title: Expansor de Configurações Gerais de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
description: 'Para editar as configurações de um director existente, você verá as seguintes seções:'
ms.openlocfilehash: e6fb587484cd4024e69c8630e49f95a978ec747a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820123"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="ca1db-103">Expansor de Configurações Gerais de Diretor</span><span class="sxs-lookup"><span data-stu-id="ca1db-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="ca1db-104">Para editar as configurações de um director existente, você verá as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="ca1db-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="ca1db-105">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="ca1db-105">General settings</span></span>
    
- <span data-ttu-id="ca1db-106">Serviços Web</span><span class="sxs-lookup"><span data-stu-id="ca1db-106">Web services</span></span>
    


## <a name="general-settings"></a><span data-ttu-id="ca1db-107">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="ca1db-107">General settings</span></span>

<span data-ttu-id="ca1db-108">FQDN (nome de domínio totalmente qualificado) do pool do diretor.</span><span class="sxs-lookup"><span data-stu-id="ca1db-108">Fully qualified domain name (FQDN) of the Director pool.</span></span> <span data-ttu-id="ca1db-109">Edite o FQDN do servidor para alterar o valor.</span><span class="sxs-lookup"><span data-stu-id="ca1db-109">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="ca1db-110">É necessário ter um registro (A) de host de Sistema de Nomes de Domínio (DNS) que coincida com o novo valor.</span><span class="sxs-lookup"><span data-stu-id="ca1db-110">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="ca1db-111">Em **Associações**, você pode editar ou especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ca1db-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="ca1db-112">Compartilhamento de arquivos para uso do pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="ca1db-112">File share for the Director pool to use.</span></span> <span data-ttu-id="ca1db-113">Selecione um compartilhamento de arquivo existente que já foi definido no construtor de topologias ou clique em **novo** para criar uma nova definição de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ca1db-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="ca1db-114">Monitorar a loja do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ca1db-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca1db-115">Antes da publicação da topologia recém-definida, o servidor especificado precisa existir e ter ingressado no domínio.</span><span class="sxs-lookup"><span data-stu-id="ca1db-115">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> <span data-ttu-id="ca1db-116">Se você criou um novo compartilhamento de arquivos, o compartilhamento de arquivos deve ser criado no servidor que você designar.</span><span class="sxs-lookup"><span data-stu-id="ca1db-116">If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="ca1db-117">Serviços Web</span><span class="sxs-lookup"><span data-stu-id="ca1db-117">Web services</span></span>

<span data-ttu-id="ca1db-118">Para editar ou especificar configurações adicionais para os serviços Web no pool de diretor, você modifica ou especifica as configurações nos serviços Web internos e nos serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="ca1db-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="ca1db-119">Para **Serviços Web internos** , você pode especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ca1db-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ca1db-120">Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos.</span><span class="sxs-lookup"><span data-stu-id="ca1db-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="ca1db-121">Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como **pool01.contoso.com**, não será possível usar o **pool01.contoso.com** para outro pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ca1db-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="ca1db-122">Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="ca1db-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="ca1db-123">Se você decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="ca1db-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="ca1db-124">Se você selecionar Substituir FQDN, poderá especificar um FQDN diferente para a identidade dos serviços Web internos no pool.</span><span class="sxs-lookup"><span data-stu-id="ca1db-124">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool.</span></span> <span data-ttu-id="ca1db-125">Por padrão, a configuração é o nome do pool atual conforme definido para o pool do diretor.</span><span class="sxs-lookup"><span data-stu-id="ca1db-125">By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="ca1db-126">Você pode especificar portas de escuta e publicadas para HTTP e HTTPS que a implantação requer.</span><span class="sxs-lookup"><span data-stu-id="ca1db-126">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="ca1db-127">A configuração padrão da porta 80 para HTTP e porta 443 para HTTPS são as configurações mais comuns e normalmente não precisa ser alterada, a menos que você tenha requisitos específicos dentro de sua organização e design de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="ca1db-127">The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="ca1db-128">Para **Serviços Web externos**, você pode especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ca1db-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="ca1db-129">Você pode definir o FQDN dos serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="ca1db-129">You can define the FQDN of the External Web services.</span></span> <span data-ttu-id="ca1db-130">O FQDN especificado aqui será normalmente definido pelos seus requisitos de conexão externa, como o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="ca1db-130">The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="ca1db-131">Você pode especificar portas de escuta e publicadas para HTTP e HTTPS que a implantação requer.</span><span class="sxs-lookup"><span data-stu-id="ca1db-131">You can specify listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="ca1db-132">As configurações padrão da porta 8080 para HTTP e da porta 4443 para HTTPS são definidas inicialmente.</span><span class="sxs-lookup"><span data-stu-id="ca1db-132">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="ca1db-133">Você poderá alterar essas configurações para as portas de escuta com base nos requisitos de proxy reverso e de rede externa.</span><span class="sxs-lookup"><span data-stu-id="ca1db-133">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="ca1db-134">As portas publicadas são definidas como padrão de porta 80 para HTTP e porta 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ca1db-134">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="ca1db-135">Esses valores determinam quais portas o pool do diretor ou o servidor diretor escutará solicitações de entrada.</span><span class="sxs-lookup"><span data-stu-id="ca1db-135">These values determine what ports the Director pool or Director server will listen for incoming requests.</span></span> <span data-ttu-id="ca1db-136">Geralmente, eles não precisam ser alterados, a menos que haja conflito de requisitos de porta no pool.</span><span class="sxs-lookup"><span data-stu-id="ca1db-136">Typically, these do not need to be changed, unless there is conflict of port requirements on the pool.</span></span> <span data-ttu-id="ca1db-137">Portas publicadas internas e externas que usam os mesmos valores de porta são esperadas.</span><span class="sxs-lookup"><span data-stu-id="ca1db-137">Internal and external published ports that use the same port values are expected.</span></span> <span data-ttu-id="ca1db-138">Isso não é um conflito.</span><span class="sxs-lookup"><span data-stu-id="ca1db-138">This is not a conflict.</span></span>
  

