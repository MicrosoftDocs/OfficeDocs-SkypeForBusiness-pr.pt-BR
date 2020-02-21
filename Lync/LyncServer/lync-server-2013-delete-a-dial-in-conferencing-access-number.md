---
title: 'Lync Server 2013: excluir um número de acesso de conferência discada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5d0e51486ed6dca7c9ac17a991b0154c2f1135
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Excluir um número de acesso de conferência discada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Siga estas etapas para excluir um número de acesso de conferência discada.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>Exclusão de um número de acesso de conferências discadas

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Conferências**, e então em **Número de acesso discado**.

4.  Na página, clique no número de discagem que deseja excluir da lista, clique em **Editar** e clique em **Excluir**.

5.  Clique em **OK**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Removendo números de acesso de conferência discada usando cmdlets do Windows PowerShell

Os números de acesso de conferência discada podem ser excluídos usando o Windows PowerShell e o cmdlet **Remove-CsDialInConferencingAccessNumber** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>Para remover um número de acesso de conferência discada específico

  - Este comando exclui o número de acesso de conferência discada com o SIP de Identidade:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>Para remover todos os números de acesso de conferência discada atribuídos a uma região específica

  - Este comando exclui todos os números de acesso de conferência discada associados com a região Noroeste:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>Para remover os números de acesso de conferência discada com base no idioma principal

  - Este comando exclui todos os números de acesso de conferência discada em que italiano é o idioma principal:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

