---
title: Atribuir uma política de PIN por usuário no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Resumo: Estágio AV e OAuth certificados para Skype para Business Server 2015.'
ms.openlocfilehash: a103d6463a02cd00d71769b8f86b43fae514a19d
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504954"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server-2015"></a>Atribuir uma política de PIN por usuário no Skype for Business Server 2015

**Resumo:** Estágio AV e OAuth certificados para Skype para Business Server 2015.
  
A política PIN (número) de identificação pessoal de conferência discada é uma das configurações individuais de uma conta de usuário que podem ser configuradas no Skype para painel de controle do servidor de negócios.
  
A implantação de uma ou mais políticas de PIN por usuário é opcional. Também é possível implantar somente uma política de PIN de nível global ou política de PIN de nível de site. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. Direitos e permissões do usuário relacionados ao uso de PINs para conferência discada assumem automaticamente o padrão daqueles definidos na política de PIN de nível global quando nenhuma política específica de nível de site ou por usuário é atribuída.
  
Após a criação de pelo menos uma política de PIN por usuário, use o procedimento neste tópico para atribuir a política que especifica as restrições que você deseja que o servidor imponha sobre os PINs criados e usados por um usuário específico.
  
### <a name="to-assign-a-per-user-pin-policy"></a>Para atribuir uma política de PIN por usuário

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.  
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. Use um dos seguintes métodos para localizar um usuário:
    
   - Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.
    
   - Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.
    
5. (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:
    
   a. Clique em **Adicionar filtro**.
    
   b. Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.
    
   c. Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
   d. Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.
    
    > [!TIP]
    > Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em **Adicionar filtro**. 
  
   f. Clique em **Localizar**.
    
6. Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.
    
    > [!TIP]
    > Se você quiser a mesma política de PIN por usuário aplicada a diversos usuários, selecione múltiplos usuários nos resultados da pesquisa e clique em  **Ações**e em **Atribuir políticas**. 
  
7. Em **Atribuir Políticas**, em **Política de PIN**, execute uma das seguintes ações:
    
    > [!NOTE]
    > Porque há várias políticas que você pode definir usando a caixa de diálogo **Atribuir políticas** , ** \<manter encontram\> ** é selecionada por padrão para cada política na caixa de diálogo. Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.
  
   - Permitir Skype para o servidor de negócios 2015 escolha automaticamente a política a nível global ou, se definida, a política de nível de site.
    
   - Clique no nome de uma política PIN por usuário definida anteriormente na página  **Política de PIN**.
    
     > [!TIP]
     > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em **Exibir** para visualizar os direitos e permissões do usuário definidos na política.
  
8. Ao concluir, clique em **OK**.
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de PIN por usuário usando Cmdlets do Windows PowerShell

Você pode atribuir políticas de PIN de por usuário usando o Windows PowerShell e o cmdlet **Grant-CsPinPolicy** . Você pode executar esse cmdlet a partir do Skype do Shell de gerenciamento do servidor de negócios ou uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Para atribuir uma política PIN por usuário a um único usuário

- O seguinte comando atribui a política PIN por usuário RedmondPinPolicy ao usuário Ken Myer.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Para atribuir uma política PIN por usuário a vários usuários

- O seguinte comando atribui a política PIN por usuário RedmondUsersPinPolicy a todos os usuários que trabalham na cidade de Redmond. Para obter detalhes sobre o parâmetro LdapFilter usada nesse comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

  ```

### <a name="to-unassign-a-per-user-pin-policy"></a>Para retirar a atribuição de uma política PIN por usuário

- O seguinte comando retira a atribuição de qualquer política PIN por usuário anteriormente atribuída a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
  ```
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

Para obter detalhes, consulte [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).
  
## <a name="see-also"></a>Consulte também

[Criar uma nova política PIN no Skype para Business Server 2015](create-a-new-pin-policy.md)