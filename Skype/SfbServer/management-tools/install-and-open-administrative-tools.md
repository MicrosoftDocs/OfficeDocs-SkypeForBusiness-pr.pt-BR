---
title: Instalar e abrir ferramentas administrativas
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
description: Este tópico descreve como instalar e abrir as ferramentas administrativas necessárias para implantar e gerenciar o Skype for Business.
ms.openlocfilehash: 72966026e414b3b36cfc49ab61bf41f045e1f864
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098777"
---
# <a name="install-and-open-administrative-tools"></a>Instalar e abrir ferramentas administrativas

Este tópico descreve como instalar as ferramentas administrativas necessárias para implantar e gerenciar o Skype for Business Server. As ferramentas administrativas são instaladas por padrão em cada servidor que executa o Skype for Business Server. Além disso, você pode instalar as ferramentas administrativas em outros computadores, tais como consoles administrativos dedicados. Recomendamos que você instale as ferramentas administrativas em um computador que esteja no mesmo domínio ou floresta que a implantação do Skype for Business Server que você está criando, para garantir que as etapas de preparação dos Serviços de Domínio active Directory já estão concluídas, o que permite que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia. Revise também os requisitos necessários antes de instalar ou usar as ferramentas administrativas do Skype for Business Server. Consulte a documentação de requisitos [no Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) ou Skype for Business Server [2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Se sua organização exigir que você localize o IIS (Serviços de Informações da Internet) e todos os Serviços Web em uma unidade diferente da unidade do sistema, você pode alterar o caminho do local de instalação para os arquivos do Skype for Business Server na caixa de diálogo Instalação. Se você instalar os arquivos de Instalação nesse caminho, incluindo OCSCore.msi, o restante dos arquivos do Skype for Business Server também será implantado nessa unidade. 

## <a name="to-install-the-administrative-tools"></a>Para instalar as ferramentas administrativas

1. Faça logon como um administrador local (requisito mínimo) no computador onde você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão no Windows e o Controle de Conta de Usuário (UAC) estiver habilitado, você será solicitado para o administrador local ou um nome de usuário e senha equivalentes de domínio.
2. Localize a mídia de instalação no seu computador e clique duas vezes em \Setup\amd64\Setup.exe.
3. Se você for solicitado a instalar o Microsoft Visual C++ distribuível, clique em **Sim**.
4. Na página Local de instalação, clique em **OK**. Altere este caminho para outro local ou unidade se precisa dos arquivos instalados em outra localização.

    > [!Important]
    > Se sua organização exigir que você localize o IIS (Serviços de Informações da Internet) e todos os Serviços Web em uma unidade diferente da unidade do sistema, você pode alterar o caminho do local de instalação para os arquivos do Skype for Business Server na caixa de diálogo Instalação. Se você instalar os arquivos de Instalação nesse caminho, incluindo OCSCore.msi, o restante dos arquivos do Skype for Business Server também será implantado nessa unidade. 

5. Na página Acordo de licença do usuário final, revise os termos de licença, clique em **Eu aceito** e em **OK**. Essa etapa é necessária antes de você poder continuar.
6. Na página Assistente de Implantação, clique em **Instalar Ferramentas de Administrador.** 
7. Quando a instalação for concluída com êxito, clique em **Sair**.

Use os procedimentos a seguir para abrir ferramentas administrativas para implantar, configurar ou solucionar problemas da topologia do Skype for Business Server.

- [Assistente de Implantação](#deployment-wizard)
- [Construtor de Topologias](#topology-builder) 
- [Painel de Controle do Skype for Business Server](#skype-for-business-server-control-panel)
- [Shell de Gerenciamento do Skype for Business Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistente de Implantação

Use o procedimento a seguir para iniciar o Assistente de Implantação localmente para adicionar ou remover arquivos de componentes.

**Para iniciar o Assistente de Implantação do Skype for Business Server**

1. Faça logoff no computador onde o Assistente de Implantação do Skype for Business Server está instalado como membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins.
2. Clique **em Iniciar,** em **Todos os Programas,** no **Skype for Business Server** e em Assistente **de Implantação do Skype for Business Server.**


## <a name="topology-builder"></a>Construtor de Topologias 

Use o procedimento a seguir para abrir o Construtor de Topologias para definir os servidores que você deseja implantar em sua topologia do Skype for Business Server.

**Para abrir o Construtor de Topologias do Skype for Business Server para projetar a topologia**

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta membro do grupo Usuários local, mas para ler, publicar ou habilitar uma topologia, que é necessária para instalar o Skype for Business Server em um servidor, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins e que tenha permissões de controle total (ou seja, , leia, escreva e modifique) no compartilhamento de arquivos que você vai usar para o armazenamento de arquivos de arquivamento para que o Construtor de Topologias possa configurar a lista de controles de acesso discricionário necessário (DACLs) ou uma conta com direitos de usuário equivalentes.
 
2. Iniciar Construtor de Topologias: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business Server** e em Construtor de Topologias do Skype for Business **Server.**

## <a name="skype-for-business-server-control-panel"></a>Painel de Controle do Skype for Business Server 

Use um dos procedimentos a seguir para abrir o Painel de Controle do Skype for Business Server para gerenciar a configuração de servidores, usuários, clientes e dispositivos em seu ambiente.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa no Painel de Controle do Skype for Business Server. Você pode usar outras funções para fazer logon no Painel de Controle do Skype for Business Server para executar tarefas de administração específicas, dependendo da tarefa que você precisa executar. Por exemplo, você pode usar CSArchivingAdministrator para administrar o Arquivamento no Painel de Controle do Skype for Business Server. Para obter detalhes sobre funções, consulte [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Para detalhes sobre as funções que podem ser usada para executar uma tarefa específica, consulte a documentação da tarefa. 

**Para abrir o Painel de Controle do Skype for Business Server de qualquer computador dentro do firewall da sua organização**

1. A partir de uma conta de usuário atribuída à função CsAdministrator ou a outra função que tenha direitos de usuário apropriados e permissões para a tarefa a ser executada, faça logon em qualquer computador em sua implantação interna com uma resolução de tela mínima de 1024 x 768.

    > [!IMPORTANT]
    > Se você configurou um URL (localizador de recurso uniforme simples de administração), poderá acessar o Painel de Controle do Skype for Business Server a partir de um navegador da Internet que está sendo executado em qualquer computador dentro do firewall da sua organização. Para obter detalhes sobre como configurar a URL simples de administração, consulte [Planning for simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls) and [Edit or configure simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-edit-or-configure-simple-urls). 

2. Abra uma janela do navegador e insira a URL do Administrador configurada para a sua organização.

**Para abrir o Painel de Controle do Skype for Business Server em um computador que executa o Skype for Business Server**

1. A partir de uma conta de usuário membro da função CsAdministrator ou de outra função que tenha direitos de usuário e permissões apropriados para a tarefa a ser executada, faça logon em um computador no qual você instalou o Skype for Business Server ou, no mínimo, as ferramentas administrativas do Skype for Business Server. Para definir configurações, o computador deve ter uma resolução de tela mínima de 1024 x 768.
2. Inicie o Painel de Controle do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** aponte para Ferramentas Administrativas, aponte para o Skype for Business **Server** e clique em Painel de Controle do Skype for Business **Server**.

## <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server 

Use o procedimento a seguir para abrir o Shell de Gerenciamento do Skype for Business Server para administrar servidores, usuários, clientes e dispositivos em seu ambiente usando a linha de comando.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa no Shell de Gerenciamento do Skype for Business Server. Você pode fazer logon usando outras funções para executar tarefas administrativas específicas, dependendo da tarefa que precisa realizar. Por exemplo, você pode usar a CSArchivingAdministrator para executar cmdlets relacionados à administração de Arquivamento. Para obter detalhes sobre funções, consulte [Planning for role-based access control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-role-based-access-control). Para detalhes sobre as funções que podem ser usada para executar um cmdlet específico, consulte a documentação do cmdlet.<br/><br/>Você também pode executar certos cmdlets usando uma conta de usuário nos grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, ou RTCUniversalReadOnlyAdmins, dependendo do cmdlet. 

**Para abrir o Shell de Gerenciamento do Skype for Business Server**

Se você abrir uma Windows PowerShell em vez do Shell de Gerenciamento do Skype for Business Server, por padrão, não será possível executar os cmdlets do Skype for Business Server. Para executar os cmdlets do Skype for Business Server de dentro Windows PowerShell, digite o seguinte no prompt de comando Windows PowerShell:

`Import-Module Lync`

Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** **em** Todos os Programas, em Skype for **Business Server** e em Shell de Gerenciamento do Skype for **Business Server.**