---
title: 'Lync Server 2013: exibir atualizações de software para dispositivos em sua organização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7926c9c10ba30ed4683b1e05d6e22c4b817f502c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a>Exibir atualizações de software para dispositivos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Com o Lync Server 2013, você usa o serviço Web de atualização de dispositivo para exibir e gerenciar atualizações de software para os dispositivos de sua organização. Essas atualizações estão disponíveis em arquivos. cab (Cabinet) no site de suporte da Microsoft [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)em. Depois de baixar o arquivo. cab, execute o cmdlet **Import-CSDeviceUpdate** para importar as regras de atualização de dispositivo do arquivo. cab. Para obter detalhes sobre o cmdlet **Import-CSDeviceUpdate** , consulte [Import-CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) na documentação do Shell de gerenciamento do Lync Server.

<div>


> [!TIP]  
> Antes de implantar uma nova atualização em sua organização, verifique se ele funciona corretamente em um dispositivo de teste.



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a>Para exibir as atualizações de software para dispositivos UC

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  No site de suporte da Microsoft [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091)em, baixe o arquivo. cab para um local em um computador do Lync Server 2013 (por exemplo,\\C\\: atualiza UCUpdates. cab).

3.  Importe as regras de atualização de dispositivo do arquivo\\C\\: updates. cab do UCUpdates executando um dos seguintes cmdlets:
    
      - Se o arquivo. cab estiver localizado no mesmo computador que está executando o serviço a ser atualizado (serviço: Redmond-websvc-2), execute o seguinte cmdlet:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - Se o arquivo. cab estiver localizado em um computador diferente do que está executando o serviço a ser atualizado (serviço: Redmond-websvc-3), execute o seguinte cmdlet:
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

5.  Na barra de navegação esquerda, clique em **Cliente** e em **Atualização de Dispositivo**.

6.  Na página **Atualização de Dispositivo**, clique em uma atualização na lista e execute um dos seguintes procedimentos:
    
      - **Cancelar uma atualização pendente.** Para impedir que a atualização selecionada seja implantada nos dispositivos de sua organização, clique no menu **Ação** e clique em **Cancelar atualizações pendentes**.
    
      - **Aprovar uma atualização.** Para permitir que a atualização selecionada seja implantada em dispositivos de sua organização, clique no menu **Ação** e, em seguida, clique **Aprovar**.
    
      - **Restaurar uma atualização.** Para permitir que uma atualização aprovada anteriormente seja implantada nos dispositivos de sua organização, clique no menu **Ação** e, em seguida, clique **Restaurar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

