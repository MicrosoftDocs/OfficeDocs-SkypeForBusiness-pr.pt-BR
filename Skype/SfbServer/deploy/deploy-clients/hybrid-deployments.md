---
title: Implantações híbridas do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para aprender a implantar o sistema de sala do Skype em um ambiente híbrido.
ms.openlocfilehash: f6364f7bb96ddf2b25aaaef2a341fce5b71372f5
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003491"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implantações híbridas do Sistema de Salas do Skype

Leia este tópico para aprender a implantar o sistema de sala do Skype em um ambiente híbrido.
  
## <a name="hybrid-deployments"></a>Implantações híbridas

Siga estas etapas se a sua topologia tiver o Skype for Business Server e o Exchange Online, e você quiser hospedar a caixa de correio de recursos do sistema de sala do Skype no Exchange Online. Esta seção também abrange um cenário híbrido onde você tem o Exchange Online e o Exchange Server implantados.
  
Para fins ilustrativos, usamos LyncSample.com para o domínio local e LyncSample.ccstp.net para o domínio online.
  
1. Crie uma caixa de correio de recursos no centro de administração do Exchange (LyncSample.ccsctp.net) conectando-se ao Shell de gerenciamento do Exchange Online, conforme descrito no aprovisionamento do Exchange Online.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    Você pode verificar a conectividade do OWA usando o lrstest5@LyncSample.ccsctp.net para fazer logon.
    
2. No centro de administração do Exchange 365 do Office, adicione um endereço de email lrstest5@LyncSample.com (domínio local) e defina-o como o endereço de resposta.
    
3. Crie uma lrstest5@LyncSample.com de usuário do Active Directory local, defina o endereço de email como lrstest5@LyncSample.com e defina o endereço de destino como lrstest5@LyncSample.com.
    
4. Disparar a sincronização de diretório e, após a conclusão da sincronização, verifique se os usuários mesclam no AAD e se você não consegue alterar as propriedades dos recursos do destinatário no centro de administração do Exchange do office365.
    
5. Verifique a conectividade do OWA usando o lrstest5@LyncSample.com. (Anteriormente, você verificou a conectividade OWA utilizando o domínio online.)
    
    Depois de criar a caixa de correio, você pode utilizar o Set-CalendarProcessing no Shell de Gerenciamento do Exchange Online para configurar a caixa de correio do. Consulte as etapas de 3 a 6 sob Implantações Locais da Floresta única para obter mais detalhes.
    
   > [!NOTE]
   > Se você tiver um ambiente híbrido com o Exchange Server e o Exchange Online, vá para o Shell de gerenciamento do Exchange e habilite-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room. Em seguida, ative a Sincronização de Diretório. 
  
    Se você quiser hospedar a caixa de correio do sistema de sala do Skype no Exchange Online, essas etapas do Shell de gerenciamento do Exchange não serão necessárias e você poderá passar para a etapa 6.
    
6. Habilite a conta do sistema de sala do Skype para o Skype for Business executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você tiver o Skype for Business online em vez do Skype for Business Server no cenário acima, depois de provisionar a caixa de correio de recursos do Exchange, configure uma conta do Skype for Business, conforme descrito no provisionamento do Skype for Business online. 
  

