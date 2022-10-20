---
title: Aparência de linha compartilhada no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.users.voice.calldelegation.tooltip
- seo-marvel-apr2020
description: Saiba mais sobre o recurso Compartilhar aparência de linha no Microsoft Teams.
ms.openlocfilehash: 7e3259e948e5a3443d5959eef693416ca3d754ca
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614093"
---
# <a name="shared-line-appearance-in-microsoft-teams"></a>Aparência de linha compartilhada no Microsoft Teams

A aparência de linha compartilhada permite que um usuário escolha um delegado para atender ou manipular chamadas em seu nome. Esse recurso será útil se um usuário tiver um assistente administrativo que manipula regularmente as chamadas do usuário. No contexto de aparência de linha compartilhada, um gerente é alguém que autoriza um representante a fazer ou receber chamadas em seu nome. Um delegado pode fazer ou receber chamadas em nome do delegador.

> [!IMPORTANT]
> Esse recurso só está disponível no modo de implantação somente do Teams. Para obter mais detalhes sobre os modos de implantação do Teams, consulte [Entender o Microsoft Teams e Skype for Business coexistência e interoperabilidade](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licença necessária

Os gerentes e representantes devem ter uma licença do Sistema de Telefonia com conectividade PSTN (Plano de Chamada, Conexão de Operador ou Roteamento Direto). A experiência de linha compartilhada faz parte da delegação e está incluída no Sistema de Telefonia. Para obter mais informações sobre licenciamento, consulte a [descrição do serviço do Microsoft Teams](/office365/servicedescriptions/teams-service-description).

## <a name="shared-line-appearance-feature-availability"></a>Disponibilidade do recurso de aparência de linha compartilhada

No momento, há suporte para a aparência de linha compartilhada nos aplicativos e dispositivos a seguir.

| Recursos | Área de Trabalho do Teams | Aplicativo Mac do Teams | Aplicativo Web do Teams (Edge) |Aplicativo móvel do Teams para iOS/Android | Telefone IP do Teams |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|
| Configurar delegação | Sim | Sim | Sim | Não | Sim |
| Receber chamadas em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Ligar para um número de telefone em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Chamar um usuário do Teams em nome de outro | Sim | Sim | Sim | Sim | Sim |
| Ver a exibição delegada de linhas compartilhadas | Sim | Sim | Sim | Não | Sim |
| Consulte a exibição delegada das atividades de chamada do gerente | Sim | Sim | Sim | Não | Sim |
| Ver a exibição de gerente de delegados | Sim | Sim | Sim | Não | Sim |
| O representante ou o gerente pode manter ou retomar | Sim | Sim | Sim | Não | Sim |

## <a name="limitations"></a>Limitações

Os gerentes podem adicionar até 25 representantes, e os representantes podem ter até 25 gerentes. Não há limite para o número de relações de delegação que podem ser criadas em um locatário. 
 
Se o delegante e o delegado não estão na mesma localização geográfica, o provedor PSTN deve permitir que a ID do chamador apareça de uma localização geográfica diferente para uma chamada delegada. 

A configuração de delegação circular não é permitida. Se os usuários delegados também tiverem delegações entre eles, eles só poderão ver sua delegação e não a delegação inicial.

## <a name="enable-delegation-and-shared-line-appearance"></a>Habilitar delegação e aparência de linha compartilhada

Habilite a delegação usando a **configuração TeamsCallingPolicy AllowDelegation** . Você pode usar o Centro de administração do Teams ou o PowerShell do Teamms. 

Quando habilitado, o usuário final pode configurar suas relações de delegação diretamente no Teams. 

> [!IMPORTANT]
> Ao desativar a delegação de um usuário, você também precisa limpar as relações de delegação para esse usuário no centro de administração do Teams para evitar o roteamento de chamadas incorreto.

## <a name="use-teams-admin-center"></a>Usar o Centro de administração do Teams

Para configurar a delegação e a aparência de linha compartilhada usando o Centro de administração do Teams, consulte [Definir configurações de chamada para seus usuários](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Usar o PowerShell

Para configurar a delegação e a aparência de linha compartilhada usando o Teams PowerShell, use os seguintes cmdlets:

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)

- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)

- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)

### <a name="examples"></a>Exemplos

No exemplo a seguir, user2@contoso.com é adicionado como um representante de user1@contoso.com com permissões para fazer e receber chamadas em nome de user1 e para alterar as configurações de outros representantes:

```powershell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

No próximo exemplo, o representante user2@contoso.com não tem mais permissão para fazer chamadas em nome de user1:

```powershell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

No exemplo a seguir, user2@contoso.com é removido como um delegado de user1@contoso.com:

```powershell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```
 
## <a name="more-information"></a>Mais informações

[Compartilhar uma linha telefônica com um representante](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

[Política de chamada do Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
