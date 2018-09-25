---
title: Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service:
- -msteams
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
description: 'Saiba como habilitar ou desabilitar chamadores anônimos para participar de uma reunião no centro de administração do Teams. '
ms.openlocfilehash: 4aec566b165385a111162641f233cd1b1e3027f4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014103"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar uma audioconferência por telefone sem um PIN no Microsoft Teams

Para os usuários que discarem para uma reunião, pode ser frustrante ficar no lobby ouvindo música porque um organizador do Microsoft Teams não iniciou a reunião. 
  
Se o organizador da reunião chama reunião, por padrão, é necessário um PIN para iniciar uma reunião. Você pode montá-lo para que qualquer pessoa pode discar para uma reunião e não ser solicitado a fornecer um PIN para iniciar a reunião. Você pode usar o Centro de administração para habilitar ou desabilitar essa configuração de um único usuário.
  
Um PIN não é necessário para o organizador da reunião, se alguém tiver iniciado a reunião do Microsoft Teams app. É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone. O PIN para reuniões é enviado ao usuário áudio quando eles recebem a licença de **Serviços de audioconferência** e estão habilitados para conferência de áudio. Consulte [Enviar um email a um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) e [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar ou desabilitar chamadores anônimos para participar de uma reunião

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

1. Na barra de navegação esquerda, clique em **Usuários**. 

2. Selecione um usuário na lista e clique em **Editar** no topo da página. 

3. Próximo a **Audioconferência**, clique em **Editar**.

4. No painel **Audioconferência**, habilite ou desabilite **Chamadores não autenticados podem ser a primeira pessoa em uma reunião**.
    
4. Clique em **Salvar**. 

**Usar o Windows PowerShell**
  
Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-else-should-you-know"></a>O que mais você precisa saber?

- Se desejar redefinir o PIN, veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião estiver habilitado:
    
  - Se a reunião não tiver sido iniciada (ainda não tem ninguém na reunião): será perguntado ao chamador se ele é o organizador; se responder que sim, ele será solicitado a inserir o PIN. Depois que o PIN for inserido, a reunião será iniciada e o usuário entrará na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.
    
- Se o acesso anônimo ou não exigir um PIN para iniciar uma reunião estiver desabilitado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador é definida como desativado, a reunião será iniciada e os chamadores anônimos serão ingressar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
