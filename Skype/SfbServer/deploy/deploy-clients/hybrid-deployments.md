---
title: Skype Implantações híbridas do Sistema de Sala
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para saber como implantar o Skype Room System em um ambiente híbrido.
ms.openlocfilehash: caebf77f0ef5abb2b56c64446ad04a052d8f98f9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841943"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype Implantações híbridas do Sistema de Sala

Leia este tópico para saber como implantar o Skype Room System em um ambiente híbrido.
  
## <a name="hybrid-deployments"></a>Implantações híbridas

Siga estas etapas se sua topologia tiver Skype for Business Server e Exchange Online, e você quiser hospedar Skype caixa de correio de recurso do Sistema de Sala Exchange Online. Esta seção também aborda um cenário híbrido em que você Exchange Online e Exchange Server implantados.
  
Para fins ilustrativos, usamos LyncSample.com para o domínio local e LyncSample.ccstp.net para o domínio online.
  
1. Crie uma caixa de correio de recurso Exchange centro de administração (LyncSample.ccsctp.net) conectando-se ao shell de gerenciamento de Exchange Online conforme descrito em Exchange Online Provisionamento.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Você pode verificar a conectividade do OWA usando lrstest5@LyncSample.ccsctp.net fazer logoff.
    
2. No centro de administração Microsoft 365 ou Office 365 Exchange, adicione um endereço de email lrstest5@LyncSample.com (domínio local) e desmarcar como o endereço de resposta.
    
3. Crie um endereço de usuário local do Active Directory lrstest5@LyncSample.com, de definir o endereço de email como lrstest5@LyncSample.com e de definir o endereço de destino como lrstest5@LyncSample.com.
    
4. Acionar a sincronização de diretório e, após a conclusão da sincronização, verifique se os usuários se mesclam no AAD e se você não é capaz de alterar as propriedades nos recursos do destinatário no centro de administração do Microsoft 365 ou Office 365 Exchange.
    
5. Verifique a conectividade OWA usando lrstest5@LyncSample.com. (Anteriormente, você verificou a conectividade OWA usando o domínio online.)
    
    Depois de criar a caixa de correio, você pode Set-CalendarProcessing no Shell de Gerenciamento Exchange Online para configurar a caixa de correio. Consulte as etapas 3 a 6 em Implantações de Floresta Única No momento para obter mais detalhes.
    
   > [!NOTE]
   > Se você tiver um ambiente híbrido com Exchange Server e Exchange Online, vá para o Shell de Gerenciamento Exchange e Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room. Em seguida, acionar a Sincronização de Diretórios. 
  
    Se você deseja hospedar Skype caixa de correio do Sistema de Sala no Exchange Online, essas etapas do Shell de Gerenciamento Exchange não são necessárias e você pode prosseguir para a etapa 6.
    
6. Habilita a Skype do Sistema de Sala para Skype for Business executando o seguinte cmdlet no Shell de Gerenciamento Skype for Business:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você tiver Skype for Business Online em vez de Skype for Business Server no cenário acima, depois de provisionar Exchange caixa de correio de recurso do Exchange, provisione uma conta Skype for Business conforme descrito em Skype for Business Provisionamento Online. 
  

