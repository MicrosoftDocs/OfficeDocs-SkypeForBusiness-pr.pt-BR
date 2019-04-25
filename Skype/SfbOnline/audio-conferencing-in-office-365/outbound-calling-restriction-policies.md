---
title: Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar o tipo de usuário final e conferência PSTN chamadas de áudio que podem ser feitas pelos usuários.
ms.openlocfilehash: 36f116acb62cd16863cb547a11fe5687457a8a4e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229783"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restrição de chamadas de saída para audioconferência e chamadas PSTN do usuário

Como administrador, você pode usar os controles de chamadas de saída para restringir o tipo de audioconferência e as chamadas PSTN de usuários finais que podem ser feitas pelos usuários em sua organização. 

Controles de chamada de saída podem ser aplicados em uma base por usuário e fornecem os seguintes dois controles para restringir independentemente de cada tipo de chamadas de saída. Por padrão, ambos os controles são definidos para permitir que as chamadas de saída nacionais e internacionais. 

|Controle|Descrição|Opções de controle|
|:-----|:-----|:-----|
|Chamadas PSTN de conferência de áudio|Restringe o tipo de saída </br>chamadas que são permitidas de dentro </br>reuniões organizadas por um usuário.|Internacional e doméstico (padrão)</br>Doméstico</br>Nenhum|
|Chamadas PSTN de usuário final|Restringe o tipo de chamadas </br>que podem ser feitas por um usuário.|Internacional e doméstico (padrão)</br>Doméstico</br>Nenhum|

   > [!NOTE]
   > Uma chamada é considerada domésticas se o número de telefone chamado esteja no mesmo país que o país que tiver sido definido no Office 365 para o organizador da reunião (no caso de serviços de audioconferência) ou o usuário final (no caso de chamadas da PSTN de usuário final). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir as chamadas de saída de conferência de áudio 

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Ao lado de **Conferência de áudio**, clique em **Editar**.

4. Em **permissão de discagem de reuniões**, selecione a opção de discagem restrição desejada.

5. Clique em **Salvar**. 

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1.  No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **usuários**e selecione o usuário da lista de usuários disponíveis.

2.  No Painel de Ações, clique em **Editar**.

3.  Em **restrições a serem dial-outs de reuniões deste usuário**, selecione a opção de discagem restrição desejada.

    ![As restrições às opções de discagem-outs](../images/restrictions-to-dial-outs.png)

5. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Usando o PowerShell**

Restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy que tem um atributo de restrição para cada um. A política não pode ser personalizada, em vez disso, há instâncias de diretiva predefinidas para cada combinação das configurações. 

Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e atribuí-las aos usuários usando o cmdlet Grant-CSDialOutPolicy. (Observe que o cmdlet Grant não contêm a palavra "Online" como o cmdlet Get faz.) 

A tabela a seguir fornece uma visão geral de cada política.

|||
|:-----|:-----|
|Identidade = 'tag: DialoutCPCandPSTNInternational'    |    Usuário na conferência pode discar para números nacionais e internacionais e esse usuário também pode fazer chamadas de saída para números nacionais e internacionais.    |
|Identidade = 'tag: DialoutCPCDomesticPSTNInternational'  |    Usuário na conferência só pode discar para números nacionais e esse usuário pode fazer chamadas de saída para números nacionais e internacionais.    |
|    Identidade = 'tag: DialoutCPCDisabledPSTNInternational'    |    Usuário na conferência não pode fazer qualquer dial-out. Esse usuário pode fazer chamadas de saída para números nacionais e internacionais.    |
|    Identidade = 'tag: DialoutCPCInternationalPSTNDomestic'    |    Usuário na conferência pode discar para números nacionais e internacionais e esse usuário só pode fazer chamadas de saída para o número PSTN doméstica.    |
|    Identidade = 'tag: DialoutCPCInternationalPSTNDisabled'    |    Usuário na conferência pode discar para números nacionais e internacionais e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.    |
|    Identidade = 'tag: DialoutCPCandPSTNDomestic'    |    Usuário na conferência só pode discar para números nacionais e esse usuário só pode fazer chamadas de saída aos números PSTN domésticas.    |
|    Identidade = 'tag: DialoutCPCDomesticPSTNDisabled'    |    Usuário na conferência só pode discar para números nacionais e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.    |
|    Identidade = 'tag: DialoutCPCDisabledPSTNDomestic'    |    Usuário na conferência não puder fazer qualquer discagem externa e esse usuário só pode fazer chamadas de saída aos números PSTN domésticas.    |
|    Identidade = 'tag: DialoutCPCandPSTNDisabled'    |    Usuário na conferência não puder fazer qualquer discagem externa e este usuário não pode fazer qualquer chamadas de saída para um número PSTN além de números de emergências.    |
