---
title: Verificar se a replicação do usuário foi concluída
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6433c1e88edf69b957047b9dc405df392e5ec104
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Verificar se a replicação do usuário foi concluída

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-28_

Ao executar o cmdlet **move-CsLegacyUser** , você pode ter uma falha devido às informações do usuário entre o AD DS (serviços de domínio Active Directory) e os bancos de dados do Lync Server 2013 que estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Lync Server 2013 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Lync Server 2013. O processo de sincronização inicial do serviço replicador de usuários do Lync Server 2013 ocorre quando o servidor front-end do Lync Server 2013 é iniciado pela primeira vez. Depois disso, a sincronização se baseia no intervalo do Replicador de Usuário. Complete os passos a seguir para verificar que a replicação de usuário foi concluída antes de executar o cmdlet **Move-CsLegacyUser**.

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Para verificar que a replicação de usuário foi concluída

1.  No servidor front-end do Lync Server 2013, clique no menu **Iniciar** e em **executar**.

2.  Insira **eventvwr.exe** e clique em **OK**.

3.  No Visualizador de Eventos, clique em **Logs de Aplicativos e Serviços** para expandir e selecione Lync Server.

4.  No painel **Ações**, clique em **Filtrar Log Atual**.

5.  Na lista **Fontes de evento**, clique em **Replicador de Usuário LS**.

6.  Em ** \<todas as identificações\> de evento** , insira **30024** e clique em **OK**.

7.  Na lista de eventos filtrados, na guia **Geral**, procure uma entrada que afirma que a replicação de usuário foi concluída com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

