---
title: Habilitar os usuários do Enterprise Voice no local
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
description: Para que um usuário use o sistema telefônico no Office 365 (Cloud PBX), primeiro você deve habilitá-los para o Enterprise Voice e atribuir a eles um número de telefone. Isso é feito usando a implantação local, enquanto o usuário ainda é hospedado na implantação local.
ms.openlocfilehash: 4409de1965fbcca641dde69d70c734d1bcd3a8b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802291"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar os usuários do Enterprise Voice no local
 
Para que um usuário use o sistema telefônico no Office 365 (Cloud PBX), primeiro você deve habilitá-los para o Enterprise Voice e atribuir a eles um número de telefone. Isso é feito usando a implantação local, enquanto o usuário ainda é hospedado na implantação local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar um usuário para Enterprise Voice no local e atribuir um número de telefone

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Utilize o menu Iniciar ou o atalho na área de trabalho para abrir o Painel de Controle do Skype for Business Server.
    
    Você também pode abrir uma janela do navegador e inserir a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.
    
5. Na tabela, clique na conta de usuário do Skype for Business online que você deseja habilitar para o Enterprise Voice.
    
6. No menu **Editar**, clique em **Exibir detalhes**.
    
7. Em **Telefonia**, clique em **Enterprise Voice**.
    
8. Clique em **URI da Linha**, digite um número de telefone único e normalizado (por exemplo, tel:+14255550200) e, em seguida, clique em **Confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Considerações especiais ao habilitar os usuários do Enterprise Voice no local

Em alguns casos, pode ser necessário modificar o modo de habilitar usuários para o Enterprise Voice para garantir que eles consigam fazer e receber chamadas. Se você tiver usuários na sua implantação que atendam às seguintes condições, siga as etapas incluídas para habilitar o usuário para o Enterprise Voice.
  
- Se um usuário for criado em seu anúncio local e sincronizado com o Skype for Business online sem estar habilitado para o Skype for Business ou para Enterprise Voice e não tiver um conjunto de LineURI, execute os seguintes cmdlets para cada usuário afetado, substituindo os valores \< \> por valores reais do seu ambiente:
    
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


