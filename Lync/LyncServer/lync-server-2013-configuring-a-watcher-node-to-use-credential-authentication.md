---
title: 'Lync Server 2013: Configurando um nó de inspetor para usar a autenticação de credenciais'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use credential authentication
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48183255
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d0fa67c4ef2688035471d2290ead78123f73239
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Configurando um nó de inspetor para usar a autenticação de credenciais no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Se o seu computador do nó do Inspetor estiver fora da rede de perímetro, você deve seguir um procedimento levemente diferente para configurar esse nó de inspetor para executar transações sintéticas. Especificamente, você não deve criar um pool de aplicativos confiável e um aplicativo confiável, e deve instalar um certificado que permita que o nó do Inspetor envie alertas para um computador dentro da rede de perímetro. Isso significa que você precisará completar duas tarefas separadas:

  - Atualize a associação no grupo de administradores somente leitura do RTC do computador local

  - Instalar os arquivos de configuração do nó do Inspetor

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Atualizando associação no grupo de administradores somente leitura local do RTC

Se o nó do Inspetor estiver fora da rede de perímetro, você deve adicionar a conta de serviço de rede ao grupo de administradores somente leitura local do RTC no computador do nó inspetor. Para fazer isso, conclua o procedimento a seguir no nó inspetor:

1.  Clique em **Iniciar**, clique com o botão direito do mouse em **computador**e clique em **gerenciar**.

2.  No Gerenciador de servidores, expanda **configuração**, expanda **usuários e grupos locais**e clique em **grupos**.

3.  No painel grupos, clique duas vezes em **RTC somente leitura administradores locais**.

4.  Na caixa de diálogo **Propriedades de administradores somente leitura do RTC local** , clique em **Adicionar**.

5.  Na caixa de diálogo **Selecionar usuários, computadores, contas de serviço ou grupos** , clique em **locais**.

6.  Na caixa de diálogo **locais** , selecione o nome do computador do nó do Inspetor e clique em **OK**.

7.  Na caixa **digite os nomes de objeto a serem selecionados** , digite **serviço de rede**e clique em **OK**.

8.  Na caixa de diálogo **Propriedades de administradores somente leitura do RTC local** , clique em **OK**e feche o **Gerenciador de servidores**.

Reinicie o computador no nó do inspetor.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Instalando os arquivos de configuração do nó do Inspetor

Após a reinicialização do computador do nó do Inspetor, a próxima etapa é executar o arquivo Watchernode. msi. Para executar esse arquivo, abra o Shell de gerenciamento do Lync Server 2013 clicando em **Iniciar**, em **todos os programas**, em **Lync Server 2013**e em **Shell de gerenciamento do Lync Server**. No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (certifique-se de especificar o caminho real para a sua cópia do Watchernode. msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Conforme observado anteriormente, o Watchernode. msi também pode ser executado em uma janela de comando. Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de Comando</STRONG> e clique em <STRONG>Executar como administrador</STRONG>. Quando a janela de comando abrir, digite o mesmo comando mostrado anteriormente.



</div>

O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável. Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

