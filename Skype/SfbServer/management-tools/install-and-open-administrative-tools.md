---
title: Instalar e abrir ferramentas administrativas
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este tópico descreve como instalar e abra as ferramentas administrativas que você precisa para implantar e gerenciar Skype para negócios.
ms.openlocfilehash: a27f16ab72d8fcdd4a5c440909dfb40baadd2572
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223161"
---
# <a name="install-and-open-administrative-tools"></a>Instalar e abrir ferramentas administrativas

Este tópico descreve como instalar as ferramentas administrativas que você precisa para implantar e gerenciar Skype para Business Server. As ferramentas administrativas são instaladas por padrão em cada servidor que executa o Skype para Business Server. Além disso, você pode instalar as ferramentas administrativas em outros computadores, como consoles administrativos dedicados. É altamente recomendável que você instala as ferramentas administrativas em um computador que esteja no mesmo domínio ou da floresta, como o Skype para implantação de servidor de negócios que você está criando, para garantir que preparação do Active Directory Domain Services etapas já forem concluídas, que permite que você use as ferramentas administrativas nesse computador posteriormente para publicar sua topologia. Também Certifique-se de examinar os requisitos necessários antes de instalar ou usar o Skype para ferramentas administrativas do servidor de negócios. Consulte a documentação de requisitos em [Skype para Business Server 2019](../../SfBServer2019/plan/system-requirements.md) ou [Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md).
 
> [!Important]
> Se sua organização requer que você localizar serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você pode alterar o caminho do local de instalação para o Skype para arquivos do servidor de negócios na caixa de diálogo Configurar. Se você instalar os arquivos de instalação para esse caminho, incluindo Ocscore, o restante do Skype para arquivos Business Server será implantado nesta unidade de disco. 

## <a name="to-install-the-administrative-tools"></a>Para instalar as ferramentas administrativas

1. Faça logon como um administrador local (requisito mínimo) para o computador onde você deseja instalar as ferramentas administrativas. Se você estiver conectado como um usuário padrão do Windows e o controle de conta de usuário (UAC) estiver habilitados, você será solicitado para o administrador local ou um nome de usuário equivalentes do domínio e uma senha.
2. Localize a mídia de instalação no seu computador e, em seguida, clique duas vezes em \setup\amd64\setup.exe..
3. Se você for solicitado a instalar o Microsoft Visual C++ distribuível, clique em **Sim**.
4. Na página Local de instalação, clique em **OK**. Altere esse caminho para outro local ou unidade, se você precisar ter os arquivos instalados para outro local.

    > [!Important]
    > Se sua organização requer que você localizar serviços de informações da Internet (IIS) e todos os serviços Web em uma unidade diferente da unidade do sistema, você pode alterar o caminho do local de instalação para o Skype para arquivos do servidor de negócios na caixa de diálogo Configurar. Se você instalar os arquivos de instalação para esse caminho, incluindo Ocscore, o restante do Skype para arquivos Business Server será implantado muito a essa unidade. 

5. Na página Contrato de licença de usuário final, analise os termos de licença, clique em **eu aceito**e, em seguida, clique em **Okey**. Esta etapa é necessária antes de continuar.
6. Na página do Assistente de implantação, clique em **Instalar ferramentas do administrador**. 
7. Quando a instalação for concluída com êxito, clique em **Sair**.

Use os procedimentos a seguir para abrir ferramentas administrativas para implantar, configurar ou solucionar problemas de sua Skype para a topologia de servidor de negócios.

- [Assistente de Implantação](#deployment-wizard)
- [Construtor de Topologias](#topology-builder) 
- [Painel de Controle do Skype for Business Server](#skype-for-business-server-control-panel)
- [Shell de Gerenciamento do Skype for Business Serverl](#skype-for-business-server-management-shell)

## <a name="deployment-wizard"></a>Assistente de Implantação

Use o procedimento a seguir para iniciar o Assistente de implantação localmente, para adicionar ou remover arquivos de componente.

**Para iniciar o Skype para o Assistente de implantação de servidor de negócios**

1. Faça logon no computador onde o Skype para o Assistente de implantação do Business Server está instalado como membro do grupo Administradores de domínio e do grupo RTCUniversalServerAdmins.
2. Clique em **Iniciar**, clique em **Todos os programas**, clique **Skype para Business Server**e clique em **Skype para o Assistente de implantação de servidor de negócios**.


## <a name="topology-builder"></a>Construtor de Topologias 

Use o procedimento a seguir para abrir o construtor de topologias para definir os servidores que você deseja implantar em sua Skype para a topologia de servidor de negócios.

**Para abrir o Skype para o construtor de topologias do Business Server projetar a topologia**

1. Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    > [!NOTE]
    > Você pode definir uma topologia usando uma conta que seja membro do grupo de usuários local, mas para ler, publicar ou habilitar uma topologia, o que é necessário para instalar o Skype para Business Server em um servidor, você deve usar uma conta que seja membro do grupo Administradores de domínio e th grupo RTCUniversalServerAdmins de f e que tem permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivos que você pretende usar para o repositório de arquivos de arquivamento para que o construtor de topologias consiga configurar o (de lista de controle de acesso discricionário necessários DACLs), ou uma conta com direitos de usuário equivalentes.
 
2. Inicie o construtor de topologia: Clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique **Skype para o construtor de topologia de servidor de negócios**.

## <a name="skype-for-business-server-control-panel"></a>Painel de Controle do Skype for Business Server 

Use um dos seguintes procedimentos para abrir o Skype para painel de controle do Business Server gerenciar a configuração dos servidores, usuários, clientes e dispositivos no seu ambiente.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa do Skype para painel de controle do servidor de negócios. Você pode usar outras funções de fazer logon para o Skype para painel de controle do Business Server realizar tarefas administrativas específicas, varia, dependendo da tarefa que precisam ser executadas. Por exemplo, você pode usar a função CSArchivingAdministrator para administrar o arquivamento no Skype para painel de controle do servidor de negócios. Para obter detalhes sobre funções, consulte [Planejando o controle de acesso baseado em função](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obter detalhes sobre as funções que você pode usar para realizar uma tarefa específica, consulte a documentação referente à tarefa. 

**Para abrir o Skype para painel de controle do Business Server a partir de qualquer computador dentro do firewall da organização**

1. Usando uma conta de usuário atribuída à função CsAdministrator ou outra função que possui direitos de usuário apropriados e permissões para a tarefa a ser executada, faça logon em qualquer computador em sua implantação interna com uma resolução de tela mínima de 1024 x 768.

    > [!IMPORTANT]
    > Se você tiver configurado um localizador de recursos uniforme simples de administração (URL), você pode acessar o Skype para painel de controle do Business Server a partir de um navegador da Internet que está sendo executado em qualquer computador dentro do firewall da organização. Para obter detalhes sobre como configurar a URL simples de administração, consulte o [guia de planejamento para URLs simples](https://technet.microsoft.com/en-us/library/gg398287(v=ocs.15).aspx) e [Editar ou configurar URLs simples](https://technet.microsoft.com/en-us/library/gg398063(v=ocs.15).aspx). 

2. Abra uma janela do navegador e insira a URL do administrador configurados para sua organização.

**Para abrir o Skype para painel de controle do Business Server em um computador executando o Skype para Business Server**

1. Usando uma conta de usuário que seja membro da função CsAdministrator ou outra função que possui direitos de usuário apropriados e permissões para a tarefa a ser executada, faça logon em um computador no qual você instalou Skype para Business Server ou, no mínimo , o Skype para ferramentas administrativas do servidor de negócios. Para definir configurações, o computador deve ter uma resolução de tela mínima de 1024 x 768.
2. Inicie o Skype para painel de controle do Business Server: clique em **Iniciar**, clique em **Todos os programas**, aponte para **Ferramentas administrativas**, aponte para **Skype para Business Server**e clique em **Skype para painel de controle do Business Server**.

## <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Serverl 

Use o procedimento a seguir para abrir o Skype do Shell de gerenciamento de servidor de negócios administrar servidores, usuários, clientes e dispositivos no seu ambiente usando a linha de comando.

> [!NOTE]
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para executar qualquer tarefa do Skype do Shell de gerenciamento do servidor de negócios. Você pode fazer logon usando outras funções para executar tarefas administrativas específicas, dependendo da tarefa que precisam ser executadas. Por exemplo, você pode usar a função CSArchivingAdministrator para executar os cmdlets relacionados à administração de arquivamento. Para obter detalhes sobre funções, consulte [Planejando o controle de acesso baseado em função](https://technet.microsoft.com/en-us/library/gg425917(v=ocs.15).aspx). Para obter detalhes sobre as funções que você pode usar para executar um cmdlet específico, consulte a documentação para o cmdlet.<br/><br/>Você também pode executar certos cmdlets usando uma conta de usuário nos grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, dependendo do cmdlet. 

**Para abrir o Skype do Shell de gerenciamento do servidor de negócios**

Se você abrir uma janela do Windows PowerShell, em vez do Skype do Shell de gerenciamento do servidor de negócios, por padrão, você não pode executar o Skype para cmdlets do servidor de negócios. Para executar o Skype para cmdlets do servidor de negócios de dentro do Windows PowerShell, digite o seguinte no prompt de comando do Windows PowerShell:

`Import-Module Lync`

Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de Business**.