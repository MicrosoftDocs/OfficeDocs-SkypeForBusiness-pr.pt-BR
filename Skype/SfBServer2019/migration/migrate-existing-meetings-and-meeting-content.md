---
title: Migrar reuniões existentes e conteúdo de reunião
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Quando uma conta de usuário é movida de um Skype para Business Server 2019 server, a seguinte informação é movida com uma conta de usuário:'
ms.openlocfilehash: bf10fa6b4ad4d555ce80dee5ec4e4a6584020ac7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874658"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

Quando uma conta de usuário é movida para uma Skype para Business Server 2019 server, a seguinte informação é movida com uma conta de usuário:
  
- **Reuniões já agendadas pelo usuário**. Isso inclui mover os diretórios de conferência e dados de conferência.
    
- **Número de identificação pessoal (PIN) do usuário**. O PIN do usuário atual continua funcionando até expirar ou o usuário solicita um novo PIN.
    
As seguintes informações de conta de usuário não move para o novo servidor.
  
- O **conteúdo das reuniões**. Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadro de comunicações, anexos ou dados de votação, usam o parâmetro **- MoveConferenceData** como parte do cmdlet **Move-CsUser** . 
    

