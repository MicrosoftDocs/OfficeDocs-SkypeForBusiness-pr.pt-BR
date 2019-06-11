---
title: 'Lync Server 2013: aprovar uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa560be6b8c341310c4831277902dab6f2e5552c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Aprovar uma regra de atualização de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Depois de importar uma regra de atualização de dispositivo, ela é instalada em seus dispositivos de teste. Se o teste for bem-sucedido e você quiser implantar a atualização em sua organização, aprove-a usando o painel de controle do Lync Server ou o Windows PowerShell.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Para aprovar uma regra de atualização de dispositivo usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na página **atualização do dispositivo** , siga um destes procedimentos:
    
      - Para aprovar uma regra, selecione essa regra.
    
      - Para aprovar todas as regras, clique em **Editar**e, em seguida, clique em **selecionar tudo**.

4.  Clique em **ação**e, em seguida, clique em **aprovar**.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Aprovando uma regra de atualização de dispositivo usando cmdlets do Windows PowerShell

As regras de atualização de dispositivo também podem ser aprovadas usando o Windows PowerShell e o cmdlet **Approve-CsDeviceUpdateRule** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Microsoft Lync Server 2010 usando o PowerShell remoto" em.



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>Para aprovar uma única regra de atualização de dispositivo

  - O comando a seguir aprova a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 encontrada na atl-cs-001.litwareinc.com do servidor Web:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>Para aprovar várias regras de atualização de dispositivo

  - Esse comando aprova todas as regras de atualização de dispositivos para dispositivos com marca Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Importar regras de atualização de dispositivo no Lync Server 2013](lync-server-2013-import-device-update-rules.md)  
[Restaurar uma regra de atualização de dispositivo no Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

