---
title: Suporte a vários troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e Servidores de Mediação. Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool de Servidor de Mediação e um gateway PSTN (Rede Telefônica Pública Comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX. Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826221"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="51939-105">Suporte a vários troncos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="51939-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="51939-106">A funcionalidade do Skype for Business Server oferece suporte a várias associações entre gateways e Servidores de Mediação.</span><span class="sxs-lookup"><span data-stu-id="51939-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="51939-107">Essas associações são feitas definindo um tronco, que é uma associação lógica entre um pool de Servidor de Mediação e um gateway PSTN (Rede Telefônica Pública Comutado), Controlador de Borda de Sessão (SBC) ou IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="51939-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="51939-108">Use o Construtor de Topologias para associar gateways a Servidores de Mediação (ou seja, troncos).</span><span class="sxs-lookup"><span data-stu-id="51939-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="51939-109">Para atribuir ou remover um tronco no Skype for Business Server, você deve primeiro definir um tronco no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="51939-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="51939-110">Um tronco consiste na seguinte associação: nome de domínio totalmente qualificado (FQDN) do Servidor de Mediação, a porta de escuta do Servidor de Mediação, o FQDN do gateway e a porta de escuta do gateway.</span><span class="sxs-lookup"><span data-stu-id="51939-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="51939-111">Para configurar vários troncos, você pode criar várias associações entre o mesmo gateway e o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="51939-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="51939-112">Isso fornece resiliência adicional para a infraestrutura do Enterprise Voice, que é especialmente útil em cenários interoperacionais pbx (central privada de computação).</span><span class="sxs-lookup"><span data-stu-id="51939-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="51939-113">Quando um tronco é definido, ele deve ser associado a uma rota.</span><span class="sxs-lookup"><span data-stu-id="51939-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="51939-114">Para associar um tronco a uma rota, defina um nome simples para o tronco no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="51939-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="51939-115">Esse nome simples é usado como o nome do tronco no Painel de Controle do Skype for Business Server, onde os troncos podem ser associados a rotas.</span><span class="sxs-lookup"><span data-stu-id="51939-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="51939-116">O nome do tronco simples é usado como o nome do gateway do Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="51939-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="51939-117">O administrador deve selecionar um tronco padrão associado a um Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="51939-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="51939-118">No Construtor de Topologias, clique com o botão direito do mouse no Servidor de Mediação associado e clique em **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="51939-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="51939-119">Especifique o gateway padrão para o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="51939-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="51939-120">O diagrama a seguir ilustra os vários troncos definidos para cada Servidor de Mediação e gateway.</span><span class="sxs-lookup"><span data-stu-id="51939-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Várias atribuições de tronco](../../media/multiple-trunk-assignments.jpg)
