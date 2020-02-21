---
title: 'Lync Server 2013: Configurando o recebimento de chamadas em grupo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Group Call Pickup
ms:assetid: b4b0a9a0-91c6-43a5-9e2b-a086caeb3f94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945645(v=OCS.15)
ms:contentKeyID: 51541505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef62fc903e70c0ff60cd86d124fbd092d9b394c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="957c0-102">Configurando o recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c0-102">Configuring Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="957c0-103">_**Última modificação do tópico:** 2013-02-01_</span><span class="sxs-lookup"><span data-stu-id="957c0-103">_**Topic Last Modified:** 2013-02-01_</span></span>

<span data-ttu-id="957c0-104">Atualização cumulativa do Lync Server 2013: fevereiro de 2013 apresenta o recebimento de chamadas em grupo como um novo recurso do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="957c0-104">Cumulative update for Lync Server 2013: February 2013 introduces Group Call Pickup as a new Enterprise Voice feature.</span></span> <span data-ttu-id="957c0-105">O recebimento de chamadas em grupo permite que os usuários escolham chamadas que estejam tocando para outro usuário discando um número de grupo de recebimento de chamada.</span><span class="sxs-lookup"><span data-stu-id="957c0-105">Group Call Pickup lets users pick up calls that are ringing for another user by dialing a call pickup group number.</span></span>

<span data-ttu-id="957c0-106">Os componentes que o recebimento de chamadas de grupo usa são instalados automaticamente e habilitados no servidor front-end ou no servidor Standard Edition quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="957c0-106">The components that Group Call Pickup uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="957c0-107">No entanto, você deve configurar o recebimento de chamadas em grupo antes de estar disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="957c0-107">However, you must configure Group Call Pickup before it is available to users.</span></span>

<span data-ttu-id="957c0-108">Esta seção orienta você durante a configuração de recebimento de chamadas em grupo.</span><span class="sxs-lookup"><span data-stu-id="957c0-108">This section guides you through the configuration of Group Call Pickup.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="957c0-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="957c0-109">In This Section</span></span>

[<span data-ttu-id="957c0-110">Pré-requisitos de configuração de recebimento de chamadas de grupo e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c0-110">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-group-call-pickup-configuration-prerequisites-and-user-rights.md)

[<span data-ttu-id="957c0-111">Processo de implantação do recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c0-111">Deployment process for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-group-call-pickup.md)

[<span data-ttu-id="957c0-112">Implantar a ferramenta SEFAUtil no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c0-112">Deploy the SEFAUtil tool in Lync Server 2013</span></span>](lync-server-2013-deploy-the-sefautil-tool.md)

[<span data-ttu-id="957c0-113">Configurar números de grupos de recebimento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c0-113">Configure call pickup group numbers in Lync Server 2013</span></span>](lync-server-2013-configure-call-pickup-group-numbers.md)

[<span data-ttu-id="957c0-114">Habilitar o recebimento de chamadas em grupo para usuários no Lync Server 2013 e atribuir um número de grupo</span><span class="sxs-lookup"><span data-stu-id="957c0-114">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>](lync-server-2013-enable-group-call-pickup-for-users-and-assign-a-group-number.md)

[<span data-ttu-id="957c0-115">Comunicar as atribuições de recebimento de chamadas de grupo aos usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c0-115">Communicate Group Call Pickup assignments to users in Lync Server 2013</span></span>](lync-server-2013-communicate-group-call-pickup-assignment-to-users.md)

[<span data-ttu-id="957c0-116">Opcion Verificar a implantação do recebimento de chamadas em grupo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="957c0-116">(Optional) Verify the Group Call Pickup deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-the-group-call-pickup-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

