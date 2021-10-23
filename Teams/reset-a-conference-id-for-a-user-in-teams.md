---
title: Redefinir a ID de conferência de um usuário no Microsoft Teams
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Saiba as etapas para redefinir a ID da conferência de reunião do usuário no Microsoft Teams e obter links para ferramentas de atualização e migração de reuniões.
ms.openlocfilehash: 3a308be01f84509ea93793d7c2b1bdfd6e084268
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536482"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Redefinir a ID de conferência de um usuário no Microsoft Teams

Uma ID de conferência dinâmica é incluída na parte inferior dos convites de reunião, juntamente com os números de telefone discados que podem ser usados pelos chamadores para ligar para uma reunião. Quando o usuário discar o número de telefone, o atendedor automático da reunião solicitará que o chamador insira essa ID de conferência para que ele possa participar da reunião.
  
> [!NOTE]
> As IDs de conferência são geradas automaticamente, terão entre 7 e 9 dígitos e serão definidas quando você habilitar a Audioconferência para um usuário. **Não há suporte para IDs de conferência estáticas.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Redefinindo a ID da conferência para um usuário

 **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, clique em **Usuários** e selecione o usuário na lista de usuários disponíveis.

2. Clique **em Editar**.

3. Em **Audioconferência,** clique **em Redefinir a ID da conferência.**

2. Na janela **Redefinir a ID da** conferência, clique em **Redefinir**. A conference ID will be automatically created and an email sent to the user with the new conference ID. Por padrão, os emails são enviados aos usuários, mas isso pode ser desligado.   
    
> [!NOTE]
> Depois de redefinir a ID da conferência, um email com a nova ID de conferência será enviado ao usuário. Esse email será enviado para o endereço de email principal, em muitos casos, seus Microsoft 365 ou Office 365 caixa de correio. O email contém a nova ID de conferência, os números de telefone de discagem padrão e as instruções para atualizar reuniões existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Você pode enviar todas as informações de conferência para o usuário em um email que inclui a ID da conferência e números de telefone discados clicando em Enviar informações de conferência no **email** para o usuário na seção **Audioconferência.** Isso não envia o PIN.
    
- Uma ID de conferência de 7 a 9 dígitos é criada pelo serviço Teams de dados. Não é possível alterar seu comprimento.
    
- Depois que for redefinido, o novo ID de conferência será listado em **ID de Conferência**.
    
- [!IMPORTANTE]  Depois que um novo ID de conferência for criado, o ID antigo não poderá ser usado por chamadores. Você deve notificar aos usuários para reagendarem suas reuniões existentes para garantir que o novo ID de conferência seja incluído nos convites. 

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps&preserve-view=true) para obter mais informações.
    
## <a name="related-topics"></a>Tópicos relacionados

[Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md)