---
title: Expansor de Configurações Gerais de Diretor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.DirectorGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2026d0dd-6745-4e53-8b44-acdc378b47d1
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar as configurações de um Diretor existente, é possível usar as seguintes seções:'
ms.openlocfilehash: 62dc9b855937d360a975e5e4035d662da276ce02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822621"
---
# <a name="director-general-settings-expander"></a><span data-ttu-id="633c3-103">Expansor de Configurações Gerais de Diretor</span><span class="sxs-lookup"><span data-stu-id="633c3-103">Director General Settings Expander</span></span>
 
<span data-ttu-id="633c3-104">Para editar as configurações de um Diretor existente, é possível usar as seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="633c3-104">To edit the settings for an existing Director, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="633c3-105">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="633c3-105">General settings</span></span>
    
- <span data-ttu-id="633c3-106">Serviços Web</span><span class="sxs-lookup"><span data-stu-id="633c3-106">Web services</span></span>
    

## <a name="general-settings"></a><span data-ttu-id="633c3-107">Configurações gerais</span><span class="sxs-lookup"><span data-stu-id="633c3-107">General settings</span></span>

<span data-ttu-id="633c3-p101">Nome de domínio totalmente qualificado (FQDN) do Diretor. Edite o FQDN do servidor para alterar o valor. É necessário ter um registro (A) de host DNS (Sistema de Nome de Domínio) que coincida com o novo valor.</span><span class="sxs-lookup"><span data-stu-id="633c3-p101">Fully qualified domain name (FQDN) of the Director pool. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="633c3-111">Em **Associações** você pode editar ou especificar:</span><span class="sxs-lookup"><span data-stu-id="633c3-111">In **Associations** you can edit or specify the following:</span></span>
  
<span data-ttu-id="633c3-112">Compartilhamento de arquivo para o pool de Diretores a ser usado.</span><span class="sxs-lookup"><span data-stu-id="633c3-112">File share for the Director pool to use.</span></span> <span data-ttu-id="633c3-113">Selecione um compartilhamento de arquivos existente que já tenha sido definido no Construtor de Topologias ou clique em **Novo** para criar uma nova definição de compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="633c3-113">Select an existing file share that has already been defined in Topology Builder, or click **New** to create a new file share definition.</span></span>
  
<span data-ttu-id="633c3-114">Monitorando o SQL Server Store.</span><span class="sxs-lookup"><span data-stu-id="633c3-114">Monitoring SQL Server store.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="633c3-p103">Antes de publicar a topologia recém-definida, o servidor especificado precisa existir e fazer parte do domínio. Se você tiver criado um novo compartilhamento de arquivo, ele deverá ter sido no servidor designado por você.</span><span class="sxs-lookup"><span data-stu-id="633c3-p103">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain. If you created a new file share, the file share must be created on the server that you designate.</span></span> 
  
## <a name="web-services"></a><span data-ttu-id="633c3-117">Serviços Web</span><span class="sxs-lookup"><span data-stu-id="633c3-117">Web services</span></span>

<span data-ttu-id="633c3-118">Para editar ou especificar configurações adicionais para os Serviços Web no pool de Diretores, modifique ou especifique as configurações nos Serviços Web Internos e nos Serviços Web Externos.</span><span class="sxs-lookup"><span data-stu-id="633c3-118">To edit or specify additional settings for the Web services on the Director pool, you modify or specify settings in the Internal Web services and External Web services.</span></span>
  
<span data-ttu-id="633c3-119">Para **Serviços Web internos**, é possível especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="633c3-119">For **Internal web services** you can specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="633c3-120">Se você tiver mais de um pool de Front-End ou Servidor Front End, o FQDN dos serviços Web externos deverá ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="633c3-120">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="633c3-121">Por exemplo, se você definir o FQDN de serviços Web externos de um Servidor front-end como **pool01.contoso.com**, não poderá usar o **pool01.contoso.com** para outro pool de front-end ou servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="633c3-121">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="633c3-122">Se você também estiver implantando Diretores, o FQDN de serviços Web externos definido para qualquer Diretor ou pool de Diretores deverá ser exclusivo de qualquer outro Diretor ou pool de Diretores, bem como de qualquer pool de Front-End ou Servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="633c3-122">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="633c3-123">Se você decidir substituir os serviços Web internos por um FQDN autodefina, cada FQDN deverá ser exclusivo de qualquer outro pool de Front-End, Diretor ou pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="633c3-123">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
<span data-ttu-id="633c3-p105">Se você selecionou Substituir FQDN, poderá especificar um FQDN diferente para a identidade dos Serviços Web internos no pool. Por padrão, a configuração é o nome do pool atual, conforme definido para o pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="633c3-p105">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the pool. By default, the setting is the current pool name as defined for the Director pool.</span></span>
  
<span data-ttu-id="633c3-p106">É possível especificar portas de escuta e de publicação para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão da porta 80 para HTTP e da porta 443 para HTTPS são as configurações mais comuns e normalmente não precisam ser alteradas, a menos que você tenha requisitos específicos dentro de sua organização e design de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="633c3-p106">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
  
<span data-ttu-id="633c3-128">Para **Serviços Web externos**, é possível especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="633c3-128">For **External web services**, you can specify the following:</span></span>
  
<span data-ttu-id="633c3-p107">É possível definir o FQDN dos Serviços Web externos. O FQDN especificado aqui será normalmente definido pelos requisitos de seus requisitos de conexão externa, como o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="633c3-p107">You can define the FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
  
<span data-ttu-id="633c3-p108">É possível especificar portas de escuta e de publicação para HTTP e HTTPS exigidas pela sua implantação. As configurações padrão da porta 8080 para HTTP e da porta 4443 para HTTPS são definidas inicialmente. Altere essas configurações para as portas de escuta com base nos requisitos de proxy reverso e de rede externa. As portas publicadas são definidas por padrão como porta 80 para HTTP e porta 443 para HTTPS. Esses valores determinam quais portas o pool de Diretores ou servidor de Diretor escutará para solicitações de entrada. Normalmente, elas não precisam ser alteradas, a menos que haja conflito de requisitos de porta no pool. Espera-se portas de publicação internas e externas que usam os mesmos valores de porta. Isso não é um conflito.</span><span class="sxs-lookup"><span data-stu-id="633c3-p108">You can specify listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. The published ports are set to default of port 80 for HTTP and port 443 for HTTPS. These values determine what ports the Director pool or Director server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the pool. Internal and external published ports that use the same port values are expected. This is not a conflict.</span></span>
  

