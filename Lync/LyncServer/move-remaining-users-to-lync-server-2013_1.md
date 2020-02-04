---
title: Mover usuários restantes para Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb5a709e896b66a1c8cd33a930bfeed5e05644f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>Mover usuários restantes para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-26_

Você pode mover usuários para a nova implantação do Lync Server 2013 usando o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server. Você deve atender a alguns requisitos para garantir uma transição tranqüila para o Lync Server 2013. Para obter detalhes sobre pré-requisitos para completar os procedimentos deste tópico, consulte [configurar clientes para migração](configure-clients-for-migration_1.md). Para ver as etapas detalhadas sobre como mover usuários, consulte [fase 6: mover usuários para o pool piloto](phase-6-move-users-to-the-pilot-pool.md).

<div>


> [!IMPORTANT]  
> Você não pode usar o snap-in usuários e computadores do Active Directory ou as ferramentas administrativas do Microsoft Office Communications Server 2007 R2 para mover os usuários do seu ambiente herdado para o Lync Server 2013.



</div>

<div>


> [!IMPORTANT]  
> O cmdlet <STRONG>move-CsLegacyUser</STRONG> requer que os nomes de usuário sejam formados corretamente e não tenham espaços à esquerda ou à direita. Você não pode mover uma conta de usuário usando o cmdlet <STRONG>move-CsLegacyUser</STRONG> se ele contiver espaços à esquerda ou à direita.



</div>

Quando você move um usuário para um pool do Lync Server 2013, os dados do usuário são movidos para o banco de dados back-end que está associado ao novo pool.

<div>


> [!IMPORTANT]  
> Isso inclui as reuniões ativas criadas pelo usuário herdado. Por exemplo, se um usuário herdado configurou uma conferência de <STRONG>reunião</STRONG> , essa conferência ainda estará disponível no novo pool do Lync Server 2013, após o usuário ter sido movido. Os detalhes para acessar a reunião ainda serão a mesma <STRONG>URL de conferência e ID de conferência</STRONG>. A única diferença é que a conferência agora está hospedada no pool do Lync Server 2013 e não no pool do Office Communications Server 2007 R2.



</div>

<div>


> [!NOTE]  
> A hospedagem de usuários no Lync Server 2013 não requer que você implante clientes atualizados ao mesmo tempo. A nova funcionalidade estará disponível para os usuários somente quando tiverem atualizado para o novo software cliente.



</div>

<div>

## <a name="post-migration-task"></a>Tarefa pós-migração

1.  Depois de mover os usuários, verifique a política de conferência atribuída a ele.

2.  Para garantir que as reuniões organizadas por usuários hospedados no Lync Server 2013 funcionem perfeitamente com usuários federados que são hospedados no Office Communications Server 2007 R2, a política de conferência atribuída aos usuários migrados deve permitir participantes anônimos.

3.  As políticas de conferência que permitem aos participantes anônimos **permitem que os participantes convidem usuários anônimos** selecionados no painel de controle do lync Server 2013 e têm o **AllowAnonymousParticipantsInMeetings** definido como **true** na saída do cmdlet **Get-CsConferencingPolicy** no Shell de gerenciamento do Lync Server.

4.  Para obter detalhes sobre como configurar a política de conferência usando o Shell de gerenciamento do Lync Server, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) na documentação do Shell de gerenciamento do Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

