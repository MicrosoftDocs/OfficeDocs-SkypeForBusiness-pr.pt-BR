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
ms.openlocfilehash: 859bf6f4a99f95c67123385c99061b1546eaa60c
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26296267"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Definir os números de telefone incluídos em convites no Microsoft Teams

A audioconferência do Office 365 permite que os usuários da sua organização criem reuniões do Microsoft Teams e permitem que os usuários disquem para essas reuniões usando um telefone. No Office 365, você tem a opção de usar uma ponte de audioconferência da Microsoft ou uma ponte de audioconferência de terceiros hospedada por um provedor de serviços de audioconferência (ACP) aprovado.
  
Uma ponte de conferência fornece um conjunto de números de telefone de discagem para a sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Definir ou alterar o número de telefone de audioconferência padrão para um usuário ou organizador da reunião

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) Usando equipes da Microsoft e Skype para Business Admin Center

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

    ![Mostra a seleção de usuários no Microsoft Teams e Skype para centro de administração do Business](media/teamsselectusers.png)

2. Na parte superior da página, clique em **Editar**.

    ![Clique em Editar no Microsoft equipes e Skype para Business Admin Center](media/teamsedituser.png)

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
