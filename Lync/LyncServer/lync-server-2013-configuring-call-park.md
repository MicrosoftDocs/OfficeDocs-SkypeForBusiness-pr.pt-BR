---
title: 'Lync Server 2013: Configurando Estacionamento de Chamadas'
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
ms.openlocfilehash: 750ea65da2b5507099f097b31044673c474bfc7c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-call-park-in-lync-server-2013"></a><span data-ttu-id="3544e-102">Configurando Estacionamento de Chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-102">Configuring Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3544e-103">_**Tópico da última modificação:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="3544e-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="3544e-104">O estacionamento de chamadas permite que um usuário de voz empresarial Coloque uma chamada em espera de um telefone e, em seguida, recupere a chamada mais tarde, discando um número interno (conhecido como um parque de chamadas *órbita*) de qualquer telefone.</span><span class="sxs-lookup"><span data-stu-id="3544e-104">Call Park enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later by dialing an internal number (known as a Call Park *orbit*) from any telephone.</span></span>

<span data-ttu-id="3544e-105">Os componentes que chamam o parque usa são instalados e habilitados automaticamente no servidor front-end ou no servidor Standard Edition ao implantar o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="3544e-105">The components that Call Park uses are automatically installed and enabled on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="3544e-106">No entanto, você deve configurar o parque da chamada antes de disponibilizá-lo para os usuários.</span><span class="sxs-lookup"><span data-stu-id="3544e-106">However, you must configure Call Park before it is available to users.</span></span>

<span data-ttu-id="3544e-107">Esta seção orienta você na configuração do parque de chamadas.</span><span class="sxs-lookup"><span data-stu-id="3544e-107">This section guides you through the configuration of Call Park.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3544e-108">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3544e-108">In This Section</span></span>

  - [<span data-ttu-id="3544e-109">Pré-requisitos de Estacionamento de Chamadas e direitos de usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-109">Call Park configuration prerequisites and user rights in Lync Server 2013</span></span>](lync-server-2013-call-park-configuration-prerequisites-and-user-rights.md)

  - [<span data-ttu-id="3544e-110">Processo de implantação para estacionamento de chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-110">Deployment process for Call Park in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-call-park.md)

  - [<span data-ttu-id="3544e-111">Configurar a tabela de órbita de Estacionamento de Chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-111">Configure the Call Park orbit table in Lync Server 2013</span></span>](lync-server-2013-configure-the-call-park-orbit-table.md)

  - [<span data-ttu-id="3544e-112">Configurar as definições do estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-112">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="3544e-113">Personalizar a chamada de música do parque em espera no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-113">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="3544e-114">Habilitar o estacionamento de chamadas para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-114">Enable Call Park for users in Lync Server 2013</span></span>](lync-server-2013-enable-call-park-for-users.md)

  - [<span data-ttu-id="3544e-115">Verificar as regras de normalização para o parque de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-115">Verify normalization rules for Call Park in Lync Server 2013</span></span>](lync-server-2013-verify-normalization-rules-for-call-park.md)

  - [<span data-ttu-id="3544e-116">Adicionais Verificar a implantação do estacionamento de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544e-116">(Optional) Verify Call Park deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-call-park-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

