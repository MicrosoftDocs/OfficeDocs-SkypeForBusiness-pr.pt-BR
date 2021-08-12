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
description: 'Quando uma conta de usuário é movida para um servidor Skype for Business Server 2019, as informações a seguir são movidas com essa conta de usuário:'
ms.openlocfilehash: e28cbce30608672d27578cfaa5ab92dbe1ed3c4cd6b234da7389b1f9a6978350
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312289"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

Quando uma conta de usuário é movida para um servidor Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:
  
- **As reuniões já foram programadas pelo usuário**. Isto inclui mover os diretórios de conferência e dados de conferência.
    
- **Número de identificação pessoal do usuário (PIN)**. O PIN atual do usuário continua a funcionar até expirar ou o usuário solicitar um novo PIN.
    
A seguinte informação de conta do usuário não é movida para o novo servidor.
  
- **Conteúdo da reunião**. Para mover o conteúdo compartilhado durante uma reunião, como PowerPoint, quadro de PowerPoint, anexos ou dados de sondagem, use o parâmetro **-MoveConferenceData** como parte do cmdlet **Move-CsUser.** 
    

