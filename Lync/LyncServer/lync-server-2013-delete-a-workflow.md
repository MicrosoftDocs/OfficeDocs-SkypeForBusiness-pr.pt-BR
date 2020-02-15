---
title: 'Lync Server 2013: excluir um fluxo de trabalho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91326023357df0903ab506217c6abb53babcdf66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Excluir um fluxo de trabalho no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Use um dos procedimentos a seguir para excluir um fluxo de trabalho.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Para usar o painel de controle do Lync Server excluir um fluxo de trabalho

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4.  Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5.  No campo de pesquisa **Selecionar um Serviço**, insira parte ou todo o nome do serviço de **ApplicationServer** que hospeda o fluxo de trabalho que você quer excluir.

6.  Na lista de serviços, clique no serviço que deseja e em **OK**.
    
    <div>
    

    > [!NOTE]  
    > A página da ferramenta de configuração do grupo de resposta é aberta. Você também pode abrir a página da ferramenta de configuração do grupo de resposta diretamente de um navegador da web conectando-se ao <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>.

    
    </div>

7.  Sob **Gerenciar um Fluxo de Trabalho Existente**, localize o fluxo de trabalho que você quer excluir e, sob **Ação**, clique em **Excluir**.

8.  Clique em **Sim**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Para usar o Windows PowerShell para excluir um fluxo de trabalho

1.  Faça logon como membro do grupo RTCUniversalServerAdmins ou como membro de uma das funções administrativas predefinidas que dão suporte ao grupo de resposta.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Na linha de comando, execute:
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    Por exemplo:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

