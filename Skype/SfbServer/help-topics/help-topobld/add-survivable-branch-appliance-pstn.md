---
title: Adicionar Aparelho PSTN a Filial Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Para definir o gateway da rede telefônica pública comutada (PSTN) para um Aparelho de Filial Persistente de um local de filial, especifique o seguinte:'
ms.openlocfilehash: 477aa014d6b4450dae3422e6893e7f7f0a48c703
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217072"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="1882f-103">Adicionar Aparelho PSTN a Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="1882f-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="1882f-104">Para definir o gateway da rede telefônica pública comutada (PSTN) para um Aparelho de Filial Persistente de um local de filial, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1882f-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="1882f-105">Um FQDN (nome de domínio totalmente qualificado) ou endereço IP para o par de gateway ao qual o Aparelho de Filial Persistente ou Servidor de Filial Persistente está associado, para roteamento de chamadas PSTN de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="1882f-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1882f-106">Se você está definindo um Aparelho de Filial Persistente, este é o gateway ao qual o Servidor de Mediação dentro do Aparelho de Filial Persistente se conectará para obter conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="1882f-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="1882f-p101">A porta de escuta a ser usada para mensagens SIP (Session Initiation Protocol). Por padrão, as portas são a 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security) em um gateway, PBX (private branch exchange) ou SBC (Session Border Controller). As portas padrão são a 5081 para TCP e 5082 para TLS em um Aparelho de Filial Persistente em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="1882f-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="1882f-p102">Recomendamos que utilize TLS por razões de segurança. Caso esteja definindo um Aparelho de Filial Persistente, consulte sua documentação do fornecedor do Aparelho de Filial Persistente para verificar se o seu Aparelho de Filial Persistente é compatível com protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="1882f-p102">For security reasons, we strongly recommend that you use TLS. If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1882f-112">Recomendamos, por motivos de segurança, que seja implantado um gateway que possa utilizar TLS.</span><span class="sxs-lookup"><span data-stu-id="1882f-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1882f-113">Caso deseje adicionar um gateway PSTN, você pode montá-lo mais tarde porém a funcionalidade total será limitada até que o gateway PSTN seja definido e configurado.</span><span class="sxs-lookup"><span data-stu-id="1882f-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

