---
title: Instalar e abrir ferramentas administrativas
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
description: Este tópico descreve como instalar e abrir as ferramentas administrativas necessárias para implantar e gerenciar Skype for Business.
ms.openlocfilehash: 21fc33f5e095100f9634695925e1000172742695
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848414"
---
# <a name="install-and-open-administrative-tools"></a>Instalar e abrir ferramentas administrativas

Este tópico descreve como instalar as ferramentas administrativas necessárias para implantar e gerenciar Skype for Business Server. As ferramentas administrativas são instaladas por padrão em cada servidor que executa Skype for Business Server. Além disso, você pode instalar as ferramentas administrativas em outros computadores, tais como consoles administrativos dedicados. Recomendamos que você instale as ferramentas administrativas em um computador que esteja no mesmo domínio ou floresta que Skype for Business Server implantação que você está criando, para garantir que as etapas de preparação dos Serviços de Domínio active Directory já estão concluídas, o que permite que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia. Além disso, revise os requisitos necessários antes de instalar ou usar as ferramentas Skype for Business Server administrativas. Consulte a documentação de requisitos [Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) [ou Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Se sua organização exigir que você localize Serviços de Informações da Internet (IIS) e todos os Serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho de local de instalação para os arquivos Skype for Business Server na caixa de diálogo Instalação. Se você instalar os arquivos de Instalação nesse caminho, incluindo OCSCore.msi, o restante dos arquivos Skype for Business Server serão implantados nessa unidade também. 

## <a name="to-install-the-administrative-tools"></a>Para instalar as ferramentas administrativas

1. Faça logon como um administrador local (requisito mínimo) no computador onde você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão no Windows e o Controle de Conta de Usuário (UAC) estiver habilitado, você será solicitado para o administrador local ou um nome de usuário e senha equivalentes de domínio.
2. Localize a mídia de instalação no seu computador e clique duas vezes em \Setup\amd64\Setup.exe.
3. Se você for solicitado a instalar o Microsoft Visual C++ distribuível, clique em **Sim**.
4. Na página Local de instalação, clique em **OK**. Altere este caminho para outro local ou unidade se precisa dos arquivos instalados em outra localização.

    > [!Important]
    > Se sua organização exigir que você localize Serviços de Informações da Internet (IIS) e todos os Serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho de local de instalação para os arquivos Skype for Business Server na caixa de diálogo Instalação. Se você instalar os arquivos de Instalação nesse caminho, incluindo OCSCore.msi, o restante dos arquivos Skype for Business Server serão implantados nessa unidade também. 

5. Na página Acordo de licença do usuário final, revise os termos de licença, clique em **Eu aceito** e em **OK**. Esta etapa é obrigatória antes de continuar.
6. Na página Assistente de Implantação, clique em **Instalar Ferramentas de Administrador.** 
7. Quando a instalação for concluída com êxito, clique em **Sair**.

Use os procedimentos a seguir para abrir ferramentas administrativas para implantar, configurar ou solucionar problemas Skype for Business Server topologia.

- [Assistente de Implantação](#deployment-wizard)
- [Construtor de Topologias](#topology-builder) 
- [Painel de Controle do Skype for Business Server](#skype-for-business-server-control-panel)
- [Shell de Gerenciamento do Skype for Business Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistente de Implantação

Use o procedimento a seguir para iniciar o Assistente de Implantação localmente para adicionar ou remover arquivos de componentes.

**Para iniciar o Assistente Skype for Business Server implantação**

1. Faça logoff no computador onde o Assistente de Implantação do Skype for Business Server está instalado como membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins.
2. Clique **em Iniciar,** em **Todos os Programas,** **Skype for Business Server** e clique Skype for Business Server Assistente **de Implantação.**


## <a name="topology-builder"></a>Construtor de Topologias 

Use o procedimento a seguir para abrir o Construtor de Topologias para definir os servidores que você deseja implantar em sua topologia de Skype for Business Server.

**Para abrir o construtor Skype for Business Server topologia para projetar a topologia**

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta membro do grupo Usuários local, mas para ler, publicar ou habilitar uma topologia, que é necessária para instalar o Skype for Business Server em um servidor, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins,  e que tem permissões de controle total (isto é, ler, gravar e modificar) no compartilhamento de arquivos que você vai usar para o armazenamento de arquivos de arquivamento para que o Construtor de Topologias possa configurar a lista de controle de acesso discricionário necessário (DACLs) ou uma conta com direitos de usuário equivalentes.
 
2. Iniciar Construtor de Topologias: clique em **Iniciar,** **clique** em Todos os Programas, Skype for Business Server **e** clique Skype for Business Server Construtor **de Topologias.**

## <a name="skype-for-business-server-control-panel"></a>Painel de Controle do Skype for Business Server 

Use um dos procedimentos a seguir para abrir o Painel de Controle Skype for Business Server para gerenciar a configuração de servidores, usuários, clientes e dispositivos em seu ambiente.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa no painel Skype for Business Server Controle. Você pode usar outras funções para fazer logon no Painel de Controle Skype for Business Server para executar tarefas de administração específicas, dependendo da tarefa que você precisa executar. Por exemplo, você pode usar CSArchivingAdministrator para administrar o arquivamento no Skype for Business Server Painel de Controle. Para obter detalhes sobre funções, consulte [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Para detalhes sobre as funções que podem ser usada para executar uma tarefa específica, consulte a documentação da tarefa. 

**Para abrir o painel Skype for Business Server de controle de qualquer computador dentro do firewall da sua organização**

1. A partir de uma conta de usuário atribuída à função CsAdministrator ou a outra função que tenha direitos de usuário apropriados e permissões para a tarefa a ser executada, faça logon em qualquer computador em sua implantação interna com uma resolução de tela mínima de 1024 x 768.

    > [!IMPORTANT]
    > Se você configurou um URL (localizador de recurso uniforme simples de administração), poderá acessar o Painel de Controle Skype for Business Server de um navegador da Internet que está sendo executado em qualquer computador dentro do firewall da sua organização. Para obter detalhes sobre como configurar a URL simples de administração, consulte [Planning for simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) and [Edit or configure simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls). 

2. Abra uma janela do navegador e insira a URL do Administrador configurada para a sua organização.

**Para abrir o painel Skype for Business Server de controle em um computador que executa Skype for Business Server**

1. De uma conta de usuário que é membro da função CsAdministrator ou de outra função que tenha direitos e permissões de usuário apropriados para a tarefa a ser executada, faça logon em um computador no qual você instalou o Skype for Business Server ou, no mínimo, as ferramentas administrativas Skype for Business Server. Para definir configurações, o computador deve ter uma resolução de tela mínima de 1024 x 768.
2. Iniciar Skype for Business Server Painel de Controle: Clique em **Iniciar,** em Todos os **Programas,** aponte para Ferramentas Administrativas, aponte para Skype for Business Server **e** clique em Skype for Business Server Painel de **Controle**.

## <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server 

Use o procedimento a seguir para abrir o Shell de Gerenciamento Skype for Business Server para administrar servidores, usuários, clientes e dispositivos em seu ambiente usando a linha de comando.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa no Shell de Gerenciamento Skype for Business Server. Você pode fazer logon usando outras funções para executar tarefas administrativas específicas, dependendo da tarefa que precisa realizar. Por exemplo, você pode usar a CSArchivingAdministrator para executar cmdlets relacionados à administração de Arquivamento. Para obter detalhes sobre funções, consulte [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Para detalhes sobre as funções que podem ser usada para executar um cmdlet específico, consulte a documentação do cmdlet.<br/><br/>Você também pode executar certos cmdlets usando uma conta de usuário nos grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, ou RTCUniversalReadOnlyAdmins, dependendo do cmdlet. 

**Para abrir Skype for Business Server Shell de Gerenciamento**

Se você abrir uma Windows PowerShell em vez do Shell de Gerenciamento Skype for Business Server, por padrão, não poderá executar os cmdlets Skype for Business Server de gerenciamento. Para executar os cmdlets Skype for Business Server de dentro Windows PowerShell, digite o seguinte no prompt de Windows PowerShell comando:

`Import-Module Lync`

Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar,** **clique** em Todos os Programas, clique Skype for Business Server **e** clique Skype for Business Server Shell **de Gerenciamento.**