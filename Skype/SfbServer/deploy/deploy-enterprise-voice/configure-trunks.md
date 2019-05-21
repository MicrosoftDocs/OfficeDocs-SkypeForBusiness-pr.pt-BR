---
title: Configurar troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumo: saiba como configurar um tronco entre um servidor de mediação e os pares para Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: 5e5fc044e5217ef4661e716ba02ba286c7a631f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289094"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="55b87-103">Configurar troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="55b87-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="55b87-104">**Resumo:** Saiba como configurar um tronco entre um servidor de mediação e os pares para Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="55b87-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="55b87-105">Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutada) para clientes e dispositivos do Enterprise Voice em sua organização:</span><span class="sxs-lookup"><span data-stu-id="55b87-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="55b87-106">Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="55b87-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="55b87-107">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="55b87-107">PSTN gateway</span></span>
    
- <span data-ttu-id="55b87-108">Central privada de comutação telefônica (PBX)</span><span class="sxs-lookup"><span data-stu-id="55b87-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="55b87-109">Para obter mais detalhes, consulte [planejar conectividade PSTN no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="55b87-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="55b87-110">A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="55b87-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="55b87-111">Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP.</span><span class="sxs-lookup"><span data-stu-id="55b87-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="55b87-112">Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).</span><span class="sxs-lookup"><span data-stu-id="55b87-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="55b87-113">Para atribuir ou remover um tronco no Skype for Business Server, primeiro você deve definir um tronco no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="55b87-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="55b87-114">Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.</span><span class="sxs-lookup"><span data-stu-id="55b87-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="55b87-115">Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="55b87-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="55b87-116">Isso fornece resiliência adicional à infraestrutura Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="55b87-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="55b87-117">Quando um tronco é definido, ele precisa ser associado à rota.</span><span class="sxs-lookup"><span data-stu-id="55b87-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="55b87-118">Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="55b87-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="55b87-119">Esse nome simples é usado como o nome do tronco no painel de controle do Skype for Business Server, em que os troncos podem ser associados às rotas.</span><span class="sxs-lookup"><span data-stu-id="55b87-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="55b87-120">O nome do tronco simples é usado como o nome do gateway do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="55b87-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="55b87-121">O administrador deve selecionar um tronco padrão associado a um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="55b87-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="55b87-122">No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="55b87-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="55b87-123">Especifique o gateway padrão do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="55b87-123">Specify the default gateway for the Mediation Server.</span></span> 
  

