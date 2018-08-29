---
title: Gerenciar contas de usuário do Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype para Business Server.
ms.openlocfilehash: 918bdf556f040c115abf5869ad7a7dcd76a3271f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250791"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gerenciar contas de usuário do Skype para Business Server

As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype para Business Server.

Para obter informações sobre como habilitar um usuário do Active Directory, consulte [criar uma nova conta de usuário](https://technet.microsoft.com/en-us/library/cc732336%28v=ws.11%29.aspx). Para obter informações sobre como excluir um usuário do Active Directory, consulte [Excluir uma conta de usuário](https://technet.microsoft.com/en-us/library/cc753730%28v=ws.11%29.aspx).

Estes procedimentos devem ser realizados durante um período de manutenção, quando Skype para uso de negócios é mais baixa. Se isso é feito em uma agenda diária ou semanal será determinado pelas necessidades da sua organização.

Este artigo contém os seguintes procedimentos:

- [Para procurar um ou mais usuários](user-accounts.md#Search)

- [Adicionar e habilitar um novo Skype para usuário Business Server](user-accounts.md#Add)

- [Desabilitar ou reabilitar uma conta de usuário que antes estavam habilitada para Skype para Business Server](user-accounts.md#Disable)

- [Desabilitar um usuário para o Enterprise Voice](user-accounts.md#Disable_EV)

- [Remover uma conta de usuário com o Skype do Shell de gerenciamento do servidor de negócios](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Para procurar um ou mais usuários
<a name="Search"> </a>

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para Skype para Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.

Você pode pesquisar usando o Skype para o painel de controle de servidor de negócios ou os usuários do Active Directory para usuários e computadores snap-in. O procedimento a seguir descreve como usar o Skype para painel de controle do servidor de negócios para procurar usuários.

> [!NOTE]
> Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procurar um usuário pelo endereço de email do usuário. Em vez disso, você pode procurar usuários especificando-se um prefixo de endereço SIP, por exemplo, sip: name, adicionar um filtro de pesquisa e selecione um endereço SIP que contém um endereço de email parcial ou use o cmdlet **Get-CSUser** .

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome, nome de conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Localizar**.

5. (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:

   a. Clique no botão de seta de expansão no canto superior direito da tela acima **resultados da pesquisa**e, em seguida, clique em **Adicionar filtro**.

   b. Insira a propriedade de usuário digitando-lo ou clicando na seta na lista suspensa para selecionar uma propriedade de usuário.

   c. Na lista **igual a** , clique em **igual a** ou **não igual a**.

   d. Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e, em seguida, clique em **Localizar**.

6. Os resultados da pesquisa aparecem em **Resultados da pesquisa**. Você pode selecionar qualquer um ou todos os usuários na lista e executar tarefas de configuração sobre os usuários selecionados.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Adicionar e habilitar um novo Skype para usuário Business Server
<a name="Add"> </a>

Após habilitar uma conta de usuário no Active Directory Users and Computers, você pode usar o Skype para painel de controle do Business Server para criar e habilitar nova Skype para contas de usuário do servidor de negócios, adicionando um usuário do Active Directory à Skype para Business Server.

Você também pode usar um cmdlet, especificamente [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Clique em **Permitir que os usuários**.

5. Na caixa de diálogo **Novo usuário do Lync Server** , clique em **Adicionar**.

6. Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome, exibir o nome, nome, sobrenome, nome de conta do Gerenciador de contas de segurança (SAM), endereço de email, Nome Principal do usuário (UPN) ou número de telefone da conta de usuário do Active Directory que você deseja e, em seguida, clique em **Localizar**.

7. Na tabela, selecione a conta que você deseja adicionar ao Skype para Business Server e clique em **Okey**.

8. Atribuir ao usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Desabilitar ou reabilitar uma conta de usuário que antes estavam habilitada para Skype para Business Server
<a name="Disable"> </a>

Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Skype para Business Server sem perder o Skype pelas configurações do servidor de negócios que você configurou para a conta de usuário. Porque você não perca o Skype para configurações de conta de usuário do Business Server, você pode reativar uma conta de usuário habilitada anteriormente novamente sem a necessidade de reconfigurar a conta de usuário.

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja desabilitar ou reabilitar, e, em seguida, clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja desabilitar ou reabilitar.

6. No menu **ação** , siga um destes procedimentos:

   - Para desabilitar temporariamente a conta de usuário para Skype para Business Server, clique em **desabilitar temporariamente para o Lync Server**.

   - Para habilitar a conta de usuário para Skype para Business Server, clique em **reabilitar para o Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar o Windows Powershell para desabilitar ou reabilitar em contas de usuário

Contas de usuário podem ser temporariamente desabilitadas e então posteriormente reabilitadas, usando o cmdlet **Set-CsUser** . Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.

### <a name="to-disable-a-user-account"></a>Para desativar uma conta de usuário

- Para desabilitar temporariamente uma conta de usuário, defina o valor da propriedade Enabled como False ($False). Por exemplo:

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Para reabilitar uma conta de usuário

- Para reativar uma conta de usuário desabilitada, defina o valor da propriedade Enabled como True ($True). Por exemplo:

  ```
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) .

## <a name="disable-a-user-for-enterprise-voice"></a>Desabilitar um usuário para o Enterprise Voice
<a name="Disable_EV"> </a>

Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário que está habilitada para Skype para Business Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para desativar uma conta de usuário para o Enterprise Voice

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.

6. No menu **Editar**, clique em **Exibir detalhes**.

7. Na página **Editar usuário do Lync Server** , em **telefonia**, clique em qualquer opção exceto **Enterprise Voice**.

    > [!NOTE]
    > Para impedir que um usuário fazer chamadas de áudio ou vídeos usando o Lync, em **telefonia**, clique em **áudio/vídeo desabilitado**.

8. Clique em **Confirmar**.

O usuário agora está apto a usar o recurso de Enterprise Voice. Informações relacionadas: <br/>[Enterprise Voice e mobilidade](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Habilitar usuários para o Enterprise Voice no Skype para Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de Gerenciamento do Skype for Business Server](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Remover uma conta de usuário com o Skype do Shell de gerenciamento do servidor de negócios
<a name="Remove"> </a>

Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Skype para Business Server.

> [!NOTE]
> Remover um usuário fará com que a perda de quaisquer configurações que você configurou para a conta de usuário. Se você quiser desabilitar temporariamente uma conta de usuário em vez disso, consulte [desabilitar ou reabilitar uma conta de usuário que antes estavam habilitada para Skype para Business Server](user-accounts.md#Disable).

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3. Na barra de navegação esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários** , digite todo ou a primeira parte do nome para exibição, nome, sobrenome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou linha identificador URI (Uniform Resource) da conta de usuário que você deseja desabilitar ou reabilitar, e, em seguida, clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja remover.

6. No menu **ação** , selecione **Remover do Lync Server**e uma caixa de diálogo caixa é exibida.

7. Na caixa de diálogo, selecione **Okey** para remover o usuário.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Remover contas de usuário com os cmdlets do Windows Powershell

Você pode remover as contas de usuário usando o cmdlet Disable-CsUser. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo em Skype para Business Server.

### <a name="to-remove-a-user-account"></a>Para remover uma conta de usuário
Para remover uma conta de usuário, use o cmdlet Disable-CsUser. Por exemplo:

  ```
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) .

## <a name="see-also"></a>Ver também
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)