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
- seo-marvel-mar2020
description: Saiba como controlar como os organizadores podem usar números de tarifa gratuita para suas reuniões da Ponte de Audioconferência.
ms.openlocfilehash: 517ffea6a15cd625320f33e3eb4911f4a250d51d
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904566"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Desativar números de chamada gratuita para usuários específicos do Microsoft Teams

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
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Usando o Windows PowerShell**  

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
