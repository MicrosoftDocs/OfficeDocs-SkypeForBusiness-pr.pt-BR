---
title: Migrar reuniões existentes e conteúdo de reunião
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Quando uma conta de usuário é movida de um Skype para Business Server 2019 server, a seguinte informação é movida com uma conta de usuário:'
ms.openlocfilehash: 03ccad0498af777c7d93765af7df2baf5da51f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030368"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="f8a3c-103">Migrar reuniões existentes e conteúdo de reunião</span><span class="sxs-lookup"><span data-stu-id="f8a3c-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="f8a3c-104">Quando uma conta de usuário é movida para uma Skype para Business Server 2019 server, a seguinte informação é movida com uma conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="f8a3c-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="f8a3c-105">**Reuniões já agendadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="f8a3c-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="f8a3c-106">Isso inclui mover os diretórios de conferência e dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="f8a3c-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="f8a3c-107">**Número de identificação pessoal (PIN) do usuário**.</span><span class="sxs-lookup"><span data-stu-id="f8a3c-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="f8a3c-108">O PIN do usuário atual continua funcionando até expirar ou o usuário solicita um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="f8a3c-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="f8a3c-109">As seguintes informações de conta de usuário não move para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="f8a3c-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="f8a3c-110">O **conteúdo das reuniões**.</span><span class="sxs-lookup"><span data-stu-id="f8a3c-110">**Meeting content**.</span></span> <span data-ttu-id="f8a3c-111">Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadro de comunicações, anexos ou dados de votação, usam o parâmetro **- MoveConferenceData** como parte do cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="f8a3c-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

