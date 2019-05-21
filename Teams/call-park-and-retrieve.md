---
title: Estacionamento e recuperação de chamadas no Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use o parque de chamadas e recupere para colocar uma chamada em espera no serviço do teams na nuvem.
ms.openlocfilehash: fc33ef6c36a9764e39840f384dc70aa1a692579c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283497"
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

Para estacionar e recuperar chamadas, um usuário deve ser um usuário de voz empresarial, e um administrador deve conceder ao usuário uma política de estacionamento de chamadas. Para obter mais informações sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para Microsoft Teams](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Ligar para o parque da chamada e recuperar a disponibilidade de recursos

O estacionamento de chamadas e a recuperação têm suporte no momento pelos seguintes clientes e dispositivos. (Compatível com o modo somente Teams, com ou sem conectividade PSTN)

| Potencial | Teams desktop | Aplicativo Teams Mac | Aplicativo Web do Teams (Edge) |Aplicativo móvel do teams para iOS/Android | Telefone IP do teams | Telefone IP do Skype for Business |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Estacionar uma chamada | Sim | Sim | Sim | Sim | Em breve| Não |
| Recuperar uma chamada estacionada | Sim | Sim | Sim | Sim | Em breve| Não |
| Retorno de chamada não recuperado | Sim | Sim | Sim | Sim | Em breve| Não |

## <a name="configuring-call-park-and-retrieve"></a>Configurar o estacionamento de chamadas e recuperar

Você deve ser um administrador para configurar o estacionamento de chamadas e a recuperação, e o recurso está desabilitado por padrão. Você pode habilitá-lo para usuários e criar grupos de usuários usando a política de estacionamento de chamadas. Quando você aplica a mesma política a um conjunto de usuários, ele pode estacionar e recuperar chamadas entre si. Para configurar os grupos de usuários do parque de chamadas para usuários e criar grupos de usuários do parque de chamadas, siga o procedimento de [política atribuir um estacionamento de chamada](#assign-a-call-park-policy) abaixo.

Para obter informações sobre como usar o recurso Park e retrieve Call, consulte [estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Habilitar uma política de estacionamento de chamadas

Siga estas etapas para habilitar uma política de estacionamento de chamadas:

1. Vá para**políticas de estacionamento de chamada**de**voz** >  **do centro** > de administração do Microsoft Teams.
2. Selecione **nova política**.
3. Dê um nome à política e, em seguida, alterne **permitir estacionamento de chamada** para **ativado**.
4. Selecione **salvar**.

### <a name="assign-a-call-park-policy"></a>Atribuir uma política de estacionamento de chamadas

Siga estas etapas para atribuir uma política de estacionamento de chamadas a um ou mais usuários:

1. Vá para**políticas de estacionamento de chamada**de**voz** >  **do centro** > de administração do Microsoft Teams.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **gerenciar usuários**.
4. No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**. Repita esta etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **salvar**.
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurar o estacionamento de chamadas e recuperar com o PowerShell

Use o cmdlet [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) do PowerShell para criar uma política de estacionamento de chamadas.

Use o cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) do PowerShell para conceder uma política de estacionamento de chamadas.

Você pode alterar a configuração padrão usando [set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) da seguinte maneira:

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Solução de problemas

Se os usuários não conseguirem ver o botão Park ou retrieve: 

- Verifique se o usuário tem a política de estacionamento de chamadas habilitada. 

Se um usuário tentar recuperar uma chamada e não tiver êxito, verifique o seguinte:

- Verifique se o usuário está usando o cliente do teams ou um dispositivo/telefone habilitado para equipes
- Agrupamento – o usuário é membro do grupo de estacionamento de chamadas?
- Modo ilha – o parque de chamadas e a recuperação não está disponível no modo da ilha Teams.
- A chamada já foi recuperada ou terminada.

## <a name="more-information"></a>Mais informações

[Estacionar uma chamada no Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).