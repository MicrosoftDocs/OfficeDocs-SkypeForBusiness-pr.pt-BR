---
title: Iniciar uma conferência de áudio por telefone sem um PIN em Teams da Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a habilitar ou desabilitar os chamadores anônimos ingressem em uma reunião a partir do Centro de administração do equipes. '
ms.openlocfilehash: c68e3a0bd9992eb53811941113a30e9362c78227
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882995"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar uma conferência de áudio por telefone sem um PIN em Teams da Microsoft

Talvez seja frustrante para usuários que discam para uma reunião para ser mantidos no lobby da reunião escutando música porque o organizador da reunião Teams da Microsoft não tiver iniciado a reunião. 
  
Se o organizador da reunião chama reunião, por padrão, é necessário um PIN para iniciar uma reunião. Você pode montá-lo para que qualquer pessoa pode discar para uma reunião e não ser solicitado a fornecer um PIN para iniciar a reunião. Você pode usar o Centro de administração para habilitar ou desabilitar essa configuração de um único usuário.
  
Um PIN não é necessário para o organizador da reunião, se alguém tiver iniciado a reunião do Microsoft Teams app. É necessário inserir um PIN somente quando o organizador da reunião participa da reunião por telefone. O PIN para reuniões é enviado ao usuário áudio quando eles recebem a licença de **Serviços de audioconferência** e estão habilitados para conferência de áudio. Consulte [Enviar um email a um usuário com as informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) e [Emails que são enviados automaticamente para os usuários quando alteram suas configurações de conferência de áudio](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar ou desabilitar chamadores anônimos para participar de uma reunião

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**. 

2. Selecione um usuário na lista e clique em **Editar** na parte superior da página. 

3. Ao lado de **Conferência de áudio**, clique em **Editar**.

4. No painel de **Conferência de áudio** , habilitar ou desabilitar **os chamadores não-autenticados podem ser a primeira pessoa em uma reunião**.
    
4. Clique em **Salvar**. 

**Usando o Windows Powershell**
  
Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-else-should-you-know"></a>O que mais você deve saber?

- Se você deseja redefinir o PIN, consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin-in-teams.md).
    
- Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, estiver habilitado:
    
  - Se a reunião ainda não iniciado (há ninguém na reunião ainda): um chamador será solicitado se ele for o organizador; Se ele diz Sim, ele será solicitado para seu PIN e depois que ele insere o PIN, iniciará a reunião e o usuário será ingressar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a um chamador se ele é o organizador e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e o chamador ingressará.
    
- Se o acesso anônimo ou não exigir um PIN iniciar uma reunião, está desativado:
    
  - Se a reunião ainda não iniciou (não há ninguém na reunião ainda): Não será perguntado a uma chamadora se ela é a organizadora e nunca lhe será solicitado o PIN. Como a configuração do organizador é definida como desativado, a reunião será iniciada e os chamadores anônimos serão ingressar na reunião.
    
  - Se a reunião já iniciou (alguém já está na reunião): Não será perguntado a uma chamadora se ele é a organizadora e nunca lhe será solicitado o PIN; a reunião já estará iniciada, e a chamadora ingressará.
    
## <a name="want-to-know-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a audioconferência no Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
