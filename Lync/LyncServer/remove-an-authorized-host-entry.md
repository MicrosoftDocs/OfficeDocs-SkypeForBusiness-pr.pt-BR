---
title: Remover uma entrada de host autorizada
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd64239460d76d63b28bb3a3abeb8c5cc8bb97d9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a><span data-ttu-id="1b44e-102">Remover uma entrada de host autorizada</span><span class="sxs-lookup"><span data-stu-id="1b44e-102">Remove an authorized host entry</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b44e-103">_**Última modificação do tópico:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="1b44e-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="1b44e-104">Este tópico descreve como remover uma entrada de host autorizado herdada (conhecida como uma *entrada de aplicativo confiável* no Lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="1b44e-104">This topic describes how to remove a legacy authorized host entry (known as a *trusted application entry* in Lync Server 2013).</span></span> <span data-ttu-id="1b44e-105">Você deve remover as entradas de host autorizadas existentes para todos os gateways SIP/CSTA em sua implantação do Office Communications Server 2007 R2 quando você migrar o controle de chamada remota para uma implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b44e-105">You must remove existing authorized host entries for any SIP/CSTA gateways in your Office Communications Server 2007 R2 deployment when you migrate remote call control to a Lync Server 2013 deployment.</span></span> <span data-ttu-id="1b44e-106">Você deve usar as ferramentas administrativas incluídas no Office Communications Server 2007 R2 para remover as entradas de host autorizadas existentes.</span><span class="sxs-lookup"><span data-stu-id="1b44e-106">You must use the administrative tools included with Office Communications Server 2007 R2 to remove the existing authorized host entries.</span></span>

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a><span data-ttu-id="1b44e-107">Para remover uma entrada de host autorizada em uma implantação do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1b44e-107">To remove an authorized host entry in an Office Communications Server 2007 R2 deployment</span></span>

1.  <span data-ttu-id="1b44e-108">Abra o console administrativo do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="1b44e-108">Open the Office Communications Server 2007 R2 administrative console.</span></span>

2.  <span data-ttu-id="1b44e-109">Expanda a árvore e clique com o botão direito no pool no qual o host autorizado foi criado.</span><span class="sxs-lookup"><span data-stu-id="1b44e-109">Expand the tree and right-click the pool where the authorized host was created.</span></span>

3.  <span data-ttu-id="1b44e-110">Clique em **Propriedades** e clique em **Propriedades do Front-End**.</span><span class="sxs-lookup"><span data-stu-id="1b44e-110">Click **Properties**, and then click **Front End Properties**.</span></span>

4.  <span data-ttu-id="1b44e-111">Clique na guia **Autorização do Host**.</span><span class="sxs-lookup"><span data-stu-id="1b44e-111">Click the **Host Authorization** tab.</span></span>

5.  <span data-ttu-id="1b44e-112">Selecione um servidor e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="1b44e-112">Select a server, and then click **Remove**.</span></span>

6.  <span data-ttu-id="1b44e-113">Em **Propriedades**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b44e-113">In **Properties**, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

