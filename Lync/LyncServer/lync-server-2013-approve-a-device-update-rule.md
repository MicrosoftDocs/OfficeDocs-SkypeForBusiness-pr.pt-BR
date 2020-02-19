---
title: 'Lync Server 2013: aprovar uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21eecf879eb9a256d15efd55281f60274a26658b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134517"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Aprovar uma regra de atualização de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Após a importação de uma regra de atualização de dispositivo, ela é instalada em seus dispositivos de teste. Se o teste for bem-sucedido e você quiser distribuir a atualização para sua organização, aprove-a usando o painel de controle do Lync Server ou o Windows PowerShell.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Para aprovar uma regra de atualização de dispositivo usando o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na página **atualização de dispositivo** , execute um dos seguintes procedimentos:
    
      - Para aprovar uma regra, selecione essa regra.
    
      - Para aprovar todas as regras, clique em **Editar**e, em seguida, clique em **selecionar tudo**.

4.  Clique em **ação**e em **aprovar**.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Aprovar uma regra de atualização de dispositivo usando cmdlets do Windows PowerShell

As regras de atualização de dispositivo também podem ser aprovadas usando o Windows PowerShell e o cmdlet **Approve-CsDeviceUpdateRule** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>Para aprovar uma única regra de atualização de dispositivo

  - O comando a seguir aprova a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 encontrada no servidor Web atl-cs-001.litwareinc.com:
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>Para aprovar várias regras de atualização de dispositivo

  - Este comando aprova todas as regras de atualização de dispositivo para dispositivos da marca Microsoft:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .

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

