---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
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
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Saiba mais sobre como usar o estacionamento de chamada e recuperar para colocar uma chamada em espera no Microsoft Teams.
ms.openlocfilehash: c541f92b265d5794df4513eb0cda5d2ff2969f20
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614234"
---
# <a name="configure-call-park-and-retrieve"></a>Configurar estacionamento de chamada e recuperar

O estacionamento de chamada e a recuperação permitem que um usuário coloque uma chamada em espera. Quando uma chamada é estacionada, o serviço gera um código exclusivo para recuperação de chamadas. O usuário que estacionou a chamada ou outra pessoa pode usar esse código com um aplicativo ou dispositivo com suporte para recuperar a chamada. (Para obter mais informações, [consulte Estacione uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).)

Alguns dos cenários comuns para usar o estacionamento de chamada são:

- Uma recepção estaciona uma chamada para alguém que trabalha em uma fábrica. Em seguida, a recepção anuncia a chamada e o número de código no sistema de endereços públicos. O usuário para quem a chamada é, em seguida, pode pegar um telefone do Teams no chão de fábrica e inserir o código para recuperar a chamada.

- Um usuário para uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia. Em seguida, o usuário pode inserir o código para recuperar a chamada de um telefone de mesa do Teams.

- Um representante de suporte para uma chamada de cliente e envia um comunicado em um canal do Teams para que um especialista recupere a chamada e ajude o cliente. Um especialista insere o código nos clientes do Teams para recuperar a chamada.

Para estacionar e recuperar chamadas, um usuário deve ser Enterprise Voice usuário e deve ser incluído em uma política de estacionamento de chamada.

Por padrão, o intervalo de números de recebimento de chamadas é de 10 a 99. Você também pode criar seu próprio intervalo personalizado entre 10 e 9999. A primeira chamada estacionada será renderizada como um código de retirada do início do intervalo (por exemplo, 10). A próxima chamada estacionada será renderizada um código de retirada incrementado em 1; ou seja, 11 e assim por diante, até o final do intervalo ser renderizado como um código de retirada. Depois disso, os códigos de retirada renderizados começam novamente do início do intervalo novamente. 

Você pode especificar um tempo limite como o número de segundos de espera antes de tocar de volta quando a chamada estacionada não tiver sido atendia. O intervalo permitido é de 120 a 1800 segundos e o valor padrão é 300 segundos.

Para configurar o estacionamento de chamada e recuperar, você deve ser um administrador do Teams. Ele está desabilitado por padrão. Você pode habilita-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamada. Quando você aplica a mesma política a um conjunto de usuários, eles podem estacionar e recuperar chamadas entre si.

> [!NOTE]
> O estacionamento de chamadas e a recuperação só estão disponíveis no modo [de implantação somente do Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md). Não há suporte para ele em Skype for Business IP.

Você pode configurar o estacionamento de chamada e recuperar usando o centro de administração do Teams ou usando o PowerShell.

## <a name="use-teams-admin-center"></a>Usar o Centro de administração do Teams

Para criar uma nova instância de política de estacionamento de chamada:

1. No painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para políticas **de** > **estacionamento de Chamada de Voz**.

2. Na guia **Gerenciar políticas** , clique em **Adicionar**.

3. Dê um nome à política e, em seguida, **alterne Permitir estacionamento de chamada** para **Ativado**.

4. Altere o intervalo e o tempo limite do parque conforme necessário.

5. Selecione **Salvar**.

Você pode editar a política selecionando-a na lista e clicando em **Editar**.

Para que a política funcione, ela deve ser atribuída aos usuários. Você pode [atribuir a política aos usuários individualmente ou](assign-policies-users-and-groups.md) atribuí-la a um grupo.

Para atribuir uma política de estacionamento de chamada a um grupo:

1. Na página **Políticas de estacionamento de** chamada, na guia **Atribuição de política de** grupo, clique **em Adicionar grupo**.

2. Pesquise o grupo que você deseja usar e clique em **Adicionar**.

3. Escolha uma classificação em comparação com outras atribuições de grupo.

4. Em **Selecionar uma política**, escolha a política à qual você deseja atribuir esse grupo.

5. Selecione **Aplicar**.

## <a name="use-powershell"></a>Usar o PowerShell

Para gerenciar o estacionamento de chamadas e recuperar políticas usando o PowerShell, use os seguintes cmdlets do Módulo do PowerShell do Teams:

- [New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

- [Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

- [Get-CsTeamsCallParkPolicy](/powershell/module/skype/get-csteamscallparkpolicy)

- [Remove-CsTeamsCallParkPolicy](/powershell/module/skype/remove-csteamscallparkpolicy)

- [Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)

### <a name="examples"></a>Exemplos

#### <a name="new-custom-call-park-policy"></a>Nova política personalizada de estacionamento de chamada

O exemplo a seguir cria uma política de estacionamento de chamada personalizada que gera números de retirada de 500 a 1500, e isso retornará o parker após 600 segundos se a chamada estacionada não for atendida.

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### <a name="change-a-call-park-policy"></a>Alterar uma política de estacionamento de chamada

O exemplo a seguir desabilita a política de estacionamento de chamada:

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### <a name="grant-a-call-park-policy-to-a-user"></a>Conceder uma política de estacionamento de chamada a um usuário

O exemplo a seguir concede a política de estacionamento de chamada a um usuário:

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### <a name="remove-a-call-park-policy"></a>Remover uma política de estacionamento de chamada

O exemplo a seguir remove a política de estacionamento de chamada:

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```

## <a name="related-topics"></a>Tópicos relacionados

[Estacione uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Atribua políticas a seus usuários no Teams](policy-assignment-overview.md)

