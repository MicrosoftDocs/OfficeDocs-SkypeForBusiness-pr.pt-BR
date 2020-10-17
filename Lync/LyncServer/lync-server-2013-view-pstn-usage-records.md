---
title: 'Lync Server 2013: exibir registros de uso de PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 558efe06fb8a91a4a1f923b004756b5791e4367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518438"
---
# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Exibir registros de uso de PSTN no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

Um registro de uso de PSTN (rede telefônica pública comutada) especifica uma classe de chamada (como interna, local ou de longa distância) que pode ser feita por vários usuários ou grupos de usuários em uma organização. Para obter detalhes, consulte [PSTN Usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) na documentação de planejamento.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Para exibir um registro de uso de PSTN usando o painel de controle do Lync Server

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de voz** e clique em uso de **PSTN**.

4.  Na página **uso de PSTN** , realce o registro de uso de PSTN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes**.
    
    <div>
    

    > [!NOTE]  
    > Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Exibindo informações de uso de PSTN usando cmdlets do Windows PowerShell

Você também pode exibir usos de PSTN usando o Windows PowerShell e o cmdlet **Get-CsPstnUsage** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Para exibir informações de uso de PSTN usando cmdlets do Windows PowerShell

  - Para exibir informações sobre todos os seus usos de PSTN, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsPstnUsage
    
    Esse comando retornará informações parecidas com:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

Para obter detalhes, consulte [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

