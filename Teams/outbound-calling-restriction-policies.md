---
title: Restrições de chamada de saída – Audioconferência & chamadas PSTN
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Os administradores podem controlar o tipo de audioconferência e chamadas PSTN do usuário final que podem ser feitas pelos usuários.
ms.openlocfilehash: fd7dc24d7a920e5fb2c151600c3a6604381044e6
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674803"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restrição de chamadas de saída de Audioconferências e Chamadas PSTN do usuário

Como administrador, você pode usar controles de chamada de saída para restringir o tipo de conferência de áudio e chamadas PSTN (Rede Telefônica Pública Comuada) do usuário final que podem ser feitas por usuários em sua organização.

Os controles de chamada de saída podem ser aplicados por usuário ou por locatário e fornecem os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída. Por padrão, ambos os controles são definidos para permitir chamadas de saída internacionais e domésticas.

|Controle|Descrição|Opções de controle|
|:-----|:-----|:-----|
|Audioconferência PSTN|Restringe o tipo de saída </br>chamadas que são permitidas de dentro </br>reuniões organizadas por um usuário.|Qualquer destino (padrão)</br>No mesmo país ou região que o organizador </br> [Somente países ou regiões da Zona A](audio-conferencing-zones.md) </br>Não permitir|
|Chamadas PSTN do usuário final|Restringe o tipo de chamadas </br>que pode ser feita por um usuário.|Internacional e Doméstico (padrão)</br>Doméstico</br>Nenhum|

Para descobrir quais países e regiões são considerados Zona A, consulte Zonas de país e região [para Audioconferência](audio-conferencing-zones.md).

   > [!NOTE]
   > Uma chamada será considerada doméstica se o número discado estiver no mesmo país em que Microsoft 365 ou Office 365 foi configurado para o organizador da reunião (no caso de audioconferência) ou o usuário final (no caso de chamadas PSTN do usuário final).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir chamadas de saída de audioconferência

### <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, selecione **Usuários** e, em seguida, selecione o nome de exibição do usuário na lista de usuários disponíveis.

2. Em seguida, vá **para Audioconferência**, selecione **Editar**.

3. Em **Discagem das reuniões**, selecione a opção de restrição de discagem desejada.

4. Selecione **Salvar**.

### <a name="using-powershell"></a>Usando o Windows PowerShell

As restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy, que tem um atributo de restrição para cada uma. A política não pode ser personalizada, em vez disso, há instâncias de política predefinida para cada combinação das configurações.

Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e usar o comando a seguir para a instalação.

**Defina a política em um nível por usuário com o cmdlet a seguir**. (O cmdlet Grant não contém a palavra "Online" como o cmdlet Get.)

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Defina a política no nível do locatário com o cmdlet a seguir**.

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

Todos os usuários do locatário que não têm nenhuma política de discagem atribuída receberão essa política. Outros usuários permanecem com a política atual.

**Verifique a política atual no nível do locatário com o cmdlet a seguir**.

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

A tabela a seguir fornece uma visão geral de cada política.

|Cmdlet do PowerShell|Descrição|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    O usuário da conferência pode discar para números internacionais e domésticos, e esse usuário também pode fazer chamadas de saída para números internacionais e domésticos.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    O usuário da conferência só pode discar para números domésticos, e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    O usuário da conferência não pode discar. Esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário não pode fazer nenhuma chamada de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    O usuário da conferência só pode discar para números domésticos, e esse usuário só pode fazer uma chamada de saída para números PSTN domésticos.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    O usuário da conferência só pode discar para números domésticos, e esse usuário não pode fazer nenhuma chamada de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    O usuário na conferência não pode discar e esse usuário só pode fazer uma chamada de saída para números PSTN domésticos.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    O usuário da conferência não pode discar e esse usuário não pode fazer nenhuma chamada de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    O usuário da conferência só pode discar para países e regiões da Zona [A](audio-conferencing-zones.md), e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    O usuário da conferência só pode discar para países e regiões da Zona [A](audio-conferencing-zones.md), e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    O usuário da conferência só pode discar para países e regiões da Zona [A](audio-conferencing-zones.md), e esse usuário não pode fazer nenhuma chamada de saída para o número PSTN além de números de emergência.    |
