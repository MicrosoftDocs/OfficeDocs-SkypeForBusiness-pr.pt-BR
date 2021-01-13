---
title: Gerenciar contas de usuário do Skype for Business Server
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype for Business Server.
ms.openlocfilehash: aa1b1b21ba089815af20b61da3360179fb10935e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832771"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a>Gerenciar contas de usuário do Skype for Business Server

As seções deste artigo descrevem como habilitar, desabilitar temporariamente ou remover usuários do Active Directory do Skype for Business Server.

Para obter informações sobre como habilitar um usuário do Active Directory, consulte [Criar uma nova conta de usuário.](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx) Para obter informações sobre como excluir um usuário do Active Directory, consulte [Excluir uma conta de usuário.](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)

Esses procedimentos devem ser executados durante uma janela de manutenção, quando o uso do Skype for Business for menor. Se isso é feito em um agendamento diário ou semanal será determinado pelas necessidades da sua organização.

Este artigo contém os seguintes procedimentos:

- [Para pesquisar por um ou mais usuários](user-accounts.md#Search)

- [Adicionar e habilitar um novo usuário do Skype for Business Server](user-accounts.md#Add)

- [Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para o Skype for Business Server](user-accounts.md#Disable)

- [Desabilitar um usuário para o Enterprise Voice](user-accounts.md#Disable_EV)

- [Remover uma conta de usuário com o Shell de Gerenciamento do Skype for Business Server](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a>Para pesquisar por um ou mais usuários
<a name="Search"> </a>

Você pode usar os resultados de uma consulta de pesquisa para configurar usuários do Active Directory para o Skype for Business Server. É possível pesquisar por usuários por nome de exibição, nome, sobrenome, nome de conta SAM (Gerenciador de contas de segurança), endereço SIP ou URI (Uniform Resource Identifier) de linha.

Você pode procurar usuários usando o Painel de Controle do Skype for Business Server ou o snap-in Usuários e Computadores do Active Directory. O procedimento a seguir descreve como usar o Painel de Controle do Skype for Business Server para pesquisar usuários.

> [!NOTE]
> Em um ambiente com uma topologia de floresta central, os resultados da pesquisa podem não ser precisos quando você procura um usuário pelo endereço de email do usuário. Em vez disso, você pode procurar usuários especificando um prefixo de endereço SIP, por exemplo, sip:name, adicionar um filtro de pesquisa e selecionar um endereço SIP que contenha um endereço de email parcial ou usar o cmdlet **Get-CSUser.**

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.

5. (Opcional) Especifique critérios de busca adicionais para limitar os resultados:

   a. Clique no botão expandir seta no canto superior direito da tela acima Resultados da pesquisa **e** clique em **Adicionar Filtro.**

   b. Insira a propriedade do usuário digitando-a ou clicando na seta na lista drop-down para selecionar uma propriedade de usuário.

   c. In the **Equal to** list, click **Equal to** or Not **equal to**.

   d. Na caixa de texto, digite os critérios de pesquisa que você deseja usar para filtrar os resultados da pesquisa e clique em **Encontrar.**

6. Os resultados da pesquisa aparecem em **Resultados da Pesquisa.** Você pode selecionar qualquer um ou todos os usuários na lista e executar tarefas de configuração nos usuários selecionados.

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a>Adicionar e habilitar um novo usuário do Skype for Business Server
<a name="Add"> </a>

Depois de habilitar uma conta de usuário em Usuários e Computadores do Active Directory, você pode usar o Painel de Controle do Skype for Business Server para criar e habilitar novas contas de usuário do Skype for Business Server adicionando um usuário do Active Directory ao Skype for Business Server.

Você também pode usar um cmdlet, especificamente [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3. Na barra de navegação da esquerda, clique em **Usuários**.

4. Clique em **Habilitar usuários**.

5. No diálogo **Novo Usuário do Lync Server**, clique em **Adicionar**.

6. Na caixa **Pesquisar usuários**, digite todo ou o primeiro nome, nome de exibição, nome, sobrenome, nome da conta SAM, endereço de email, UPN ou número de telefone da conta de usuário do Active Directory que você deseja e clique em **Localizar**.

7. Na tabela, selecione a conta que você deseja adicionar ao Skype for Business Server e clique em **OK.**

8. Atribua o usuário a um pool, especifique qualquer detalhe adicional, atribua as políticas ao usuário desejado e clique em **Habilitar**.

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a>Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para o Skype for Business Server
<a name="Disable"> </a>

Você pode usar o procedimento a seguir para desabilitar uma conta de usuário habilitada anteriormente no Skype for Business Server sem perder as configurações do Skype for Business Server que você definiu para a conta de usuário. Como você não perde as configurações da conta de usuário do Skype for Business Server, é possível reabilitar uma conta de usuário habilitada anteriormente sem precisar reconfigurar a conta de usuário.

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. Na caixa **Usuários de pesquisa**, digite todo ou a primeira parte do nome de exibição, primeiro nome, último nome, nome de conta do Gerenciador de contas de segurança (SAM), endereço SIP ou alinhe o Identificador de recurso uniforme (URI) da conta do usuário que você quer desabilitar ou reabilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você quer habilitar ou reabilitar.

6. No menu **Ação**, faça o seguinte:

   - Para desabilitar temporariamente a conta de usuário do Skype for Business Server, clique em **Desabilitar temporariamente para o Lync Server.**

   - Para habilitar a conta de usuário do Skype for Business Server, clique em **Reabilitar para Lync Server.**

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Usar o Windows Powershell para desabilitar ou reabilitar contas de usuário

As contas de usuário podem ser temporariamente desabilitadas e reativadas posteriormente usando o cmdlet **Set-CsUser.** Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

### <a name="to-disable-a-user-account"></a>Para desabilitar uma conta de usuário

- Para desabilitar uma conta temporariamente, defina o valor da propriedade Enabled como falso ($False). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a>Para reabilitar uma conta de usuário

- Para reabilitar uma conta de usuário, defina o valor da propriedade Enabled como verdadeiro ($True). Por exemplo:

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsUser.](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)

## <a name="disable-a-user-for-enterprise-voice"></a>Desabilitar um usuário para o Enterprise Voice
<a name="Disable_EV"> </a>

Use o procedimento a seguir para desabilitar o Enterprise Voice para uma conta de usuário habilitada para o Skype for Business Server.

### <a name="to-disable-a-user-account-for-enterprise-voice"></a>Para desabilitar uma conta de usuário para o Enterprise Voice

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.

5. Na tabela, clique na conta de usuário que você deseja habilitar para o Enterprise Voice.

6. No menu **Editar**, clique em **Exibir detalhes**.

7. Na página **Editar usuário do servidor Lync**, sob **Telefonia**, clique em qualquer opção exceto **Enterprise Voice**.

    > [!NOTE]
    > Para restringir um usuário de fazer chamadas de áudio ou vídeo usando o Lync, em **Telefonia,** clique em **Áudio/vídeo desabilitado.**

8. Clique em **Confirmar**.

O usuário agora não pode usar o recurso do Enterprise Voice. Informações relacionadas: <br/>[Enterprise Voice e mobilidade](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [Habilitar usuários para o Enterprise Voice no Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [Shell de Gerenciamento do Skype for Business Server](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a>Remover uma conta de usuário com o Shell de Gerenciamento do Skype for Business Server
<a name="Remove"> </a>

Você pode usar o procedimento a seguir para remover uma conta de usuário adicionada anteriormente no Skype for Business Server.

> [!NOTE]
> Remover um usuário pode causar a perda de qualquer configuração definida para a conta de usuário. Se você quiser desabilitar temporariamente uma conta de usuário, consulte Desabilitar ou reabilitar uma conta de usuário habilitada anteriormente para [o Skype for Business Server.](user-accounts.md#Disable)

1. Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2. Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3. Na barra de navegação à esquerda, clique em **Usuários**.

4. Na caixa **Pesquisar usuários**, digite todo ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta de usuário que você deseja desabilitar ou reabilitar e clique em **Encontrar**.

5. Na tabela, clique na conta de usuário que deseja remover.

6. No menu **Ação**, selecione **Remover do Lync Server** e uma caixa de diálogo aparece.

7. Na caixa de diálogo, selecione **OK** para remover o usuário.

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a>Remover contas de usuário com cmdlets do Windows Powershell

Você pode remover contas de usuário usando o Disable-CsUser cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). O processo é o mesmo no Skype for Business Server.

### <a name="to-remove-a-user-account"></a>Para remover uma conta de usuário
Para remover uma conta de usuário, utilize o cmdlet Disable-CsUser. Por exemplo:

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Disable-CsUser.](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)

## <a name="see-also"></a>Confira também
<a name="Remove"> </a>

[Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
