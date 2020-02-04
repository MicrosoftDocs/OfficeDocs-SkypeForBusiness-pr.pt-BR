---
title: 'Lync Server 2013: habilitar a qualidade da experiência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dbccfd145ad8143edab10f92a10901e626075e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Habilitar a qualidade de experiência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

A Qualidade de experiência (QoE) registra os dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nome de dispositivos, drivers, endereços IP e tipos de pontos de extremidade envolvidos nas chamadas e sessões. Para obter detalhes, consulte [planejando a monitoração no Lync Server 2013](lync-server-2013-planning-for-monitoring.md) na documentação de planejamento.

Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.

<div>


> [!NOTE]  
> Para habilitar a QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento. Para obter detalhes, consulte <A href="lync-server-2013-deploying-monitoring.md">implantando o monitoramento no Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>Para habilitar a QoE usando o painel de controle do Lync Server

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.

4.  Na página **Dados de Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **Habilitar QoE**.

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Habilitando a QoE usando cmdlets do Windows PowerShell

Você pode habilitar a QoE usando o Windows PowerShell e o cmdlet **set-CsQoEConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>Para habilitar a QoE para um único local

  - Para habilitar a QoE, defina o parâmetro EnableQoE para True ($True).
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>Para desabilitar a QoE para um único local

  - Para desabilitar a QoE, defina o parâmetro EnableQoE para False ($False). Isso não desinstala o monitoramento; pausa o conjunto e armazena os dados de QoE.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Para usar um único comando para habilitar a QoE em vários locais

  - Este comando habilita a QoE para todas as definições de configuração de QoE atualmente em uso na sua organização.
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

Para obter detalhes, consulte [set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de monitoramento no Lync Server 2013](lync-server-2013-planning-for-monitoring.md)  
[Implantando o monitoramento no Lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

