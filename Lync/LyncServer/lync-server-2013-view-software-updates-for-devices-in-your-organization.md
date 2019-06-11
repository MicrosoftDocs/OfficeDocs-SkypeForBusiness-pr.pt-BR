---
title: 'Lync Server 2013: exibir atualizações de software para dispositivos em sua organização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Exibir atualizações de software para dispositivos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Com o Lync Server 2013, você usa o serviço Web de atualização de dispositivo para exibir e gerenciar atualizações de software para os dispositivos da sua organização. Essas atualizações estão disponíveis em arquivos. cab (Cabinet) a partir do website de suporte [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)da Microsoft em. Depois de baixar o arquivo. cab, execute o cmdlet **Import-CSDeviceUpdate** para importar as regras de atualização de dispositivo do arquivo. cab. Para obter detalhes sobre o cmdlet **Import-CSDeviceUpdate** , consulte [importar-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) na documentação do Shell de gerenciamento do Lync Server.

<div>


> [!TIP]  
> Antes de implantar uma nova atualização em sua organização, verifique se ela funciona corretamente em um dispositivo de teste.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Para exibir atualizações de software para dispositivos de comunicação unificada

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  No site de suporte da Microsoft [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)em, baixe o arquivo. cab para um local em um computador com o Lync Server 2013 (por exemplo\\,\\C: atualiza UCUpdates. cab).

3.  Importe as regras de atualização de dispositivo do arquivo\\C\\: updates UCUpdates. cab executando um dos seguintes cmdlets:
    
      - Se o arquivo. cab estiver localizado no mesmo computador que está executando o serviço a ser atualizado (serviço: Redmond-websvc-2), execute o seguinte cmdlet:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Se o arquivo. cab estiver localizado em um computador diferente do que o que está executando o serviço a ser atualizado (serviço: Redmond-websvc-3), execute o seguinte cmdlet:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Na barra de navegação à esquerda, clique em **clientes**e em **atualização de dispositivo**.

6.  Na página **atualização do dispositivo** , clique em uma atualização na lista e siga um destes procedimentos:
    
      - **Cancelar uma atualização pendente.** Para impedir que a atualização selecionada seja implantada nos dispositivos da sua organização, clique no menu **ação** e, em seguida, clique em **cancelar atualizações pendentes**.
    
      - **Aprove uma atualização.** Para permitir que a atualização selecionada seja implantada nos dispositivos da sua organização, clique no menu **ação** e, em seguida, clique em **aprovar**.
    
      - **Restaurar uma atualização.** Para permitir que uma atualização aprovada anteriormente seja implantada nos dispositivos da sua organização, clique no menu **ação** e, em seguida, clique em **restaurar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

