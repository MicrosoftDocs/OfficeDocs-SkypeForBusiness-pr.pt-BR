---
title: Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba como habilitar ou desabilitar chamadores anônimos para participar de uma reunião no centro de administração do Teams. '
ms.openlocfilehash: 380272f3f70d68a04a171ea820e391dd2dd5347a
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41580838"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams

Para os usuários que discarem para uma reunião, pode ser frustrante ficar no lobby ouvindo música porque um organizador do Microsoft Teams não iniciou a reunião. 
  
Por padrão, se o organizador de uma reunião faz uma chamada de entrada para a reunião, é necessário um PIN para iniciar a reunião. É possível configurar a reunião para que qualquer pessoa possa discar para uma reunião e não ser solicitado a digitar um PIN para iniciá-la. É possível usar o centro de administração para ativar ou desativar essa configuração para um único usuário.
  
Não é obrigatório um PIN para o organizador da reunião se alguém tiver iniciado a reunião a partir do aplicativo Microsoft Teams. É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone. O PIN da reunião é enviado para o usuário de áudio quando a licença de **Audioconferência** é atribuída a ele ou quando ele é habilitado para audioconferência. Consulte[Enviar um e-mail para um usuário com as informações de audioconferência](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) e[E-mails enviados automaticamente para os usuários quando as configurações de audioconferência são alteradas](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar ou desabilitar chamadores anônimos para participar de uma reunião

![Um ícone mostrando o logotipo](media/teams-logo-30x30.png) do Microsoft Teams **usando o centro de administração do Microsoft Teams**

1. Na barra de navegação esquerda, clique em **Usuários**. 

2. Selecione um usuário na lista e clique em **Editar** no topo da página. 

3. Próximo a **Audioconferência**, clique em **Editar**.

4. No painel **conferência de áudio** , habilite ou desabilite **chamadores de discagem podem ser a primeira pessoa em uma reunião**.
    
4. Clique em **Aplicar**. 

**Usando o Windows PowerShell**
  
Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-else-should-you-know"></a>O que mais você precisa saber?

- Se desejar redefinir o PIN, veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião estiver desabilitado:
    
  - Se a reunião não tiver sido iniciada (ainda não tem ninguém na reunião): será perguntado ao chamador se ele é o organizador; se responder que sim, ele será solicitado a inserir o PIN. Depois que o PIN for inserido, a reunião será iniciada e o usuário entrará na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião estiver habilitado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador está definida como desativada, a reunião será iniciada e os chamadores anônimos poderão entrar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
