---
title: Desativar números de chamada gratuita para usuários específicos do Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números de chamada gratuita para suas reuniões.
ms.openlocfilehash: 7bc830529fc24a61be914998e923ad2d5288b7c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837261"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Desativar números de chamada gratuita para usuários específicos do Microsoft Teams

Se sua organização tiver números de chamada gratuita em sua ponte de conferência de áudio da Microsoft, você poderá permitir ou impedir o uso nas reuniões de organizadores específicos.  

Por padrão, todos os usuários de sua organização estão habilitados para usar números de chamada gratuita, o que significa que esses números, se estiverem disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões. Se esse não for o comportamento desejado para alguns usuários da sua organização, você poderá impedir que usuários específicos usem esses números em suas reuniões por meio de um controle de habilitação de número de chamada gratuita. 

Quando números de chamada gratuita são desativados para um organizador específico: 
 - Um número de chamada gratuita não será mais incluído em seus convites de reunião. 
 - Os números de chamada gratuita não serão mais listados na página "encontrar um número local" que é referenciado em seus convites de reunião. 
 - Os participantes não poderão participar da reunião do organizador específico se discarem qualquer número de chamada gratuita da organização. 
 - Todas as reuniões do organizador serão automaticamente reagendadas e o número de chamada gratuita será removido delas.  

    > [!IMPORTANT]
    > Isso reenviará todos os convites de email do organizador para todos os participantes dessas reuniões. 

 - Os participantes podem continuar a ingressar em reuniões do organizador usando números de chamada tarifada. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desativar números gratuitos para usuários específicos 

No **centro de administração do Microsoft Teams**:

1. Na navegação à esquerda, clique em **usuários**e selecione o usuário na lista de usuários disponíveis.

2. Ao lado de **conferência de áudio**, clique em **Editar**.

3. Defina **incluir números de chamada gratuita em solicitações de reunião desse usuário** para **desativar**. 

4. Clique em **salvar.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Usando o PowerShell**  

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
