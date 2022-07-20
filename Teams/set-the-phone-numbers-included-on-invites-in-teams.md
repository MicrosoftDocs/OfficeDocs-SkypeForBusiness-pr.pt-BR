---
title: Definir os números de telefone incluídos em convites
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Siga estas etapas para criar um número de telefone padrão para os chamadores ingressarem em uma reunião do Microsoft Teams.
ms.openlocfilehash: f0956007d5df72c1fd6c6ae905433e73bd855a56
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884840"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Definir os números de telefone incluídos em convites no Microsoft Teams

A Audioconferência no Microsoft 365 e Office 365 permite que os usuários em sua organização criem reuniões do Microsoft Teams e, em seguida, permitem que os usuários disquem para essas reuniões usando um número de telefone.

Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.

Além dos números de telefone incluídos no convite da reunião para um organizador da reunião, há também um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone de discagem que podem ser usados para ingressar em uma reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>Atribuição inicial de números de telefone incluídos nos convites da reunião para usuários

Os números de telefone incluídos nos convites de reunião de usuários habilitados para Audioconferência são definidos no *TeamsAudioConferencingPolicy* atribuído aos usuários. Quando um *TeamsAudioConferencingPolicy* é atribuído a um usuário, todos os números de telefone de chamada tarifada e gratuita adicionados na política são incluídos em convites de reunião para usuários que têm essa política. Se um usuário receber um *TeamsAudioConferencingPolicy* e não houver números de telefone de chamada tarifada ou gratuita adicionados à política, nesse caso, os números de telefone que aparecem nos convites de reunião desses usuários serão definidos pelo número de telefone de chamada tarifada de conferência padrão e o número de telefone de chamada gratuita de conferência padrão nas configurações de cada usuário individual.

> [!NOTE]
> Números de telefone de chamada tarifada ou gratuita adicionados ao *TeamsAudioConferencingPolicy* de um usuário têm precedência sobre os números de telefone definidos individualmente usando o número de telefone de chamada tarifada de conferência padrão e o número de telefone de chamada gratuita de conferência padrão nas configurações de um usuário.

Conforme mencionado acima, além dos números de telefone, cada convite de reunião contém um link que abre a lista completa de todos os números de telefone discados que podem ser usados para ingressar em uma determinada reunião.

> [!IMPORTANT]
> Pode levar até 24 horas para que os números de telefone atribuídos apareçam no convite da reunião. Se você não estiver vendo os números atualizados serem exibidos, aguarde pelo menos 24 horas antes de entrar em contato com o suporte.

### <a name="new-users"></a>Novos usuários

Os números de telefone de chamada tarifada e gratuita incluídos nos convites de reunião para novos usuários também são definidos pelo *TeamsAudioconferencingPolicy* atribuído a esses usuários. Por padrão, todos os novos usuários recebem o Global *TeamsAudioconferencingPolicy*. A política global não tem nenhum número de telefone adicionado (a menos que isso seja alterado pelo Administrador de Locatários). Nesse caso, os números de telefone que são incluídos nos convites de reunião de usuários habilitados para Audioconferência são definidos pelo número de telefone de chamada tarifada de conferência padrão e o número de telefone de chamada gratuita de conferência padrão encontrado nas configurações de cada usuário.

Para um novo usuário, os números de chamada tarifada de conferência padrão são atribuídos com base no Local de Uso definido no Centro de administração do Microsoft 365 do usuário quando o usuário está habilitado para o serviço de Audioconferência. Se houver um número de pedágio na ponte de conferência que corresponda ao país do usuário, esse número será atribuído automaticamente como o número de chamada tarifada padrão do usuário. Se não houver um, o número definido como o número de pedágio padrão da ponte de conferência será atribuído como o número de chamada tarifada padrão do usuário.  

Depois que o usuário estiver habilitado para o serviço de Audioconferência, os números de telefone padrão de chamada tarifada e gratuita do usuário poderão ser alterados pelo administrador do locatário de seus valores iniciais, conforme necessário.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>Definir ou alterar o número de telefone de audioconferência padrão para usuários no Powershell usando o cmdlet *TeamsAudioConferencingPolicy*

Confira as [configurações da política de Audioconferência para números de chamada tarifada e gratuita](audio-conferencing-toll-free-numbers-policy.md)

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>Definir ou alterar o número de telefone de audioconferência padrão para um organizador ou usuário da reunião individualmente

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Faça logon no centro de administração do Microsoft Teams.

2. No painel de navegação esquerdo, clique em **Usuários**.

    ![Mostra a seleção de usuários no centro de administração do Microsoft Teams.](media/Admin-users.png)

3. Clique no nome de usuário na lista de usuários disponíveis.

4. Ao lado **de Audioconferência**, clique em **Editar**.

    ![Clique em Editar ao lado de Audioconferência.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Use os **campos número de** chamada **tarifada ou** número de chamada gratuita para inserir os números do usuário.

> [!IMPORTANT]
> Quando você altera as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Microsoft Teams devem ser atualizadas e enviadas aos participantes.

> [!NOTE]
> Os números de telefone inseridos nessa configuração só serão usados se *o TeamsAudioConferencingPolicy* atribuído ao usuário não tiver nenhum número de telefone adicionado.

## <a name="want-to-use-windows-powershell"></a>Deseja usar Windows PowerShell

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar o Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para definir ou alterar o número de telefone de audioconferência padrão para um organizador ou usuário de reunião usando o [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps), **`ServiceNumber`** **`TollFreeServiceNumber`** defina os parâmetros do cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) como um dos números disponíveis.

## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre a Audioconferência no Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Alterar os números de telefone em sua ponte de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
