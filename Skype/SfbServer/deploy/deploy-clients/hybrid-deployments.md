---
title: Implantações híbridas do sistema de salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para saber como implantar o sistema de salas do Skype em um ambiente híbrido.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219671"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implantações híbridas do sistema de salas do Skype

Leia este tópico para saber como implantar o sistema de salas do Skype em um ambiente híbrido.
  
## <a name="hybrid-deployments"></a>Implantações híbridas

Siga estas etapas se sua topologia tiver o Skype for Business Server e o Exchange Online e você quiser hospedar a caixa de correio de recurso do sistema de salas do Skype no Exchange Online. Esta seção também aborda um cenário híbrido em que você tem o Exchange Online e o Exchange Server implantados.
  
Para fins ilustrativos, usamos o LyncSample.com para o domínio local e o LyncSample.ccstp.net para o domínio online.
  
1. Crie uma caixa de correio de recurso no centro de administração do Exchange (LyncSample.ccsctp.net) conectando-se ao Shell de gerenciamento do Exchange Online, conforme descrito no aprovisionamento do Exchange Online.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Você pode verificar a conectividade do OWA usando o lrstest5@LyncSample.ccsctp.net para fazer logon.
    
2. No centro de administração do Exchange do Microsoft 365 ou do Office 365, adicione um endereço de email lrstest5@LyncSample.com (domínio local) e defina-o como o endereço de resposta.
    
3. Criar um lrstest5@LyncSample.com de usuário do Active Directory local, definir o endereço de email como lrstest5@LyncSample.com e definir o endereço de destino como lrstest5@LyncSample.com.
    
4. Disparam a sincronização de diretórios e, após a conclusão da sincronização, verifique se os usuários mesclam no AAD e se não é possível alterar as propriedades dos recursos do destinatário no centro de administração do Exchange do Microsoft 365 ou do Office 365.
    
5. Verifique a conectividade do OWA usando o lrstest5@LyncSample.com. (Anteriormente, você verificou a conectividade do OWA usando o domínio online.)
    
    Após criar a caixa de correio, você pode usar Set-CalendarProcessing no Shell de gerenciamento do Exchange Online para configurar a caixa de correio. Consulte as etapas de 3 a 6 sob implantações locais da floresta única para obter mais detalhes.
    
   > [!NOTE]
   > Se você tiver um ambiente híbrido com o Exchange Server e o Exchange Online, vá para o Shell de gerenciamento do Exchange e habilite-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room. Em seguida, acione a sincronização de diretório. 
  
    Se você deseja hospedar a caixa de correio do sistema de salas do Skype no Exchange Online, essas etapas do Shell de gerenciamento do Exchange não são necessárias e você pode prosseguir para a etapa 6.
    
6. Habilite a conta do sistema de salas do Skype para o Skype for Business executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você tiver o Skype for Business online em vez do Skype for Business Server no cenário acima, depois de provisionar a caixa de correio de recurso do Exchange, Provisione uma conta do Skype for Business conforme descrito em provisionamento do Skype for Business online. 
  

