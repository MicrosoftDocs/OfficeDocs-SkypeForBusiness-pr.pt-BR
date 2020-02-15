---
title: Atualizar registros SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1440740e8fc25f5873dcb7bbdf5e8db953f6cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Atualizar registros SRV DNS

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.

Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Lync Server 2013. Após todos os usuários terem sido movidos para o Lync Server 2013, mas antes de o pool ou diretor herdado do Lync Server 2010 ser descomissionado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP. Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.

**Para configurar um registro SRV de DNS**

1.  No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.

2.  Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Lync Server 2013 está instalado e ** \_** navegue até a configuração TCP.

3.  No painel direito, clique com o botão direito do mouse em ** \_sipinternaltls** e selecione **Propriedades**.

4.  Em **host que oferece esse serviço**, atualize o FQDN do host para apontar para o pool do Lync Server 2013.

5.  Clique em **OK**.

**Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido**

1.  Faça logon em um computador cliente no domínio.

2.  Clique em **Iniciar** e em **Executar**.

3.  Na caixa **Abrir**, digite **cmd** e clique em **OK**.

4.  No prompt de comando, digite FQDN do **nslookup** \<do pool\> de front- \<ends ou FQDN do servidor\>Standard Edition e pressione Enter.

5.  Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.

</div>

<span> </span>

</div>

</div>

</div>

