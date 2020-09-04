---
title: Habilitar os usuários para o Enterprise Voice no local
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para que um usuário use o sistema de telefonia (Cloud PBX), primeiro você deve habilitá-lo para o Enterprise Voice e atribuir a eles um número de telefone. Você faz isso usando sua implantação local enquanto o usuário ainda está hospedado na implantação local.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359187"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar os usuários para o Enterprise Voice no local
 
Para que um usuário use o sistema de telefonia (Cloud PBX), primeiro você deve habilitá-lo para o Enterprise Voice e atribuir a eles um número de telefone. Você faz isso usando sua implantação local enquanto o usuário ainda está hospedado na implantação local.

> [!Important]
> O Skype for Business online será desativado no dia 31 de julho de 2021 depois do qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business online não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar um usuário para o Enterprise Voice no local e atribuir um número de telefone

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Use o menu iniciar ou o atalho da área de trabalho para abrir o painel de controle do Skype for Business Server.
    
    Você também pode abrir uma janela do navegador e, em seguida, inserir a URL do administrador para abrir o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário do Skype for Business online que você deseja habilitar para o Enterprise Voice.
    
6. No menu **Editar** , clique em **Mostrar detalhes**.
    
7. Em **telefonia**, clique em **Enterprise Voice**.
    
8. Clique em **URI de linha**e digite um número de telefone normalizado exclusivo (por exemplo, Tel: + 14255550200). Em seguida, clique em **confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerações especiais ao habilitar usuários para o Enterprise Voice no local

Em alguns casos, talvez seja necessário modificar a maneira como você permite que os usuários do Enterprise Voice tenham certeza de que eles podem fazer e receber chamadas com êxito. Se você tiver usuários na sua implantação que atendam às condições a seguir, execute as etapas incluídas para habilitar o usuário para o Enterprise Voice.
  
- Se um usuário é criado em seu AD local e, em seguida, sincronizado com o Skype for Business online sem estar habilitado para o Skype for Business ou para o Enterprise Voice e não tem um conjunto de LineURI, execute os seguintes cmdlets para cada usuário afetado, substituindo os valores por \< \> valores reais para seu ambiente:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário já estiver habilitado para o Skype for Business no local, mas não tiver sido habilitado para o Enterprise Voice ou atribuído a um LineURI antes de ser movido para o Skype for Business Online, execute o seguinte cmdlet para cada usuário:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário já estiver habilitado no Skype for Business no local, mas não estiver habilitado para o Enterprise Voice, mesmo que já tenha atribuído um LineURI, execute o seguinte cmdlet para cada usuário afetado:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


