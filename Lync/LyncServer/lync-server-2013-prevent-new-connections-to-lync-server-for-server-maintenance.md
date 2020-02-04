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
ms.openlocfilehash: fb0e2db6eeff584c4d1ab08bdd293113f1394e4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Impedir novas conexões com o Lync Server 2013 para manutenção do servidor

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

O Lync Server permite que você coloque um servidor offline (por exemplo, para aplicar atualizações de software ou hardware) sem perda de serviço aos usuários.

Quando você especificar a opção para impedir novas conexões ou chamadas para um servidor em um pool, ela deixará de fazer novas conexões e chamadas assim que você implementar essa opção. Essas novas conexões e chamadas são roteadas por meio de outros servidores no pool. Um servidor que está impedindo novas conexões permite que suas sessões em conexões existentes continuem até que elas terminem naturalmente. Quando todas as sessões existentes terminarem, o servidor estará pronto para ser colocado offline.

Quando você impede novas conexões a um servidor front-end, alguns recursos e serviços do Lync Server dependem do balanceamento de carga de DNS para garantir que ele funcione corretamente. Se você não estiver usando o balanceamento de carga de DNS no pool, as conexões por meio desses serviços não poderão ser reencaminhadas a outros servidores durante o período em que o servidor está impedindo novas conexões e, portanto, quando o servidor for colocado offline, algumas sessões e chamadas poderão ser interrompido. Os recursos que dependem do balanceamento de carga de DNS para garantir que essa opção funcione corretamente são os seguintes:

  - Atendedor

  - Aplicativo Comunicado de Conferência

  - Aplicativo Grupo de Resposta

  - Aplicativo Comunicado

  - Aplicativo de Estacionamento de Chamada

Para obter detalhes sobre o balanceamento de carga de DNS, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

Além de impedir novas conexões para todos os serviços em um servidor que executa o Lync Server, você também pode impedir novas conexões para serviços individuais do Lync Server. Por exemplo, esse método é útil em uma situação em que você precisa aplicar uma atualização do Lync Server que não exija que todo o servidor seja desligado. Observe que, ao impedir conexões para um serviço, você deve selecionar um serviço como ele está agrupado e exibido na lista de serviços do Windows. Por exemplo, o serviço de front-end do Lync Server e o agente de coleta de dados para monitoramento são serviços do Lync Server separados, mas na lista de serviços do Windows eles são consolidados e exibidos como o serviço de front-end do Lync Server. Você pode impedir novas conexões para o serviço de front-end do Lync Server, mas não pode impedir novas conexões para esses dois serviços individuais do Lync Server subjacentes separadamente.

<div>


> [!IMPORTANT]
> Quando você define um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão, o servidor começará imediatamente a aceitar novas conexões depois que ele for iniciado. Para evitar isso, defina o servidor para pausar e retomar manualmente, antes de reiniciar o servidor.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>Para impedir novas conexões com o Lync Server:

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Abra o console do snap-in Serviços: clique em **Iniciar**, aponte para **todos os programas**, aponte para **Ferramentas administrativas**e clique em **Serviços**.

3.  Na lista, clique duas vezes no serviço do Windows Lync Server ao qual você deseja impedir novas conexões.

4.  Na caixa de diálogo Propriedades, em **status do serviço: iniciado**, clique em **Pausar**.

5.  Opcionalmente, mas recomendado, ao lado de **tipo de inicialização**, clique em **manual**.
    
    <div>
    

    > [!IMPORTANT]
    > Quando você define um servidor para impedir novas conexões e, em seguida, reiniciar o servidor, por padrão, o servidor começará imediatamente a aceitar novas conexões depois que ele for iniciado. Para evitar isso, defina o servidor para pausar e retomar manualmente, antes de reiniciar o servidor.

    
    </div>

6.  Ao concluir, clique em **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

