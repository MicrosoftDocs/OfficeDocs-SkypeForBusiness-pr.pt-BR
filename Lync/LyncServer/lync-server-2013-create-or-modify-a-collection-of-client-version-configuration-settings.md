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
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Criar ou modificar um conjunto de definições de configuração de versão do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

As configurações da versão cliente são usadas para ativar ou desativar o controle de versão do cliente. A configuração de versão do cliente global é instalada com o Lync Server e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Você também pode configurar as definições de configuração de versão do cliente para sites individuais. Você pode criar ou modificar as definições de configuração de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.

<div>


> [!NOTE]
> Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Para criar ou modificar as definições de configuração de versão do cliente usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de versão do cliente** .

4.  Na página **configuração de versão do cliente** , faça o seguinte:
    
      - Para criar uma nova configuração, clique em **novo**, selecione um site, clique em **OK** nome e atualize as configurações.
    
      - Para modificar uma configuração, selecione a configuração, clique em **Editar**, clique em **Mostrar detalhes**e faça alterações nas configurações.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando ou modificando definições de configuração de versão do cliente usando cmdlets do Windows PowerShell

Você pode criar definições de configuração de versão do cliente usando o cmdlet **New-CsClientVersionConfiguration** e modificá-las usando o cmdlet **set-CsClientVersionConfiguration** . Esses cmdlets podem ser executados no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Para criar um novo conjunto de definições de configuração de versão do cliente

  - O comando a seguir cria uma nova coleção de definições de configuração de versão do cliente aplicada ao site Redmond. Neste exemplo, o controle de versão do cliente está desabilitado para o site Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Para habilitar o controle de versão do cliente para um site

  - Esse comando habilita o controle de versão do cliente para o site Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Para desabilitar o controle de versão do cliente em toda a organização

  - Neste exemplo, o controle de versão do cliente está desabilitado para todas as definições de configuração de versão do cliente em uso na organização.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Para obter detalhes, consulte o tópico da ajuda para os cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) e [set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

