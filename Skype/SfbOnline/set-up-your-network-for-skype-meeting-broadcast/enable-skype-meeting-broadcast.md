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
description: Para que as pessoas em sua organização possam usar a Transmissão de Reunião do Skype, você precisa habilita-la. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um parceiro da Microsoft para fazer esta etapa por você.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865135"
---
# <a name="enable-skype-meeting-broadcast"></a>Habilitar a Transmissão de Reunião do Skype

> [!IMPORTANT]
> O Skype for Business Online se desposenta em 31 de julho de 2021, momento em que o acesso ao serviço terminará. Incentivamos os clientes a iniciar a atualização para o Microsoft Teams, o cliente principal para comunicações e trabalho em equipe no Microsoft 365.

Para que as pessoas em sua organização possam usar a Transmissão de Reunião do Skype, você precisa habilita-la. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.



> [!NOTE]
> O Centro de administração do Microsoft Teams substituiu o Centro de administração do Skype for Business (portal herdado). Todas as configurações para gerenciar o Skype for Business agora estão no Centro de administração do Teams. Você deve ter a função de administrador do [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de Administrador global ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no Centro de administração do Teams. Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business

![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**

1. Entre com sua conta de administrador global ou com a conta de administrador do Skype for Business em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. No centro de administração, vá para **o Teams do Centro de**  >  **administração.**
    
3. No Centro **de administração do Teams,** vá para **o Portal Herdado** Online Para transmitir reuniões, selecione  >    >  Habilitar Transmissão **de Reunião do Skype.**
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>Habilitar a Transmissão de Reunião do Skype usando o PowerShell

1. Verifique se você está executando a versão 3.0 ou superior do Windows PowerShell.
    
2. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
3. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
4. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
5. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
6. No **Menu Iniciar,** escolha **Windows PowerShell.**
    
7. Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:
    
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

[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
