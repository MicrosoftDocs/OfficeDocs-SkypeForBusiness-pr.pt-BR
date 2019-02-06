---
title: Definir os números de telefone incluídos em convites no Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenha as etapas para criar um número de telefone padrão para os chamadores ingressar em uma reunião do Microsoft Teams. '
ms.openlocfilehash: 8cbe7a88d1fcb857ce94a95b2a9af7a159ccef5a
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754555"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Definir os números de telefone incluídos em convites no Microsoft Teams

Serviços de audioconferência no Office 365 permite aos usuários em sua organização criar reuniões Teams da Microsoft e, em seguida, permitir que os usuários discam para essas reuniões usando um telefone.
  
Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Atribuição inicial dos números de telefone que estão incluídos na reunião convida para novos usuários

Os números de telefone que serão incluídos na reunião convidam de usuários habilitados para conferência de áudio são definidas pelas configurações de padrão conferência telefone gratuitos número do usuário e o número de telefone de Chamada Tarifada de conferência padrão. Cada configuração especifica qual Chamada Tarifada e o número de chamada gratuito serão incluídas no convite da reunião de um determinado usuário. Conforme observado anteriormente, cada convite de reunião contém o número de chamada um Tarifada, um número de chamada gratuito opcional e um link que abre a lista completa de todos os números de telefone de discagem que podem ser usados para ingressar em uma reunião determinada.

Para um novo usuário, os números de Chamada Tarifada conferência padrão é atribuído com base no país que está definido no Office 365 perfil do usuário quando o usuário está habilitado para o serviço de conferência de áudio. Se houver um número de Chamada Tarifada na ponte de conferência que coincida com o país do usuário, esse número será atribuído automaticamente como o número de Chamada Tarifada padrão do usuário. Se não houver um, o número que é definido como o número de Chamada Tarifada do padrão de ponte de conferência será atribuído como o número de Chamada Tarifada padrão do usuário.  

Depois que o usuário estiver habilitado para o serviço de conferência de áudio, a chamada Tarifada do padrão e números de telefone gratuitos do usuário podem ser alterados pelo administrador do locatário de seus valores iniciais a qualquer momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Definir ou alterar o número de telefone de conferência de áudio padrão para um usuário ou o organizador da reunião

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

    ![Mostra a seleção de usuários no Centro de administração do Microsoft Teams](media/teamsselectusers.png)

2. Na parte superior da página, clique em **Editar**.

    ![Clique em Editar no Centro de administração do Microsoft Teams](media/teamsedituser.png)

3. Ao lado de **Conferência de áudio**, clique em **Editar**. 
    
    ![Clique em Editar ao lado de conferência de áudio](media/teamseditaudioconf.png)

4. Use os campos de **número de Chamada Tarifada** ou **número de chamada gratuito** para inserir os números para o usuário.


> [!IMPORTANT]
> Quando você altera as configurações de conferência de áudio de um usuário, recorrentes e futuras reuniões de Teams da Microsoft devem ser atualizados e enviados aos participantes. 

## <a name="want-to-use-windows-powershell"></a>Você deseja usar o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações. 
  
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
