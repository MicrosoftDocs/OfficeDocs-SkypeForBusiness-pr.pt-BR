---
title: Restrições de chamada de saída - AudioConferência & chamadas PSTN
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Os administradores podem controlar o tipo de audioconferência e chamadas PSTN do usuário final que podem ser feitas pelos usuários.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908650"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário

Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização. 

Os controles de chamada de saída podem ser aplicados por usuário e fornecem os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída. Por padrão, os dois controles são definidos para permitir chamadas internacionais e domésticas. 

|Controle|Descrição|Opções de controle|
|:-----|:-----|:-----|
|Chamadas PSTN de audioconferência|Restringe o tipo de saída </br>chamadas que são permitidas a partir de dentro </br>reuniões organizadas por um usuário.|Qualquer destino (padrão)</br>No mesmo país ou região que o organizador </br> [Zona A somente países ou regiões](audio-conferencing-zones.md) </br>Não permitir|
|Chamadas PSTN do usuário final|Restringe o tipo de chamadas </br>que podem ser feitas por um usuário.|Internacional e Doméstico (padrão)</br>Doméstico</br>Nenhum|

Para descobrir quais países e regiões são considerados Zona A, confira as zonas país e [região para Audioconferência.](audio-conferencing-zones.md)

   > [!NOTE]
   > Uma chamada é considerada doméstica se o número discado estiver no mesmo país em que o Microsoft 365 ou o Office 365 foi configurada para o organizador da reunião (no caso de audioconferência) ou para o usuário final (no caso de chamadas PSTN do usuário final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir chamadas de saída de audioconferência

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários** e clique no nome de exibição do usuário na lista de usuários disponíveis.

3. Ao lado **de Audioconferência,** clique em **Editar.**

4. Em **Discagem de reuniões,** selecione a opção de restrição de discagem que você deseja.

5. Clique em **Salvar**. 

![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

1. No Centro **de administração do Skype for Business,** na navegação à esquerda, vá para Usuários de **Audioconferência** e selecione o usuário na lista  >  de usuários disponíveis.

2. No Painel de Ações, clique em **Editar**.

3.  Em **Restrições para discagem de reuniões** deste usuário, selecione a opção de restrição de discagem que você deseja.

      ![As restrições às opções de discagem](media/restrictions-to-dial-outs.png)
      

4. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usando o Windows PowerShell**

As restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy, que tem um atributo de restrição para cada um. A política não pode ser personalizada, em vez disso, há instâncias de política pré-definidas para cada combinação das configurações. 

Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy de saída. (Observe que o cmdlet Grant não contém a palavra "Online" como o cmdlet Obter.) 

A tabela a seguir fornece uma visão geral de cada política.

|||
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário também pode fazer chamadas de saída para números internacionais e domésticos.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    O usuário na conferência só pode discar para números domésticos, e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    O usuário da conferência não pode fazer discagem. Esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    O usuário na conferência só pode discar para números domésticos, e esse usuário só pode fazer chamada de saída para números PSTN domésticos.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    O usuário na conferência só pode discar para números domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    O usuário da conferência não pode fazer discagem, e esse usuário só pode fazer chamada de saída para números PSTN domésticos.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    O usuário da conferência não pode fazer discagem, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    O usuário na conferência só pode discar para países e regiões da Zona [A,](audio-conferencing-zones.md)e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    O usuário na conferência só pode discar para países e regiões da Zona [A,](audio-conferencing-zones.md)e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    O usuário na conferência só pode discar para países e regiões da Zona [A,](audio-conferencing-zones.md)e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
