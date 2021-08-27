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
ms.localizationpriority: medium
description: 'Quando uma conta de usuário é movida para um servidor Skype for Business Server 2019, as informações a seguir são movidas com essa conta de usuário:'
ms.openlocfilehash: 826b511250e46e2c87720a5b074b43cd545b15c6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589297"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

Quando uma conta de usuário é movida para um servidor Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:
  
- **As reuniões já foram programadas pelo usuário**. Isto inclui mover os diretórios de conferência e dados de conferência.
    
- **Número de identificação pessoal do usuário (PIN)**. O PIN atual do usuário continua a funcionar até expirar ou o usuário solicitar um novo PIN.
    
A seguinte informação de conta do usuário não é movida para o novo servidor.
  
- **Conteúdo da reunião**. Para mover o conteúdo compartilhado durante uma reunião, como PowerPoint, quadro de PowerPoint, anexos ou dados de sondagem, use o parâmetro **-MoveConferenceData** como parte do cmdlet **Move-CsUser.** 
    

