---
title: Habilitar os usuários para Enterprise Voice local
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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para que um usuário use Sistema de Telefonia (Cloud PBX), primeiro você deve habilita-los para Enterprise Voice e atribuí-los um número de telefone. Você faz isso usando sua implantação local enquanto o usuário ainda está em casa na implantação local.
ms.openlocfilehash: a71b47b5b7b5ec7ca7328bbe9b0ee864b87f36ac
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563710"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar os usuários para Enterprise Voice local
 
Para que um usuário use Sistema de Telefonia (Cloud PBX), primeiro você deve habilita-los para Enterprise Voice e atribuí-los um número de telefone. Você faz isso usando sua implantação local enquanto o usuário ainda está em casa na implantação local.

> [!Important]
> O Skype for Business Online foi retirado em 31 de julho de 2021 e a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não tem mais suporte.  Saiba como conectar sua rede de telefonia local a Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar um usuário para Enterprise Voice local e atribuir um número de telefone

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Use o menu Iniciar ou o atalho da área de trabalho para abrir o painel Skype for Business Server Controle.
    
    Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o painel Skype for Business Server Controle.
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário Skype for Business Online que você deseja habilitar para Enterprise Voice.
    
6. No menu **Editar,** clique em **Mostrar Detalhes.**
    
7. Em **Telefonia,** clique **em Enterprise Voice**.
    
8. Clique **em URI de** linha e digite um número de telefone exclusivo e normalizado (por exemplo, `tel:+14255550200` ). Em seguida, **clique em Commit**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerações especiais ao habiligá-Enterprise Voice no local

Em alguns casos, talvez seja necessário modificar a maneira como permite que os usuários Enterprise Voice para garantir que eles possam fazer e receber chamadas com êxito. Se você tiver usuários em sua implantação que atendem às seguintes condições, execute as etapas incluídas para habilitar o usuário para Enterprise Voice.
  
- Se um usuário for criado no seu AD local e sincronizado com o Skype for Business Online sem ser habilitado para Skype for Business ou para Enterprise Voice e não tiver um conjunto LineURI, execute os seguintes cmdlets para cada usuário afetado, substituindo os valores por valores reais para seu \< \> ambiente:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário já estiver habilitado para Skype for Business local, mas não tiver sido habilitado para o Enterprise Voice ou atribuído um LineURI antes de ser movido para o Skype for Business Online, execute o seguinte cmdlet para cada usuário:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário já estiver habilitado no Skype for Business local, mas não estiver habilitado para Enterprise Voice, mesmo que já tenha atribuído um LineURI, execute o seguinte cmdlet para cada usuário afetado:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```