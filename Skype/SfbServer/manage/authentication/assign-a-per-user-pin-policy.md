---
title: Atribuir uma política de PIN por usuário em Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Resumo: Estágio AV e certificados OAuth para Skype for Business Server.'
---

# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a>Atribuir uma política de PIN por usuário em Skype for Business Server

**Resumo:** Estágio AV e certificados OAuth para Skype for Business Server.
  
A política pin (número de identificação pessoal) de conferência discada é uma das configurações individuais de uma conta de usuário que pode ser configurada no Painel de Controle Skype for Business Server.
  
A implantação de uma ou mais políticas de PIN por usuário é opcional. Também é possível implantar somente uma política de PIN de nível global ou política de PIN de nível de site. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. Direitos e permissões do usuário relacionados ao uso de PINs para conferência discada assumem automaticamente o padrão daqueles definidos na política de PIN de nível global quando nenhuma política específica de nível de site ou por usuário é atribuída.
  
Após a criação de pelo menos uma política de PIN por usuário, use o procedimento neste tópico para atribuir a política que especifica as restrições que você deseja que o servidor imponha sobre os PINs criados e usados por um usuário específico.
  
### <a name="to-assign-a-per-user-pin-policy"></a>Para atribuir uma política de PIN por usuário

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.  
    
3. Na barra de navegação à esquerda, clique em **Usuários**.
    
4. Utilize um dos métodos a seguir para localizar um usuário:
    
   - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
   - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.
    
5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa à sua consulta, clique em **Adicionar filtro**. 
  
   e. Clique em **Localizar**.
    
6. Clique em um usuário nos resultados da pesquisa, clique em **Ação** e clique em **Atribuir políticas**.
    
    > [!TIP]
    > Se você quiser a mesma política de PIN por usuário aplicada a diversos usuários, selecione múltiplos usuários nos resultados da pesquisa e clique em **Ações** e em **Atribuir políticas**. 
  
7. Em **Atribuir Políticas**, em **Política de PIN**, execute uma das seguintes ações:
    
    > [!NOTE]
    > Como há várias políticas que você pode configurar usando a caixa de  diálogo Atribuir Políticas, **\<Keep as is\>** é selecionado por padrão para cada política na caixa de diálogo. Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.
  
   - Permita Skype for Business Server escolha automaticamente a política de nível global ou, se definida, a política no nível do site.
    
   - Clique no nome de uma política PIN por usuário definida anteriormente na página **Política de PIN**.
    
     > [!TIP]
     > Para ajudá-lo a decidir a política que você deseja atribuir, após clicar em um nome de política, clique em **Exibir** para exibir os direitos e permissões de usuário definidos na política.
  
8. Quando terminar, clique em **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política Per-User PIN usando Windows PowerShell cmdlets

Você pode atribuir políticas de PIN por usuário usando Windows PowerShell e o cmdlet **Grant-CsPinPolicy**. Você pode executar este cmdlet usando o Shell de gerenciamento do Skype for Business Server ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Administração remota do Microsoft Lync PowerShell"](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Para atribuir uma política PIN por usuário para um único usuário

- O seguinte comando atribui a política PIN por usuário RedmondPinPolicy para o usuário Ken Myer.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Para atribuir uma política PIN por usuário a vários usuários

- O seguinte comando atribui a política PIN por usuário RedmondUsersPinPolicy para todos os usuários que trabalham na cidade de Redmond. Para obter detalhes sobre o parâmetro LdapFilter usado neste comando, consulte [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Para retirar a atribuição de uma política PIN por usuário

- O seguinte comando retira a atribuição de qualquer política PIN por usuário anteriormente atribuído ao Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Para obter detalhes, [consulte Grant-CsPinPolicy](/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Confira também

[Criar uma nova política de PIN no Skype for Business Server](create-a-new-pin-policy.md)