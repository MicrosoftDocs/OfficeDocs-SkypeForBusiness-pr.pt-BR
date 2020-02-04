---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 927bdab6721583fd744f68969a852f29ba478027
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Atualizar registros de DNS SRV

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-29_

Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.

Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Lync Server 2013. Depois que todos os usuários tiverem sido movidos para o Lync Server 2013, mas antes do pool herdado do Office Communications Server 2007 R2 ser encerrado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP. Este procedimento pressupõe que o seu DNS interno tem zonas para seus domínios de usuário SIP.

**Para configurar um registro SRV DNS**

1.  No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.

2.  Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Lync Server 2013 está instalado e ** \_** navegue até a configuração TCP.

3.  No painel direito, clique com o botão direito do mouse em ** \_sipinternaltls** e selecione **Propriedades**.

4.  Em **host oferecendo esse serviço**, atualize o FQDN do host para apontar para o pool do Lync Server 2013.

5.  Clique em **OK**.

**Para verificar se o FQDN do servidor de front-end ou do servidor Standard Edition pode ser resolvido**

1.  Faça logon em um computador cliente no domínio.

2.  Clique em  **Iniciar ** e em  **Executar **.

3.  Na caixa **abrir** , digite **cmd**e clique em **OK**.

4.  No prompt de comando, digite FQDN do **nslookup** \<do pool\> de front- \<end ou FQDN do servidor\>Standard Edition e, em seguida, pressione Enter.

5.  Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.

</div>

<span> </span>

</div>

</div>

</div>

