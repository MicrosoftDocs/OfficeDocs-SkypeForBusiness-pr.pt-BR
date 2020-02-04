---
title: 'Lync Server 2013: exibir informações sobre as regras de atualização de dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e26b67aba2bf792b3248e7771f938a8bced1668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Exibir informações sobre as regras de atualização de dispositivos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Exiba detalhes sobre as regras de atualização de dispositivos que já foram importadas, incluindo o tipo, o modelo e a marca de dispositivos aos quais a atualização se aplica; versão e tipo de atualização; e a localidade e o pool para a atualização. As informações estão disponíveis para todas as regras de atualização de dispositivo importadas, que têm aprovação pendente, implantada (aprovada), recuperada (restaurada) e aquelas que você decidiu não usar (Redefinir). Acesse essas informações de um painel de controle do Lync Server ou do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como importar, aprovar, redefinir, restaurar e remover regras, consulte os tópicos listados em <A href="lync-server-2013-device-update-rules.md">regras de atualização de dispositivos no Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Para exibir as regras de atualização de dispositivos usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação de **atualização do dispositivo** . As regras importadas são listadas na página **atualização do dispositivo** .

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Exibindo regras de atualização de dispositivos usando cmdlets do Windows PowerShell

Informações detalhadas sobre todas as suas regras de atualização de dispositivo também podem ser visualizadas usando o Windows PowerShell e o cmdlet **Get-CsDeviceUpdateRule** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.

<div>


> [!NOTE]  
> Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Microsoft Lync Server 2010 usando o PowerShell remoto" em.



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Para ver todas as suas regras de atualização de dispositivo

  - O comando a seguir retorna informações sobre todas as regras de atualizações de dispositivo configuradas para uso em sua organização:
    
        Get-CsDeviceUpdateRule
    
    O comando retorna informações semelhantes às seguintes para cada uma de suas regras de atualização de dispositivo:
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>Para exibir todas as regras de atualização de dispositivos em um servidor Web específico

  - Para exibir as regras de atualização de dispositivo em um computador específico, use o parâmetro Filter seguido pela identidade do servidor e o caractere\*curinga (). Por exemplo:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Para obter detalhes, consulte o tópico da ajuda para o cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

