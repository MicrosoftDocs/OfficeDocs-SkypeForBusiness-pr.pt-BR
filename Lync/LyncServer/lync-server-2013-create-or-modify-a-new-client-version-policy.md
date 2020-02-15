---
title: 'Lync Server 2013: criar ou modificar uma nova política de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8464e64c3de1e85f823bb3e1b5dac4dd1837effd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Criar ou modificar uma nova política de versão do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Você pode usar políticas de versão do cliente para especificar as versões dos clientes que são compatíveis com o seu ambiente. O uso do controle de versão do cliente pode ajudar a reduzir os custos associados ao suporte a várias versões de cliente. Também pode melhorar a experiência geral do usuário, porque quando as versões anteriores e posteriores dos clientes interagem, os recursos disponíveis podem ser limitados pela versão anterior do cliente. Você pode criar ou modificar políticas de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Para criar ou modificar políticas de versão do cliente usando o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes**.
    
    <div>
    

    > [!NOTE]  
    > A guia <STRONG>Política de Versões de Clientes</STRONG> está selecionada por padrão.

    
    </div>

4.  Na página **política de versão do cliente** , execute um dos seguintes procedimentos:
    
      - Para criar uma política de versão de cliente, clique em **novo**, selecione **política de site**, **política de pool**ou **política de usuário**e clique em **OK**.
    
      - Para modificar a política global ou outra política de versão de cliente existente, selecione a política, clique em **Editar**e em **Mostrar detalhes**.

5.  Na página **Editar política de versão do cliente** , crie ou modifique regras, conforme descrito em [criar ou modificar uma nova regra de política de versão do cliente no Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Criando ou modificando políticas de versão do cliente usando cmdlets do Windows PowerShell

Você pode criar políticas de versão do cliente usando o cmdlet **New-CsClientVersionPolicy** e modificá-las usando o cmdlet **set-CsClientVersionPolicy** . Esses cmdlets podem ser executados a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>Para criar uma nova política de versão de cliente com escopo de site

  - O comando a seguir cria uma nova política de versão do cliente aplicada ao site de Redmond. Como nenhum parâmetro adicional é especificado, a nova política usará as configurações de versão do cliente padrão.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>Para criar uma nova política de versão do cliente por usuário

  - Para criar uma política por usuário, use um comando semelhante ao seguinte:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Para obter detalhes, consulte os tópicos de ajuda para o cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) e o cmdlet [set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

