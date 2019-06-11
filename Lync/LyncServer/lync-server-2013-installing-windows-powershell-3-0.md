---
title: 'Lync Server 2013: Instalando Windows PowerShell 3.0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 471fd6bd04dd1ec0839aa32c4e71d171dea28de7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Instalando Windows PowerShell 3.0 para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-27_

Para implantar o Lync Server 2013 com êxito, você precisará do Windows PowerShell 3,0 em cada computador que faz parte da sua topologia do Lync Server.

Agora, para sistemas que executam o Windows Server 2012 ou o Windows Server 2012 R2, você não precisa fazer nada aqui, e pode passar para o próximo estágio da implantação, porque o PowerShell 3,0 está incluído nesses sistemas operacionais.

<div>


> [!IMPORTANT]  
> Mas para sistemas que executam o Windows Server 2008 R2 SP1, você precisará instalar o PowerShell 3,0 como pré-requisito antes de instalar o Lync Server 2013 ou as coisas não funcionarão. Para instalar o PowerShell 3,0, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Este é um link direto para a página de download do PowerShell 3,0, além de informações relacionadas à instalação bem-sucedida.



</div>

Depois de fazer a instalação, ou se você só quiser verificar e ter certeza antes de continuar a implantação do Lync Server, confirmar que o PowerShell 3,0 está em um servidor é bem simples se você fizer isso:

1.  No servidor que você deseja verificar, escolha **Iniciar**, clique em **todos os programas**, clique em **acessórios**, clique em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.

2.  No console do Windows PowerShell, digite o seguinte comando no prompt de comando e pressione ENTER:
    
        Get-Host | Select-Object Version

3.  Se o Windows PowerShell 3,0 estiver instalado, você verá uma saída parecida com esta:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

