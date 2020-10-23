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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Antes que as pessoas em sua organização possam usar a transmissão de reunião do Skype, você precisa habilitá-la. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um parceiro da Microsoft para fazer esta etapa para você.
ms.openlocfilehash: 601cef096b032dd387de6d84bb7e676dc08054ec
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739049"
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar a Transmissão de Reunião do Skype

> [!IMPORTANT]
> O centro de administração do Microsoft Teams substituiu o centro de administração do Skype for Business (Portal herdado). Todas as configurações para gerenciar o Skype for Business agora estão no centro de administração do teams. Para saber mais, confira [gerenciar as configurações do Skype for Business no centro de administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).

Antes que as pessoas em sua organização possam usar a transmissão de reunião do Skype, você precisa habilitá-la. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

1. Entre com sua conta de administrador global ou uma conta de administrador do Skype for Business em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. No centro de administração, vá para equipes de **centros de administração**  >  **Teams**.
    
3. No **centro de administração do teams**, vá para reuniões online do **portal herdado**  >  **Online meetings**  >  **reuniões de transmissão**e selecione **habilitar transmissão de reunião do Skype**.
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar a Transmissão de Reunião do Skype usando o PowerShell

1. Verifique se você está executando a versão 3.0 ou superior do Windows PowerShell.
    
2. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
3. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
4. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0. Reinicie o computador quando for solicitado.
    
5. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
6. No **menu iniciar**, escolha **Windows PowerShell**.
    
7. Na janela do **Windows PowerShell** , conecte-se ao seu Microsoft 365 ou ao Office 365 executando:
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. Confirme sua configuração do Transmissão de Reunião do Skype atual executando:
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    Verifique se o parâmetro  _EnableBroadcastMeeting_ está definido como `False`.
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. Habilite o Transmissão de Reunião do Skype para sua organização executando:
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    Você pode confirmar se a configuração está habilitada executando-se  `Get-CsBroadcastMeetingConfiguration` novamente.
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > [!DICA] Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype. 
  
10. Agora os usuários podem realizar reuniões de transmissão com outros usuários na empresa. Para que eles comecem, indique [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>Configurar a rede para transmitir reuniões com participantes externos

Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md). 
  
Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.
  
Para ignorar esta etapa e adicionar outra empresa à federação, veja [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md). 
  
## <a name="related-topics"></a>Tópicos relacionados

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
