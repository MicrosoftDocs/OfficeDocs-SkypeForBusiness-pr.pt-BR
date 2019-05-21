---
title: Migrar reuniões existentes e conteúdo de reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Quando uma conta de usuário é movida de um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:'
ms.openlocfilehash: 4b5c7981374f3e2bf6dc2d87a0b21d972ddb14ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288597"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="14beb-103">Migrar reuniões existentes e conteúdo de reunião</span><span class="sxs-lookup"><span data-stu-id="14beb-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="14beb-104">Quando uma conta de usuário é movida para um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="14beb-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="14beb-105">**Reuniões já programadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="14beb-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="14beb-106">Isso inclui a movimentação dos diretórios de conferências e dos dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="14beb-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="14beb-107">**PIN (número de identificação pessoal) do usuário**.</span><span class="sxs-lookup"><span data-stu-id="14beb-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="14beb-108">O PIN atual do usuário continua a funcionar até que ele expire ou que o usuário solicitou um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="14beb-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="14beb-109">As seguintes informações da conta de usuário não se movem para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="14beb-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="14beb-110">**Conteúdo da reunião**.</span><span class="sxs-lookup"><span data-stu-id="14beb-110">**Meeting content**.</span></span> <span data-ttu-id="14beb-111">Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadro de comunicações, anexos ou dados de votação, use o parâmetro **-MoveConferenceData** como parte do cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="14beb-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

