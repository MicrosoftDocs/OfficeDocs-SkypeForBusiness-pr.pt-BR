---
title: Restrições de chamada de saída - Audioconferência & chamadas PSTN
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Os administradores podem controlar o tipo de audioconferência e chamadas PSTN do usuário final que podem ser feitas pelos usuários.
ms.openlocfilehash: 7f1ec4886c1e1ede22c280091f2ebce9965b6d3b
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766234"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Políticas de restrição de chamadas de saída de Audioconferências e Chamadas PSTN do usuário

Como administrador, você pode usar controles de chamada de saída para restringir o tipo de audioconferência e chamadas PSTN (Rede Telefônica Pública Comucionada) do usuário final que podem ser feitas pelos usuários em sua organização.

Os controles de chamada de saída podem ser aplicados por usuário ou por locatário e fornecem os dois controles a seguir para restringir independentemente cada tipo de chamadas de saída. Por padrão, ambos os controles são definidos para permitir chamadas de saída internacionais e domésticas.

|Controle|Descrição|Opções de controle|
|:-----|:-----|:-----|
|Chamadas PSTN de audioconferência|Restringe o tipo de saída </br>chamadas permitidas de dentro </br>reuniões organizadas por um usuário.|Qualquer destino (padrão)</br>No mesmo país ou região que o organizador </br> [Zona A somente países ou regiões](audio-conferencing-zones.md) </br>Não permitir|
|Chamadas PSTN de usuário final|Restringe o tipo de chamadas </br>que pode ser feita por um usuário.|Internacional e Doméstico (padrão)</br>Doméstico</br>Nenhum|

Para descobrir quais países e regiões são considerados Zona A, consulte Zonas de país e [região para Audioconferência](audio-conferencing-zones.md).

   > [!NOTE]
   > Uma chamada é considerada doméstica se o número discado estiver no mesmo país em que Microsoft 365 ou Office 365 foi configurada para o organizador da reunião (no caso da audioconferência) ou para o usuário final (no caso de chamadas PSTN do usuário final).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Restringir chamadas de saída de audioconferência

**Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, selecione **Usuários** e selecione o nome de exibição do usuário na lista de usuários disponíveis.

3. Ao lado **de Audioconferência,** selecione **Editar**.

4. Em **Discagem de reuniões,** selecione a opção de restrição de discagem que você deseja.

5. Selecione **Salvar**.


**Usando o Windows PowerShell**

As restrições de chamada de saída são controladas por uma única política chamada OnlineDialOutPolicy, que tem um atributo de restrição para cada um. A política não pode ser personalizada, em vez disso, há instâncias de política pré-definidas para cada combinação das configurações.

Você pode usar o cmdlet Get-CSOnlineDialOutPolicy para exibir as políticas de chamada de saída e usar o comando a seguir para a instalação.

**De definir a política em um nível por usuário com o cmdlet a seguir.** (O cmdlet Grant não contém a palavra "Online" como o cmdlet Get faz.)

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**De definir a política no nível do locatário com o cmdlet a seguir.**

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

Todos os usuários do locatário que não têm nenhuma política de discagem atribuída receberão essa política. Outros usuários permanecem com sua política atual.

**Verifique a política atual no nível do locatário com o cmdlet a seguir.**

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

A tabela a seguir fornece uma visão geral de cada política.

|Cmdlet do PowerShell|Descrição|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário também pode fazer chamadas de saída para números internacionais e domésticos.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    O usuário na conferência só pode discar para números domésticos, e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    O usuário na conferência não pode discar. Esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    O usuário na conferência pode discar para números internacionais e domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    O usuário na conferência só pode discar para números domésticos, e esse usuário só pode fazer chamada de saída para números PSTN domésticos.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    O usuário na conferência só pode discar para números domésticos, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    O usuário na conferência não pode discar e esse usuário só pode fazer chamada de saída para números PSTN domésticos.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    O usuário na conferência não pode discar e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    O usuário na conferência só pode discar para zona [A](audio-conferencing-zones.md)países e regiões, e esse usuário pode fazer chamadas de saída para números internacionais e domésticos.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    O usuário na conferência só pode discar para zona [A](audio-conferencing-zones.md)países e regiões, e esse usuário só pode fazer chamadas de saída para o número PSTN doméstico.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    O usuário na conferência só pode discar para zona [A](audio-conferencing-zones.md)países e regiões, e esse usuário não pode fazer chamadas de saída para o número PSTN além de números de emergência.    |
