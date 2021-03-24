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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para que um usuário use o Sistema de Telefonia (Cloud PBX), primeiro você deve habilita-los para Enterprise Voice e atribuí-los um número de telefone. Você faz isso usando sua implantação local enquanto o usuário ainda está em casa na implantação local.
ms.openlocfilehash: b26e51ba316c63e0f992b843a7763586d7e9b575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098587"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar os usuários para Enterprise Voice local
 
Para que um usuário use o Sistema de Telefonia (Cloud PBX), primeiro você deve habilita-los para Enterprise Voice e atribuí-los um número de telefone. Você faz isso usando sua implantação local enquanto o usuário ainda está em casa na implantação local.

> [!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021 após o qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto](/MicrosoftTeams/direct-routing-landing-page).
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar um usuário para Enterprise Voice local e atribuir um número de telefone

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Use o menu Iniciar ou o atalho da área de trabalho para abrir o Painel de Controle do Skype for Business Server.
    
    Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário do Skype for Business Online que você deseja habilitar para Enterprise Voice.
    
6. No menu **Editar,** clique em **Mostrar Detalhes.**
    
7. Em **Telefonia,** clique **em Enterprise Voice**.
    
8. Clique **em URI** de linha e digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200). Em seguida, **clique em Commit**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerações especiais ao habiligá-Enterprise Voice usuários no local

Em alguns casos, talvez seja necessário modificar a maneira como permite que os usuários Enterprise Voice para garantir que eles possam fazer e receber chamadas com êxito. Se você tiver usuários em sua implantação que atendem às seguintes condições, execute as etapas incluídas para habilitar o usuário para Enterprise Voice.
  
- Se um usuário for criado no seu AD local e sincronizado com o Skype for Business Online sem ser habilitado para o Skype for Business ou para Enterprise Voice e não tiver um conjunto LineURI, execute os seguintes cmdlets para cada usuário afetado, substituindo os valores por valores reais para seu \< \> ambiente:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário já estiver habilitado para o Skype for Business no local, mas não tiver sido habilitado para Enterprise Voice ou atribuído um LineURI antes de ser movido para o Skype for Business Online, execute o seguinte cmdlet para cada usuário:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário já estiver habilitado no Skype for Business local, mas não estiver habilitado para Enterprise Voice, mesmo que já tenha atribuído um LineURI, execute o seguinte cmdlet para cada usuário afetado:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```