---
title: 'Lync Server 2013: habilitando usuários para E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling users for E9-1-1
ms:assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425892(v=OCS.15)
ms:contentKeyID: 48183884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a5ba14f24694bf3b9485e60102007a0bfee788c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-users-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="61eaa-102">Habilitando usuários para E9-1-1 no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61eaa-102">Enabling users for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61eaa-103">_**Última modificação do tópico:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="61eaa-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="61eaa-104">Durante o registro do cliente, o Lync Server usa uma política de local para configurar as propriedades E9-1-1 para usuários habilitados para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="61eaa-104">During client registration, Lync Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="61eaa-105">Esta política contém as configurações que definem como o E9-1-1 é implementado.</span><span class="sxs-lookup"><span data-stu-id="61eaa-105">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="61eaa-106">Por exemplo, a política de local contém informações como a cadeia de caracteres de discagem de emergência, e se um usuário é ou não solicitado a inserir manualmente um local se o serviço de informações de local não fornecer um.</span><span class="sxs-lookup"><span data-stu-id="61eaa-106">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="61eaa-107">Para obter uma definição completa de uma política de local, consulte [definindo a política de local para o Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="61eaa-107">For a complete definition of a location policy, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="61eaa-108">O Lync Server pode atribuir uma política de local a clientes com base na sub-rede ou nos usuários com base em uma política global, por site ou por usuário.</span><span class="sxs-lookup"><span data-stu-id="61eaa-108">Lync Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="61eaa-109">Para ajudar a decidir como você habilitará usuários, primeiro responda as perguntas a seguir.</span><span class="sxs-lookup"><span data-stu-id="61eaa-109">To help decide how you will enable users, you should first answer the following questions.</span></span>

  - <span data-ttu-id="61eaa-110">**Você planeja habilitar todos os usuários ou limitar o suporte a áreas geográficas específicas da empresa?**</span><span class="sxs-lookup"><span data-stu-id="61eaa-110">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>  
    <span data-ttu-id="61eaa-111">Você pode atribuir um local para todos os usuários em sua empresa usando uma política de local global.</span><span class="sxs-lookup"><span data-stu-id="61eaa-111">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="61eaa-112">No entanto, atribuindo uma política de local a um site de rede do Lync Server e, em seguida, adicionando sub-redes ao site, você pode limitar o suporte a E9-1-1 para locais selecionados dentro da empresa e especificar o comportamento de roteamento E9-1-1 por site.</span><span class="sxs-lookup"><span data-stu-id="61eaa-112">However, by assigning a location policy to a Lync Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span>

<!-- end list -->

  - <span data-ttu-id="61eaa-113">**Você planeja habilitar usuários individuais por meio de uma política de usuário?**</span><span class="sxs-lookup"><span data-stu-id="61eaa-113">**Do you plan to enable individual users through a user policy?**</span></span>  
    <span data-ttu-id="61eaa-114">Você pode atribuir políticas de local diretamente a usuários específicos ou a objetos de contato telefônico de área comum se deseja personalizar seu suporte do E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="61eaa-114">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>

<!-- end list -->

  - <span data-ttu-id="61eaa-115">**Quando clientes usam perfil móvel fora da rede ou conectam a partir de uma sub-rede indefinida, os clientes ainda devem ser habilitados para E9-1-1?**</span><span class="sxs-lookup"><span data-stu-id="61eaa-115">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>  
    <span data-ttu-id="61eaa-116">Se os usuários recebem uma política de local global, de site ou por usuário, eles podem ser necessários para inserir manualmente um local no cliente se o cliente não estiver localizado dentro de uma sub-rede definida ou se nenhum local for encontrado pelo serviço de informações de local.</span><span class="sxs-lookup"><span data-stu-id="61eaa-116">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="61eaa-117">Para obter detalhes, consulte [definir a experiência do usuário para adquirir manualmente um local no Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="61eaa-117">For details, see [Defining the user experience for manually acquiring a location in Lync Server 2013](lync-server-2013-defining-the-user-experience-for-manually-acquiring-a-location.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

