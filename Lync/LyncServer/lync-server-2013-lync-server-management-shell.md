---
title: 'Lync Server 2013: Shell de gerenciamento do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Shell de Gerenciamento do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-09-20_

<div>


> [!NOTE]  
> A referência do cmdlet do Skype for Business mudou para docs.microsoft.com. Ao clicar nos links abaixo, você será direcionado para a nova página docs.microsoft.com. O conteúdo agora está aberto e disponível para contribuições da comunidade através do GitHub. Tem interesse em contribuir? Confira o LEIAme no repositório aqui:<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

O Microsoft Lync Server 2010 introduziu um grande conjunto de recursos novos e aprimorados em comparação com o que estava disponível no Microsoft Office Communications Server 2007 R2. Um aperfeiçoamento é a maneira pela qual você gerencia a implementação. Por exemplo, há uma nova interface de usuário, chamada painel de controle do Lync Server, que representa um grande turno do que a maioria das pessoas é usada com o console de gerenciamento da Microsoft. O outro maior aprimoramento para a capacidade de gerenciamento é a inclusão do Windows PowerShell.

O Windows PowerShell permite que você gerencie aplicativos da Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos de produtos e uma linguagem de script completa. O Windows PowerShell foi introduzido pela primeira vez como uma versão disponível para download para o sistema operacional Windows, em 2006, e foi incorporado como a interface de linha de comando para a capacidade de gerenciamento do Microsoft Exchange Server 2007. A partir desse ponto, ele continuou a crescer, e foi incorporado à maioria dos produtos de servidor da Microsoft, o que é o Microsoft Lync Server 2013 mais recente. O Lync Server 2010 introduziu próximo a 550 cmdlets específicos do produto que você pode usar para gerenciar todos os aspectos da sua implantação.

As seções a seguir contêm uma lista de cmdlets e suas descrições. Essas informações também estão disponíveis diretamente na linha de comando. Basta digitar o seguinte no prompt de comando do Shell de gerenciamento do Lync Server:

    Get-Help <cmdlet name> -Full

Por exemplo, para recuperar a Ajuda no prompt de comando, no cmdlet **New-CsVoicePolicy**, digite:

    Get-Help New-CsVoicePolicy -Full

O que se deve saber sobre o Windows PowerShell no Lync Server 2013:

  - Para executar os cmdlets do Lync Server, abra o Shell de gerenciamento do Lync Server.
    
    <div>
    

    > [!WARNING]  
    > Se você abrir uma janela do Windows PowerShell em vez do Shell de gerenciamento do Lync Server, por padrão, não poderá executar os cmdlets do Lync Server. Para executar os cmdlets do Lync Server dentro do Windows PowerShell, primeiro digite o seguinte no prompt de comando do Windows PowerShell:<BR>Importar-módulo Lync

    
    </div>

  - O Shell de gerenciamento do Lync Server é instalado automaticamente em cada servidor front-end do Lync Server Enterprise Edition ou Standard Edition.

  - Informações novas e atualizadas, scripts de exemplo e ajuda para começar e saber mais sobre os cmdlets do Windows PowerShell e do Microsoft Lync Server 2013 estão disponíveis no blog [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)do Windows PowerShell do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

