---
title: Impedir novas conexões com a manutenção do Lync Server para servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc787dee62152e9ace76663a084fe5c1c428b1f2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Impedir novas conexões com o Lync Server 2013 para manutenção do servidor

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

O Lync Server permite que você coloque um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem nenhuma perda de serviço aos usuários.

Quando você especifica a opção para impedir novas conexões ou chamadas a um servidor em um pool, ele para de aceitar novas conexões e chamadas assim que você implementa essa opção. As novas conexões e chamadas são roteadas através de outros servidores no pool. Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até terminarem de modo natural. Quando todas as sessões existentes são concluídas, o servidor está pronto para ser colocado offline.

Quando você impede novas conexões a um servidor front-end, alguns recursos e serviços do Lync Server dependem do balanceamento de carga DNS para garantir que funcionem corretamente. Se você não estiver usando o balanceamento de carga DNSno pool, as conexões por meio desses serviços poderão não ser redirecionados para outros servidores durante o período no qual o servidor está impedindo novas conexões e, portanto, quando o servidor é colocado offline, algumas sessões e chamadas podem ser interrompidas. Estes são os recursos que dependem do balanceamento de carga DNS para garantir que esta opção funcione corretamente:

  - Automático

  - Aplicativo Comunicado de Conferência

  - Aplicativo Grupo de Resposta

  - Aplicativo de comunicado

  - Call Park application

Para obter detalhes sobre o balanceamento de carga DNS, consulte [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

Além de impedir novas conexões para todos os serviços em um servidor executando o Lync Server, você também pode impedir novas conexões para serviços individuais do Lync Server. Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização do Lync Server que não exige o desligamento completo do servidor. Observe que, quando você impede conexões com um serviço, deve selecionar um serviço que é agrupado e exibido na lista de serviços do Windows. Por exemplo, o serviço front-end do Lync Server e o agente de coleta de dados para monitoramento são serviços separados do Lync Server, mas na lista de serviços do Windows eles são consolidados e exibidos como o serviço front-end do Lync Server. Você pode impedir novas conexões para o serviço de front-ends do Lync Server, mas não pode impedir novas conexões para esses dois serviços de Lync Server subjacentes individuais separadamente.

<div>


> [!IMPORTANT]
> Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Para impedir novas conexões ao Lync Server:

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Abra o console de snap-in de serviços: clique em **Iniciar**, aponte para **todos os programas**, aponte para **Ferramentas administrativas**e clique em **Serviços**.

3.  Na lista, clique duas vezes no serviço do Windows Lync Server para o qual você deseja impedir novas conexões.

4.  Na caixa de diálogo Propriedades, em **status do serviço: iniciado**, clique em **Pausar**.

5.  Opcionalmente, mas recomendado, ao lado de **tipo de inicialização**, clique em **manual**.
    
    <div>
    

    > [!IMPORTANT]
    > Quando você define um servidor para impedir novas conexões e reiniciar o servidor, por padrão, o servidor começa imediatamente a aceitar novas conexões depois de ser inicializado. Para evitar isso, defina o servidor para apenas pausar e reiniciar manualmente antes de reiniciá-lo.

    
    </div>

6.  Quando tiver concluído, clique em **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

