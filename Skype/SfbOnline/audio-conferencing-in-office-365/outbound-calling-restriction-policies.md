---
title: Saída diretivas de restrição de chamada para chamadas PSTN de conferência de áudio e usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Os administradores podem controlar o tipo de usuário final e conferência PSTN chamadas de áudio que podem ser feitas pelos usuários.
ms.openlocfilehash: 2929198a8bfff866f0d9f6d375593cd429885b2e
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Saída diretivas de restrição de chamada para chamadas PSTN de conferência de áudio e usuário

Como administrador, você pode usar controles de chamada de saída para restringir o tipo de usuário final e conferência PSTN chamadas de áudio que podem ser feitas pelos usuários em sua organização. 

Controles de chamada de saída podem ser aplicados em uma base por usuário e fornecem os seguintes dois controles para restringir independentemente de cada tipo de chamadas de saída. Por padrão, ambos os controles são definidos para permitir que as chamadas de saída nacionais e internacionais. 

|Controle|Descrição|Opções de controle|
|:-----|:-----|:-----|
|Chamadas PSTN de conferência de áudio|Restringe o tipo de saída </br>chamadas que são permitidas de dentro </br>reuniões organizadas por um usuário.|Internacional e doméstico (padrão)</br>Doméstico</br>Nenhum|
|Chamadas PSTN de usuário final|Restringe o tipo de chamadas </br>que podem ser feitas por um usuário.|Internacional e doméstico (padrão)</br>Doméstico</br>Nenhum|

   > [!NOTE]
   > Uma chamada é considerada domésticas se o número de telefone chamado esteja no mesmo país que o país que tiver sido definido no Office 365 para o organizador da reunião (no caso de serviços de audioconferência) ou o usuário final (no caso de chamadas da PSTN de usuário final). 


## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir as chamadas de saída de conferência de áudio 

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Clique no menu ao lado de **Pontes de conferência**e clique em **Editar** na lista suspensa.

4. No painel de **provedor de ponte de conferência** , em **restrições a serem dial-outs de reuniões deste usuário**, selecione a opção de restrição de discagem desejado.

5. Clique em **Aplicar**. 

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
