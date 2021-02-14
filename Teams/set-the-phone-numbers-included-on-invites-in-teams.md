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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Siga estas etapas para criar um número de telefone padrão para os chamadores ingressarem em uma reunião do Microsoft Teams.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372180"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Definir os números de telefone incluídos em convites no Microsoft Teams

A Audioconferência no Microsoft 365 e no Office 365 permite que os usuários em sua organização criem reuniões do Microsoft Teams e permitem que os usuários disquem para essas reuniões usando um telefone.
  
Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Atribuição inicial de números de telefone incluídos nos convites da reunião para novos usuários

Os números de telefone que são incluídos nos convites de reunião de usuários habilitados para AudioConferência são definidos pelo número de telefone de chamada tarifada de conferência padrão e pelas configurações de número de telefone de chamada gratuita de conferência padrão do usuário. Cada configuração especifica qual número de tarifa tarifada e gratuita será incluído no convite da reunião de um determinado usuário. Conforme mencionado acima, cada convite de reunião contém um número de chamada tarifada, um número de chamada gratuita opcional e um link que abre a lista completa de todos os números de telefone de discagem que podem ser usados para ingressar em uma determinada reunião.

Para um novo usuário, os números de tarifa de conferência padrão são atribuídos com base no Local de Uso definido no Centro de administração do Microsoft 365 do usuário quando o usuário está habilitado para o serviço de Audioconferência. Se houver um número de tarifa na ponte de conferência que corresponde ao país do usuário, esse número será atribuído automaticamente como o número de tarifa padrão do usuário. Se não houver uma, o número definido como o número de tarifa padrão da ponte de conferência será atribuído como o número de tarifa padrão do usuário.  

Depois que o usuário é habilitado para o serviço de Audioconferência, os números de telefone de chamada tarifada e gratuita padrão do usuário podem ser alterados pelo administrador do locatário a partir de seus valores iniciais a qualquer momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Definir ou alterar o número de telefone de audioconferência padrão para um organizador ou usuário da reunião

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

Você deve ser um administrador do serviço do Teams para fazer essas alterações. Confira [as funções de administrador do Teams para gerenciar o Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) para ler sobre como obter funções e permissões de administrador.

1. Entre no Centro de administração do Microsoft Teams.

2. No painel de navegação esquerdo, clique em **Usuários.**

    ![Mostra a seleção de usuários no Centro de administração do Microsoft Teams](media/Admin-users.png)

3. Clique no nome de usuário na lista de usuários disponíveis.

4. Ao lado **de Audioconferência,** clique em **Editar.**

    ![Clique em Editar ao lado de Audioconferência](media/teams-set-phone-numbers-on-invites-image3.png)

5. Use os **campos Número de** tarifa ou número de tarifa **gratuita** para inserir os números do usuário.

> [!IMPORTANT]
> Quando você altera as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Microsoft Teams devem ser atualizadas e enviadas aos participantes.

## <a name="want-to-use-windows-powershell"></a>Deseja usar o Windows PowerShell

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar Audioconferência no Microsoft 365 ou no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Alterar os números de telefone em sua ponte de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
