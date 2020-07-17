---
title: Migrar reuniões existentes e conteúdo de reunião
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Quando uma conta de usuário é movida de um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752683"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a><span data-ttu-id="ee323-103">Migrar reuniões existentes e conteúdo de reunião</span><span class="sxs-lookup"><span data-stu-id="ee323-103">Migrate existing meetings and meeting content</span></span>

<span data-ttu-id="ee323-104">Quando uma conta de usuário é movida para um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:</span><span class="sxs-lookup"><span data-stu-id="ee323-104">When a user account is moved to a Skype for Business Server 2019 server, the following information is moved with that user account:</span></span>
  
- <span data-ttu-id="ee323-105">**As reuniões já foram programadas pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="ee323-105">**Meetings already scheduled by the user**.</span></span> <span data-ttu-id="ee323-106">Isto inclui mover os diretórios de conferência e dados de conferência.</span><span class="sxs-lookup"><span data-stu-id="ee323-106">This includes moving the conferencing directories and conferencing data.</span></span>
    
- <span data-ttu-id="ee323-107">**PIN (número de identificação pessoal) do usuário**.</span><span class="sxs-lookup"><span data-stu-id="ee323-107">**User's personal identification number (PIN)**.</span></span> <span data-ttu-id="ee323-108">O PIN atual do usuário continua funcionando até que ele expire ou o usuário solicite um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="ee323-108">The user's current PIN continues to work until it expires or the user requests a new PIN.</span></span>
    
<span data-ttu-id="ee323-109">A seguinte informação de conta do usuário não é movida para o novo servidor.</span><span class="sxs-lookup"><span data-stu-id="ee323-109">The following user account information does not move to the new server.</span></span>
  
- <span data-ttu-id="ee323-110">**Conteúdo da reunião**.</span><span class="sxs-lookup"><span data-stu-id="ee323-110">**Meeting content**.</span></span> <span data-ttu-id="ee323-111">Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadros de comunicações, anexos ou dados de pesquisa, use o parâmetro **-MoveConferenceData** como parte do cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="ee323-111">In order to move the content shared during a meeting, such as PowerPoint, Whiteboard, attachments, or poll data, use the **-MoveConferenceData** parameter as part of the **Move-CsUser** cmdlet.</span></span> 
    

