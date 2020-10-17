---
title: Verificar a conclusão da replicação de usuário
description: Verifique se a replicação do usuário foi concluída.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bca44fcce811c29b1633bd4d3a39f832851885
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555477"
---
# <a name="verify-user-replication-has-completed"></a>Verificar a conclusão da replicação de usuário

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-17_

Ao executar o cmdlet **move-CsUser** , você pode ter uma falha porque as informações do usuário entre os serviços de domínio do Active Directory (AD DS) e os bancos de dados do Lync Server 2013 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Lync Server 2013 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Lync Server 2013. O processo de sincronização inicial do serviço replicador de usuários do Lync Server 2013 ocorre quando o servidor front-end do Lync Server 2013 é iniciado pela primeira vez. Depois disso, a sincronização se baseia no intervalo do User Replicator. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet **Move-CsUser**.

<div>

## <a name="to-verify-user-replication-has-completed"></a>Para verificar se a replicação de usuário foi concluída

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Clique no menu **Iniciar** e em **Executar**.

3.  Insira **eventvwr.exe** e clique em **OK**.

4.  No Visualizador de Eventos, clique em **Logs de Aplicativos e Serviços** para expandir e selecione Lync Server.

5.  No painel **Ações**, clique em **Filtrar Log Atual**.

6.  Na lista **Fontes de evento**, clique em **Replicador de Usuário LS**.

7.  Em **\<All Event IDs\>** digite **30024** e clique em **OK**.

8.  Na lista de eventos filtrados, na guia **Geral**, procure uma entrada que afirma que a replicação de usuário foi concluída com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

