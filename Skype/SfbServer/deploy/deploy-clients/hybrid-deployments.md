---
title: Implantações híbridas do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para saber como implantar o sistema de sala do Skype em um ambiente híbrido.
ms.openlocfilehash: ce57178a03a466b76edfbafdcc467d9458028845
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997290"
---
# <a name="skype-room-system-hybrid-deployments"></a>Implantações híbridas do Sistema de Salas do Skype
 
Leia este tópico para saber como implantar o sistema de sala do Skype em um ambiente híbrido.
  
## <a name="hybrid-deployments"></a>Implantações Híbridas

Siga estas etapas se sua topologia tem Skype para Business Server e o Exchange Online, e você deseja hospedar a caixa de correio de recursos de sistema do Skype sala no Exchange Online. Esta seção também abrange um cenário híbrido onde você tem o Exchange Online e o Exchange Server implantados.
  
Para fins ilustrativos, usamos LyncSample.com para o domínio local e LyncSample.ccstp.net para o domínio online.
  
1. Crie uma caixa de correio de recurso no Centro de administração do Exchange (LyncSample.ccsctp.net) estabelecendo conexão com o shell de gerenciamento do Exchange Online, conforme descrito no Exchange Online provisionamento.
    
  ```
  New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
  ```

    Você pode verificar a conectividade do OWA usando lrstest5@LyncSample.ccsctp.net para fazer logon.
    
2. No Centro de administração do Exchange do Office 365, adicione um endereço de email lrstest5@LyncSample.com (domínio em prem) e defini-la como o endereço de resposta.
    
3. Criar no prem Active Directory usuário lrstest5@LyncSample.com, defina o endereço de email como lrstest5@LyncSample.com e definir o endereço de destino para lrstest5@LyncSample.com.
    
4. Acionar a sincronização de diretórios e, depois de sincronização estiver concluída, verifique se os usuários mesclagem em AAD e que não é possível alterar as propriedades em recursos do destinatário Office365 Exchange admin center.
    
5. Verifique a conectividade do OWA usando lrstest5@LyncSample.com. (Anteriormente, você verificou a conectividade OWA utilizando o domínio online.)
    
    Depois de criar a caixa de correio, você pode utilizar o Set-CalendarProcessing no Shell de Gerenciamento do Exchange Online para configurar a caixa de correio do. Consulte as etapas de 3 a 6 sob Implantações Locais da Floresta única para obter mais detalhes.
    
    > [!NOTE]
    > Se você tiver um ambiente híbrido com o Exchange Server e o Exchange Online, vá para o Shell de gerenciamento do Exchange e Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-sala. Em seguida, ative a Sincronização de Diretório. 
  
    Se você quiser hospedar a caixa de correio do sistema do Skype sala no Exchange Online, estas etapas do Shell de gerenciamento do Exchange não são necessárias e prossiga para a etapa 6.
    
6. Habilite a conta do sistema do Skype sala para Skype para negócios executando o seguinte cmdlet em Skype do Shell de gerenciamento de negócios:
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Se você tiver Skype para negócios Online em vez do Skype para Business Server na situação acima, em seguida, após a provisionamento a caixa de correio de recursos do Exchange, provisione um Skype para conta comercial, conforme descrito em Skype para provisionamento Online de negócios. 
  

