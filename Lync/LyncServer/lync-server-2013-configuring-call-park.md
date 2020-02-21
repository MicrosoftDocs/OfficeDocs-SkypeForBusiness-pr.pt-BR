---
title: 'Lync Server 2013: Configurando estacionamento de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Call Park
ms:assetid: e4c5da53-7f6c-4535-bc9b-9da2026caec8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399014(v=OCS.15)
ms:contentKeyID: 48185732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d96b75072a2d23773feef0cf5095345ddeb7322
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="b9b4f-102">Configurando o estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9b4f-103">_**Última modificação do tópico:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="b9b4f-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="b9b4f-104">O estacionamento de chamada permite que um usuário do Enterprise Voice Coloque uma chamada em espera de um telefone e, em seguida, recupere a chamada mais tarde discando um número interno (conhecido como *órbita*de estacionamento de chamada) de qualquer telefone.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="b9b4f-105">Os componentes que usam o estacionamento de chamadas são instalados e habilitados automaticamente no servidor front-end ou no servidor Standard Edition quando você implanta o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b9b4f-106">No entanto, você deve configurar o estacionamento de chamada antes que ele esteja disponível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="b9b4f-107">Esta seção orienta você durante a configuração do estacionamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b9b4f-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b9b4f-108">In This Section</span></span>

  - [<span data-ttu-id="b9b4f-109">Pré-requisitos de configuração do estacionamento de chamadas e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="b9b4f-110">Processo de implantação para estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="b9b4f-111">Configurar a tabela de órbita de estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="b9b4f-112">Definir configurações de estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="b9b4f-113">Personalizar o estacionamento de chamada música em espera no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="b9b4f-114">Habilitar estacionamento de chamada para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="b9b4f-115">Verificar regras de normalização para estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="b9b4f-116">Opcion Verificar a implantação do estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9b4f-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

