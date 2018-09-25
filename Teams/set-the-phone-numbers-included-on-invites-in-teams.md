---
title: Definir o telefone números incluídos no convidam no Teams da Microsoft
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
ms.openlocfilehash: f62a6e63181c474d19f403d6c81f858177bd8cd0
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016193"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Definir os números de telefone incluídos em convites no Microsoft Teams

Serviços de audioconferência no Office 365 permite aos usuários em sua organização criar reuniões Teams da Microsoft e, em seguida, permitir que os usuários discam para essas reuniões usando um telefone. No Office 365, você tem a opção de usar uma ponte de conferência de áudio da Microsoft ou uma ponte de conferência de áudio de terceiros que é hospedada por um provedor de serviços de audioconferência aprovada (ACP).
  
Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Definir ou alterar o número de telefone de audioconferência padrão para um usuário ou organizador da reunião

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

    ![Mostra a seleção de usuários no Centro de Administração do Microsoft Teams e do Skype for Business](media/teamsselectusers.png)

2. No topo da página, clique em **Editar**.

    ![Clique no Centro de Administração do Microsoft Teams e do Skype for Business](media/teamsedituser.png)

3. Próximo a **Audioconferência**, clique em **Editar**. 
    
    ![Clique em Editar próximo a Audioconferência](media/teamseditaudioconf.png)

4. Use os campos **Número tarifado** ou **Número gratuito** para inserir os números para o usuário.


> [!IMPORTANT]
> Ao alterar as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Microsoft Teams precisam ser atualizadas e enviadas aos participantes. 

## <a name="want-to-use-windows-powershell"></a>Deseja usar o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações. 
  
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
