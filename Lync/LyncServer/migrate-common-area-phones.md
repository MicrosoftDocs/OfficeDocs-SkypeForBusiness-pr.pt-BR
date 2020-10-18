---
title: Migrar telefones de área comum
description: Migrar telefones de área comum.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Common Area Phones
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49733604
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b8df4d94a3db3274df7e4e82ed2185c3626de12
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579347"
---
# <a name="migrate-common-area-phones"></a><span data-ttu-id="4206b-103">Migrar telefones de área comum</span><span class="sxs-lookup"><span data-stu-id="4206b-103">Migrate Common Area Phones</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4206b-104">_**Última modificação do tópico:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="4206b-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="4206b-105">Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica.</span><span class="sxs-lookup"><span data-stu-id="4206b-105">Common Area Phones are IP phones that most often reside in a shared workspace or common area, like a lobby, kitchen, or factory floor.</span></span> <span data-ttu-id="4206b-106">Os telefones de área comum não precisam estar conectados a um computador para fornecer a funcionalidade UC do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4206b-106">Common Area Phones do not need to be connected to a computer to provide Lync Server UC functionality.</span></span> <span data-ttu-id="4206b-107">Após a migração de uma implantação do Lync Server 2010 para o Lync Server 2013, você também deve migrar os objetos de contato associados ao telefone de área comum herdado.</span><span class="sxs-lookup"><span data-stu-id="4206b-107">After migrating an Lync Server 2010 deployment to Lync Server 2013, you must also migrate the contact objects associated with the legacy Common Area Phone.</span></span> <span data-ttu-id="4206b-108">Usando o Shell de gerenciamento do Lync Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comum do Lync Server 2010 e, em seguida, moverá esses objetos para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4206b-108">Using Lync Server Management Shell you will first retrieve all contact objects associated with the Lync Server 2010 Common Area Phones, and then move those objects to the Lync Server 2013 pool.</span></span>

<span data-ttu-id="4206b-109">**Migrar telefones de área comum**</span><span class="sxs-lookup"><span data-stu-id="4206b-109">**Migrate Common Area Phones**</span></span>

1.  <span data-ttu-id="4206b-110">No servidor front-end do Lync Server 2013, abra o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4206b-110">From the Lync Server 2013 Front End server, open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="4206b-111">Na linha de comando, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4206b-111">From the command line, type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  <span data-ttu-id="4206b-112">Para verificar se todos os objetos de contato foram movidos para o pool do Lync Server 2013, no Shell de gerenciamento do Lync Server, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4206b-112">To verify all contact objects have been moved to the Lync Server 2013 pool, from the Lync Server Management Shell type the following:</span></span>
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    <span data-ttu-id="4206b-113">Verifique se todos os objetos de contato agora estão associados ao pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4206b-113">Verify all contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

