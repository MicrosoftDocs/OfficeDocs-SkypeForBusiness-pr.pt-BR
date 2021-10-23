---
title: Definir os números de telefone incluídos em convites
ms.author: tonysmit
author: tonysmit
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
description: Siga estas etapas para criar um número de telefone padrão para os chamadores ingressarem em uma Microsoft Teams reunião.
ms.openlocfilehash: bef8575e1e799c63159bec5cbfb06c80f4af6c83
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536742"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Definir os números de telefone incluídos em convites no Microsoft Teams

A audioconferência em Microsoft 365 e Office 365 permite que os usuários em sua organização criem reuniões Microsoft Teams e, em seguida, permitir que os usuários discem para essas reuniões usando um telefone.
  
Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Atribuição inicial de números de telefone incluídos nos convites da reunião para novos usuários

Os números de telefone que são incluídos nos convites de reunião de usuários habilitados para Audioconferência são definidos pelo número de telefone de chamada de chamada de conferência padrão e pelas configurações padrão do número de telefone gratuito de conferência do usuário. Cada configuração especifica qual número gratuito e de tarifa será incluído no convite de reunião de um determinado usuário. Conforme mencionado acima, cada convite de reunião contém um número de chamada gratuita, um número gratuito opcional e um link que abre a lista completa de todos os números de telefone discados que podem ser usados para ingressar em uma determinada reunião.

Para um novo usuário, os números de tarifa de conferência padrão são atribuídos com base no Local de Uso definido no centro de administração Microsoft 365 do usuário quando o usuário está habilitado para o serviço de Audioconferência. Se houver um número de pedágio na ponte de conferência que corresponde ao país do usuário, esse número será atribuído automaticamente como o número de tarifa padrão do usuário. Se não houver um, o número definido como o número de tarifa padrão da ponte de conferência será atribuído como o número de tarifa padrão do usuário.  

Depois que o usuário for habilitado para o serviço de Audioconferência, os números de telefone de chamada gratuita e de chamada padrão do usuário poderão ser alterados pelo administrador de locatários de seus valores iniciais a qualquer momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Definir ou alterar o número de telefone de audioconferência padrão para um organizador de reunião ou usuário

 **Usando o centro de administração do Microsoft Teams**

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Faça logoff no Microsoft Teams de administração.

2. Na navegação à esquerda, clique em **Usuários**.

    ![Mostra a seleção de usuários no Microsoft Teams de administração.](media/Admin-users.png)

3. Clique no nome do usuário na lista de usuários disponíveis.

4. Ao lado **de Audioconferência,** clique em **Editar**.

    ![Clique em Editar ao lado de Audioconferência.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Use os **campos Número de Telefone** ou Número **gratuito** para inserir os números do usuário.

> [!IMPORTANT]
> Quando você altera as configurações de audioconferência de um usuário, reuniões Microsoft Teams reuniões recorrentes e futuras devem ser atualizadas e enviadas aos participantes.

## <a name="want-to-use-windows-powershell"></a>Deseja usar Windows PowerShell

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para definir ou alterar o número de telefone de audioconferência padrão para um organizador de reunião ou usuário usando [o Microsoft Teams PowerShell,](/powershell/module/teams/?view=teams-ps)defina os parâmetros ou do **`ServiceNumber`** **`TollFreeServiceNumber`** cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) para um dos números disponíveis.

## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Alterar os números de telefone em sua ponte de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
