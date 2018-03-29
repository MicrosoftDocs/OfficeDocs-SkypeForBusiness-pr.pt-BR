---
title: Configurar troncos no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumo: Saiba como configurar um tronco entre um servidor de mediação e parceiros para o Enterprise Voice no Skype para Business Server 2015.'
ms.openlocfilehash: a2630d3e37e6ab15a0e88593549e9365ac69a3e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="d1913-103">Configurar troncos no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d1913-103">Configure trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d1913-104">**Resumo:** Saiba como configurar um tronco entre um servidor de mediação e parceiros para o Enterprise Voice no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d1913-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d1913-105">Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes computadores para fornecer conectividade PSTN (rede) telefônica pública comutada clientes Enterprise Voice e dispositivos em sua organização:</span><span class="sxs-lookup"><span data-stu-id="d1913-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="d1913-106">Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="d1913-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="d1913-107">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="d1913-107">PSTN gateway</span></span>
    
- <span data-ttu-id="d1913-108">Central privada de comutação telefônica (PBX)</span><span class="sxs-lookup"><span data-stu-id="d1913-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="d1913-109">Para obter mais detalhes, consulte [Planejar a conectividade PSTN em Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="d1913-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="d1913-110">Skype para a funcionalidade do Business Server suporta vários associações entre gateways e servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="d1913-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="d1913-111">Essas associações são feitas por meio da definição de um tronco, que é uma associação de lógica entre um pool do servidor de mediação e um gateway PSTN (rede) telefônica pública comutada, controlador de borda de sessão (SBC) ou IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="d1913-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="d1913-112">Use o construtor de topologia para associar os gateways com servidores de mediação (ou seja, troncos).</span><span class="sxs-lookup"><span data-stu-id="d1913-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="d1913-113">Para atribuir ou remover um tronco no Skype para Business Server, você deve definir um tronco no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="d1913-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="d1913-114">Consiste em um tronco a associação a seguir: servidor de mediação totalmente qualificado (FQDN) do nome de domínio, a porta de escuta do servidor de mediação, o gateway FQDN e a porta de escuta do gateway.</span><span class="sxs-lookup"><span data-stu-id="d1913-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="d1913-115">Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="d1913-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="d1913-116">Isso oferece resiliência adicional a infraestrutura do Enterprise Voice, o que é especialmente útil em cenários interoperational do privada de comutação telefônica (PBX).</span><span class="sxs-lookup"><span data-stu-id="d1913-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="d1913-117">Quando um tronco é definido, ele precisa ser associado à rota.</span><span class="sxs-lookup"><span data-stu-id="d1913-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="d1913-118">Para associar um tronco a uma rota, você pode definir um nome simples para o tronco no construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="d1913-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="d1913-119">Esse nome simple é usado como o nome do tronco no Skype para painel de controle do Business Server, onde troncos podem ser associados a rotas.</span><span class="sxs-lookup"><span data-stu-id="d1913-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="d1913-120">O nome do tronco simples é usado como o nome de gateway a partir do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d1913-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="d1913-121">O administrador deve selecionar um tronco padrão associado a um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="d1913-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="d1913-122">No Topology Builder, com o botão direito do servidor de mediação associado e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d1913-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="d1913-123">Especifique o gateway padrão para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="d1913-123">Specify the default gateway for the Mediation Server.</span></span> 
  

