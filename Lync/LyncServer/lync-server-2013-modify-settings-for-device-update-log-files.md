---
title: 'Lync Server 2013: modificar configurações para arquivos de log de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2118cac5e8380d27e8f273f5cb469efdbddfd9bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534328"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Modificar configurações para arquivos de log de atualização de dispositivo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Você pode alterar as configurações de como as informações de atualização de dispositivo são registradas em sua organização usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server. A tabela a seguir mostra quais configurações podem ser modificadas e quais ferramentas você usa para modificar as configurações.

As configurações de log podem ser alteradas e aplicadas globalmente, ou por site.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para alterar</th>
<th>Usar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>O tamanho máximo (em bytes) para um arquivo de log</p></td>
<td><p>Painel de controle do Lync Server</p>
<p>-ou-</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="even">
<td><p>A quantidade máxima de informações (em bytes) que podem ser mantidas no cache</p></td>
<td><p>Painel de controle do Lync Server</p>
<p>-ou-</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Frequência (em minutos) de gravação de informações armazenadas em cache no arquivo de log</p></td>
<td><p>Painel de controle do Lync Server</p>
<p>-ou-</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Quanto tempo (em dias) para manter os arquivos de log</p></td>
<td><p>Painel de controle do Lync Server</p>
<p>-ou-</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Quando (hora do dia) para verificar se há arquivos expirados que devem ser excluídos</p></td>
<td><p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Quais extensões de arquivo de log permitir</p></td>
<td><p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Quais tipos de arquivo de log manter</p></td>
<td><p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Para alterar as configurações de log usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação à esquerda, clique em **clientes**e em **configuração de log de dispositivo**.

3.  Na página **configuração do log do dispositivo** , clique duas vezes na configuração que você deseja alterar.

4.  Na caixa de diálogo **Editar configuração de log** , altere qualquer uma das seguintes configurações:
    
      - **Tamanho máximo do arquivo (bytes)**     Especifica o tamanho máximo que um arquivo de log pode ser antes de ser removido. O padrão é 1.024.000 bytes (1 MB).
    
      - **Tamanho máximo do cache (bytes)**     Especifica a quantidade máxima de informações (em bytes) que podem ser mantidas no cache de arquivos de log antes que o cache seja apagado e os dados são gravados em um arquivo de log. O padrão é 512.000 bytes (0,5 MB).
    
      - **Número de minutos para liberar o cache (1-60)**     Indica com que frequência as informações armazenadas no cache de arquivos de log são gravadas no arquivo de log real. Depois que os dados são registrados, o cache é limpo. O padrão é cinco minutos.
    
      - **Número de dias para manter arquivos de log (1-365)**     Especifica o número de dias que os arquivos de log são mantidos antes de serem limpos. O padrão é 10 dias.

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Alterar as configurações de log usando cmdlets do Windows PowerShell

As configurações de arquivo de log de atualização de dispositivo podem ser modificadas usando o Windows PowerShell e o cmdlet **set-CsDeviceUpdateConfiguration** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

Os exemplos a seguir mostram algumas das maneiras que você pode usar **set-CsDeviceUpdateConfiguration** para modificar as configurações.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Para modificar o tamanho máximo do arquivo de log e o intervalo de limpeza de log

  - O comando a seguir modifica as configurações de log de atualização de dispositivo aplicadas ao site Redmond. Neste exemplo, o tamanho máximo do arquivo de log é definido como 204800 bytes e o intervalo de limpeza do log é definido como 14 dias.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Para modificar o horário de limpeza do log do dia

  - Este comando define o tempo de limpeza do log para o site Redmond para 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

