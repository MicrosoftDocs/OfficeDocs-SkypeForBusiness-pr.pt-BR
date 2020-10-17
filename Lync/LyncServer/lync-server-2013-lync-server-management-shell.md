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
ms.openlocfilehash: b77fae816140784e35c81dd9c30f4cf8790f5bef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534728"
---
# <a name="lync-server-2013-management-shell"></a>Shell de gerenciamento do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-09-20_

<div>


> [!NOTE]  
> A referência de cmdlet do Skype for Business foi movida para o docs.microsoft.com. Clicando nos links abaixo, você será retirado da nova página do docs.microsoft.com. O conteúdo agora é aberto e está disponível para contribuições da Comunidade por meio do GitHub. Interessado em contribuir? Confira o LEIAme no repositório aqui: <A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

O Microsoft Lync Server 2010 introduziu um amplo conjunto de recursos novos e aprimorados em comparação com o que estava disponível no Microsoft Office Communications Server 2007 R2. Uma melhoria é a maneira como você gerencia sua implementação. Por exemplo, há uma nova interface de usuário, chamada painel de controle do Lync Server, que representa uma grande mudança do que a maioria das pessoas usa com o console de gerenciamento da Microsoft. A outra grande melhoria da capacidade de gerenciamento é a inclusão do Windows PowerShell.

O Windows PowerShell permite que você gerencie aplicativos da Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. O Windows PowerShell foi introduzido pela primeira vez como uma versão baixável para o sistema operacional Windows no final de 2006 e foi incorporado como a interface de linha de comando para a capacidade de gerenciamento do Microsoft Exchange Server 2007. A partir desse ponto, ela continuou crescendo e foi incorporada na maioria dos produtos de servidor da Microsoft, sendo que a última delas é o Microsoft Lync Server 2013. O Lync Server 2010 introduziu próximo a 550 cmdlets específicos do produto que você pode usar para gerenciar todos os aspectos da sua implantação.

As seções a seguir contêm uma lista de cmdlets e suas descrições. Essas informações também estão disponíveis diretamente na linha de comando. Basta digitar o seguinte no prompt de comando do Shell de gerenciamento do Lync Server:

    Get-Help <cmdlet name> -Full

Por exemplo, para recuperar a ajuda do prompt de comando no cmdlet **New-CsVoicePolicy** , digite o seguinte:

    Get-Help New-CsVoicePolicy -Full

Coisas que você precisa saber sobre o Windows PowerShell no Lync Server 2013:

  - Para executar os cmdlets do Lync Server, abra o Shell de gerenciamento do Lync Server.
    
    <div>
    

    > [!WARNING]  
    > Se você abrir uma janela do Windows PowerShell em vez do Shell de gerenciamento do Lync Server, por padrão, não será possível executar os cmdlets do Lync Server. Para executar os cmdlets do Lync Server no Windows PowerShell, primeiro digite o seguinte no prompt de comando do Windows PowerShell:<BR>Import-Module Lync

    
    </div>

  - O Shell de gerenciamento do Lync Server é instalado automaticamente em todos os servidores front-end do Lync Server Enterprise Edition ou Standard Edition.

  - Informações novas e atualizadas, exemplos de scripts e ajuda para introdução e saiba mais sobre o Windows PowerShell e os cmdlets do Microsoft Lync Server 2013 estão disponíveis no blog do Lync Server Windows PowerShell [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150) .

</div>

<span> </span>

</div>

</div>

</div>

