---
title: Gerenciar políticas de PIN para conferência discada no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Resumo: Saiba como gerenciar políticas de PIN para conferência discada no Skype para Business Server.'
ms.openlocfilehash: 29fd3e2fff1628eaa96d7296e8fe9d7b9183d690
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893318"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a>Gerenciar políticas de PIN para conferência discada no Skype para Business Server
 
**Resumo:** Saiba como gerenciar políticas de PIN para conferência discada no Skype para Business Server.
  
Skype para usuários de Business Server que possuem credenciais do Active Directory Domain Services (AD DS) em sua organização pode ingressar em conferências discadas como usuários autenticados usando um número de identificação pessoal (PIN). A política de PIN define as regras de funcionamento dos PINs de conferências de discagem.
  
 Se você quiser usar a mesma política de PIN para toda a organização, utilize a política de PIN global e modifique-a conforme necessário. A política de PIN global define as regras para PINs de conferência de discagem no nível da floresta. Você pode modificar a política de PIN global, mas não pode excluí-la.
  
É possível criar uma nova política de PIN se você quiser que uma política específica seja aplicada a um site ou a determinado grupo de usuários.
  
As políticas de PIN se aplicam aos usuários do escopo mais estreito para o mais amplo. Se você atribuir uma política de PIN no nível de usuário a um usuário, essas configurações terão precedência. Se você não atribuir uma política de usuário, a política de PIN no nível de site será aplicada, se existir. Se nenhuma política de usuário ou site se aplicar, a política de PIN global fornecerá as configurações padrão.
  
## <a name="view-information-about-pin-policies"></a>Exibir informações sobre políticas de PIN

Você pode exibir informações sobre diretivas de PIN usando Skype para o painel de controle do Business Server ou usando Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a>Exibir informações sobre diretivas de PIN usando Skype para o painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique na política de PIN que você deseja exibir, clique em **Editar** e clique em **Mostrar detalhes**.
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a>Exibir informações sobre diretivas de PIN usando Skype do Shell de gerenciamento do servidor de negócios

Para exibir informações sobre políticas de PIN, use o cmdlet **Get-CsPinPolicy**. Por exemplo, o seguinte comando retorna informações sobre uma única política de PIN com a identidade site:Redmond:
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e a lista de parâmetros, consulte [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).
  
## <a name="modify-the-global-pin-policy"></a>Modificar a política de PIN global

Você pode modificar a política PIN global usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar a conferência de discagem global política de PIN usando Skype para o painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique na política **Global**, em **Editar** e em **Mostrar detalhes**.
    
5. Em **Editar Política de PIN**, em **Comprimento mínimo do PIN**, digite ou selecione o comprimento mínimo do PIN que você deseja permitir. O comprimento mínimo padrão é de cinco dígitos.
    
6. Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon**. Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.
    
7. Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.
    
8. Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.
    
9. Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.
    
10. Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.
    
11. Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.
    
    > [!IMPORTANT]
    > Por motivos de segurança, a Microsoft recomenda que você não permita padrões comuns. 
  
12. Clique em **Confirmar**.
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar a conferência de discagem global política de PIN usando Skype do Shell de gerenciamento do servidor de negócios

Para modificar a política de PIN de conferência de discagem global, use o cmdlet **Set-CsPinPolicy**.
  
O seguinte comando altera o valor de MinPasswordLength em todas as políticas de PIN configuradas para uso na organização. Para isso, o comando chama primeiro o cmdlet **Get-CsPinPolicy**. sem nenhum parâmetro para recuperar uma coleção de todas as políticas de PIN existentes. Esta coleção é então canalizada ao cmdlet **Set-CsPinPolicy**, que modifica o valor da propriedade MinPasswordLength de cada política da coleção:
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e a lista de parâmetros, consulte [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="create-a-user-or-site-pin-policy"></a>Criar uma política de PIN de site ou usuário

Você pode criar um usuário ou a política de PIN de site usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Criar um usuário ou a política de PIN de site usando o Skype para painel de controle do servidor de negócios

1. A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique em **Novo** e execute uma das seguintes ações:
    
   - Para criar uma política de nível de usuário, clique em **Política de usuário**. Em **Nova Política de PIN**, em **Nome**, digite um nome que descreve a política.
    
   - Para criar uma política de nível de site, clique em **Política de site**. No campo de pesquisa **Selecionar um Site**, digite todo ou parte do nome do site para o qual você deseja criar uma política. Na lista de sites, clique no site que você deseja e clique em **OK**.
    
5. No campo **Descrição**, digite uma descrição da política de PIN.
    
6. No campo **Tamanho mínimo do PIN**, digite ou selecione o tamanho mínimo do PIN que você deseja permitir. O tamanho mínimo padrão é de cinco dígitos.
    
7. Para poder especificar o número máximo de tentativas de logon antes que um usuário seja bloqueado, marque a caixa de seleção **Especificar o máximo de tentativas de logon**. Se você não selecionar essa opção, o número máximo de tentativas permitidas será determinado automaticamente com base no tamanho do PIN. Por padrão, o número máximo de tentativas é determinado automaticamente.
    
8. Se você marcou a caixa de seleção **Especificar o máximo de tentativas de logon**, em **Máximo de tentativas de logon**, digite ou selecione o número máximo de tentativas de logon que você deseja permitir.
    
9. Para fazer com que os PINs expirem, marque a caixa de seleção **Habilitar validade do PIN**. Se você não selecionar essa opção, os PINs nunca expirarão. Por padrão, os PINs nunca expiram.
    
10. Se você marcou a caixa de seleção **Habilitar validade do PIN**, em **O PIN expira após (dias)**, digite ou selecione o número de dias após o qual o PIN expirará.
    
11. Em **Contagem do histórico de PINs**, digite o número de PINs que um usuário precisa criar antes de poder reutilizar um PIN. Por padrão, os usuários podem reutilizar seus PINs.
    
12. Para permitir padrões comuns de dígitos nos PINs, como números sequenciais e conjuntos repetitivos de números, marque a caixa de seleção **Permitir padrões comuns**. Se você não selecionar essa opção, somente os padrões complexos de dígitos serão permitidos. Por padrão, somente os padrões complexos de dígitos são permitidos.
    
    > [!IMPORTANT]
    > Por motivos de segurança, a Microsoft recomenda que você não permita padrões comuns. 
  
13. Clique em **Confirmar**.
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Criar um usuário ou a política de PIN de site usando o Skype do Shell de gerenciamento do servidor de negócios

Para criar uma política de PIN de site ou usuário, use o cmdlet **New-CsPinPolicy**.
  
O comando a seguir cria uma nova política de PIN com a Identidade site:Redmond. Esse comando inclui apenas um parâmetro opcional (MinPasswordLength), que é usado para definir a propriedade MinPasswordLength como sendo 7. Todas as demais propriedades de política serão configuradas usando-se os valores padrão.
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 Para obter mais informações, incluindo uma descrição de sintaxe completa e a lista de parâmetros, consulte [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).
  
## <a name="modify-a-user-or-site-pin-policy"></a>Modificar uma política de PIN de site ou usuário

Você pode modificar a um usuário ou a política de PIN de site usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Modificar um usuário ou a política de PIN de site usando Skype para o painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique na política de PIN que você deseja alterar, clique em **Editar** e clique em **Mostrar detalhes**.
    
5. Em **Editar Política de PIN**, modifique quaisquer configurações de política (exceto o nome da política, que não pode ser modificado).
    
6. Clique em **Confirmar**.
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Modificar um usuário ou a política de PIN de site usando Skype do Shell de gerenciamento do servidor de negócios

Para modificar a política de PIN de conferência de discagem, use o cmdlet **Set-CsPinPolicy**.
  
O seguinte comando modifica a política de PIN atribuída ao site de Redmond. Nesse caso, o comando alterará o valor da propriedade MinPasswordLength para 10. Isso significa que os novos PINs deverão conter pelo menos dez dígitos:
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e a lista de parâmetros, consulte [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).
  
## <a name="delete-a-user-or-site-pin-policy"></a>Excluir uma política de PIN de site ou usuário

Você pode excluir um usuário ou a política de PIN de site usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a>Excluir um usuário ou a política de PIN de site usando o Skype para painel de controle do servidor de negócios

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes), ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon no qualquer computador que esteja na rede em que você implantou Skype para Business Server .
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e **Política de PIN**.
    
4. Na página **Política de PIN**, clique na política de PIN que você deseja alterar, clique em **Editar** e clique em **Excluir**.
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a>Excluir um usuário ou a política de PIN de site usando o Skype do Shell de gerenciamento do servidor de negócios

Para excluir uma política de PIN de site ou usuário, use o cmdlet **Remove-CsPinPolicy**.
  
O comando a seguir remove todas as diretivas de PIN que foram configuradas no escopo do site. Para fazer isso, o cmdlet **Get-CsPinPolicy** é usado, com o parâmetro Filter, para retornar uma coleção de todas as diretivas que tenham Identidade começando com os caracteres "site:". A coleção é então canalizada para o cmdlet **Remove-CsPinPolicy**, que exclui todas as diretivas na coleção.
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

Para obter mais informações, incluindo uma descrição de sintaxe completa e a lista de parâmetros, consulte [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).
  

