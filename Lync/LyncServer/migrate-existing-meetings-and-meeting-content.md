---
title: Migrar reuniões existentes e conteúdo de reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a6036421dd84f466df0f2353b6d5264e0680c2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="dac8e-102">Migrar reuniões existentes e conteúdo de reunião</span><span class="sxs-lookup"><span data-stu-id="dac8e-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dac8e-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="dac8e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="dac8e-104">Quando uma conta de usuário é movida do Lync Server 2010 para um servidor do Lync Server 2013, as seguintes informações são movidas com essa conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="dac8e-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="dac8e-p101">**As reuniões já foram programadas pelo usuário**. Isto inclui mover os diretórios de conferência e dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="dac8e-p101">**Meetings already scheduled by the user**. This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="dac8e-p102">**Número de identificação pessoal (PIN) do usuário**. O PIN atual do usuário continua a funcionar até vencer ou o usuário solicitar um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="dac8e-p102">**User’s personal identification number (PIN)**. The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="dac8e-109">A seguinte informação de conta do usuário não é movida para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="dac8e-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="dac8e-p103">**Conteúdo da reunião**. Para poder mover o conteúdo compartilhado durante uma reunião, por exemplo, PowerPoint, Quadro de Avisos, anexos ou dados do pool, use o parâmetro **-MoveConferenceData** como parte do cmdlet **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="dac8e-p103">**Meeting content**. In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

