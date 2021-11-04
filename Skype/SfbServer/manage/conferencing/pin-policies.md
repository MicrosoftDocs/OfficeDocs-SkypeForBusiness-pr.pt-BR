---
title: Gerenciar políticas de PIN para conferência discagem em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Resumo: Saiba como gerenciar políticas de PIN para conferência discagem em Skype for Business Server.'
ms.openlocfilehash: d82be95a3e6ff6fcfc65c5fd7449f9035ee64635
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763809"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Gerenciar políticas de PIN para conferência discagem em Skype for Business Server
 
**Resumo:** Saiba como gerenciar políticas de PIN para conferência discagem em Skype for Business Server.
  
Skype for Business Server usuários que têm credenciais do Active Directory Domain Services (AD DS) em sua organização podem ingressar em conferências discadas como usuários autenticados usando um PIN (número de identificação pessoal). A política de PIN define as regras de funcionamento dos PINs de conferências de discagem.
  
 Se você quiser usar a mesma política de PIN para toda sua organização, poderá usar a política de PIN global e modificá-la conforme o necessário. A política de PIN global define as regras para PINs de conferências de discagem no nível da floresta. Você pode modificar a política de PIN global, mas não pode excluí-la.
  
É possível criar uma nova política de PIN se você quiser que uma política específica seja aplicada a um site ou a determinado grupo de usuários.
  
As políticas de PIN se aplicam aos usuários a partir do escopo mais estreito para o mais amplo. Se você atribuir uma política de PIN no nível de usuário a um usuário, essas configurações terão precedência. Se você não atribuir uma política de usuário, a política de PIN no nível de site será aplicada, se existir. Se nenhuma política de usuário ou site se aplicar, a política de PIN global fornecerá as configurações padrão.
  
## <a name="view-information-about-pin-policies"></a>Exibir informações sobre políticas de PIN

Você pode exibir informações sobre políticas de PIN usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Exibir informações sobre políticas de PIN usando Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN,** clique na política de PIN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes.**
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Exibir informações sobre políticas de PIN usando Skype for Business Server Shell de Gerenciamento

Para exibir informações sobre políticas de PIN, use o cmdlet **Get-CsPinPolicy.** Por exemplo, o comando a seguir retorna informações sobre uma única política de PIN com Identity site:Redmond:
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modificar a política de PIN global

Você pode modificar a política de PIN global usando Skype for Business Server Painel de Controle ou usando o Shell de Gerenciamento Skype for Business Server Gerenciamento.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar a política de PIN de conferência discada global usando Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique na política **Global**, em **Editar** e em **Mostrar detalhes**.
    
5. Em **Editar Política de PIN**, em **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.
    
6. Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon** . Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.
    
7. Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.
    
8. Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.
    
9. Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.
    
10. Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.
    
11. Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.
    
    > [!IMPORTANT]
    > Por motivos de segurança, a Microsoft recomenda que você não permita padrões comuns. 
  
12. Clique em **Confirmar**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar a política global de PIN de conferência discada usando Skype for Business Server Shell de Gerenciamento

Para modificar a política global de PIN de conferência discada, use o cmdlet **Set-CsPinPolicy.**
  
O comando a seguir altera o valor do MinPasswordLength para todas as políticas de PIN configuradas para uso na organização. Para fazer isso, o comando chama primeiro o cmdlet **Get-CsPinPolicy** sem parâmetros para recuperar uma coleção de todas as políticas de PIN existentes. Essa coleção é então canalada para o cmdlet **Set-CsPinPolicy,** que modifica o valor da propriedade MinPasswordLength para cada política na coleção:
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Criar uma política de PIN de usuário ou site

Você pode criar uma política de PIN de usuário ou de site usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Criar uma política de PIN de usuário ou de site usando Skype for Business Server Painel de Controle

1. De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique em **Novo** e execute uma das seguintes ações:
    
   - Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de PIN**, em **Nome**, digite um nome que descreve a política.
    
   - Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecionar um Site**, digite todo ou parte do nome do site para o qual você deseja criar uma política. Na lista de sites, clique no site que você deseja e clique em **OK**.
    
5. No campo **Descrição**, digite uma descrição da política de PIN.
    
6. No campo **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.
    
7. Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon** . Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.
    
8. Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.
    
9. Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.
    
10. Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.
    
11. Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.
    
12. Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.
    
    > [!IMPORTANT]
    > Por motivos de segurança, a Microsoft recomenda que você não permita padrões comuns. 
  
13. Clique em **Confirmar**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Criar uma política de PIN de usuário ou de site usando Skype for Business Server Shell de Gerenciamento

Para criar uma política de PIN de usuário ou site, use o cmdlet **New-CsPinPolicy.**
  
O comando a seguir cria uma nova política de PIN com Identity site:Redmond. Este comando inclui apenas um parâmetro opcional, MinPasswordLength, que é usado para definir a propriedade MinPasswordLength como 7. Todas as demais propriedades de política serão configuradas usando-se os valores padrão.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modificar uma política de PIN de usuário ou site

Você pode modificar uma política de PIN de usuário ou de site usando o Painel de Controle Skype for Business Server ou usando Skype for Business Server Shell de Gerenciamento.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar uma política de PIN de usuário ou de site usando Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique na política de PIN que você deseja alterar, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Política de PIN**, modifique quaisquer configurações de política (exceto o nome da política, que não pode ser modificado).
    
6. Clique em **Confirmar**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar uma política de PIN de usuário ou site usando Skype for Business Server Shell de Gerenciamento

Para modificar a política de PIN de conferência discada, use o cmdlet **Set-CsPinPolicy.**
  
O comando a seguir modifica a política de PIN atribuída ao site redmond. Nesse caso, o comando altera o valor da propriedade MinPasswordLength para 10; isso significa que os novos PINs terão que conter pelo menos 10 dígitos:
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Excluir uma política de PIN de usuário ou site

Você pode excluir uma política de PIN de usuário ou site usando Skype for Business Server Painel de Controle ou usando Skype for Business Server Shell de Gerenciamento.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Excluir uma política de PIN de usuário ou site usando Skype for Business Server Painel de Controle

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou Skype for Business Server.
    
2.  Abra Skype for Business Server Painel de Controle.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN,** clique na política pin que você deseja alterar, clique em **Editar** e clique em **Excluir**.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Excluir uma política de PIN de usuário ou de site usando Skype for Business Server Shell de Gerenciamento

Para excluir uma política de PIN de usuário ou site, use o cmdlet **Remove-CsPinPolicy.**
  
O comando a seguir remove todas as políticas de PIN que foram configuradas no escopo do site. Para fazer isso, use o cmdlet **Get-CsPinPolicy,** juntamente com o parâmetro Filter, para retornar uma coleção de todas as políticas que têm uma Identity que começa com os caracteres "site:". Essa coleção é então canalada para o cmdlet **Remove-CsPinPolicy,** que exclui cada política na coleção:
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, [consulte Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
