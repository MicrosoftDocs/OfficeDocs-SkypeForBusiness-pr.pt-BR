---
title: Migrar reuniões existentes e conteúdo de reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Quando uma conta de usuário é movida de um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:'
ms.openlocfilehash: 6394ebf798560ce5a13fe7ba931076364257decc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813469"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="e2a69-103">Migrar reuniões existentes e conteúdo de reunião</span><span class="sxs-lookup"><span data-stu-id="e2a69-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="e2a69-104">Quando uma conta de usuário é movida para um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="e2a69-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="e2a69-105">**Reuniões já programadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="e2a69-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="e2a69-106">Isso inclui a movimentação dos diretórios de conferências e dos dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="e2a69-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="e2a69-107">**PIN (número de identificação pessoal) do usuário**.</span><span class="sxs-lookup"><span data-stu-id="e2a69-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="e2a69-108">O PIN atual do usuário continua a funcionar até que ele expire ou que o usuário solicitou um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="e2a69-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="e2a69-109">As seguintes informações da conta de usuário não se movem para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="e2a69-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="e2a69-110">**Conteúdo da reunião**.</span><span class="sxs-lookup"><span data-stu-id="e2a69-110">**Meeting content**.</span></span> <span data-ttu-id="e2a69-111">Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadro de comunicações, anexos ou dados de votação, use o parâmetro **-MoveConferenceData** como parte do cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="e2a69-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

