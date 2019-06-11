---
title: 'Lync Server 2013: modificar as configurações dos arquivos de log de atualização do dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37002e1043f990ae1e726301b9c720af35556201
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826882"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Modificar as configurações dos arquivos de log de atualização de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Você pode alterar as configurações de como as informações de atualização do dispositivo são registradas em sua organização usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server. A tabela a seguir mostra quais configurações podem ser modificadas e quais ferramentas você usa para modificar as configurações.

As configurações de log podem ser alteradas e aplicadas globalmente ou por site.


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
<td><p>O tamanho máximo (em bytes) de um arquivo de log</p></td>
<td><p>Painel de Controle do Lync Server</p>
<p>or</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="even">
<td><p>A quantidade máxima de informações (em bytes) que podem ser mantidas no cache</p></td>
<td><p>Painel de Controle do Lync Server</p>
<p>or</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Com que frequência (em minutos) gravar informações armazenadas em cache no arquivo de log</p></td>
<td><p>Painel de Controle do Lync Server</p>
<p>or</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="even">
<td><p>Quanto tempo (em dias) para manter os arquivos de log</p></td>
<td><p>Painel de Controle do Lync Server</p>
<p>or</p>
<p>Shell de Gerenciamento do Lync Server</p></td>
</tr>
<tr class="odd">
<td><p>Quando (hora do dia) verificar se há arquivos expirados que devem ser excluídos</p></td>
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

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Para alterar as configurações de registro em log usando o painel de controle do Lync Server

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique em **configuração do log do dispositivo**.

3.  Na página **configuração de log do dispositivo** , clique duas vezes na configuração que você deseja alterar.

4.  Na caixa de diálogo **Editar configuração do log** , altere qualquer uma das seguintes configurações:
    
      - **Tamanho máximo de arquivo (bytes)**   especifica o tamanho máximo que um arquivo de log pode ficar antes de ser limpo. O padrão é 1.024.000 bytes (1 MB).
    
      - **Tamanho máximo de cache (bytes)**   especifica a quantidade máxima de informações (em bytes) que podem ser mantidas no cache de arquivos de log antes que o cache seja limpo e os dados sejam gravados em um arquivo de log. O padrão é 512.000 bytes (0,5 MB).
    
      - **Número de minutos para liberar o cache (1-60)**   indica a frequência com que as informações armazenadas no cache do arquivo de log são gravadas no arquivo de log real. Depois que os dados são registrados, o cache é limpo. O padrão é cinco minutos.
    
      - **Número de dias para manter os arquivos de log (1-365)**   especifica o número de dias durante os quais os arquivos de log são mantidos antes de serem limpos. O padrão é 10 dias.

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Alterando as configurações de log usando cmdlets do Windows PowerShell

As configurações de arquivo de log de atualização de dispositivo podem ser modificadas usando o Windows PowerShell e o cmdlet **set-CsDeviceUpdateConfiguration** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Microsoft Lync Server 2010 usando o PowerShell remoto" em.



</div>

Os exemplos a seguir mostram algumas maneiras pelas quais você pode usar **set-CsDeviceUpdateConfiguration** para modificar as configurações.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>Para modificar o tamanho máximo do arquivo de log e o intervalo de limpeza do log

  - O comando a seguir modifica as configurações do log de atualização de dispositivo aplicadas ao site Redmond. Neste exemplo, o tamanho máximo do arquivo de log é definido como 204800 bytes, e o intervalo de limpeza do log é definido como 14 dias.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>Para modificar a hora de limpeza do log do dia

  - Esse comando define o tempo de limpeza do log para o site Redmond para 3:00 AM.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

Para obter detalhes, consulte o tópico da ajuda para o cmdlet [set-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

