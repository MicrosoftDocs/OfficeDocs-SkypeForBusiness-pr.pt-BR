---
title: 'Lync Server 2013: usando cmdlets para reverter a preparação da floresta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse forest preparation
ms:assetid: f48c7eb3-ccb0-48e6-ac79-ab7c7062b9d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413024(v=OCS.15)
ms:contentKeyID: 48185822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b644b5b703e1515a4417b7fa318b4e9ed6080b94
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-forest-preparation-for-lync-server-2013"></a>Usando cmdlets para reverter a preparação da floresta para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-06-19_

Use o cmdlet **Disable-CsAdForest** para reverter a etapa de preparação da floresta.

<div>


> [!WARNING]  
> Se você executar o cmdlet <STRONG>Disable-CsAdForest</STRONG> em um ambiente onde você também tem uma versão anterior do Lync Server implantada, as configurações globais da versão anterior também serão excluídas.



</div>

<div>

## <a name="to-use-cmdlets-to-reverse-forest-preparation"></a>Para usar cmdlets para reverter a preparação da floresta

1.  Faça o login em um computador que faz parte de um domínio como membro do grupo Administradores de Domínio no domínio raiz da floresta.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Disable-CsAdForest [-Force] [-GroupDomain <FQDN of the domain in which universal groups were created>]
    
    Por exemplo:
    
        Disable-CsAdForest -Force -GroupDomain contoso.net
    
    O parâmetro Force especifica se deve forçar a execução da tarefa. Se esse parâmetro não estiver presente, o comando não será executado se mesmo um domínio da floresta ainda estiver preparado para o Lync Server 2013. Se o parâmetro Force é especificado, a ação continuará independente do estado dos outros domínios na floresta.
    
    Se você não especificar o parâmetro GroupDomain, o valor padrão é o domínio local.

</div>

<div>

## <a name="see-also"></a>Confira também


[Executando a preparação da floresta para o Lync Server 2013](lync-server-2013-running-forest-preparation.md)  


[Preparando a floresta para o Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

