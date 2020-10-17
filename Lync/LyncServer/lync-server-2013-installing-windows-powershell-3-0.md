---
title: 'Lync Server 2013: Instalando o Windows PowerShell 3,0'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205328(v=OCS.15)
ms:contentKeyID: 48185621
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18de45679983221d80171dde8dd37397a8b3a965
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534778"
---
# <a name="installing-windows-powershell-30-for-lync-server-2013"></a>Instalando o Windows PowerShell 3,0 para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-27_

Para implantar o Lync Server 2013 com êxito, você precisará do Windows PowerShell 3,0 em cada computador que faz parte da sua topologia do Lync Server.

Agora, para sistemas que executam o Windows Server 2012 ou o Windows Server 2012 R2, você não precisa fazer nada aqui e pode prosseguir para o próximo estágio de implantação, porque o PowerShell 3,0 está incluído nesses sistemas operacionais.

<div>


> [!IMPORTANT]  
> Mas para sistemas executando o Windows Server 2008 R2 SP1, você precisará instalar o PowerShell 3,0 como pré-requisito antes de instalar o Lync Server 2013 ou as coisas não funcionarão. Para instalar o PowerShell 3,0, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3,0</A>. Este é um link direto para a página de download do PowerShell 3,0, juntamente com informações relacionadas à instalação bem-sucedida.



</div>

Depois de fazer a instalação, ou se você só quiser verificar e ter certeza antes de continuar com a implantação do Lync Server, confirmar se o PowerShell 3,0 está em um servidor é bem simples se você fizer isso:

1.  No servidor que você deseja verificar, escolha **Iniciar**, clique em **todos os programas**, em **acessórios**, clique em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.

2.  No console do Windows PowerShell, digite o seguinte comando no prompt de comando e pressione ENTER:
    
        Get-Host | Select-Object Version

3.  Se o Windows PowerShell 3,0 estiver instalado, você verá a saída parecida com esta:
    
        Version
        -------
        3.0

</div>

<span> </span>

</div>

</div>

</div>

