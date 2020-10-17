---
title: 'Lync Server 2013: Configurando conferência discada'
description: 'Lync Server 2013: Configurando conferência discada.'
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
ms.openlocfilehash: d9c3353caa1344b717b0f64c271149f078f194e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557937"
---
# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="49122-103">Configurando a conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-103">Configuring dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49122-104">_**Última modificação do tópico:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="49122-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="49122-105">Esta seção orienta você durante a configuração da conferência discada do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="49122-105">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="49122-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="49122-106">In This Section</span></span>

  - [<span data-ttu-id="49122-107">Pré-requisitos e permissões de configuração de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-107">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="49122-108">Lista de verificação de implantação para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-108">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="49122-109">Configurar planos de discagem para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-109">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="49122-110">Verifique se os planos de discagem Lync Server 2013 possuem regiões atribuídas</span><span class="sxs-lookup"><span data-stu-id="49122-110">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="49122-111">Opcion Verificar as configurações de política de PIN no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-111">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="49122-112">Configurar a política de conferência para discagem no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-112">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="49122-113">Configurar números de acesso de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-113">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="49122-114">Opcion Verificar as configurações de conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-114">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="49122-115">Opcion Modificar o mapeamento de teclas para comandos DTMF no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-115">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="49122-116">Opcion Habilitar e desabilitar comunicados de ingresso e saída de conferência no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-116">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="49122-117">Opcion Verificar a conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-117">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="49122-118">Implantar o suplemento reunião online para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="49122-118">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="49122-119">Definir configurações de conta de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-119">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="49122-120">Recomenda Criar diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="49122-120">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="49122-121">Opcion Usuários de boas-vindas para conferência discada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-121">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="49122-122">Seções Relacionadas</span><span class="sxs-lookup"><span data-stu-id="49122-122">Related Sections</span></span>

[<span data-ttu-id="49122-123">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49122-123">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

