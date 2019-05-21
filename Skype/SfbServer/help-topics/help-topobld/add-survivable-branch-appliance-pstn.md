---
title: Adicionar PSTN de Aparelho de Filial Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Para definir o gateway PSTN (rede telefônica pública comutada) para um aparelho de ramificação sobreviventes em um site de filial, especifique o seguinte:'
ms.openlocfilehash: 3a146a5bf9b879681b0d490a1d03198853c72305
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303663"
---
# <a name="add-survivable-branch-appliance-pstn"></a><span data-ttu-id="96d0b-103">Adicionar PSTN de Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="96d0b-103">Add Survivable Branch Appliance PSTN</span></span>
 
<span data-ttu-id="96d0b-104">Para definir o gateway PSTN (rede telefônica pública comutada) para um aparelho de ramificação sobreviventes em um site de filial, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="96d0b-104">To define the public switched telephone network (PSTN) gateway for a Survivable Branch Appliance at a branch site, specify the following:</span></span> 
  
- <span data-ttu-id="96d0b-105">Um FQDN (nome de domínio totalmente qualificado) ou um endereço IP para o par de gateways ao qual o aplicativo de ramificação sobreviventes ou o servidor de ramificação sobreviventes está associado para chamadas PSTN de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="96d0b-105">A fully qualified domain name (FQDN) or IP address for the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound and outbound PSTN calls.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="96d0b-106">Se você estiver definindo um aparelho de ramificação sobreviventes, esse é o gateway ao qual o servidor de mediação dentro da ramificação de ramificação sobreviventes se conectará para conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="96d0b-106">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span> 
  
- <span data-ttu-id="96d0b-p101">A porta de escuta a ser usada para mensagens SIP (Session Initiation Protocol). Por padrão, as portas são a 5066 para protocolo TCP e 5067 para o protocolo TLS em um gateway, central privada de comutação telefônica (PBX) ou SBC (Session Border Controller). As portas padrão são a 5081 para TCP e 5082 para TLS em um Aparelho de Filial Persistente em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="96d0b-p101">The listening port to be used for Session Initiation Protocol (SIP) messages. By default, the ports are 5066 for Transmission Control Protocol (TCP) and 5067 for Transport Layer Security (TLS) on a gateway, private branch exchange (PBX), or Session Border Controller (SBC). On a Survivable Branch Appliance at a branch site, the default ports are 5081 for TCP and 5082 for TLS.</span></span>
    
- <span data-ttu-id="96d0b-110">Por motivos de segurança, recomendamos que você use o TLS.</span><span class="sxs-lookup"><span data-stu-id="96d0b-110">For security reasons, we strongly recommend that you use TLS.</span></span> <span data-ttu-id="96d0b-111">Se você estiver definindo um aparelho de ramificação sobreviventes, confira a documentação do fornecedor da sua agência de ramificação sobreviventes para verificar se o seu aparelho de ramificação sobreviventes é compatível com o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="96d0b-111">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="96d0b-112">Recomendamos, por motivos de segurança, que seja implantado um gateway que possa utilizar TLS.</span><span class="sxs-lookup"><span data-stu-id="96d0b-112">For security reasons, we strongly recommended that you deploy a gateway that can use TLS.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="96d0b-113">Caso deseje adicionar um gateway PSTN, você pode configurá-lo depois, porém a funcionalidade total será limitada até que o gateway PSTN seja definido e configurado.</span><span class="sxs-lookup"><span data-stu-id="96d0b-113">If you want to add a PSTN gateway, you can set it up later, but full functionality will be limited until the PSTN gateway is defined and configured.</span></span> 
  

