---
title: Habilite os usuários para o Enterprise Voice no local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para um usuário usar o sistema telefônico no Office 365 (nuvem PBX), você deve primeiro habilitá-los para o Enterprise Voice e atribuí-las um número de telefone. Você fazer isso usando sua implantação no local enquanto o usuário ainda é hospedado na implantação no local.
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883373"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilite os usuários para o Enterprise Voice no local
 
Para um usuário usar o sistema telefônico no Office 365 (nuvem PBX), você deve primeiro habilitá-los para o Enterprise Voice e atribuí-las um número de telefone. Você fazer isso usando sua implantação no local enquanto o usuário ainda é hospedado na implantação no local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar um usuário para o Enterprise Voice no local e atribuir um número de telefone

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Utilize o menu Iniciar ou o atalho na área de trabalho para abrir o Painel de Controle do Skype for Business Server.
    
    Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique no Skype para Business Online conta de usuário que você deseja habilitar para o Enterprise Voice.
    
6. No menu **Editar**, clique em **Exibir detalhes**.
    
7. Em **Telefonia**, clique em **Enterprise Voice**.
    
8. Clique em **URI da Linha**, digite um número de telefone único e normalizado (por exemplo, tel:+14255550200) e, em seguida, clique em **Confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerações especiais ao habilitar usuários para o Enterprise Voice no local

Em alguns casos, pode ser necessário modificar o modo de habilitar usuários para o Enterprise Voice para garantir que eles consigam fazer e receber chamadas. Se você tiver usuários em sua implantação que atendem às seguintes condições, execute as etapas foram incluídas para permitir que o usuário para o Enterprise Voice.
  
- Se um usuário é criado no seu local AD e sincronizadas com Skype para Business Online sem sendo habilitados para o Skype para negócios ou para o Enterprise Voice e não tem um LineURI definido, execute os seguintes cmdlets para cada usuário afetado, substituindo os valores em < C0 > <b1></b1> com valores reais para seu ambiente:
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário já estiver habilitado para Skype para negócios localmente, mas não foi habilitado para Enterprise Voice ou atribuído um LineURI antes que está sendo movido para Skype para Business Online, execute o seguinte cmdlet para cada usuário:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Se um usuário é já está habilitado no Skype for Business no local, mas não habilitado para o Enterprise Voice, mesmo se já atribuído um LineURI, execute o seguinte cmdlet para cada usuário afetado:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


