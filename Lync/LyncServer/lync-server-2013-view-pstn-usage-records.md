---
title: 'Lync Server 2013: exibir registros de uso de PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9042eca0b8ddd1f04b34c3fea0b57dd6235b69c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Exibir registros de uso de PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Um registro de uso de rede telefônica pública comutada (PSTN) especifica uma classe de chamada (como interna, local ou longa distância) que pode ser feita por vários usuários ou grupos de usuários em uma organização. Para obter detalhes, consulte [registros de uso PSTN no Lync Server 2013](lync-server-2013-pstn-usage-records.md) na documentação de planejamento.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Para exibir um registro de uso PSTN usando o painel de controle do Lync Server

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de voz** e em **Uso do PSTN**.

4.  Na página **Uso do PSTN**, destaque o registro de uso PSTN que você deseja exibir, clique em **Editar** e em **Mostrar detalhes**.
    
    <div>
    

    > [!NOTE]  
    > Uma página somente leitura do registro de uso PSTN selecionado mostra as rotas associadas e as políticas de voz associadas.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Exibir informações de uso de PSTN usando cmdlets do Windows PowerShell

Você também pode exibir usos de PSTN usando o Windows PowerShell e o cmdlet **Get-CsPstnUsage** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Para exibir informações de uso de PSTN usando cmdlets do Windows PowerShell

  - Para ver as informações sobre todos os usos de PSTN, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsPstnUsage
    
    Este comando retorna informações semelhantes para o seguinte:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

Para obter detalhes, consulte [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

