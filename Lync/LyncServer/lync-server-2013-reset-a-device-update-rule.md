---
title: 'Lync Server 2013: redefinir uma regra de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aa5bd589a6368e99401f2f84d702756d595f9be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214927"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Redefinir uma regra de atualização de dispositivo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Se você não gostar da forma como uma atualização funciona em seus dispositivos de teste, é possível redefinir a regra de atualização de dispositivo, que remove o status pendente da regra e desinstala a atualização dos dispositivos de teste.

Você pode remover uma regra de atualização de dispositivo usando o painel de controle do Lync Server ou o Windows PowerShell.

<div>


> [!NOTE]  
> Para desinstalar uma regra que você já aprovou (isto é, distribuída), restaure-a. Para obter detalhes, consulte <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update Rule in Lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Para redefinir uma regra de atualização de dispositivo usando o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **atualização de dispositivo** .

4.  Na página **atualização de dispositivo** , execute um dos seguintes procedimentos:
    
      - Para redefinir uma regra, selecione a regra que você deseja redefinir.
    
      - Para redefinir todas as regras, no menu **Editar** , clique em **selecionar tudo**.
    
      - Para redefinir todas as regras para uma marca, use o menu coluna **da marca** .

5.  Clique em **ação**e, em seguida, clique em **cancelar atualizações pendentes**.
    
    <div>
    

    > [!TIP]  
    > Se você tiver certeza de que nunca vai querer distribuir as regras de atualização de dispositivo que você cancelou, convém excluí-las. Para obter detalhes, consulte <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update Rule in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Redefinindo uma regra de atualização de dispositivo usando os cmdlets do Windows PowerShell

As regras de atualização de dispositivo também podem ser redefinidas usando o Windows PowerShell e o cmdlet **Reset-CsDeviceUpdateRule** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>2010 using Remote PowerShell" em.



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>Para redefinir uma regra de atualização de dispositivo específica em um servidor

  - O comando a seguir redefine a regra de atualização de dispositivo d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 no servidor Web atl-cs-001.litwareinc.com:
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>Para redefinir todas as regras de atualização de dispositivo em um servidor

  - Este comando redefine todas as regras de atualização de dispositivo no servidor Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>Para redefinir todas as regras de atualização de dispositivos que têm uma marca específica

  - Neste exemplo, todas as atualizações de dispositivo em toda a organização que têm uma marca igual à Microsoft são redefinidas:
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

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

