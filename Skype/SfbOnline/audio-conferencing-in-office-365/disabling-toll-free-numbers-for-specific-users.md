---
title: Desabilitando números gratuitos para usuários Skype for Business Online específicos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar como os organizadores podem usar números gratuitos para suas reuniões.
ms.openlocfilehash: 4fae54e3ed140ab876e6fadef10907e40f59057e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238506"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Desabilitando números gratuitos para usuários Skype for Business Online específicos

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> Para obter informações sobre como desabilitar números sem ferramentas para usuários Teams, consulte Desabilitando números gratuitos para usuários Teams [específicos.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)

Se sua organização tiver números gratuitos em sua Ponte de Audioconferência da Microsoft, você poderá permitir ou impedir seu uso nas reuniões de organizadores específicos.  

Por padrão, todos os usuários em sua organização estão habilitados para o uso de números gratuitos, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões. Se esse não for o comportamento desejado para alguns usuários em sua organização, você poderá restringir usuários específicos de usar esses números em suas reuniões por meio de um controle de habilitação de número gratuito. 

Quando os números gratuitos são desabilitados para um determinado organizador: 
 - Um número gratuito não será mais incluído em seus convites de reunião. 
 - Os números gratuitos não serão mais listados na página "Encontrar um número local" referenciada em seus convites de reunião. 
 - Os participantes não poderão participar da reunião do organizador se discarem qualquer número gratuito da organização. 
 - Todas as reuniões do organizador serão reagendadas automaticamente e o número gratuito será removido delas.  

    > [!IMPORTANT]
    > Isso enviará todos os convites de email do organizador a todos os participantes dessas reuniões. 

 - Os participantes podem continuar participando de reuniões do organizador usando números de telefone. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desativar números gratuitos para usuários específicos 

No centro **de Microsoft Teams de administração**:

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Ao lado **de Audioconferência,** clique em **Editar**.

3. Set **Include toll-free numbers in meeting requests from this user** to **Off**. 

4. Clique **em Salvar.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Usando o Windows PowerShell**  

Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle. Por exemplo: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
