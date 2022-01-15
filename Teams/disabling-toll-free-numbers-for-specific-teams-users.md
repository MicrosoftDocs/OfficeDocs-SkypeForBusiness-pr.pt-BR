---
title: Desativar números de chamada gratuita para usuários específicos do Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Saiba como controlar como os organizadores podem usar números gratuitos para suas reuniões da Ponte de Audioconferência.
ms.openlocfilehash: 18696143930c42649304bb62b5693e95179397e4
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055431"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Desativar números de chamada gratuita para usuários específicos do Microsoft Teams

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
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-powershell"></a>Usando o Windows PowerShell

Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
