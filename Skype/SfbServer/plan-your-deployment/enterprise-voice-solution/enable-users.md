---
title: Habilitar usuários para E9-1-1 no Skype for Business Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisões necessárias para a política de local para uma implantação de E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários em roaming.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825741"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="c9e2c-103">Habilitar usuários para E9-1-1 no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c9e2c-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="c9e2c-104">Decisões necessárias para a política de local para uma implantação de E9-1-1 no Skype for Business Server Enterprise Voice, incluindo quais usuários habilitar e como dar suporte a usuários em roaming.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="c9e2c-105">Durante o registro do cliente, o Skype for Business Server usa uma política de local para configurar as propriedades do E9-1-1 para usuários habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="c9e2c-106">Esta política contém as configurações que definem como o E9-1-1 é implementado.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="c9e2c-107">Por exemplo, a política de local contém informações como a cadeia de caracteres de discagem de emergência e se um usuário precisa ou não inserir manualmente um local se o serviço de Informações de Local não fornecer um automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="c9e2c-108">Para uma definição completa de uma política de local, consulte Planejar políticas [de local para o Skype for Business Server.](location-policies.md)</span><span class="sxs-lookup"><span data-stu-id="c9e2c-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="c9e2c-109">O Skype for Business Server pode atribuir uma política de local a clientes com base em sub-rede ou a usuários com base em uma política global, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="c9e2c-110">Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="c9e2c-111">**Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**</span><span class="sxs-lookup"><span data-stu-id="c9e2c-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="c9e2c-112">Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="c9e2c-113">No entanto, ao atribuir uma política de local a um site de rede do Skype for Business Server e adicionar sub-redes ao site, você pode limitar o suporte do E9-1-1 a locais selecionados dentro da empresa e especificar o comportamento de roteamento E9-1-1 por site.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="c9e2c-114">**Você planeja habilitar usuários individuais por meio de uma política de usuário?**</span><span class="sxs-lookup"><span data-stu-id="c9e2c-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="c9e2c-115">Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="c9e2c-116">**Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="c9e2c-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="c9e2c-117">Se os usuários são atribuídos a uma política de local global, por site ou por usuário, eles podem ser obrigados a inserir manualmente um local no cliente se o cliente não está localizado dentro de uma sub-rede definida ou se nenhum local foi encontrado pelo serviço de Informações de Local.</span><span class="sxs-lookup"><span data-stu-id="c9e2c-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="c9e2c-118">Para obter detalhes, [consulte Definir a experiência do usuário para adquirir manualmente um local no Skype for Business Server.](manually-acquiring-a-location.md)</span><span class="sxs-lookup"><span data-stu-id="c9e2c-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

