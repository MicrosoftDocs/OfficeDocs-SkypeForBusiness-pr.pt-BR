---
title: 'Lync Server 2013: abrir ferramentas administrativas do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a>Abrir ferramentas administrativas do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-28_

Você pode usar os procedimentos deste tópico para abrir ferramentas administrativas para implantar, configurar ou solucionar problemas na sua topologia do Lync Server 2013.

  - Assistente de Implantação

  - Construtor de Topologias

  - Painel de Controle do Lync Server

  - Shell de Gerenciamento do Lync Server

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a>Assistente de Implantação

Use o procedimento a seguir para iniciar o assistente de implantação localmente para adicionar ou remover arquivos de componentes do Lync Server 2013.

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a>Para iniciar o assistente de implantação do Lync Server 2013

1.  Faça logon no computador em que o assistente de implantação do Lync Server está instalado como membro do grupo Domain admins e do grupo RTCUniversalServerAdmins.

2.  Clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Assistente de implantação do Lync Server**.

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a>Construtor de Topologias

Use o procedimento a seguir para abrir o construtor de topologias e definir os servidores que você deseja implantar na sua topologia do Lync Server 2013.

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a>Para abrir o construtor de topologia do Lync Server 2013 para desenhar a topologia

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.
    
    <div>
    

    > [!NOTE]  
    > Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas para ler, publicar ou habilitar uma topologia, o que é necessário para instalar o Lync Server 2013 em um servidor, você deve usar uma conta que seja membro do grupo Administradores do domínio e do RTCUniv ersalServerAdmins grupo, e que tem permissões de controle total (ou seja, ler, gravar e modificar) no compartilhamento de arquivo que você vai usar para o repositório de arquivos de arquivamento para que o construtor de topologia possa configurar a lista de controle de acesso discricional (DACLs) necessária, ou uma conta com direitos de usuário equivalentes.

    
    </div>

2.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a>Painel de Controle do Lync Server 2013

Use um dos procedimentos a seguir para abrir o painel de controle do Lync Server 2013 para gerenciar a configuração de servidores, usuários, clientes e dispositivos em seu ambiente.

<div>


> [!NOTE]  
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para realizar qualquer tarefa no painel de controle do Lync Server 2013. Você pode usar outras funções para fazer logon no painel de controle do Lync Server 2013 para executar tarefas de administração específicas, dependendo da tarefa que você precisa executar. Por exemplo, você pode usar o CSArchivingAdministrator para administrar o arquivamento no painel de controle do Lync Server 2013. Para obter detalhes sobre as funções, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejar o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento. Para obter detalhes sobre as funções que você pode usar para realizar uma tarefa específica, consulte a documentação da tarefa.



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a>Para abrir o painel de controle do Lync Server 2013 em qualquer computador dentro do firewall da sua organização

1.  Em uma conta de usuário que é atribuída à função CsAdministrator ou outra função que tenha direitos e permissões de usuário apropriados para a tarefa ser realizada, faça logon em qualquer computador em sua implantação interna com uma resolução de tela mínima de 1024 x 768.
    
    <div>
    

    > [!IMPORTANT]  
    > Se você configurou um URL (Uniform Resource Locator) simples de administração, pode acessar o painel de controle do Lync Server 2013 em um navegador da Internet que esteja em execução em qualquer computador dentro do firewall da sua organização. Para obter detalhes sobre como configurar a URL simples de administração, consulte <A href="lync-server-2013-planning-for-simple-urls.md">planejando URLs simples no Lync server 2013</A> na documentação de planejamento e <A href="lync-server-2013-edit-or-configure-simple-urls.md">edite ou configure URLs simples no Lync Server 2013</A> na documentação de implantação.

    
    </div>

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração configurada para sua organização.

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a>Para abrir o painel de controle do Lync Server 2013 em um computador com o Lync Server 2013

1.  A partir de uma conta de usuário que seja membro da função CsAdministrator ou outra função que tenha direitos e permissões de usuário apropriados para a tarefa ser realizada, faça logon em um computador no qual você instalou o Lync Server 2013 ou, no mínimo, o Lync Server 2013 administração ferramentas de que. Para definir as configurações, o computador deve ter uma resolução de tela mínima de 1024 x 768.

2.  Inicie o painel de controle do Lync Server 2013: clique em **Iniciar**, em **todos os programas**, aponte para **Ferramentas administrativas**, aponte para **Microsoft Lync Server 2013**e clique em **painel de controle do Lync Server 2013**.

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a>Shell de Gerenciamento do Lync Server 2013

Use o procedimento a seguir para abrir o Shell de gerenciamento do Lync Server 2013 para administrar servidores, usuários, clientes e dispositivos em seu ambiente usando a linha de comando.

<div>


> [!NOTE]  
> Você pode usar uma conta de usuário atribuída à função CsAdministrator para realizar qualquer tarefa no Shell de gerenciamento do Lync Server 2013. Você pode fazer logon usando outras funções para executar tarefas específicas de administração, dependendo da tarefa que você precisa executar. Por exemplo, você pode usar CSArchivingAdministrator para executar cmdlets relacionados à administração do arquivamento. Para obter detalhes sobre as funções, consulte <A href="lync-server-2013-planning-for-role-based-access-control.md">planejar o controle de acesso baseado em função no Lync Server 2013</A> na documentação de planejamento. Para obter detalhes sobre as funções que você pode usar para executar um cmdlet específico, consulte a documentação do cmdlet.<BR>Você também pode executar determinados cmdlets usando uma conta de usuário nos grupos RTCUniversalServerAdmins, RTCUniversalUserAdmins ou RTCUniversalReadOnlyAdmins, dependendo do cmdlet.



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a>Para abrir o Shell de gerenciamento do Lync Server 2013

  - Se você abrir uma janela do Windows PowerShell em vez do Shell de gerenciamento do Lync Server 2013, por padrão, não poderá executar os cmdlets do Lync Server 2013. Para executar os cmdlets do Lync Server 2013 dentro do Windows PowerShell, digite o seguinte no prompt de comando do Windows PowerShell:
    
    `Import-Module Lync`

  - Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Instalar ferramentas administrativas do Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md)  


[Ferramentas administrativas do Lync Server 2013](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

