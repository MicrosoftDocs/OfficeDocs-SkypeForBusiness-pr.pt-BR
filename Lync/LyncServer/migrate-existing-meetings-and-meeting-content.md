---
title: Migrar reuniões existentes e conteúdo de reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38b4f374aef66fa95d49b2330a07f9def4135328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="17e0e-102">Migrar reuniões existentes e conteúdo de reunião</span><span class="sxs-lookup"><span data-stu-id="17e0e-102">Migrate existing meetings and meeting content</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17e0e-103">_**Tópico da última modificação:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="17e0e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="17e0e-104">Quando uma conta de usuário é movida do Lync Server 2010 para um servidor do Lync Server 2013, as seguintes informações são movidas com essa conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="17e0e-104">When a user account is moved from Lync Server 2010 to a Lync Server 2013 server, the following information is moved with that user account:</span></span>

  - <span data-ttu-id="17e0e-105">**Reuniões já programadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="17e0e-106">Isso inclui a movimentação dos diretórios de conferências e dos dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="17e0e-106">This includes moving the conferencing directories and conferencing data.</span></span>

  - <span data-ttu-id="17e0e-107">**PIN (número de identificação pessoal) do usuário**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-107">**User’s personal identification number (PIN)**.</span></span> <span data-ttu-id="17e0e-108">O PIN atual do usuário continua a funcionar até que ele expire ou que o usuário solicitou um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="17e0e-108">The user’s current PIN continues to work until it expires or the user requests a new PIN.</span></span>

<span data-ttu-id="17e0e-109">As seguintes informações da conta de usuário não se movem para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="17e0e-109">The following user account information does not move to the new server.</span></span>

  - <span data-ttu-id="17e0e-110">**Conteúdo da reunião**.</span><span class="sxs-lookup"><span data-stu-id="17e0e-110">**Meeting content**.</span></span> <span data-ttu-id="17e0e-111">Para mover o conteúdo compartilhado durante uma reunião, por exemplo, PowerPoint, quadro de comunicações, anexos ou dados de votação, use o parâmetro **-MoveConferenceData** como parte do cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="17e0e-111">In order to move the content shared during a meeting, for example PowerPoint, Whiteboard, attachments or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

