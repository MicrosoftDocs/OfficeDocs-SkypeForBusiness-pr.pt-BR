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
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

Quando uma conta de usuário é movida para um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:
  
- **Reuniões já programadas pelo usuário**. Isso inclui a movimentação dos diretórios de conferências e dos dados de conferência.
    
- **PIN (número de identificação pessoal) do usuário**. O PIN atual do usuário continua a funcionar até que ele expire ou que o usuário solicitou um novo PIN.
    
As seguintes informações da conta de usuário não se movem para o novo servidor.
  
- **Conteúdo da reunião**. Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadro de comunicações, anexos ou dados de votação, use o parâmetro **-MoveConferenceData** como parte do cmdlet **move-CsUser** . 
    

