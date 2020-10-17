---
title: 'Lync Server 2013: remover arquivos de atualização do dispositivo não associados a um dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a21ef2e9dae4c09ce975bd048f628930cd3dfeda
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536438"
---
# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a>Remover arquivos de atualização de dispositivo não associados a um dispositivo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-20_

Cada vez que novas atualizações de dispositivos são carregadas para o sistema, uma regra de atualização de dispositivo correspondente é criada. Por padrão, essas novas regras de atualização de dispositivo são atribuídas ao estado pendente. Isso significa que as regras podem ser baixadas e instaladas em dispositivos de teste, mas não em dispositivos de produção, que permitem testar as atualizações antes de disponibilizá-las aos usuários. Com base nos testes, você pode aceitar e implantar ou rejeitar e excluir a atualização. Quando você rejeita uma atualização, a atualização do dispositivo é desassociada da regra de atualização do dispositivo.

<div>


Arquivos de atualização de dispositivos que não estão mais associados a um dispositivo podem ser removidos usando o Windows PowerShell e o cmdlet **Clear-CsDeviceUpdateFile** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .



</div>

<div>


  - Por exemplo, o comando a seguir remove todas as regras de atualização de dispositivo no servidor Web atl-cs-001.litwareinc.com que não estão mais associadas a um dispositivo:
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

