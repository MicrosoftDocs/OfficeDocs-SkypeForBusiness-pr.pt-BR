---
title: Verificar a conclusão da replicação de usuário
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
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Verificar a conclusão da replicação de usuário

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-28_

Ao executar o cmdlet **move-CsLegacyUser** , você pode ter uma falha devido a informações do usuário entre os serviços de domínio Active Directory (AD DS), e os bancos de dados do Lync Server 2013 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Lync Server 2013 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Lync Server 2013. O processo de sincronização inicial do serviço Duplicador de usuários do Lync Server 2013 ocorre quando o servidor front-end do Lync Server 2013 é iniciado pela primeira vez. Depois disso, a sincronização é baseada no intervalo de Duplicador do usuário. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet **move-CsLegacyUser** .

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>Para verificar se a duplicação do usuário foi concluída

1.  No servidor de front-end do Lync Server 2013, clique no menu **Iniciar** e, em seguida, clique em **executar**.

2.  Insira **eventvwr. exe** e clique em **OK**.

3.  Em Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e selecione Lync Server.

4.  No painel **ações** , clique em **Filtrar log atual**.

5.  Na lista **fontes de eventos** , clique em **Duplicador de usuários ls**.

6.  Em ** \<todas as identificações\> de evento** , insira **30024** e clique em **OK**.

7.  Na lista eventos filtrados, na guia **geral** , procure por uma entrada que declara que a duplicação do usuário foi concluída com êxito.

</div>

</div>

<span> </span>

</div>

</div>

</div>

