---
title: 'Lync Server 2013: Configurando conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d722abaf76ef915b7587039cb7732cb281a06308
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="3ebb6-102">Configurando conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ebb6-103">_**Tópico da última modificação:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="3ebb6-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="3ebb6-104">Esta seção orienta você na configuração da conferência discada do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3ebb6-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3ebb6-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3ebb6-105">In This Section</span></span>

  - [<span data-ttu-id="3ebb6-106">Pré-requisitos e permissões de configuração de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="3ebb6-107">Lista de verificação de implantação para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="3ebb6-108">Configurar planos de discagem para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="3ebb6-109">Verifique se os planos de discagem do Lync Server 2013 atribuiram regiões</span><span class="sxs-lookup"><span data-stu-id="3ebb6-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="3ebb6-110">(Opcional) Verificar configurações de política de PIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="3ebb6-111">Configurar política de conferência para discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="3ebb6-112">Configurar número de acesso da conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="3ebb6-113">(Opcional) Verificar configurações de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="3ebb6-114">(Opcional) Modificar mapeamento principal de comandos DTMF no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="3ebb6-115">(Opcional) Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="3ebb6-116">(Opcional) Verificar conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="3ebb6-117">Implantar suplemento Online Meeting para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="3ebb6-118">Definir configurações de conta do usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="3ebb6-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="3ebb6-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="3ebb6-120">(Opcional) Dar as boas-vindas aos usuários na conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="3ebb6-121">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="3ebb6-121">Related Sections</span></span>

[<span data-ttu-id="3ebb6-122">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ebb6-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

