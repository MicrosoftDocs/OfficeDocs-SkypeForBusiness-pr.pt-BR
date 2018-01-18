---
title: "Movendo o provedor de audioconferência de um usuário para Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 3a518241-1ecc-406a-93a1-d2653eecc0f5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.PSTNConferencingEnableUsers
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Change your Skype for Business users from third-party audio conferencing providers (ACP) to a Microsoft dial-in conferencing provider. '
ms.openlocfilehash: 79697299ce2c3e3fa398150cd300e305ef0c672a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="moving-a-users-audio-conferencing-provider-to-microsoft"></a>Movendo o provedor de audioconferência de um usuário para Microsoft

Para usar conferência de áudio no Office 365 com Skype para negócios e Teams da Microsoft, os usuários em sua organização precisam ter uma licença de **Serviços de audioconferência** atribuída a eles e seu provedor de serviços de audioconferência devem ser definidos para a Microsoft. Para obter mais informações sobre licenciamento e quanto custa, consulte [tente ou adquirir audioconferência no Office 365](try-or-purchase-audio-conferencing-in-office-365.md) .
  
## <a name="to-move-a-users-audio-conferencing-provider-to-microsoft"></a>Para mover o provedor de serviços de audioconferência do usuário à Microsoft

Se uma licença de **Serviços de audioconferência** for atribuída a um usuário que não tem um provedor de serviços de audioconferência, o provedor do usuário será automaticamente definido como o Microsoft e você não precisa fazer qualquer outra coisa. Se o usuário já tiver um provedor de serviços de audioconferência, você deverá alterar o provedor do usuário à Microsoft após atribuindo a elas uma licença de **Serviços de audioconferência** .
  
Para definir a Microsoft como o provedor de serviços de audioconferência para um usuário que tenha uma licença de **Serviços de audioconferência** atribuída, mas está usando outro provedor de serviços de audioconferência, faça o seguinte:
  
1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, vá para a **conferência de áudio**.
    
4. Se você vir um banner informando que não existem usuários que têm uma **Conferência de áudio** licença atribuída, mas não tenho o Microsoft definido como seu provedor de serviços de audioconferência ainda, clique em **clique aqui para movê-los**. Se você não vir o banner, no **Skype para centro de administração de negócios** clique em **usuários**e, em seguida, selecione o filtro de **usuários prontos para ser movida para conferência de áudio** .
    
5. Selecione os usuários que você deseja mover e, em seguida, no painel de ações, clique em **Editar**.
    
6. Selecione **Microsoft** na lista **nome do provedor** .
    
    > [!NOTE]
    > Quando o provedor de serviços de audioconferência de um usuário é alterado para a Microsoft, as informações de conferência de áudio do usuário serão alterado. Se você precisa manter essas informações, por favor, registre-a em algum lugar antes de alterar o provedor de qualquer um dos usuários. 
  
7. Clique em **Salvar**.
    
## <a name="what-else-should-i-know"></a>O que mais devo saber?

- Se você selecionar o usuário na lista, você pode exibir as informações de conferência de áudio padrão do usuário, mas não será possível ver o PIN de conferência de áudio. Você pode redefinir o PIN de um usuário de serviços de audioconferência clicando em **Redefinir**.
    
- Se você deseja alterar as configurações de serviços de audioconferência para um usuário, você pode selecione o usuário na lista e, em seguida, clique em **Editar** e faça suas alterações na página **Propriedades** . 
    
## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Audioconferência para o Skype for Business e o Microsoft Teams](set-up-audio-conferencing.md)
  

