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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Use o estacionamento de chamada e recuperação para colocar uma chamada em espera no serviço de equipes na nuvem.
ms.openlocfilehash: 798e53ef9a0638be659da8567419b7bd3d3c3555
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993498"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Estacionamento e recuperação de chamadas no Microsoft Teams

Estacionamento de chamada e recuperação é um recurso que permite ao usuário colocar uma chamada em espera no serviço de equipes na nuvem. Quando uma chamada estiver estacionada, o serviço gera um código exclusivo para recuperação de chamada. O usuário que a colocou a chamada ou outra pessoa, em seguida, pode usar esse código e um dispositivo ou aplicativo suportados para recuperar a chamada. 

Estes são alguns dos cenários comuns para o uso de estacionamento de chamada: 

- Um recepcionista parques uma chamada para alguém trabalhando em uma fábrica. O recepcionista comunica a chamada e o número de código sobre o sistema de endereço público. Em seguida, o usuário que a chamada é para pode Pegue um telefone de equipes na fábrica e digite o código para recuperar a chamada.
- Um usuário parques uma chamada em um dispositivo móvel, pois a bateria do dispositivo está ficando sem energia. O usuário pode, em seguida, insira o código para recuperar a chamada de um telefone de mesa de equipes.
- Um parques representante de suporte um cliente chamar e envia um anúncio em um canal de equipes para um especialista recuperar a chamada e ajudar o cliente. Com um perito indica o código nos clientes de equipes para recuperar a chamada

> [!IMPORTANT]
> Este recurso só está disponível no modo exclusivo para as equipes de implantação. Para obter mais informações sobre modos de implantação de equipes, consulte [entender as equipes da Microsoft e Skype para interoperabilidade e coexistência de negócios](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>É necessária uma licença

Para estacionar e recuperar chamadas, um usuário deve ser um usuário do Enterprise Voice e um administrador deve conceder ao usuário uma política de estacionamento de chamada. Para obter mais informações sobre o modelo de licenciamento, consulte [Licenciamento do Office 365 para equipes da Microsoft](office-365-licensing.md).

## <a name="call-park-and-retrieve-feature-availability"></a>Estacionamento de chamada e recuperar a disponibilidade de recursos

Estacionamento de chamada e recuperação no momento é suportado pelos seguintes clientes e dispositivos. (Suportado no equipes somente modo, com ou sem conectividade PSTN).

| Recurso | Área de trabalho de equipes | As equipes Mac App | As equipes Web App (borda) |As equipes móveis iOS/Android App | Telefone IP de equipes | Skype para negócios IP phone |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| Estacionar uma chamada | Sim | Sim | Sim | Sim | Em breve| Não |
| Recuperar uma chamada estacionada | Sim | Sim | Sim | Sim | Em breve| Não |
| Toque de chamada não recuperado novamente | Sim | Sim | Sim | Sim | Em breve| Não |

## <a name="configuring-call-park-and-retrieve"></a>Configurando o estacionamento de chamada e recuperação

Você deve ser um administrador para configurar o estacionamento de chamada e recuperação, e o recurso é desabilitado por padrão. Você pode habilitá-lo para usuários e criar grupos de usuários usando a diretiva de estacionamento de chamada. Quando você aplica a mesma política a um conjunto de usuários, eles podem estacionar e recuperar chamadas entre si. Para configurar o estacionamento de chamadas para usuários e criar grupos de usuários de estacionamento de chamada, siga o procedimento abaixo [atribuir uma política de estacionamento de chamada](#assign-a-call-park-policy) .

Para obter informações sobre como usar o estacionamento de chamada e recuperar um recurso, consulte [estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).

### <a name="enable-a-call-park-policy"></a>Habilitar uma política de estacionamento de chamada

Siga estas etapas para habilitar uma diretiva de estacionamento de chamada:

1. Vá para **o Centro de administração do Microsoft equipes** > **voz** > **políticas de estacionamento de chamadas**.
2. Selecione **nova política**.
3. Forneça um nome para a diretiva e, em seguida, trocar **Permitir Call park** para **ativado**.
4. Selecione **Salvar**.

### <a name="assign-a-call-park-policy"></a>Atribuir uma política de estacionamento de chamada

Siga estas etapas para atribuir uma política de estacionamento de chamada a um ou mais usuários:

1. Vá para **o Centro de administração do Microsoft equipes** > **voz** > **políticas de estacionamento de chamadas**.
2. Selecione a política clicando à esquerda do nome da política.
3. Selecione **Gerenciar usuários**.
4. No painel de **Gerenciar usuários** , procure o usuário pelo nome de exibição ou nome de usuário, selecione o nome e selecione **Adicionar**. Repita essa etapa para cada usuário que você deseja adicionar.
5. Quando terminar de adicionar usuários, selecione **Salvar**.
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>Configurar o estacionamento de chamada e recuperar com o PowerShell

Use o cmdlet [New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) do PowerShell para criar uma política de estacionamento de chamada.

Use o cmdlet [Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) do PowerShell para conceder uma política de estacionamento de chamada.

Você pode alterar a configuração padrão usando [Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) da seguinte maneira:

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>Solução de problemas

Se os usuários não podem ver o estacionamento ou recuperar botão: 

- Verifique se o usuário tem a diretiva de estacionamento de chamada ativada. 

Se um usuário tenta recuperar uma chamada e for bem sucedido, verifique o seguinte:

- Verificar se o usuário está usando o cliente de equipes ou um equipes dispositivo/telefone habilitado
- Agrupamento – é o usuário membro do grupo de estacionamento de chamada?
- Modo de ilha – estacionamento de chamada e recuperar não está disponível no modo de ilha de equipes.
- A chamada já foi recuperada ou encerrada.

## <a name="more-information"></a>Mais informações

[Estacionamento de uma chamada em equipes](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f).