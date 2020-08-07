---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 04/12/2019
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: Saiba como usar o estacionamento de chamadas e recuperar para colocar uma chamada em espera no serviço do teams na nuvem.
ms.openlocfilehash: 8c6f275ea1b1aac9bfa011fba76d17aeb1811e10
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582648"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento e recuperação de chamadas no Microsoft Teams

O estacionamento de chamadas e a recuperação são um recurso que permite que um usuário faça uma chamada em espera no serviço do teams na nuvem. Quando uma chamada está estacionada, o serviço gera um código exclusivo para recuperação de chamadas. O usuário que estacionau a chamada ou outra pessoa pode usar esse código e um aplicativo ou dispositivo com suporte para recuperar a chamada. 

Alguns dos cenários comuns para usar o parque de chamadas são: 

- Um recepcionista é um pedido de alguém trabalhando em uma fábrica. Em seguida, o recepcionista anuncia a chamada e o número do código pelo sistema de endereços público. O usuário para o qual a chamada é para pode pegar um telefone de equipe no chão de fábrica e digitar o código para recuperar a chamada.
- Um usuário representa uma chamada em um dispositivo móvel porque a bateria do dispositivo está ficando sem energia. Em seguida, o usuário pode inserir o código para recuperar a chamada em um telefone de mesa do teams.
- Um representante de suporte tem um representante do cliente e envia um comunicado em um canal de equipe para que um especialista para recuperar a chamada e ajudar o cliente. Um especialista insere o código em clientes do teams para recuperar a chamada

> [!IMPORTANT]
> Esse recurso só está disponível no modo de implantação do teams. Para obter mais informações sobre os modos de implantação do Teams, consulte [entender o Microsoft Teams e a coexistência e interoperabilidade do Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>Licença necessária

Para estacionar e recuperar chamadas, um usuário deve ser um usuário de voz empresarial, e um administrador deve conceder ao usuário uma política de estacionamento de chamadas. Para obter mais informações sobre o modelo de licenciamento, consulte [Descrição de serviço do Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).

## <a name="call-park-and-retrieve-feature-availability"></a>Ligar para o parque da chamada e recuperar a disponibilidade de recursos

O estacionamento de chamadas e a recuperação têm suporte no momento pelos seguintes clientes e dispositivos. (Compatível com o modo somente Teams, com ou sem conectividade PSTN)

| Funcionalidade | Teams desktop | Aplicativo Teams Mac | Aplicativo Web do Teams (Edge) |Aplicativo móvel do teams para iOS/Android | Telefone IP do teams | Telefone IP do Skype for Business |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Estacionar uma chamada | Sim | Sim | Sim | Sim | Sim | Não |
| Recuperar uma chamada estacionada | Sim | Sim | Sim | Sim | Sim | Não |
| Retorno de chamada não recuperado | Sim | Sim | Sim | Sim | Sim | Não |

## <a name="configure-call-park-and-retrieve"></a>Configurar o estacionamento e a recuperação de chamadas

Você deve ser um administrador para configurar o estacionamento de chamadas e a recuperação, e o recurso está desabilitado por padrão. Você pode habilitá-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamadas. Quando você aplica a mesma política a um conjunto de usuários, ele pode estacionar e recuperar chamadas entre si. Para configurar os grupos de usuários do parque de chamadas para usuários e criar grupos de usuários do parque de chamadas, siga o procedimento de [política atribuir um estacionamento de chamada](#assign-a-call-park-policy) abaixo.

Para obter informações sobre como usar o recurso Park e retrieve Call, consulte [estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Habilitar uma política de estacionamento de chamadas

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de estacionamento de chamada**de voz.
2. Selecione **Adicionar**.
3. Dê um nome à política e, em seguida, alterne **permitir estacionamento de chamada** para **ativado**.
4. Selecione **salvar**.

#### <a name="using-powershell"></a>Usando o PowerShell

Veja [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps).

### <a name="edit-a-call-park-policy"></a>Editar uma política de estacionamento de chamadas

1. Na navegação à esquerda do centro de administração do Microsoft Teams, **Voice**vá para  >  **políticas de estacionamento de chamada**de voz.
2. Selecione a política clicando à esquerda do nome da política e, em seguida, clique em **Editar**.
3. Alternar para ativar ou **desativar** o estacionamento **de** **chamadas** .
4. Clique em **Salvar**.

#### <a name="using-powershell"></a>Usando o PowerShell

Consulte [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps). Por exemplo, para alterar a configuração padrão, execute o seguinte:

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a>Atribuir uma política de estacionamento de chamadas

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
Consulte também [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps).

## <a name="troubleshooting"></a>Solução de problemas

Se os usuários não conseguirem ver o botão Park ou retrieve: 

- Verifique se o usuário tem a política de estacionamento de chamadas habilitada. 

Se um usuário tentar recuperar uma chamada e não tiver êxito, verifique o seguinte:

- Verifique se o usuário está usando o cliente do teams ou um dispositivo/telefone habilitado para equipes
- Agrupamento – é o usuário membro do grupo de estacionamento de chamadas, que se baseia em ter as mesmas equipes de chamada de equipe de estacionamento atribuídas. 
- Modo ilha – o parque de chamadas e a recuperação não está disponível no modo da ilha Teams.
- A chamada já foi recuperada ou terminada.

## <a name="related-topics"></a>Tópicos relacionados

[Estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[Atribuir políticas a seus usuários no Teams](assign-policies.md)
