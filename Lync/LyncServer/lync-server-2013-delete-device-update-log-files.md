---
title: 'Lync Server 2013: excluir arquivos de log de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Device Update log files
ms:assetid: 58d4097f-5bbf-4824-a04d-2a6555cd93c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994039(v=OCS.15)
ms:contentKeyID: 51803949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 685b3e34c0f2bd5392f71899564d0738e814b616
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-device-update-log-files-in-lync-server-2013"></a>Excluir arquivos de log de atualização de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

O serviço Web de atualização de dispositivo mantém uma ampla coleção de arquivos de log. Essa coleção inclui os logs de auditoria conduzidos pelo próprio serviço e arquivos de log carregados de dispositivos clientes. Para impedir que o servidor seja preenchido com logs do serviço Web de atualização de dispositivos, você provavelmente desejará desmarcá-lo de arquivos de log que já estão por um determinado número de dias. Defina esse número de dias com base na atividade de atualização e no número de dispositivos clientes em sua organização e usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server.

<div>

## <a name="to-clear-the-device-update-log-by-using-lync-server-control-panel"></a>Para limpar o log de atualização de dispositivo usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação à esquerda, clique em **clientes**e em **configuração de log de dispositivo**.

3.  Na página **configuração do log do dispositivo** , clique duas vezes na configuração que você deseja alterar.

4.  Na caixa de diálogo **Editar configuração de log** , em **número de dias para manter arquivos de log (1-365)**, especifique um número de dias.

5.  Clique em **Confirmar**. Todos os arquivos que estão no servidor por mais do que o número de dia especificado são excluídos. Essa configuração será aplicada a essa configuração até que você a altere.

</div>

<div>

## <a name="clearing-the-device-update-log-by-using-the-windows-powershell-cmdlets"></a>Limpando o log de atualização de dispositivo usando os cmdlets do Windows PowerShell

Você pode limpar logs de atualização de dispositivo usando o Windows PowerShell e o cmdlet **Clear-CsDeviceUpdateLog** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.



</div>

<div>

## <a name="to-clear-device-update-logs-on-one-server"></a>Para limpar logs de atualização de dispositivo em um servidor

  - O comando a seguir limpa o log de atualização do dispositivo no servidor Web atl-cs-001.litwareinc.com. Todas as entradas de log com mais de 10 dias (o valor especificado pelo parâmetro DaysBack) serão removidas do log.
    
        Clear-CsDeviceUpdateLog -Identity "service:WebServer:atl-cs-001.litwareinc.com" -DaysBack 10

</div>

<div>

## <a name="to-clear-all-device-update-logs"></a>Para limpar todos os logs de atualização de dispositivo

  - Este comando remove as entradas desatualizadas (neste exemplo, entradas com mais de 10 dias) de todos os logs de atualização de dispositivo atualmente em uso na organização.
    
        Get-CsService -WebServer | Foreach-Object {Clear-CsDeviceUpdateLog -Identity $_.Identity -DaysBack 10}

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Clear-CsDeviceUpdateLog](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateLog) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

