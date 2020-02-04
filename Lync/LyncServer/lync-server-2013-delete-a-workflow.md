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
ms.openlocfilehash: 4ed32780e23cce82027271e74a89fb87e194cc4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Excluir um fluxo de trabalho no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Use um dos procedimentos a seguir para excluir um fluxo de trabalho.

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Para usar o painel de controle do Lync Server excluir um fluxo de trabalho

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Grupos de Resposta** e em **Fluxo de Trabalho**.

4.  Na página **Fluxo de Trabalho**, clique em **Criar ou editar um fluxo de trabalho**.

5.  No campo **selecionar um serviço** de pesquisa, digite parte ou todo o nome do serviço **ApplicationServer** que hospeda o fluxo de trabalho que você deseja excluir.

6.  Na lista de serviços, clique no serviço desejado e, em seguida, clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > A página da ferramenta de configuração de grupo de resposta é aberta. Você também pode abrir a página da Web da ferramenta de configuração de grupo de resposta diretamente de um navegador da web conectando-se à <STRONG>&lt;https://webPoolFqdn&gt;/RgsConfig</STRONG>.

    
    </div>

7.  Em **gerenciar um fluxo de trabalho existente**, localize o fluxo de trabalho que você deseja excluir e, em seguida, em **ação**, clique em **excluir**.

8.  Clique em **Sim**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Para usar o Windows PowerShell para excluir um fluxo de trabalho

1.  Faça logon como um membro do grupo RTCUniversalServerAdmins ou como um membro de uma das funções administrativas predefinidas que oferecem suporte ao Grupo de Resposta.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

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

