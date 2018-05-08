---
title: Habilitar usuários para E9-1-1 no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisões necessárias para a política de local para uma implantação do E9-1-1 em Skype para Business Server Enterprise Voice, incluindo quais usuários habilitem e como dar suporte a usuários móveis.
ms.openlocfilehash: 72a2a290a846ec39b13f51a16ea231249ea11b9b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server-2015"></a><span data-ttu-id="048b4-103">Habilitar usuários para E9-1-1 no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="048b4-103">Enable users for E9-1-1 in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="048b4-104">Decisões necessárias para a política de local para uma implantação do E9-1-1 em Skype para Business Server Enterprise Voice, incluindo quais usuários habilitem e como dar suporte a usuários móveis.</span><span class="sxs-lookup"><span data-stu-id="048b4-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="048b4-105">Durante o registro de cliente, Skype para Business Server usa uma política de local para configurar as propriedades de E9-1-1 para usuários habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="048b4-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="048b4-106">Esta política contém as configurações que definem como o E9-1-1 é implementado.</span><span class="sxs-lookup"><span data-stu-id="048b4-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="048b4-107">Por exemplo, a política de local contém informações como cadeia de caracteres de discagem de emergência e independentemente de um usuário precisa digitar um local manualmente, se o serviço de informações de local não ocorra automaticamente ou não fornecer um.</span><span class="sxs-lookup"><span data-stu-id="048b4-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="048b4-108">Para obter uma definição completa de uma política de local, consulte [planejar políticas de local para Skype para Business Server 2015](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="048b4-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server 2015](location-policies.md).</span></span>
  
<span data-ttu-id="048b4-109">Skype para Business Server pode atribuir uma política de local para clientes baseados em sub-rede ou para usuários com base em global, cada site ou política por usuário.</span><span class="sxs-lookup"><span data-stu-id="048b4-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="048b4-110">Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.</span><span class="sxs-lookup"><span data-stu-id="048b4-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="048b4-111">**Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**</span><span class="sxs-lookup"><span data-stu-id="048b4-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="048b4-112">Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global.</span><span class="sxs-lookup"><span data-stu-id="048b4-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="048b4-113">No entanto, atribuindo uma política de local a um Skype para o site de rede do servidor de negócios e, em seguida, adicionando sub-redes ao site, você pode limitar o suporte do E9-1-1 a locais selecionados na empresa e especificar o comportamento de roteamento do E9-1-1 em uma base por site.</span><span class="sxs-lookup"><span data-stu-id="048b4-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="048b4-114">**Você planeja habilitar usuários individuais por meio de uma política de usuário?**</span><span class="sxs-lookup"><span data-stu-id="048b4-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="048b4-115">Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="048b4-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="048b4-116">**Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="048b4-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="048b4-117">Se os usuários recebem um global, site, ou política de local por usuário, podem ser necessários para digitar manualmente um local ao cliente se o cliente não estiver localizado dentro de uma sub-rede definida ou nenhum local foi encontrado pelo serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="048b4-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="048b4-118">Para obter detalhes, consulte [Define a experiência do usuário para adquirir manualmente um local no Skype para Business Server 2015](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="048b4-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server 2015](manually-acquiring-a-location.md).</span></span>
    

