---
title: Habilitar a Transmissão de Reunião do Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Para que as pessoas em sua organização possam usar Reunião do Skype Transmissão, você precisa habilita-la. Para fazer isso, você precisa saber como usar Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um Parceiro Microsoft para realizar essa etapa para você.
ms.openlocfilehash: ec42de04b139537f05cadabbdffb84f645edcf2a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731260"
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar a Transmissão de Reunião do Skype

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> Skype for Business Online está se retirando em 31 de julho de 2021, quando o acesso ao serviço terminará. Incentivamos os clientes a começar a atualização para Microsoft Teams, o cliente principal para comunicações e trabalho em equipe Microsoft 365.

Para que as pessoas em sua organização possam usar Reunião do Skype Transmissão, você precisa habilita-la. Para fazer isso, você precisa saber como usar Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.



> [!NOTE]
> O Microsoft Teams de administração substituiu o Skype for Business de administração (portal herdado). Todas as configurações para o Skype for Business agora estão no centro Teams administrador. Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou Skype for Business para gerenciar Skype for Business recursos no centro de administração Teams do Azure. Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business

![Um ícone mostrando o logotipo Skype for Business.](../images/sfb-logo-30x30.png) **Usando o Skype for Business de administração**

1. Entre com sua conta de administrador global ou Skype for Business de administrador em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. No centro de administração, vá para **Centros de administração**  >  **Teams**.
    
3. No centro **de Teams de** administração, vá para Reuniões de transmissão de transmissão de reuniões do **portal**  >  **herdado** e selecione  >   **Habilitar Reunião do Skype Transmissão**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar a Transmissão de Reunião do Skype usando o PowerShell

1. Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).
    
2. Abra um prompt Windows PowerShell de comando e execute os seguintes comandos: 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. Confirme sua configuração do Transmissão de Reunião do Skype atual executando:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Verifique se o parâmetro  _EnableBroadcastMeeting_ está definido como `False`.
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Habilite o Transmissão de Reunião do Skype para sua organização executando:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Você pode confirmar se a configuração está habilitada executando  `Get-CsBroadcastMeetingConfiguration` novamente.
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > [!DICA] Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype. 
  
10. Agora os usuários podem realizar reuniões de transmissão com outros usuários na empresa. Para que eles comecem, indique [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurar a rede para transmitir reuniões com participantes externos

Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.
  
Para ignorar esta etapa e adicionar outra empresa à federação, veja [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Tópicos relacionados

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
