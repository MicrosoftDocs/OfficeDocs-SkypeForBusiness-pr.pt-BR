---
title: Redefinir o ID de conferência de um usuário no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
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
description: Conheça as etapas para redefinir o ID de conferência de reunião de um usuário no Microsoft Teams e obtenha links para as ferramentas de atualização e migração da reunião.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662121"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Redefinir o ID de conferência de um usuário no Microsoft Teams

Esse ID de conferência dinâmico é incluído no final dos convites de reunião, juntamente com os números de telefone que podem ser discados para que os chamadores participem de uma reunião. Quando o usuário discar para o número de telefone, um atendedor automático da reunião solicitará que ele insira esse ID de conferência para que possam participar da reunião.
  
> [!NOTE]
> As IDs de conferência são geradas automaticamente, serão entre 7-9 dígitos e são definidas quando você habilita a videoconferência para um usuário. **Não há suporte para IDs de conferência estática.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Redefinir a ID de conferência de um usuário

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. No painel de navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Clique em **Editar**.

3. Em **Audioconferência** clique em **Redefinir ID de conferência**.

2. Na janela **Redefinir ID de conferência**, clique em **Redefinir**. Um ID de conferência será criado automaticamente e um e-mail será enviado ao usuário com o novo ID de conferência. Por padrão, os e-mails são enviados aos usuários, mas isso pode ser desativado.   

    
> [!NOTE]
> Depois de redefinir o ID de conferência, um e-mail com o novo ID de conferência será enviado ao usuário. Este e-mail será enviado ao endereço de email principal, em muitos casos, à sua caixa de correio do Microsoft 365 ou do Office 365. O e-mail contém o novo ID de conferência, o(s) número(s) de telefone de discagem padrão e instruções para atualizar as reuniões existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>O que mais preciso saber?

- Você pode enviar todas as informações da conferência para o usuário em um único e-mail, que inclui o ID de conferência e os números de telefone de discagem, clicando em **Enviar informações de conferência por e-mail** para o usuário na seção **Audioconferência**. O e-mail não envia o PIN.
    
- Uma ID de conferência de dígito de 7-9 é criada pelo serviço Teams. Não é possível alterar seu tamanho.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- [!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. 

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md)
