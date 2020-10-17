---
title: 'Lync Server 2013: Configurando um nó do inspetor para usar autenticação de credenciais'
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
ms.openlocfilehash: 4e05ac48896b50b4b83e4211a5036f6a6d513d43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517684"
---
# <a name="configuring-a-watcher-node-to-use-credential-authentication-in-lync-server-2013"></a>Configurando um nó do inspetor para usar a autenticação de credenciais no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Se seu computador no nó do inspetor estiver fora da rede de perímetro, será necessário seguir um procedimento um pouco diferente para configurar o nó do inspetor a fim de executar transações sintéticas. Especificamente, não crie um pool de aplicativos confiáveis e um aplicativo confiável, e é necessário instalar um certificado que permita ao nó do inspetor enviar alertas a um computador dentro da rede de perímetro. Isso significa que será necessário completar duas tarefas separadas:

  - Atualize a associação no grupo Administradores locais somente leitura RTC do computador

  - Instale os arquivos de configuração do nó do inspetor

<div>

## <a name="updating-membership-in-the-rtc-local-read-only-administrators-group"></a>Atualizando a associação no grupo Administradores locais somente leitura RTC

Se seu nó de inspetor estiver fora da rede de perímetro, será necessário adicionar a conta Serviço de Rede ao grupo Administradores locais somente leitura RTC no computador no nó do inspetor. Para fazer isso, complete o seguinte procedimento no nó do inspetor:

1.  Clique em **Iniciar**, clique com o botão direito do mouse em **Computador** e clique em **Gerenciar**.

2.  No Gerenciador de Servidor, expanda **Configuração**, expanda **Usuários e Grupos Locais** e clique em **Grupos**.

3.  No painel Grupos, clique duas vezes em **Administradores locais somente leitura RTC**.

4.  Na caixa  de diálogo **Propriedades de Administradores Locais Somente Leitura RTC**, clique em **Adicionar**.

5.  Na caixa de diálogo **Selecionar Usuários, Computadores, Contas de Serviço ou Grupos**, clique em **Locais**

6.  Na caixa de diálogo **Locais**, selecione o nome do computador no nó de inspetor e clique em **OK**.

7.  Na caixa **Digite os nomes de objeto a serem selecionados**, digite **Serviço de Rede** e clique em **OK**.

8.  Na caixa  de diálogo **Propriedades de Administradores Locais Somente Leitura RTC**, clique em **OK** e feche o **Gerenciador de Servidor**.

Reinicie o computador no nó do inspetor.

</div>

<div>

## <a name="installing-the-watcher-node-configuration-files"></a>Instalando os Arquivos de Configuração no Nó do Inspetor

Após a reinicialização do computador no nó de inspetor, sua próxima etapa será executar o arquivo Watchernode.msi. Para executar esse arquivo, abra o Shell de gerenciamento do Lync Server 2013 clicando em **Iniciar**, em **todos os programas**, em **Lync Server 2013**e em **Shell de gerenciamento do Lync Server**. No Shell de gerenciamento do Lync Server, digite o seguinte comando e pressione ENTER (tenha certeza e especifique o caminho real para a sua cópia do Watchernode.msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate

<div>


> [!NOTE]  
> Conforme indicado anteriormente, Watchernode.msi também pode ser executado a partir de uma janela de comando. Para abrir uma janela de comando, clique em <STRONG>Iniciar</STRONG>, clique com o botão direito do mouse em <STRONG>Prompt de Comando</STRONG> e clique em <STRONG>Executar como administrador</STRONG>. Quando a janela de comando for aberta, digite o mesmo comando exibido anteriormente.



</div>

O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável. Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.

</div>

</div>

<span> </span>

</div>

</div>

</div>

