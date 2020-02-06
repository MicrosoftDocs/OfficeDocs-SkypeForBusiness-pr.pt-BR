---
title: Habilitar usuários para o E9-1-1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisões necessárias para a política de localização de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários móveis.
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802951"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="55af1-103">Habilitar usuários para o E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="55af1-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="55af1-104">Decisões necessárias para a política de localização de uma implantação do E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários móveis.</span><span class="sxs-lookup"><span data-stu-id="55af1-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="55af1-105">Durante o registro do cliente, o Skype for Business Server usa uma política de localização para configurar as propriedades E9-1-1 para usuários habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="55af1-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="55af1-106">Esta política contém as configurações que definem como o E9-1-1 é implementado.</span><span class="sxs-lookup"><span data-stu-id="55af1-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="55af1-107">Por exemplo, a política de localização contém informações como a cadeia de caracteres de discagem de emergência e se um usuário precisa ou não inserir um local manualmente se o serviço de informações de localização não fornecer uma conta automaticamente.</span><span class="sxs-lookup"><span data-stu-id="55af1-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="55af1-108">Para obter uma definição completa de uma política de localização, consulte [planejar políticas de localização para o Skype for Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="55af1-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="55af1-109">O Skype for Business Server pode atribuir uma política de localização a clientes com base na sub-rede ou aos usuários com base em políticas globais, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="55af1-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="55af1-110">Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.</span><span class="sxs-lookup"><span data-stu-id="55af1-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="55af1-111">**Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**</span><span class="sxs-lookup"><span data-stu-id="55af1-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="55af1-112">Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global.</span><span class="sxs-lookup"><span data-stu-id="55af1-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="55af1-113">No entanto, ao atribuir uma política de localização a um site de rede do Skype for Business Server e adicionar sub-redes ao site, você pode limitar o suporte a E9-1 a locais selecionados dentro da empresa e especificar o comportamento de roteamento E9-1-1 por site.</span><span class="sxs-lookup"><span data-stu-id="55af1-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="55af1-114">**Você planeja habilitar usuários individuais por meio de uma política de usuário?**</span><span class="sxs-lookup"><span data-stu-id="55af1-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="55af1-115">Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="55af1-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="55af1-116">**Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="55af1-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="55af1-117">Se os usuários forem atribuídos a uma política de local global, de site ou por usuário, eles poderão ser solicitados a inserir um local manualmente no cliente se o cliente não estiver localizado dentro de uma sub-rede definida ou se nenhum local tiver sido encontrado pelo serviço informações de localização.</span><span class="sxs-lookup"><span data-stu-id="55af1-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="55af1-118">Para obter detalhes, consulte [definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="55af1-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

