---
title: 'Lync Server 2013: Usando cmdlets para reverter preparação da floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd186fc3b2c6171b49cf3fd4c9e78b8e66b4cc71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Usando cmdlets para reverter preparação da floresta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-06-19_

Use o cmdlet **Disable-CsAdForest** para reverter a etapa de preparação da floresta.

<div>


> [!WARNING]  
> Se você executar o cmdlet <STRONG>Disable-CsAdForest</STRONG> em um ambiente em que você também tenha uma versão anterior do Lync Server implantada, as configurações globais para a versão anterior também serão excluídas.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Para usar cmdlets para reverter a preparação da floresta

1.  Faça logon em um computador que esteja associado a um domínio como membro do grupo Domain admins no domínio raiz da floresta.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Por exemplo:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    O parâmetro Force especifica se deve forçar a execução da tarefa. Se esse parâmetro não estiver presente, o comando não será executado se mesmo um domínio na floresta ainda estiver preparado para o Lync Server 2013. Se o parâmetro Force for especificado, a ação continuará independentemente do estado de outros domínios na floresta.
    
    Se você não especificar o parâmetro GroupDomain, o valor padrão será o domínio local.

</div>

<div>

## <a name="see-also"></a>Confira também


[Executando preparação de floresta para Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Preparando a floresta para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

