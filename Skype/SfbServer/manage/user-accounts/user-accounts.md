---
title: Gerenciar contas de usuário para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory de Skype for Business Server.
ms.openlocfilehash: 0bdb2e1d8319a3e4c6379a2563f5d858c3648a77
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856638"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gerenciar contas de usuário para Skype for Business Server

As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory de Skype for Business Server.

Para obter informações sobre como habilitar um usuário do Active Directory, consulte [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)). Para obter informações sobre como excluir um usuário do Active Directory, consulte [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).

Esses procedimentos devem ser executados durante uma janela de manutenção, quando Skype for Business uso é mais baixo. Se isso for feito em uma agenda diária ou semanal será determinado pelas necessidades da sua organização.

Este artigo contém os seguintes procedimentos:

- [Para pesquisar por um ou mais usuários](user-accounts.md#Search)

- [Adicionar e habilitar um novo Skype for Business Server usuário](user-accounts.md#Add)

- [Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para Skype for Business Server](user-accounts.md#Disable)

- [Desabilitar um usuário para Enterprise Voice](user-accounts.md#Disable_EV)

- [Remover uma conta de usuário com o Shell Skype for Business Server Gerenciamento](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Para pesquisar por um ou mais usuários
<a name="Search"> </a>

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.

Você pode pesquisar usuários usando o Painel de Controle Skype for Business Server ou o snap-in Usuários e Computadores do Active Directory. O procedimento a seguir descreve como usar Skype for Business Server Painel de Controle para pesquisar usuários.

> [!NOTE]
> Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procura um usuário pelo endereço de email do usuário. Em vez disso, você pode pesquisar usuários especificando um prefixo de endereço SIP, por exemplo, sip:name, adicionar um filtro de pesquisa e selecionar um endereço SIP que contenha um endereço de email parcial ou usar o cmdlet **Get-CSUser.**

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. Na  caixa Pesquisar usuários, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Encontrar**.

5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:

   a. Clique no botão expandir seta no canto superior direito da tela acima **Resultados** da pesquisa e clique em **Adicionar Filtro**.

   b. Insira a propriedade user digitando-a ou clicando na seta na listada para selecionar uma propriedade do usuário.

   c. Na lista **Igual a,** clique em **Igual a** ou Não **igual a**.

   d. Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **Encontrar**.

6. Os resultados da pesquisa aparecem em **Resultados da Pesquisa**. Você pode selecionar qualquer um ou todos os usuários da lista e executar tarefas de configuração nos usuários selecionados.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Adicionar e habilitar um novo Skype for Business Server usuário
<a name="Add"> </a>

Depois de habilitar uma conta de usuário em Usuários e Computadores do Active Directory, você pode usar o Painel de Controle Skype for Business Server para criar e habilitar novas contas de usuário Skype for Business Server adicionando um usuário do Active Directory ao Skype for Business Server.

Você também pode usar um cmdlet, especificamente [Enable-CsUser](/powershell/module/skype/enable-csuser).

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação da esquerda, clique em **Usuários**.

4. Clique em **Habilitar usuários**.

5. No diálogo **Novo Usuário do Lync Server**, clique em **Adicionar**.

6. Na caixa **Pesquisar usuários**, digite todo ou o primeiro nome, nome de exibição, nome, sobrenome, nome da conta SAM, endereço de email, UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.

7. Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK**.

8. Atribua o usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para Skype for Business Server
<a name="Disable"> </a>

Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente Skype for Business Server sem perder as Skype for Business Server configurações que você configurou para a conta de usuário. Como você não perde as Skype for Business Server de conta de usuário, você pode habilitar novamente uma conta de usuário habilitada anteriormente sem precisar reconfigurar a conta de usuário.

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. Na caixa **Usuários de pesquisa**, digite todo ou a primeira parte do nome de exibição, primeiro nome, último nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou alinhe o Identificador de recurso uniforme (URI) da conta do usuário que você quer desabilitar ou reabilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você quer habilitar ou reabilitar.

6. No menu **Ação**, faça o seguinte:

   - Para desabilitar temporariamente a conta de usuário para Skype for Business Server, clique em **Temporariamente desabilitar para o Lync Server**.

   - Para habilitar a conta de usuário para Skype for Business Server, clique em **Habilitar para o Lync Server**.

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar Windows Powershell para desabilitar ou habilitar contas de usuário

As contas de usuário podem ser temporariamente desabilitadas e habilitadas posteriormente usando o cmdlet **Set-CsUser.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.

### <a name="to-disable-a-user-account"></a>Para desabilitar uma conta de usuário

- Para desabilitar uma conta temporariamente, defina o valor da propriedade Enabled como falso ($False). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Para habilitar uma conta de usuário

- Para reabilitar uma conta de usuário, defina o valor da propriedade Enabled como verdadeiro ($True). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Desabilitar um usuário para Enterprise Voice
<a name="Disable_EV"> </a>

Use o procedimento a seguir para desabilitar Enterprise Voice para uma conta de usuário habilitada para Skype for Business Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para desabilitar uma conta de usuário para Enterprise Voice

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja habilitar para Enterprise Voice.

6. No menu **Editar**, clique em **Exibir detalhes**.

7. Na página **Editar usuário do servidor Lync**, sob **Telefonia**, clique em qualquer opção exceto **Enterprise Voice**.

    > [!NOTE]
    > Para restringir um usuário de fazer chamadas de áudio ou vídeo usando o Lync, em **Telefonia,** clique **em Áudio/vídeo desabilitado.**

8. Clique em **Confirmar**.

O usuário agora não pode usar o recurso Enterprise Voice usuário. Informações relacionadas: <br/>[Enterprise Voice e mobilidade](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Habilitar usuários para Enterprise Voice em Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de Gerenciamento do Skype for Business Server](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Remover uma conta de usuário com o Shell Skype for Business Server Gerenciamento
<a name="Remove"> </a>

Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente Skype for Business Server.

> [!NOTE]
> Remover um usuário pode causar a perda de qualquer configuração definida para a conta de usuário. Se você quiser desabilitar temporariamente uma conta de usuário, consulte [Disable or re-enable a user account](user-accounts.md#Disable)previously enabled for Skype for Business Server .

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários**, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Encontrar**.

5. Na tabela, clique na conta de usuário que deseja remover.

6. No menu **Ação**, selecione **Remover do Lync Server** e uma caixa de diálogo aparece.

7. Na caixa de diálogo, selecione **OK** para remover o usuário.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Remover contas de usuário com Windows cmdlets do Powershell

Você pode remover contas de usuário usando o Disable-CsUser cmdlet. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.

### <a name="to-remove-a-user-account"></a>Para remover uma conta de usuário
Para remover uma conta de usuário, utilize o cmdlet Disable-CsUser. Por exemplo:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Após este comando ser executado, não há forma de reabilitar a conta e suas configurações anteriores. Ao invés disso, você precisará usar o cmdlet Enable-CsUser para criar uma nova conta para Ken Myer.

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Confira também
<a name="Remove"> </a>

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
