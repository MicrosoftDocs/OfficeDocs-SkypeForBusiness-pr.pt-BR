---
title: Redefinir o ID de conferência de um usuário no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Conheça as etapas para redefinir o ID de conferência de reunião de um usuário no Microsoft Teams e obtenha links para as ferramentas de atualização e migração da reunião. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887848"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Redefinir o ID de conferência de um usuário no Microsoft Teams

Esse ID de conferência dinâmico é incluído no final dos convites de reunião, juntamente com os números de telefone que podem ser discados para que os chamadores participem de uma reunião. Quando o usuário discar para o número de telefone, um atendedor automático da reunião solicitará que ele insira esse ID de conferência para que possam participar da reunião.
  
> [!NOTE]
> Se o seu provedor de conferência for da Microsoft, os IDs de conferência dos usuários serão definidos como Somente dinâmicos por padrão. Infelizmente, não é possível alterá-lo para que se torne estático, pois isso não tem mais suporte. Os IDs de conferência são definidos automaticamente somente para usuários do Microsoft Teams habilitados para a audioconferência. 


## <a name="resetting-the-conference-id-for-a-user"></a>Redefinir o ID de conferência de um usuário

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. No topo da página, clique em **Editar**.

3. Em **Audioconferência** clique em **Redefinir ID de conferência**.

2. Na janela **Redefinir ID de conferência**, clique em **Redefinir**. Um ID de conferência será criado automaticamente e um e-mail será enviado ao usuário com o novo ID de conferência. Por padrão, os e-mails são enviados aos usuários, mas isso pode ser desativado.   

    
> [!NOTE]
> Depois de redefinir o ID de conferência, um e-mail com o novo ID de conferência será enviado ao usuário. Esse e-mail será enviado para o endereço de e-mail principal, em muitos casos, para a caixa de correio do Office 365. O e-mail contém o novo ID de conferência, o(s) número(s) de telefone de discagem padrão e instruções para atualizar as reuniões existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>O que mais preciso saber?

- Você pode enviar todas as informações da conferência para o usuário em um único e-mail, que inclui o ID de conferência e os números de telefone de discagem, clicando em **Enviar informações de conferência por e-mail** para o usuário na seção **Audioconferência**. O e-mail não envia o PIN.
    
- Um ID de conferência contém sete dígitos e o tamanho não pode ser alterado.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado pelos chamadores. Você deve notificar os usuários para que reagendem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. 

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md)
