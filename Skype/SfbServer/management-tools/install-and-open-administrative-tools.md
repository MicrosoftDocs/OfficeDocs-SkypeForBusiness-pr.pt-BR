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
ms.openlocfilehash: d31fe784b62a5d709049dc5061e323034065df37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835091"
---
# <a name="install-and-open-administrative-tools"></a>Instalar e abrir ferramentas administrativas

Este tópico descreve como instalar as ferramentas administrativas necessárias para implantar e gerenciar o Skype for Business Server. As ferramentas administrativas são instaladas por padrão em cada servidor que executa o Skype for Business Server. Além disso, você pode instalar as ferramentas administrativas em outros computadores, tais como consoles administrativos dedicados. É fortemente recomendável instalar as ferramentas administrativas em um computador que esteja no mesmo domínio ou floresta que a implantação do Skype for Business Server que você está criando, para garantir que as etapas de preparação dos Serviços de Domínio Active Directory já estão concluídas, o que permite que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia. Também certifique-se de revisar os requisitos necessários antes de instalar ou usar as ferramentas administrativas do Skype for Business Server. Consulte a documentação de requisitos [no Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md) ou no Skype for Business Server [2015.](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md)
 
> [!Important]
> Se sua organização exigir que você localize os Serviços de Informações da Internet (IIS) e todos os Serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Skype for Business Server na caixa de diálogo Instalação. Se você instalar os arquivos de Instalação nesse caminho, incluindo o OCSCore.msi, o restante dos arquivos do Skype for Business Server também será implantado nessa unidade. 

## <a name="to-install-the-administrative-tools"></a>Para instalar as ferramentas administrativas

1. Faça logon como um administrador local (requisito mínimo) no computador onde você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão no Windows e o UAC (Controle de Conta de Usuário) estiver habilitado, o administrador local ou um nome de usuário e senha equivalentes do domínio serão solicitados.
2. Localize a mídia de instalação no seu computador e clique duas vezes em \Setup\amd64\Setup.exe.
3. Se você for solicitado a instalar o Microsoft Visual C++ distribuível, clique em **Sim.**
4. Na página Local de instalação, clique em **OK**. Altere este caminho para outro local ou unidade se precisa dos arquivos instalados em outra localização.

    > [!Important]
    > Se sua organização exigir que você localize os Serviços de Informações da Internet (IIS) e todos os Serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Skype for Business Server na caixa de diálogo Instalação. Se você instalar os arquivos de Instalação nesse caminho, incluindo o OCSCore.msi, o restante dos arquivos do Skype for Business Server também será implantado nessa unidade. 

5. Na página Acordo de licença do usuário final, revise os termos de licença, clique em **Eu aceito** e em **OK**. Essa etapa é necessária antes de você poder continuar.
6. Na página Assistente de Implantação, clique em **Instalar Ferramentas de Administrador.** 
7. Quando a instalação for concluída com êxito, clique em **Sair**.

Use os procedimentos a seguir para abrir ferramentas administrativas para implantar, configurar ou solucionar problemas de sua topologia do Skype for Business Server.

- [Assistente de Implantação](#deployment-wizard)
- [Construtor de Topologias](#topology-builder) 
- [Painel de Controle do Skype for Business Server](#skype-for-business-server-control-panel)
- [Shell de Gerenciamento do Skype for Business Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistente de Implantação

Use o procedimento a seguir para iniciar o Assistente de Implantação localmente para adicionar ou remover arquivos de componente.

**Para iniciar o Assistente de Implantação do Skype for Business Server**

1. Faça logoff no computador em que o Assistente de Implantação do Skype for Business Server está instalado como membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins.
2. Clique **em** Iniciar, em **Todos os Programas,** **no Skype for Business Server** e no Assistente de Implantação do Skype for **Business Server.**


## <a name="topology-builder"></a>Construtor de Topologias 

Use o procedimento a seguir para abrir o Construtor de Topologias para definir os servidores que você deseja implantar em sua topologia do Skype for Business Server.

**Para abrir o Construtor de Topologias do Skype for Business Server para projetar a topologia**

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo Usuários local, mas para ler, publicar ou habilitar uma topologia, que é necessária para instalar o Skype for Business Server em um servidor, você deve usar uma conta que seja membro do grupo Administradores de Domínio e do grupo RTCUniversalServerAdmins e que tenha permissões de controle total (ou seja, , ler, gravar e modificar) no compartilhamento de arquivos que você usará para o armazenamento de arquivos de arquivamento para que o Construtor de Topologias possa configurar a lista de controle de acesso discricionário (DACLs) necessária ou uma conta com direitos de usuário equivalentes.
 
2. Start Topology Builder: Click **Start**, click **All Programs**, click **Skype for Business Server**, and then click Skype for Business Server **Topology Builder**.

## <a name="skype-for-business-server-control-panel"></a>Painel de Controle do Skype for Business Server 

Use um dos procedimentos a seguir para abrir o Painel de Controle do Skype for Business Server para gerenciar a configuração de servidores, usuários, clientes e dispositivos em seu ambiente.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa no Painel de Controle do Skype for Business Server. Você pode usar outras funções para fazer logon no Painel de Controle do Skype for Business Server para executar tarefas de administração específicas, dependendo da tarefa que você precisa executar. Por exemplo, você pode usar o CSArchivingAdministrator para administrar o Arquivamento no Painel de Controle do Skype for Business Server. Para obter detalhes sobre funções, [consulte Planejamento para controle de acesso baseado em função.](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx) Para detalhes sobre as funções que podem ser usada para executar uma tarefa específica, consulte a documentação da tarefa. 

**Para abrir o Painel de Controle do Skype for Business Server de qualquer computador dentro do firewall da sua organização**

1. A partir de uma conta de usuário atribuída à função CsAdministrator ou a outra função que tenha direitos de usuário e permissões apropriadas para a tarefa a ser executada, faça logon em qualquer computador em sua implantação interna com uma resolução de tela mínima de 1024 x 768.

    > [!IMPORTANT]
    > Se você configurou uma URL simples de administração, você pode acessar o Painel de Controle do Skype for Business Server a partir de um navegador da Internet que está sendo executado em qualquer computador dentro do firewall da sua organização. Para obter detalhes sobre como configurar a URL simples de administração, consulte [Planejamento para URLs simples](https://technet.microsoft.com/library/gg398287(v=ocs.15).aspx) e Editar ou configurar [URLs simples.](https://technet.microsoft.com/library/gg398063(v=ocs.15).aspx) 

2. Abra uma janela do navegador e insira a URL do Administrador configurada para a sua organização.

**Para abrir o Painel de Controle do Skype for Business Server em um computador que executa o Skype for Business Server**

1. A partir de uma conta de usuário que seja membro da função CsAdministrator ou de outra função que tenha os direitos e permissões de usuário apropriados para a tarefa a ser executada, faça logon em um computador no qual você instalou o Skype for Business Server ou, no mínimo, as ferramentas administrativas do Skype for Business Server. Para definir as configurações, o computador deve ter uma resolução de tela mínima de 1024 x 768.
2. Inicie o Painel de Controle do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** aponte para Ferramentas Administrativas, aponte para o Skype for Business **Server** e clique no Painel de Controle do Skype for Business **Server.**

## <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server 

Use o procedimento a seguir para abrir o Shell de Gerenciamento do Skype for Business Server para administrar servidores, usuários, clientes e dispositivos em seu ambiente usando a linha de comando.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa no Shell de Gerenciamento do Skype for Business Server. Você pode fazer logon usando outras funções para executar tarefas administrativas específicas, dependendo da tarefa que precisa realizar. Por exemplo, você pode usar a CSArchivingAdministrator para executar cmdlets relacionados à administração de Arquivamento. Para obter detalhes sobre funções, [consulte Planejamento para controle de acesso baseado em função.](https://technet.microsoft.com/library/gg425917(v=ocs.15).aspx) Para detalhes sobre as funções que podem ser usada para executar um cmdlet específico, consulte a documentação do cmdlet.<br/><br/>Você também pode executar certos cmdlets usando uma conta de usuário nos grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins, ou RTCUniversalReadOnlyAdmins, dependendo do cmdlet. 

**Para abrir o Shell de Gerenciamento do Skype for Business Server**

Se você abrir uma janela do Windows PowerShell em vez do Shell de Gerenciamento do Skype for Business Server, por padrão não poderá executar os cmdlets do Skype for Business Server. Para executar os cmdlets do Skype for Business Server no Windows PowerShell, digite o seguinte no prompt de comando do Windows PowerShell:

`Import-Module Lync`

Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**
