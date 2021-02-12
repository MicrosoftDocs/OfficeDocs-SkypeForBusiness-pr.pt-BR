---
title: Configurar troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Resumo: saiba como configurar um tronco entre um Servidor de Mediação e pares do Enterprise Voice no Skype for Business Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824951"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="08768-103">Configurar troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="08768-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="08768-104">**Resumo:** Saiba como configurar um tronco entre um Servidor de Mediação e pares do Enterprise Voice no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="08768-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="08768-105">Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um Servidor de Mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutado) para clientes e dispositivos Enterprise Voice em sua organização:</span><span class="sxs-lookup"><span data-stu-id="08768-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="08768-106">Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="08768-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="08768-107">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="08768-107">PSTN gateway</span></span>
    
- <span data-ttu-id="08768-108">Central privada de comutação telefônica (PBX)</span><span class="sxs-lookup"><span data-stu-id="08768-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="08768-109">Para obter mais detalhes, [consulte Plano para conectividade PSTN no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)</span><span class="sxs-lookup"><span data-stu-id="08768-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="08768-110">A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e Servidores de Mediação.</span><span class="sxs-lookup"><span data-stu-id="08768-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="08768-111">Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool de Servidor de Mediação e um gateway PSTN (Rede Telefônica Pública Comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="08768-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="08768-112">Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).</span><span class="sxs-lookup"><span data-stu-id="08768-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="08768-113">Para atribuir ou remover um tronco no Skype for Business Server, você deve primeiro definir um tronco no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="08768-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="08768-114">Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do Servidor de Mediação, a porta de escuta do Servidor de Mediação, o FQDN do gateway e a porta de escuta do gateway.</span><span class="sxs-lookup"><span data-stu-id="08768-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="08768-115">Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="08768-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="08768-116">Isso fornece resiliência adicional para a infraestrutura do Enterprise Voice, que é especialmente útil em cenários interoperacionais pbx (central privada de computação).</span><span class="sxs-lookup"><span data-stu-id="08768-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="08768-117">Quando um tronco é definido, ele deve ser associado a uma rota.</span><span class="sxs-lookup"><span data-stu-id="08768-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="08768-118">Para associar um tronco a uma rota, defina um nome simples para o tronco no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="08768-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="08768-119">Esse nome simples é usado como o nome do tronco no Painel de Controle do Skype for Business Server, onde os troncos podem ser associados a rotas.</span><span class="sxs-lookup"><span data-stu-id="08768-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="08768-120">O nome do tronco simples é usado como o nome do gateway do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="08768-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="08768-121">O administrador deve selecionar um tronco padrão associado a um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="08768-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="08768-122">No Construtor de Topologias, clique com o botão direito do mouse no Servidor de Mediação associado e clique em **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="08768-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="08768-123">Especifique o gateway padrão para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="08768-123">Specify the default gateway for the Mediation Server.</span></span> 
  

