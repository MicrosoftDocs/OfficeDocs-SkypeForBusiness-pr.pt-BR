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
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

Quando uma conta de usuário é movida para uma Skype para Business Server 2019 server, a seguinte informação é movida com uma conta de usuário:
  
- **Reuniões já agendadas pelo usuário**. Isso inclui mover os diretórios de conferência e dados de conferência.
    
- **Número de identificação pessoal (PIN) do usuário**. O PIN do usuário atual continua funcionando até expirar ou o usuário solicita um novo PIN.
    
As seguintes informações de conta de usuário não move para o novo servidor.
  
- O **conteúdo das reuniões**. Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadro de comunicações, anexos ou dados de votação, usam o parâmetro **- MoveConferenceData** como parte do cmdlet **Move-CsUser** . 
    

