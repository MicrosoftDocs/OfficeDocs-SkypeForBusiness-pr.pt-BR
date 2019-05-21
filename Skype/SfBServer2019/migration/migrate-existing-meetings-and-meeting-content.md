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
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

Quando uma conta de usuário é movida para um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:
  
- **Reuniões já programadas pelo usuário**. Isso inclui a movimentação dos diretórios de conferências e dos dados de conferência.
    
- **PIN (número de identificação pessoal) do usuário**. O PIN atual do usuário continua a funcionar até que ele expire ou que o usuário solicitou um novo PIN.
    
As seguintes informações da conta de usuário não se movem para o novo servidor.
  
- **Conteúdo da reunião**. Para mover o conteúdo compartilhado durante uma reunião, como o PowerPoint, quadro de comunicações, anexos ou dados de votação, use o parâmetro **-MoveConferenceData** como parte do cmdlet **move-CsUser** . 
    

