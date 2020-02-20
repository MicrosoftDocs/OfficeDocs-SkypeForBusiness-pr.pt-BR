---
title: Mover os usuários restantes para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27b95ad3ba755839090cb74a174789c71b16d9eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Mover os usuários restantes para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Você pode mover os usuários para a nova implantação do Lync Server 2013 usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server. Você deve atender a alguns requisitos para garantir uma transição suave para o Lync Server 2013. Para obter detalhes sobre os pré-requisitos para concluir os procedimentos deste tópico, consulte [Configure clients for Migration](configure-clients-for-migration.md). Para obter etapas detalhadas sobre como mover usuários, consulte [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Você não pode usar o snap-in usuários e computadores do Active Directory ou as ferramentas administrativas do Lync Server 2010 para mover usuários do seu ambiente herdado para o Lync Server 2013.



</div>

Quando você mover um usuário para um pool do Lync Server 2013, os dados do usuário serão movidos para o banco de dados back-end associado ao novo pool.

<div>


> [!IMPORTANT]  
> Isso inclui as reuniões ativas criadas pelo usuário herdado. Por exemplo, se um usuário herdado configurou uma conferência de <STRONG>reunião</STRONG> , essa conferência ainda estará disponível no novo pool do Lync Server 2013 depois que o usuário tiver sido movido. Os detalhes para acessar essa a reunião ainda terão a mesma <STRONG>URL e ID da conferência</STRONG>. A única diferença é que a conferência agora está hospedada no pool do Lync Server 2013 e não no pool do Lync Server 2010.



</div>

<div>


> [!NOTE]  
> A hospedagem de usuários no Lync Server 2013 não requer a implantação de clientes atualizados ao mesmo tempo. A nova funcionalidade estará disponível para os usuários apenas quando eles tiverem o novo software cliente.



</div>

<div>

## <a name="post-migration-task"></a>Tarefa pós-migração

1.  Depois de mover os usuários, verifique a política de conferência atribuída a eles.

2.  Para garantir que as reuniões organizadas pelos usuários hospedados no Lync Server 2013 funcionem perfeitamente com usuários federados hospedados no Lync Server 2010, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.

3.  As políticas de conferência que permitem que os participantes anônimos **permitam que os participantes convidem usuários anônimos** selecionados no painel de controle do lync Server 2013 e tenham o **AllowAnonymousParticipantsInMeetings** definido como **true** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de gerenciamento do Lync Server.

4.  Para obter detalhes sobre como configurar a política de conferência usando o Shell de gerenciamento do Lync Server, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) na documentação do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

