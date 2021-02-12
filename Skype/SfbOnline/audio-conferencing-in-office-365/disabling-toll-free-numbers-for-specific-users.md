---
title: Desabilitando números de chamada gratuita para usuários específicos do Skype for Business Online
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
description: Os administradores podem controlar como os organizadores podem usar números de tarifa gratuita para suas reuniões.
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695676"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Desabilitando números de chamada gratuita para usuários específicos do Skype for Business Online
 
> [!Note]
> Para obter informações sobre como desabilitar números sem ferramentas para usuários do Teams, consulte Desabilitar números de tarifa gratuita [para usuários específicos do Teams.](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users)

Se sua organização tiver números de tarifa gratuita em sua Ponte de Audioconferência da Microsoft, você poderá permitir ou impedir o uso deles nas reuniões de organizadores específicos.  

Por padrão, todos os usuários em sua organização estão habilitados para usar números de tarifa gratuita, o que significa que esses números, se disponíveis, podem ser usados pelos participantes para ingressar em suas reuniões. Se esse não for o comportamento desejado para alguns usuários em sua organização, você pode restringir usuários específicos de usar esses números em suas reuniões por meio de um controle de habilitação de número de ligação gratuita. 

Quando os números de tarifa gratuita são desabilitados para um determinado organizador: 
 - Um número de ligação gratuita não será mais incluído em seus convites de reunião. 
 - Os números de tarifa gratuita não serão mais listados na página "Encontrar um número local" referenciada em seus convites de reunião. 
 - Os participantes não poderão ingressar na reunião do organizador se discarem para qualquer número de tarifa gratuita da organização. 
 - Todas as reuniões do organizador serão reagenddas automaticamente, e o número da tarifa gratuita será removido delas.  

    > [!IMPORTANT]
    > Isso resende todos os convites por email do organizador para todos os participantes dessas reuniões. 

 - Os participantes podem continuar in joining meetings of the organizer using toll numbers. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desativar números gratuitos para usuários específicos 

No Centro **de administração do Microsoft Teams:**

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Ao lado **de Audioconferência,** clique em **Editar.**

3. Definir **Incluir números de tarifa gratuita em solicitações de reunião deste usuário** para **Desligado.** 

4. Clique **em Salvar.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Usando o Windows PowerShell**  

Você pode usar o parâmetro AllowTollFreeDialIn do cmdlet Set-CsOnlineDialInConferencingUser para habilitar ou desabilitar esse controle. Por exemplo: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
