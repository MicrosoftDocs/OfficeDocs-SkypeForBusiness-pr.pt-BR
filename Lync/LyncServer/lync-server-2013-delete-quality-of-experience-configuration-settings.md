---
title: 'Lync Server 2013: excluir definições de configuração de qualidade da experiência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c2a3d9b8907d888f7edbd65c550315dfabe3306
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Excluir definições de configuração de qualidade de experiência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Os atributos métricos da Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "jitter" (diferenças no atraso de pacotes). Esses atributos métricos são armazenados em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação do QoE, independentemente de outros registros de dados.

Quando você instala o Microsoft Lync Server 2013, um único conjunto global de definições de configuração de QoE é criado para você. Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais. Por design, as configurações no escopo do site têm precedência sobre configurações no escopo global. Se você excluir definições no escopo do site, o QoE será gerenciado naquele site usando as configurações globais.

Observe que você também pode “excluir” as definições globais. Contudo, elas não serão realmente removidas. Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão. Por exemplo, por padrão, a exclusão é habilitada em um conjunto de configurações de QoE. Digamos que você modifique o conjunto global para que a exclusão seja desabilitada. Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão. Nesse caso, isso significa que a exclusão será habilitada novamente.

Você pode remover as definições de configuração de QoE usando o painel de controle do Lync Server ou usando o cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) .

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Para excluir as definições de configuração de QoE usando o painel de controle do Lync Server

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.

4.  Na página **Dados de Qualidade de Experiência**, clique na política que quiser, clique em **Editar** e em **Excluir**.

5.  Clique em **OK**.

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração de QoE usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração de QoE usando o Windows PowerShell e o cmdlet **Remove-CsQoEConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>Para remover um conjunto especificado de definições de configuração de QoE

  - Esse comando remove as definições de configuração de QoE aplicadas ao site de Redmond:
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração de QoE aplicadas no escopo do site

  - Esse comando remove todas as definições de configuração de QoE aplicadas ao escopo do site:
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Para remover todas as definições de configuração de QoE onde o monitoramento de QoE for desabilitado

  - Este comando remove todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado:
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

Para obter detalhes, consulte [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

