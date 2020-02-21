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
ms.openlocfilehash: 539408bfaa32565ef76312e1b0d96767edecc169
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Habilitar a qualidade da experiência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

A QoE (Qualidade da Experiência) registra dados numéricos que indicam a qualidade da mídia e informações sobre participantes, nomes de dispositivo, drivers, endereços IP e tipos de ponto de extremidade envolvidos em chamadas e sessões. Para obter detalhes, consulte [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) na documentação de planejamento.

Use o procedimento a seguir para habilitar QoE para toda sua organização ou para cada site em sua organização.

<div>


> [!NOTE]  
> Para habilitar o QoE, é necessário primeiro configurar o monitoramento e um back-end de monitoramento. Para obter detalhes, consulte <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>Para habilitar a QoE usando o painel de controle do Lync Server

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Dados da Qualidade da Experiência**.

4.  Na página **Dados da Qualidade da Experiência**, clique no conjunto adequado na tabela, clique em **Ação** e em **habilitar QoE**.

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Habilitando o QoE usando cmdlets do Windows PowerShell

Você pode habilitar o QoE usando o Windows PowerShell e o cmdlet **set-CsQoEConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>Para habilitar o QoE para um único local

  - Para habilitar o QoE, defina o parâmetro EnableQoE para True ($True).
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>Para desabilitar o QoE para um único local

  - Para desabilitar o QoE, defina o parâmetro EnableQoE para False ($False). Isto não desinstala o monitoramento. Pausa o conjunto e armazena os dados do QoE.
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Para usar um único comando para habilitar o QoE em vários locais

  - Este comando habilita o QoE para todas as definições de configuração do QoE atualmente em uso na sua organização.
    
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

