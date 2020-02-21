---
title: Criar ou modificar um conjunto de definições de configuração de versão do cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6851a332b0b2c33d769328a0656f206d5f7d271c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Criar ou modificar um conjunto de definições de configuração de versão do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão do cliente global é instalada com o Lync Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Você também pode definir as definições de configuração de versão do cliente para sites individuais. Você pode criar ou modificar definições de configuração de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.

<div>


> [!NOTE]
> Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Para criar ou modificar as definições de configuração de versão do cliente usando o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração da versão do cliente** .

4.  Na página **configuração de versão do cliente** , faça o seguinte:
    
      - Para criar uma nova configuração, clique em **novo**, selecione um site, clique em nome **OK** e atualize as configurações.
    
      - Para modificar uma configuração, selecione a configuração, clique em **Editar**, em **Mostrar detalhes**e faça alterações nas configurações.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando ou modificando definições de configuração de versão do cliente usando cmdlets do Windows PowerShell

Você pode criar definições de configuração de versão de cliente usando o cmdlet **New-CsClientVersionConfiguration** e modificá-las usando o cmdlet **set-CsClientVersionConfiguration** . Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Para criar um novo conjunto de definições de configuração de versão do cliente

  - O comando a seguir cria um novo conjunto de definições de configuração de versão do cliente aplicadas ao site Redmond. Neste exemplo, o controle de versão do cliente está desabilitado para o site de Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Para habilitar o controle de versão do cliente para um site

  - Este comando habilita o controle de versão do cliente para o site de Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Para desabilitar o controle de versão do cliente em toda a organização

  - Neste exemplo, o controle de versão do cliente está desabilitado para todas as definições de configuração de versão do cliente em uso na organização.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Para obter detalhes, consulte o tópico de ajuda para os cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) e [set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

