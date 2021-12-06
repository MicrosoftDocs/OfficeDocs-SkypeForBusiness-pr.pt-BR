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
ms.openlocfilehash: 39016a83c11553cd39448efa34d61ffbba5045e9
ms.sourcegitcommit: 2aae13454178dc2e2cbc8cca967cd181c5f9d044
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2021
ms.locfileid: "61314209"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gerenciar contas de usuário para Skype for Business Server

As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory de Skype for Business Server.

Para obter informações sobre como habilitar um usuário do Active Directory, consulte [Create a New User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732336(v=ws.11)). Para obter informações sobre como excluir um usuário do Active Directory, consulte [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).

Esses procedimentos devem ser executados durante uma janela de manutenção, quando Skype for Business uso é mais baixo. Se isso for feito em uma agenda diária ou semanal será determinado pelas necessidades da sua organização.

Este artigo contém os seguintes procedimentos:

- [Pesquisar por um ou mais usuários](#search-for-one-or-more-users)

- [Adicionar e habilitar um novo Skype for Business Server usuário](#add-and-enable-a-new-skype-for-business-server-user)

- [Desabilitar ou reabilitar uma conta de usuário para Skype for Business Server](#disable-or-re-enable-a-user-account-for-skype-for-business-server)

- [Desabilitar um usuário para Enterprise Voice](#disable-a-user-for-enterprise-voice)

- [Remover uma conta de usuário com o Shell Skype for Business Server Gerenciamento](#remove-a-user-account-with-the-skype-for-business-server-management-shell)

## <a name="search-for-one-or-more-users"></a>Pesquisar por um ou mais usuários

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.

Você pode pesquisar usuários usando o Painel de Controle Skype for Business Server ou o snap-in Usuários e Computadores do Active Directory. O procedimento a seguir descreve como usar Skype for Business Server Painel de Controle para pesquisar usuários.

> [!NOTE]
> Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procura um usuário pelo endereço de email do usuário. Em vez disso, você pode pesquisar usuários especificando um prefixo de endereço SIP, por exemplo, sip:name, adicionar um filtro de pesquisa e selecionar um endereço SIP que contenha um endereço de email parcial ou usar o cmdlet **Get-CSUser.**

### <a name="search-for-users-using-the-new-control-panel"></a>Pesquisar usuários usando o novo Painel de Controle 

1. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.
 
2. Faça logon usando uma conta de usuário atribuída à função CsUserAdministrator ou à função CsAdministrator.

3. No painel esquerdo, selecione **Usuários**.

4. Na página **Usuários,** na caixa **Pesquisa,** digite todo ou a primeira parte do nome de exibição que você deseja pesquisar e pressione **Enter**.

5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:

    1. Clique no botão filtro ao lado da **caixa Pesquisar.**

    2. No painel **Filtro** que aparece, selecione a propriedade do usuário necessária clicando na seta na lista de menus suspensos.

    3. Clique na seta na lista de operadores suspensos, para selecionar o operador necessário.

    4. Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **OK**.

6. Os resultados da pesquisa aparecem na **página Usuários.** Você pode selecionar qualquer um ou todos os usuários da lista e executar tarefas de configuração nos usuários selecionados.

> [!NOTE]
> O novo Painel de Controle não está disponível para Skype for Business Server 2015.

### <a name="search-for-users-using-the-legacy-control-panel"></a>Pesquisar usuários usando o Painel de Controle herdado 

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. No painel esquerdo, selecione **Usuários**.

4. Na  caixa Pesquisar usuários, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja pesquisar e clique em **Encontrar**.

5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:

    1. Clique no botão expandir seta no canto superior direito da tela acima **Resultados** da pesquisa e clique em **Adicionar Filtro**.

    2. Insira a propriedade do usuário digitando-a ou clicando na seta na lista de menus suspensos para selecionar uma propriedade do usuário.

    3. Na lista **Igual a,** selecione **Igual a** ou Não **igual a**.

    4. Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **Encontrar**.

6. Os resultados da pesquisa aparecem em **Resultados da Pesquisa**. Você pode selecionar qualquer um ou todos os usuários da lista e executar tarefas de configuração nos usuários selecionados.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Adicionar e habilitar um novo Skype for Business Server usuário

Depois de habilitar uma conta de usuário em Usuários e Computadores do Active Directory, você pode usar o Painel de Controle Skype for Business Server para criar e habilitar novas contas de usuário Skype for Business Server adicionando um usuário do Active Directory ao Skype for Business Server.

Você também pode usar um cmdlet, especificamente [Enable-CsUser](/powershell/module/skype/enable-csuser).

### <a name="add-a-user-using-the-new-control-panel"></a>Adicionar um usuário usando o novo Painel de Controle 

1. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.
 
2. Faça logon usando uma conta de usuário atribuída à função CsUserAdministrator ou à função CsAdministrator.

3. Navegue **até Usuários**  >  **Habilitar Usuários** e clique em **Adicionar**.

4. Na caixa **Pesquisa,** digite todo ou a primeira parte do nome de exibição e clique em **Encontrar**.

5. (Opcional) Para especificar critérios de usuário adicionais, clique em **+ Adicionar filtro,** selecione a propriedade de usuário necessária, selecione o operador e insira o valor. Clique em **Localizar**.

6. Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK**.

7. Atribua o usuário a um pool, especifique quaisquer detalhes adicionais e atribua as políticas necessárias ao usuário e clique em **Habilitar**.

> [!NOTE]
> O novo Painel de Controle não está disponível para Skype for Business Server 2015.

### <a name="add-a-user-using-the-legacy-control-panel"></a>Adicionar um usuário usando o Painel de Controle herdado 

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. Navegue **até Usuários**  >  **Habilitar usuários** Novo Usuário do  >  **Lync Server** e clique em **Adicionar.**

6. Na caixa **Pesquisar usuários**, digite todo ou o primeiro nome, nome de exibição, nome, sobrenome, nome da conta SAM, endereço de email, UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.

7. Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK**.

8. Atribua o usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.

## <a name="disable-or-re-enable-a-user-account-for-skype-for-business-server"></a>Desabilitar ou reabilitar uma conta de usuário para Skype for Business Server

Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente Skype for Business Server sem perder as Skype for Business Server configurações que você configurou para a conta de usuário. Como você não perde as Skype for Business Server de conta de usuário, você pode habilitar novamente uma conta de usuário habilitada anteriormente sem precisar reconfigurar a conta de usuário.

### <a name="disable-or-re-enable-a-user-account-using-the-new-control-panel"></a>Desabilitar ou reabilitar uma conta de usuário usando o novo Painel de Controle

1. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.
 
2. Faça logon usando uma conta de usuário atribuída à função CsUserAdministrator ou à função CsAdministrator.

3. No painel esquerdo, selecione **Usuários**.

4. Na página **Usuários,** na caixa **Pesquisa,** digite todo ou a primeira parte do nome de exibição e pressione **Enter**.

5. Na tabela, clique duas vezes na conta de usuário que você deseja desabilitar ou reabilitar.
    1. No painel exibido, para desabilitar temporariamente a conta de usuário para Skype for Business Server, selecione **Desabilitar Usuário**. No painel exibido, clique em **Salvar**.
    2. Para habilitar a conta de usuário para Skype for Business Server, no painel, selecione **Habilitar Usuário .** No próximo painel exibido, clique em **Salvar**.

> [!NOTE]
> O novo Painel de Controle não está disponível para Skype for Business Server 2015.

### <a name="disable-or-re-enable-a-user-account-using-the-legacy-control-panel"></a>Desabilitar ou reabilitar uma conta de usuário usando o Painel de Controle herdado

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. No painel esquerdo, selecione **Usuários**.

4. Na caixa **Usuários de pesquisa**, digite todo ou a primeira parte do nome de exibição, primeiro nome, último nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou alinhe o Identificador de recurso uniforme (URI) da conta do usuário que você quer desabilitar ou reabilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você quer habilitar ou reabilitar.

6. No menu **Ação**, faça o seguinte:
   1. Para desabilitar temporariamente a conta de usuário para Skype for Business Server, selecione **Temporariamente desabilitar para o Lync Server**.
   2. Para habilitar a conta de usuário para Skype for Business Server, selecione **Habilitar para o Lync Server**.
  
### <a name="disable-or-re-enable-user-accounts-using-windows-powershell"></a>Desabilitar ou reabilitar contas de usuário usando Windows PowerShell

As contas de usuário podem ser temporariamente desabilitadas e habilitadas posteriormente usando o cmdlet **Set-CsUser.** Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.

### <a name="to-disable-a-user-account-using-windows-powershell"></a>Para desabilitar uma conta de usuário usando Windows PowerShell

- Para desabilitar temporariamente uma conta de usuário, de definir o valor da propriedade habilitada como False ($False). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account-using-windows-powershell"></a>Para habilitar uma conta de usuário usando Windows PowerShell

- Para habilitar uma conta de usuário desabilitada, de definir o valor da propriedade habilitada como True ($True). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obter mais informações, consulte o tópico de ajuda do cmdlet [Set-CsUser.](/powershell/module/skype/set-csuser)

## <a name="disable-a-user-for-enterprise-voice"></a>Desabilitar um usuário para Enterprise Voice

Use o procedimento a seguir para desabilitar Enterprise Voice para uma conta de usuário habilitada para Skype for Business Server.

### <a name="disable-a-user-for-enterprise-voice-using-new-control-panel"></a>Desabilitar um usuário para Enterprise Voice usando o novo Painel de Controle

1. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.
 
2. Faça logon usando uma conta de usuário atribuída à função CsUserAdministrator ou à função CsAdministrator.

3. No painel esquerdo, clique em **Usuários**.

4. Na caixa **Pesquisa,** digite todo ou a primeira parte do nome de exibição e clique em **Encontrar**.

5. Na tabela, clique duas vezes na conta de usuário que você deseja desabilitar para Enterprise Voice.

6. No painel exibido, clique no ícone de lápis ao lado **de Políticas Atribuídas.**

7. No painel **Políticas Atribuídas,** em **Telefonia**, clique em qualquer opção, **exceto** Enterprise Voice na listada.

8. Clique em **Salvar**.

    > [!NOTE]
    > Para restringir um usuário de fazer chamadas de áudio ou vídeo, em **Telefonia,** clique **em Áudio/Vídeo desabilitado**.

O usuário agora não pode usar o recurso Enterprise Voice usuário. 

> [!NOTE]
> O novo Painel de Controle não está disponível para Skype for Business Server 2015.

### <a name="disable-a-user-account-for-enterprise-voice-using-legacy-control-panel"></a>Desabilitar uma conta de usuário para Enterprise Voice usando o Painel de Controle herdado

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. No painel esquerdo, clique em **Usuários**.

4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja habilitar para Enterprise Voice.

6. No menu **Editar**, clique em **Exibir detalhes**.

7. Na página **Editar usuário do servidor Lync**, sob **Telefonia**, clique em qualquer opção exceto **Enterprise Voice**.

    > [!NOTE]
    > Para restringir um usuário de fazer chamadas de áudio ou vídeo usando o Lync, em **Telefonia,** clique **em Áudio/vídeo desabilitado.**

8. Clique em **Confirmar**.

O usuário agora não pode usar o recurso Enterprise Voice usuário.

Informações relacionadas: <br/>[Enterprise Voice e mobilidade](/previous-versions/office/lync-server-2013/lync-server-2013-managing-enterprise-voice-for-users)<br/> [Habilitar usuários para Enterprise Voice em Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de Gerenciamento do Skype for Business Server](../management-shell.md)

## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Remover uma conta de usuário com o Shell Skype for Business Server Gerenciamento

Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente Skype for Business Server.

> [!NOTE]
> Remover um usuário pode causar a perda de qualquer configuração definida para a conta de usuário. Se você quiser desabilitar temporariamente uma conta de usuário, consulte [Disable or re-enable a user account](#disable-or-re-enable-a-user-account-for-skype-for-business-server)previously enabled for Skype for Business Server .

### <a name="remove-a-user-using-the-new-control-panel"></a>Remover um usuário usando o novo Painel de Controle

1. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.
 
2. Faça logon usando uma conta de usuário atribuída à função CsUserAdministrator ou à função CsAdministrator.

3. No painel esquerdo, selecione **Usuários**.

4. Na caixa **Pesquisa,** digite todo ou a primeira parte do nome de exibição e clique em **Encontrar**.

5. Na tabela, clique duas vezes na conta de usuário que você deseja remover.

6. No painel exibido, clique em **Remover Usuário**. No próximo painel exibido, clique em **OK**.

> [!NOTE]
> O novo Painel de Controle não está disponível para Skype for Business Server 2015.

### <a name="remove-a-user-using-the-legacy-control-panel"></a>Remover um usuário usando o Painel de Controle herdado

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3. No painel esquerdo, selecione **Usuários**.

4. Na  caixa Pesquisar usuários, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta sam, endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja remover e clique em **Encontrar**.

5. Na tabela, clique na conta de usuário que deseja remover.

6. No menu **Ação**, selecione **Remover do Lync Server** e uma caixa de diálogo aparece.

7. Na caixa de diálogo, selecione **OK** para remover o usuário.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Remover contas de usuário com Windows PowerShell cmdlets

Você pode remover contas de usuário usando o Disable-CsUser cmdlet. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota Windows PowerShell. Para obter detalhes sobre como usar Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte [Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). O processo é o mesmo no Skype for Business Server.

Para remover uma conta de usuário, utilize o cmdlet Disable-CsUser. Por exemplo:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

Após este comando ser executado, não há forma de reabilitar a conta e suas configurações anteriores. Ao invés disso, você precisará usar o cmdlet Enable-CsUser para criar uma nova conta para Ken Myer.

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser.](/powershell/module/skype/disable-csuser)

## <a name="see-also"></a>Confira também

[Enable-CsUser](/powershell/module/skype/enable-csuser)

[Disable-CsUser](/powershell/module/skype/disable-csuser)
