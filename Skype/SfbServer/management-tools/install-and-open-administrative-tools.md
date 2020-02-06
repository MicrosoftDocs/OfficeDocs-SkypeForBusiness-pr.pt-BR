---
title: Instalar e abrir ferramentas administrativas
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
description: Este tópico descreve como instalar e abrir as ferramentas administrativas necessárias para implantar e gerenciar o Skype for Business.
ms.openlocfilehash: c720aba3998df8742406f4c9954f523b20e9af5f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816550"
---
# <a name="install-and-open-administrative-tools"></a>Instalar e abrir ferramentas administrativas

Este tópico descreve como instalar as ferramentas administrativas necessárias para implantar e gerenciar o Skype for Business Server. As ferramentas administrativas são instaladas por padrão em cada servidor que executa o Skype for Business Server. Além disso, você pode instalar as ferramentas administrativas em outros computadores, como consoles administrativos dedicados. É altamente recomendável que você instale as ferramentas administrativas em um computador que esteja no mesmo domínio ou floresta que a implantação do Skype for Business Server que você está criando, para garantir que as etapas de preparação dos serviços de domínio Active Directory já estejam concluídas. que permite que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia. Além disso, certifique-se de rever os requisitos necessários antes de instalar ou usar as ferramentas administrativas do Skype for Business Server. Veja a documentação de requisitos no [Skype for Business server 2019](../../SfBServer2019/plan/system-requirements.md) ou no [Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Se a sua organização exigir que você localize os serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Skype for Business Server na caixa de diálogo Configurar. Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Skype for Business Server também será implantado nessa unidade. 

## <a name="to-install-the-administrative-tools"></a>Para instalar as ferramentas administrativas

1. Faça logon como administrador local (requisito mínimo) para o computador em que você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão no Windows e o UAC (controle de conta de usuário) estiver habilitado, você será solicitado a fornecer o administrador local ou um nome de usuário e uma senha equivalentes ao domínio.
2. Localize a mídia de instalação no seu computador e, em seguida, clique duas vezes em \Setup\amd64\Setup.exe.
3. Se você for solicitado a instalar o Microsoft Visual C++ Redistributable, clique em **Sim**.
4. Na página Local de instalação, clique em **OK**. Altere esse caminho para outro local ou unidade se precisar ter os arquivos instalados em outro local.

    > [!Important]
    > Se a sua organização exigir que você localize os serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Skype for Business Server na caixa de diálogo Configurar. Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Skype for Business Server também será implantado nesta unidade. 

5. Na página contrato de licença de usuário final, examine os termos de licença, clique em **aceito**e, em seguida, clique em **OK**. Esta etapa é necessária para que você possa continuar.
6. Na página Assistente de implantação, clique em **instalar ferramentas de administrador**. 
7. Quando a instalação for concluída com êxito, clique em **sair**.

Use os procedimentos a seguir para abrir ferramentas administrativas para implantar, configurar ou solucionar problemas de topologia do Skype for Business Server.

- [Assistente de Implantação](#deployment-wizard)
- [Construtor de Topologias](#topology-builder) 
- [Painel de Controle do Skype for Business Server](#skype-for-business-server-control-panel)
- [Shell de Gerenciamento do Skype for Business Server](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistente de Implantação

Use o procedimento a seguir para iniciar o assistente de implantação localmente para adicionar ou remover arquivos de componentes.

**Para iniciar o assistente de implantação do Skype for Business Server**

1. Faça logon no computador em que o assistente de implantação do Skype for Business Server está instalado como membro do grupo Domain admins e do grupo RTCUniversalServerAdmins.
2. Clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server**e, em seguida, clique em **Assistente de implantação do Skype for Business Server**.


## <a name="topology-builder"></a>Construtor de Topologias 

Use o procedimento a seguir para abrir o construtor de topologias e definir os servidores que você deseja implantar na topologia do Skype for Business Server.

**Para abrir o construtor de topologias do Skype for Business Server para projetar a topologia**

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para ler, publicar ou habilitar uma topologia, o que é necessário para instalar o Skype for Business Server em um servidor, você deve usar uma conta que seja membro do grupo Administradores de domínio e Grupo e RTCUniversalServerAdmins e com permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você vai usar para o repositório de arquivos de arquivamento para que o construtor de topologia possa configurar a lista de controle de acesso discricional necessária ( DACLs) ou uma conta com direitos de usuário equivalentes.
 
2. Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server**e em **Construtor de topologias do Skype for Business Server**.

## <a name="skype-for-business-server-control-panel"></a>Painel de Controle do Skype for Business Server 

Use um dos seguintes procedimentos para abrir o painel de controle do Skype for Business Server para gerenciar a configuração de servidores, usuários, clientes e dispositivos em seu ambiente.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para realizar qualquer tarefa no painel de controle do Skype for Business Server. Você pode usar outras funções para fazer logon no painel de controle do Skype for Business Server para executar tarefas específicas de administração, dependendo da tarefa que você precisa executar. Por exemplo, você pode usar o CSArchivingAdministrator para administrar o arquivamento no painel de controle do Skype for Business Server. Para obter detalhes sobre as funções, consulte [planejar o controle de acesso baseado em função](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obter detalhes sobre as funções que você pode usar para realizar uma tarefa específica, consulte a documentação da tarefa. 

**Para abrir o painel de controle do Skype for Business Server em qualquer computador dentro do firewall da sua organização**

1. Em uma conta de usuário que é atribuída à função CsAdministrator ou outra função que tenha direitos e permissões de usuário apropriados para a tarefa ser realizada, faça logon em qualquer computador em sua implantação interna com uma resolução de tela mínima de 1024 x 768.

    > [!IMPORTANT]
    > Se você tiver configurado um URL (Uniform Resource Locator) simples de administração, poderá acessar o painel de controle do Skype for Business Server em um navegador da Internet que esteja em execução em qualquer computador dentro do firewall da sua organização. Para obter detalhes sobre como configurar a URL simples de administração, consulte [planejando URLs simples](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) e [editando ou configurando URLs simples](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Abra uma janela do navegador e, em seguida, insira a URL de administração configurada para sua organização.

**Para abrir o painel de controle do Skype for Business Server em um computador que esteja executando o Skype for Business Server**

1. Em uma conta de usuário que seja membro da função CsAdministrator ou outra função que tenha direitos e permissões de usuário apropriados para a tarefa ser realizada, faça logon em um computador no qual você instalou o Skype for Business Server ou, no mínimo, , as ferramentas administrativas do Skype for Business Server. Para definir as configurações, o computador deve ter uma resolução de tela mínima de 1024 x 768.
2. Inicie o painel de controle do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, aponte para **Ferramentas administrativas**, aponte para **Skype for Business Server**e clique em **painel de controle do Skype for Business Server**.

## <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server 

Use o procedimento a seguir para abrir o Shell de gerenciamento do Skype for Business Server para administrar servidores, usuários, clientes e dispositivos em seu ambiente usando a linha de comando.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para realizar qualquer tarefa no Shell de gerenciamento do Skype for Business Server. Você pode fazer logon usando outras funções para executar tarefas específicas de administração, dependendo da tarefa que você precisa executar. Por exemplo, você pode usar CSArchivingAdministrator para executar cmdlets relacionados à administração do arquivamento. Para obter detalhes sobre as funções, consulte [planejar o controle de acesso baseado em função](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obter detalhes sobre as funções que você pode usar para executar um cmdlet específico, consulte a documentação do cmdlet.<br/><br/>Você também pode executar determinados cmdlets usando uma conta de usuário nos grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, dependendo do cmdlet. 

**Para abrir o Shell de gerenciamento do Skype for Business Server**

Se você abrir uma janela do Windows PowerShell em vez do Shell de gerenciamento do Skype for Business Server, por padrão, não poderá executar os cmdlets do Skype for Business Server. Para executar os cmdlets do Skype for Business Server dentro do Windows PowerShell, digite o seguinte no prompt de comando do Windows PowerShell:

`Import-Module Lync`

Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
