---
title: 'Lync Server 2013: remover uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b02da5927b6a33cabefd005a8f026ca65f99b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Remover uma regra de atualização de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Remover uma regra de atualização de dispositivo a retira permanentemente da fila de atualização do dispositivo.

Remover uma regra é diferente de desinstalar uma atualização dos dispositivos na sua implantação ou de seus dispositivos de teste. Para desinstalar uma atualização aprovada da sua implantação, *restaure* a regra de atualização de dispositivo. Para obter detalhes, consulte [Restore a Device Update Rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Para desinstalar uma atualização que você não aprovou dos dispositivos de teste, *redefina* -a. Para obter detalhes, consulte [Reset a Device Update Rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

Você pode remover uma regra de atualização de dispositivo usando o painel de controle do Lync Server ou o Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Para remover as regras de atualização de dispositivo usando o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **atualização de dispositivo** .

4.  Na página **atualização de dispositivo** , execute um dos seguintes procedimentos:
    
      - Para remover uma regra, selecione a regra que você deseja excluir.
    
      - Para remover todas as regras, clique no menu **Editar** e, em seguida, clique em **selecionar tudo**.

5.  Clique em **Editar**e em **excluir**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Removendo regras de atualização de dispositivo usando cmdlets do Windows PowerShell

As regras de atualização de dispositivo também podem ser removidas usando o Windows PowerShell e o cmdlet **Remove-CsDeviceUpdateRule** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Para remover uma regra de atualização de dispositivo único de um servidor

  - O comando a seguir remove a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 do servidor Web no atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Para remover todas as regras de atualização de dispositivo de um servidor

  - Este comando Remove todas as regras de atualização de dispositivo do servidor Web no atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Aprovar uma regra de atualização de dispositivo no Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

