---
title: Redefinir o ID de conferência de um usuário
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn the steps to reset a user's meeting conference ID, and get links to meeting update and migration tools. "
ms.openlocfilehash: 3c40c4bb59dd6628730542f73d8bdbddae7b9ad7
ms.sourcegitcommit: a72a1b71a8ef8e9581038503130c2c1a58a4abdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2018
---
# <a name="reset-a-conference-id-for-a-user"></a>Redefinir o ID de conferência de um usuário

Uma ID de conferência dinâmico é incluída na parte inferior da reunião convites, juntamente com os números de telefone de discagem que podem ser usados por chamadores para efetuar uma chamada para uma reunião. Quando o usuário disca o número de telefone, o atendedor automático para a reunião pedirá que o chamador para inserir esta ID de conferência, de forma que eles podem participar da reunião.
  
> [!NOTE]
> Se seu provedor de conferência for Microsoft, IDs de conferência dos usuários são definidos para somente dinâmico por padrão. Infelizmente, não há nenhuma capacidade para alterá-lo no Skype para o Centro de administração de negócios ou usando o Windows Powershell para se tornar estáticas, como agora está sem suporte.
IDs de conferência são definidas apenas automaticamente somente para Skype para usuários de negócios e Teams Microsoft habilitados para conferência de áudio. 
  
## <a name="resetting-the-conference-id-for-a-user"></a>Redefinindo o ID de conferência para um usuário

**Usando equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Clique no menu ao lado de **Pontes de conferência**e, em seguida, clique em **Redefinir id de conferência** na lista suspensa.

2. Na janela **Redefinir id de conferência** , clique em **Okey**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.   

**Usando o Skype para o Centro de administração de negócios**
    
1. No **Skype para centro de administração de negócios**, clique em **conferência de áudio** > **usuários**, selecione um usuário e clique em **Redefinir**no painel de ação em **ID da conferência** .
    
2. No **Redefinir ID de conferência?** janela, clique em **Sim**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Por padrão, os emails são enviados aos usuários, mas isso pode ser desativado.
    
> [!NOTE]
> [!OBSERVAçãO] Depois de redefinir a ID de conferência, um email com a nova ID de conferência será enviado para o usuário. Esse email será enviado para o endereço de email primário do usuário. Em muitos casos, para a caixa de correio do Office 365. O email contém a nova ID de conferência, o(s) número(s) de telefone padrão de discagem e as instruções de como usar a Ferramenta de Atualização de Reunião do Skype for Business para atualizar reuniões existentes. 
  
## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Você pode enviar todas as informações de conferência para o usuário em um email que inclua a ID de conferência e os números de telefone de discagem ao clicar em **Enviar informações de conferência via email** para o usuário no painel de ações. Isso não envia o PIN.
    
- Uma ID de conferência conterá 7 dígitos, e você não poderá alterar seu tamanho no Skype para centro de administração de negócios ou usando o Windows PowerShell.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- O ID de conferência para um usuário para conferência de áudio pode ser exibido na parte inferior do painel de ação em **conferência de áudio** quando você seleciona o usuário na página **usuários** .
    
- Depois que uma nova ID de conferência for criada, a ID antiga não poderá ser usada por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que a nova ID de conferência seja incluída nos convites. Os usuários podem usar Skype para ferramenta de reunião de negócios para atualizar suas reuniões existentes. Para ver como baixar, instalar e executar o Skype para ferramenta de atualização de reunião de negócios, consulte:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, ferramenta de migração de reuniões (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, ferramenta de migração de reuniões (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de audioconferência de um usuário](reset-the-audio-conferencing-pin-for-a-user.md)
