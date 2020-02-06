---
title: Gerenciar contas de usuário do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções neste artigo descrevem como habilitar, desabilitar ou remover temporariamente usuários do Active Directory do Skype for Business Server.
ms.openlocfilehash: 33af0305fe25b9d7a272e89ae196923e97c4cfd3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817051"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gerenciar contas de usuário do Skype for Business Server

As seções neste artigo descrevem como habilitar, desabilitar ou remover temporariamente usuários do Active Directory do Skype for Business Server.

Para obter informações sobre como habilitar um usuário do Active Directory, consulte [criar uma nova conta de usuário](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Para obter informações sobre como excluir um usuário do Active Directory, consulte [excluir uma conta de usuário](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).

Esses procedimentos devem ser executados durante uma janela de manutenção, quando o uso do Skype for Business for o mais baixo. O fato de isso ser feito em um cronograma diário ou semanal será determinado pelas necessidades da sua organização.

Este artigo contém os seguintes procedimentos:

- [Para procurar um ou mais usuários](user-accounts.md#Search)

- [Adicionar e habilitar um novo usuário do Skype for Business Server](user-accounts.md#Add)

- [Desabilitar ou habilitar novamente uma conta de usuário habilitada anteriormente para o Skype for Business Server](user-accounts.md#Disable)

- [Desabilitar um usuário para Enterprise Voice](user-accounts.md#Disable_EV)

- [Remover uma conta de usuário com o Shell de gerenciamento do Skype for Business Server](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Para procurar um ou mais usuários
<a name="Search"> </a>

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para o Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.

Você pode pesquisar usuários usando o painel de controle do Skype for Business Server ou o snap-in usuários e computadores do Active Directory. O procedimento a seguir descreve como usar o painel de controle do Skype for Business Server para pesquisar usuários.

> [!NOTE]
> Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos ao pesquisar por um usuário pelo endereço de email do usuário. Em vez disso, você pode procurar usuários especificando um prefixo de endereço SIP, por exemplo, SIP: Name, adicionar um filtro de pesquisa e selecionar um endereço SIP que contenha um endereço de email parcial ou usar o cmdlet **Get-CSUser** .

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI da linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.

5. (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:

   a. Clique no botão de seta de expansão no canto superior direito da tela acima de **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.

   b. Digite a propriedade do usuário digitando-a ou clicando na seta na lista suspensa para selecionar uma propriedade de usuário.

   c. Na lista **igual a** , clique em **igual** ou **não igual a**.

   d. Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e, em seguida, clique em **Localizar**.

6. Os resultados da pesquisa são exibidos em **resultados da pesquisa**. Você pode selecionar qualquer um dos usuários na lista e executar tarefas de configuração nos usuários selecionados.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Adicionar e habilitar um novo usuário do Skype for Business Server
<a name="Add"> </a>

Depois de habilitar uma conta de usuário em usuários e computadores do Active Directory, você pode usar o painel de controle do Skype for Business Server para criar e habilitar novas contas de usuário do Skype for Business Server ao adicionar um usuário do Active Directory ao Skype for Business Server.

Você também pode usar um cmdlet, [habilite-o especificamente para CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Clique em **habilitar usuários**.

5. Na caixa de diálogo **novo usuário do Lync Server** , clique em **Adicionar**.

6. Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome, nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam) nome da conta, endereço de email, nome UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.

7. Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK**.

8. Atribua o usuário a um pool, especifique os detalhes adicionais e atribua as políticas ao usuário desejado e, em seguida, clique em **habilitar**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Desabilitar ou habilitar novamente uma conta de usuário habilitada anteriormente para o Skype for Business Server
<a name="Disable"> </a>

Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Skype for Business Server sem perder as configurações do Skype for Business Server que você configurou para a conta de usuário. Como você não perde as configurações da conta de usuário do Skype for Business Server, é possível habilitar novamente uma conta de usuário habilitada anteriormente sem precisar reconfigurar a conta do usuário.

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja desabilitar ou habilitar novamente.

6. No menu **ação** , siga um destes procedimentos:

   - Para desativar temporariamente a conta de usuário do Skype for Business Server, clique em **desativar temporariamente para Lync Server**.

   - Para habilitar a conta de usuário do Skype for Business Server, clique em **habilitar novamente para Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar o Windows PowerShell para desabilitar ou habilitar novamente as contas de usuário

As contas de usuário podem ser desabilitadas temporariamente e, em seguida, reativadas posteriormente usando-se o cmdlet **set-CsUser** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

### <a name="to-disable-a-user-account"></a>Para desabilitar uma conta de usuário

- Para desativar temporariamente uma conta de usuário, defina o valor da propriedade Enabled como false ($False). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Para habilitar novamente uma conta de usuário

- Para habilitar novamente uma conta de usuário desabilitada, defina o valor da propriedade Enabled como true ($True). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .

## <a name="disable-a-user-for-enterprise-voice"></a>Desabilitar um usuário para Enterprise Voice
<a name="Disable_EV"> </a>

Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário habilitada para o Skype for Business Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para desabilitar uma conta de usuário para o Enterprise Voice

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.

6. No menu **Editar**, clique em **Exibir detalhes**.

7. Na página **Editar usuário do Lync Server** , em **telefonia**, clique em qualquer opção exceto **Enterprise Voice**.

    > [!NOTE]
    > Para impedir que um usuário faça chamadas de áudio ou vídeo usando o Lync, em **telefonia**, clique em **áudio/vídeo desabilitado**.

8. Clique em **Confirmar**.

O usuário agora não pode usar o recurso Enterprise Voice. Informações relacionadas: <br/>[Enterprise Voice and Mobility](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Habilitar usuários do Enterprise Voice no Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de Gerenciamento do Skype for Business Server](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Remover uma conta de usuário com o Shell de gerenciamento do Skype for Business Server
<a name="Remove"> </a>

Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Skype for Business Server.

> [!NOTE]
> A remoção de um usuário fará com que você perca todas as configurações que você configurou para a conta de usuário. Se quiser desabilitar temporariamente uma conta de usuário, confira [desabilitar ou habilitar novamente uma conta de usuário habilitada anteriormente para o Skype for Business Server](user-accounts.md#Disable).

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja remover.

6. No menu **ação** , selecione **remover do Lync Server**, e uma caixa de diálogo será exibida.

7. Na caixa de diálogo, selecione **OK** para remover o usuário.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Remover contas de usuário com cmdlets do Windows PowerShell

Você pode remover contas de usuário usando o cmdlet Disable-CsUser. Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo ["início rápido: Gerenciando o Microsoft Lync Server 2010 usando o PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

### <a name="to-remove-a-user-account"></a>Para remover uma conta de usuário
Para remover uma conta de usuário, use o cmdlet Disable-CsUser. Por exemplo:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Confira também
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
