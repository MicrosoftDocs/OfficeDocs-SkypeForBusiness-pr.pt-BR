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
description: 'Quando uma conta de usuário é movida de um servidor Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:'
ms.openlocfilehash: 6513f581f55028ec28d4cf05f1f1b3df37c49e65
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752683"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

Quando uma conta de usuário é movida para um servidor do Skype for Business Server 2019, as seguintes informações são movidas com essa conta de usuário:
  
- **As reuniões já foram programadas pelo usuário**. Isto inclui mover os diretórios de conferência e dados de conferência.
    
- **Número de identificação pessoal (PIN)** do usuário. O PIN atual do usuário continua a funcionar até expirar ou o usuário solicitar um novo PIN.
    
A seguinte informação de conta do usuário não é movida para o novo servidor.
  
- **Conteúdo da reunião**. Para mover o conteúdo compartilhado durante uma reunião, como PowerPoint, Quadro de Branco, anexos ou dados de sondagem, use o parâmetro **-MoveConferenceData** como parte do cmdlet **Move-CsUser.** 
    

