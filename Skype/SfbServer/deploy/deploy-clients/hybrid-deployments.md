---
title: Implantações híbridas do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente híbrido.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805891"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implantações híbridas do Sistema de Sala do Skype

Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente híbrido.
  
## <a name="hybrid-deployments"></a>Implantações híbridas

Siga estas etapas se sua topologia tiver o Skype for Business Server e o Exchange Online e você quiser hospedar a caixa de correio de recursos do Sistema de Sala do Skype no Exchange Online. Esta seção também aborda um cenário híbrido em que você tem o Exchange Online e o Exchange Server implantados.
  
Para fins ilustrativos, usamos LyncSample.com para o domínio local e LyncSample.ccstp.net para o domínio online.
  
1. Crie uma caixa de correio de recursos no centro de administração do Exchange (LyncSample.ccsctp.net) conectando-se ao shell de Gerenciamento do Exchange Online, conforme descrito no Provisionamento do Exchange Online.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Você pode verificar a conectividade OWA usando lrstest5@LyncSample.ccsctp.net para fazer logoff.
    
2. No Centro de administração do Microsoft 365 ou Office 365 Exchange, adicione um endereço de email lrstest5@LyncSample.com (domínio local) e de definida como o endereço de resposta.
    
3. Crie um endereço de usuário local do Active Directory lrstest5@LyncSample.com, de definir o endereço de email como lrstest5@LyncSample.com e de definir o endereço de destino como lrstest5@LyncSample.com.
    
4. Acionar a sincronização de diretórios e, após a conclusão da sincronização, verifique se os usuários são mesclados no AAD e se você não consegue alterar as propriedades nos recursos do destinatário no Centro de administração do Microsoft 365 ou Office 365 Exchange.
    
5. Verifique a conectividade do OWA usando lrstest5@LyncSample.com. (Anteriormente, você verificou a conectividade OWA usando o domínio online.)
    
    Depois de criar a caixa de correio, você pode Set-CalendarProcessing no Shell de Gerenciamento do Exchange Online para configurar a caixa de correio. Consulte as etapas de 3 a 6 em Implantações De floresta única no prem para obter mais detalhes.
    
   > [!NOTE]
   > Se você tiver um ambiente híbrido com o Exchange Server e o Exchange Online, vá para o Shell de Gerenciamento do Exchange e Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Em seguida, acionar a Sincronização de Diretórios. 
  
    Se você deseja hospedar a caixa de correio do Sistema de Sala do Skype no Exchange Online, essas etapas do Shell de Gerenciamento do Exchange não são necessárias e você pode prosseguir para a etapa 6.
    
6. Habilita a conta do Sistema de Sala do Skype for Business executando o seguinte cmdlet no Shell de Gerenciamento do Skype for Business:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você tiver o Skype for Business Online em vez do Skype for Business Server no cenário acima, depois de provisionar a caixa de correio de recursos do Exchange, provisione uma conta do Skype for Business conforme descrito no Provisionamento do Skype for Business Online. 
  

