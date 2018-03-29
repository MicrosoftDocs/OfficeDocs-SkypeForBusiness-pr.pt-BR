---
title: Adicionar PSTN de Aparelho de Filial Persistente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Para definir o gateway PSTN (rede) telefônica comutada pública para um aparelho de filial persistente em um site de filial, especifique o seguinte:'
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="35c17-103">Adicionar PSTN de Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="35c17-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="35c17-104">Para definir o gateway PSTN (rede) telefônica comutada pública para um aparelho de filial persistente em um site de filial, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="35c17-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="35c17-105">Um nome de domínio totalmente qualificado (FQDN) ou o endereço IP para o par de gateway que o aparelho de filial persistente ou servidor de filial persistente está associado para roteamento de entrada e saída chamadas PSTN.</span><span class="sxs-lookup"><span data-stu-id="35c17-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="35c17-106">Se você estiver definindo um aparelho de filial persistente, este é o gateway ao qual o servidor de mediação dentro do aparelho de filial persistente se conectará para conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="35c17-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="35c17-p101">A porta de escuta a ser usada para mensagens SIP (Session Initiation Protocol). Por padrão, as portas são a 5066 para protocolo TCP e 5067 para o protocolo TLS em um gateway, central privada de comutação telefônica (PBX) ou SBC (Session Border Controller). As portas padrão são a 5081 para TCP e 5082 para TLS em um Aparelho de Filial Persistente em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="35c17-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="35c17-110">Por motivos de segurança, recomendamos que você use o TLS.</span><span class="sxs-lookup"><span data-stu-id="35c17-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="35c17-111">Se você estiver definindo um aparelho de filial persistente, consulte a documentação do fornecedor de aparelho de filial persistente para verificar se o seu aparelho de filial persistente suporta o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="35c17-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="35c17-112">Recomendamos, por motivos de segurança, que seja implantado um gateway que possa utilizar TLS.</span><span class="sxs-lookup"><span data-stu-id="35c17-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="35c17-113">Caso deseje adicionar um gateway PSTN, você pode configurá-lo depois, porém a funcionalidade total será limitada até que o gateway PSTN seja definido e configurado.</span><span class="sxs-lookup"><span data-stu-id="35c17-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

