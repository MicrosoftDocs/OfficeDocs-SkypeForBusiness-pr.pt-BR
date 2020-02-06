---
title: Suporte a vários troncos no Skype for Business Server
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
description: A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e servidores de mediação. Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP. Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).
ms.openlocfilehash: 6f950f089d23687f0215bd9db1f253eb57c17c75
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816941"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="0d164-105">Suporte a vários troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0d164-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="0d164-106">A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e servidores de mediação.</span><span class="sxs-lookup"><span data-stu-id="0d164-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="0d164-107">Essas associações são feitas pela definição de um tronco, que é uma associação lógica entre um pool do servidor de mediação e um gateway de rede telefônica pública comutada (SBC), ou PBX IP.</span><span class="sxs-lookup"><span data-stu-id="0d164-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="0d164-108">Use o construtor de topologias para associar gateways a servidores de mediação (ou seja, troncos).</span><span class="sxs-lookup"><span data-stu-id="0d164-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="0d164-109">Para atribuir ou remover um tronco no Skype for Business Server, primeiro você deve definir um tronco no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0d164-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="0d164-110">Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do servidor de mediação, a porta de escuta do servidor de mediação, o FQDN do gateway e a porta de escuta do gateway.</span><span class="sxs-lookup"><span data-stu-id="0d164-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="0d164-111">Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="0d164-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="0d164-112">Isso fornece resiliência adicional à infraestrutura Enterprise Voice, que é especialmente útil em cenários de interoperabilidade de PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="0d164-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="0d164-113">Quando um tronco é definido, ele precisa ser associado à rota.</span><span class="sxs-lookup"><span data-stu-id="0d164-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="0d164-114">Para associar um tronco a uma rota, você define um nome simples para o tronco no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0d164-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="0d164-115">Esse nome simples é usado como o nome do tronco no painel de controle do Skype for Business Server, em que os troncos podem ser associados às rotas.</span><span class="sxs-lookup"><span data-stu-id="0d164-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="0d164-116">O nome do tronco simples é usado como o nome do gateway do Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0d164-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="0d164-117">O administrador deve selecionar um tronco padrão associado a um servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="0d164-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="0d164-118">No construtor de topologias, clique com o botão direito do mouse no servidor de mediação associado e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0d164-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="0d164-119">Especifique o gateway padrão do servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="0d164-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="0d164-120">O diagrama a seguir ilustra os vários troncos que são definidos para cada servidor e gateway de mediação.</span><span class="sxs-lookup"><span data-stu-id="0d164-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Várias atribuições de tronco](../../media/multiple-trunk-assignments.jpg)
