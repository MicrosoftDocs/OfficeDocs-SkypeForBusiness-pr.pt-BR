---
title: Definir o escopo da implantação do E9-1-1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: Decisões necessárias para o planejamento de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813421"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="42bd9-103">Definir o escopo da implantação do E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="42bd9-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="42bd9-104">Decisões necessárias para o planejamento de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="42bd9-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="42bd9-105">Antes de configurar o Skype for Business para E9-1-1, você precisa planejar sua implantação do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="42bd9-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="42bd9-106">Algumas das questões a serem consideradas são:</span><span class="sxs-lookup"><span data-stu-id="42bd9-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="42bd9-107">**Qual é a política e as obrigações legais da sua organização em relação ao E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="42bd9-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="42bd9-108">Os requisitos legais de E9-1-1 para PBXs (chamados de Multi-line Telephone Systems, ou MLTS, no linguajar de E9-1-1) diferem de acordo com o estado.</span><span class="sxs-lookup"><span data-stu-id="42bd9-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="42bd9-109">Você deve consultar sua equipe jurídica para entender as obrigações que podem se aplicar à sua implantação do Skype for Business em suas geografias relevantes.</span><span class="sxs-lookup"><span data-stu-id="42bd9-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="42bd9-110">**Quais áreas dentro de sua empresa precisam estar habilitadas para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="42bd9-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="42bd9-p103">É possível habilitar o E9-1-1 para toda a empresa ou para locais selecionados. Por exemplo, talvez você tenha requisitos variados de E9-1-1 para escritórios em estados diferentes ou queira excluir sites fora dos EUA.</span><span class="sxs-lookup"><span data-stu-id="42bd9-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="42bd9-113">**Como você implantará o E9-1-1 em sites de filiais?**</span><span class="sxs-lookup"><span data-stu-id="42bd9-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="42bd9-114">A resiliência de voz é um conceito importante para compreender quando implantar o E9-1-1 no site local.</span><span class="sxs-lookup"><span data-stu-id="42bd9-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="42bd9-115">Se você centralizou os troncos SIP E-9-1-1 e ocorre uma paralisação WAN, os clientes que entraram podem não conseguir obter um local do serviço de Informações de Local ou se conectar ao provedor de serviços de emergência.</span><span class="sxs-lookup"><span data-stu-id="42bd9-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="42bd9-116">O Skype for Business oferece várias estratégias para lidar com a resiliência de voz em filiais, incluindo: ter redes de dados resilientes, implantar um tronco SIP em cada filial ou enviar chamadas de emergência para o gateway local durante paralisações.</span><span class="sxs-lookup"><span data-stu-id="42bd9-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="42bd9-117">Para obter detalhes, consulte [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span><span class="sxs-lookup"><span data-stu-id="42bd9-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="42bd9-118">**Você habilitará o E9-1-1 para usuários trabalhando fora da rede?**</span><span class="sxs-lookup"><span data-stu-id="42bd9-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="42bd9-119">A aquisição automática de localização está disponível apenas para clientes localizados dentro da rede da organização, portanto, sua organização precisa decidir se dará suporte a chamadas E9-1-1 feitas de clientes do Skype for Business fora do local.</span><span class="sxs-lookup"><span data-stu-id="42bd9-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="42bd9-120">Por exemplo, você habilitará usuários para fazer chamadas de emergência se eles estiverem trabalhando de cada ou no local de um cliente?</span><span class="sxs-lookup"><span data-stu-id="42bd9-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="42bd9-121">Se um cliente estiver localizado fora da rede empresarial, ele poderá ser configurado para solicitar ao usuário um local.</span><span class="sxs-lookup"><span data-stu-id="42bd9-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="42bd9-122">No entanto, como esses locais fornecidos pelo usuário não podem ser pré-validados com base no MSAG (Catálogo de Endereços Principal), o despachante do provedor de serviços de emergência necessitarão confirmar a validade do local verbalmente com o chamador antes de rotear a chamada para o PSAP (ponto de atendimento público seguro).</span><span class="sxs-lookup"><span data-stu-id="42bd9-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="42bd9-123">Clientes do Skype for Business de usuários que se conectam à rede da sua organização usando VPN podem obter informações de endereço IP internos, mas como esses endereços não podem ser usados para identificar o local real do usuário, é essencial que as sub-redes VPN sejam excluídas do serviço de Informações de Local.</span><span class="sxs-lookup"><span data-stu-id="42bd9-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="42bd9-124">**Você deseja fornecer roteamento de chamada de emergência para sites fora dos EUA?**</span><span class="sxs-lookup"><span data-stu-id="42bd9-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="42bd9-p106">Talvez você queira fornecer roteamento de emergência para áreas de sua empresa que não são atendidas por um provedor de serviços de emergência (por exemplo, locais internacionais). Para fazer isso, crie um novo site e atribua políticas de voz aos sites que se referem a um uso do PSTN que roteia a chamada pelo gateway PSTN local.</span><span class="sxs-lookup"><span data-stu-id="42bd9-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


