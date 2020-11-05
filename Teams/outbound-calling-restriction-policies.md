---
title: Restrições de chamadas de saída-conferências de áudio & chamadas PSTN
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
description: Os administradores podem controlar o tipo de conferência de áudio e as chamadas PSTN do usuário final que podem ser feitas pelos usuários.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908650"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário

Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização. 

Os controles de chamada de saída podem ser aplicados por usuário e fornecer os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída. Por padrão, ambos os controles são definidos para permitir chamadas internacionais e domésticas de saída. 

|Controle|Descrição|Opções de controle|
|:-----|:-----|:-----|
|Chamadas PSTN de conferência de áudio|Restringe o tipo de saída </br>chamadas que são permitidas dentro </br>reuniões organizadas por um usuário.|Qualquer destino (padrão)</br>No mesmo país ou região do organizador </br> [Zona para apenas países ou regiões](audio-conferencing-zones.md) </br>Não permitir|
|Chamadas PSTN do usuário final|Restringe o tipo de chamadas </br>que podem ser feitas por um usuário.|Internacional e doméstico (padrão)</br>Doméstico</br>Nenhum|

Para descobrir quais países e regiões são considerados zona A, consulte [zonas de país e região para videoconferências](audio-conferencing-zones.md).

   > [!NOTE]
   > Uma chamada será considerada doméstica se o número discado estiver no mesmo país em que o Microsoft 365 ou o Office 365 foi configurado para o organizador da reunião (no caso de videoconferência) ou o usuário final (no caso de chamadas PSTN do usuário final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir chamadas de saída de áudio videoconferência

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **usuários** e, em seguida, clique no nome para exibição do usuário na lista de usuários disponíveis.

3. Ao lado de **conferência de áudio** , clique em **Editar**.

4. Em **discagem de reuniões** , selecione a opção de restrição de discagem que você deseja.

5. Clique em **Salvar**. 

![Um ícone mostrando o logotipo do Skype for Business](media/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

1. No **centro de administração do Skype for Business** , no painel de navegação esquerdo, vá para **Audio conferencing**  >  **usuários** de audioconferência e, em seguida, selecione o usuário na lista de usuários disponíveis.

2. No Painel de Ações, clique em **Editar**.

3.  Em **restrições a chamadas discadas de reuniões desse usuário** , selecione a opção de restrição discada que você deseja.

      ![Restrições às opções de discagem](media/restrictions-to-dial-outs.png)
      

4. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usando o PowerShell**

Restrições de chamadas de saída são controladas por uma única política chamada OnlineDialOutPolicy que tem um atributo Restriction para cada. A política não pode ser personalizada, em vez disso, há instâncias de política predefinidas para cada combinação das configurações. 

Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamadas de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy. (Observe que o cmdlet Grant não contém a palavra "online" como o cmdlet Get.) 

A tabela a seguir fornece uma visão geral de cada política.

|||
|:-----|:-----|
|Identity = ' marca: DialoutCPCandPSTNInternational '    |    O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário também pode fazer chamadas de saída para números internacionais e nacionais.    |
|Identity = ' marca: DialoutCPCDomesticPSTNInternational '  |    O usuário na conferência pode discar para números domésticos e esse usuário pode fazer chamadas de saída para números internacionais e nacionais.    |
|    Identity = ' marca: DialoutCPCDisabledPSTNInternational '    |    O usuário na conferência não pode fazer dial-out. Este usuário pode fazer chamadas de saída para números internacionais e nacionais.    |
|    Identity = ' marca: DialoutCPCInternationalPSTNDomestic '    |    O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.    |
|    Identity = ' marca: DialoutCPCInternationalPSTNDisabled '    |    O usuário na conferência pode discar para números internacionais e nacionais, e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.    |
|    Identity = ' marca: DialoutCPCandPSTNDomestic '    |    O usuário na conferência pode discar para números domésticos e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.    |
|    Identity = ' marca: DialoutCPCDomesticPSTNDisabled '    |    O usuário na conferência pode discar para números domésticos e esse usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.    |
|    Identity = ' marca: DialoutCPCDisabledPSTNDomestic '    |    O usuário na conferência não pode fazer dial-out, e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.    |
|    Identity = ' marca: DialoutCPCandPSTNDisabled '    |    O usuário na conferência não pode fazer dial-out, e este usuário não pode fazer chamadas de saída para o número PSTN além dos números de emergência.    |
|    Identity = ' marca: DialoutCPCZoneAPSTNInternational '    |    O usuário na conferência só pode discar para [países e regiões da região](audio-conferencing-zones.md), e esse usuário pode fazer chamadas de saída para números internacionais e nacionais.    |
|    Identity = ' marca: DialoutCPCZoneAPSTNDomestic '    |    O usuário na conferência só pode discar para [países e regiões da região](audio-conferencing-zones.md), e esse usuário somente pode fazer chamadas de saída para números PSTN domésticos.    |
|    Identity = ' marca: DialoutCPCZoneAPSTNDisabled '    |    O usuário na conferência só pode discar para [países e regiões da região](audio-conferencing-zones.md), e esse usuário não pode fazer chamadas de saída para números PSTN além de números de emergência.    |
