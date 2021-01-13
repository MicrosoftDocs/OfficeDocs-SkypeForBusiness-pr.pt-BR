---
title: Gerenciar políticas de PIN para conferência discada no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Resumo: Saiba como gerenciar políticas de PIN para conferência discada no Skype for Business Server.'
ms.openlocfilehash: 6544586071f1107537232a117de196dfbffeb4aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827947"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Gerenciar políticas de PIN para conferência discada no Skype for Business Server
 
**Resumo:** Saiba como gerenciar políticas de PIN para conferência discada no Skype for Business Server.
  
Os usuários do Skype for Business Server que têm credenciais do AD DS (Serviços de Domínio Active Directory) em sua organização podem ingressar em conferências discadas como usuários autenticados usando um PIN (número de identificação pessoal). A política de PIN define as regras de funcionamento dos PINs de conferências de discagem.
  
 Se você quiser usar a mesma política de PIN para toda sua organização, poderá usar a política de PIN global e modificá-la conforme o necessário. A política de PIN global define as regras para PINs de conferências de discagem no nível da floresta. Você pode modificar a política de PIN global, mas não pode excluí-la.
  
É possível criar uma nova política de PIN se você quiser que uma política específica seja aplicada a um site ou a determinado grupo de usuários.
  
As políticas de PIN se aplicam aos usuários a partir do escopo mais estreito para o mais amplo. Se você atribuir uma política de PIN no nível de usuário a um usuário, essas configurações terão precedência. Se você não atribuir uma política de usuário, a política de PIN no nível de site será aplicada, se existir. Se nenhuma política de usuário ou site se aplicar, a política de PIN global fornecerá as configurações padrão.
  
## <a name="view-information-about-pin-policies"></a>Exibir informações sobre políticas de PIN

Você pode exibir informações sobre políticas de PIN usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Exibir informações sobre políticas de PIN usando o Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN,** clique na política de PIN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes.**
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Exibir informações sobre políticas de PIN usando o Shell de Gerenciamento do Skype for Business Server

Para exibir informações sobre políticas de PIN, use o cmdlet **Get-CsPinPolicy.** Por exemplo, o comando a seguir retorna informações sobre uma única política de PIN com a Identidade site:Redmond:
  
```PowerShell
Get-CsPinPolicy -Identity "site:Redmond"
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modificar a política de PIN global

Você pode modificar a política de PIN global usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar a política de PIN de conferência discada global usando o Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
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
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar a política de PIN de conferência discada global usando o Shell de Gerenciamento do Skype for Business Server

Para modificar a política de PIN de conferência discada global, use o cmdlet **Set-CsPinPolicy.**
  
O comando a seguir altera o valor de MinPasswordLength para todas as políticas de PIN configuradas para uso na organização. Para fazer isso, o comando primeiro chama o cmdlet **Get-CsPinPolicy** sem nenhum parâmetro para recuperar uma coleção de todas as políticas de PIN existentes. Essa coleção será então canalizada para o cmdlet **Set-CsPinPolicy,** que modificará o valor da propriedade MinPasswordLength de cada diretiva na coleção:
  
```PowerShell
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Criar uma política de PIN de site ou usuário

Você pode criar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Criar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server

1. Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
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
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Criar uma política de PIN de site ou usuário usando o Shell de Gerenciamento do Skype for Business Server

Para criar uma política de PIN de site ou usuário, use o cmdlet **New-CsPinPolicy.**
  
O comando a seguir cria uma nova política de PIN com a Identidade site:Redmond. Esse comando inclui apenas um parâmetro opcional, MinPasswordLength, que é usado para definir a propriedade MinPasswordLength como 7. Todas as demais propriedades de política serão configuradas usando-se os valores padrão.
  
```PowerShell
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modificar uma política de PIN de site ou usuário

Você pode modificar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique na política de PIN que você deseja alterar, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Política de PIN**, modifique quaisquer configurações de política (exceto o nome da política, que não pode ser modificado).
    
6. Clique em **Confirmar**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar uma política de PIN de site ou usuário usando o Shell de Gerenciamento do Skype for Business Server

Para modificar a política de PIN de conferência discada, use o cmdlet **Set-CsPinPolicy.**
  
O comando a seguir modifica a política de PIN atribuída ao site Redmond. Nesse caso, o comando altera o valor da propriedade MinPasswordLength para 10; Isso significa que os novos PINs terão que conter pelo menos 10 dígitos:
  
```PowerShell
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, consulte [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Excluir uma política de PIN de site ou usuário

Você pode excluir uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server ou o Shell de Gerenciamento do Skype for Business Server.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Excluir uma política de PIN de site ou usuário usando o Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que está na rede na qual você implantou o Skype for Business Server.
    
2.  Abra o Painel de Controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN,** clique na política de PIN que você deseja alterar, clique em **Editar** e em **Excluir.**
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Excluir uma política de PIN de site ou usuário usando o Shell de Gerenciamento do Skype for Business Server

Para excluir uma política de PIN de site ou usuário, use o cmdlet **Remove-CsPinPolicy.**
  
O comando a seguir remove todas as políticas de PIN que foram configuradas no escopo do site. Para fazer isso, use o cmdlet **Get-CsPinPolicy,** juntamente com o parâmetro Filter, para retornar uma coleção de todas as políticas que tenham uma Identidade que comece com os caracteres "site:". Esta coleção será então canalada para o cmdlet **Remove-CsPinPolicy,** que excluirá cada política na coleção:
  
```PowerShell
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e uma lista de parâmetros, [consulte Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
  

