---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb3c5a3f74d3a85fbc5742514a92015df08d5c9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Atualizar registros de DNS SRV

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-29_

Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.

Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Lync Server 2013. Após todos os usuários terem sido movidos para o Lync Server 2013, mas antes que o pool ou o diretor herdado do Office Communications Server 2007 R2 seja encerrado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP. Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.

**Para configurar um registro SRV de DNS**

1.  No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.

2.  Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Lync Server 2013 está instalado e navegue até a configuração ** \_ TCP** .

3.  No painel direito, clique com o botão direito do mouse em ** \_ sipinternaltls** e selecione **Propriedades**.

4.  Em **host que oferece esse serviço**, atualize o FQDN do host para apontar para o pool do Lync Server 2013.

5.  Clique em **OK**.

**Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido**

1.  Faça logon em um computador cliente no domínio.

2.  Clique em **Iniciar** e em **Executar**.

3.  Na caixa **Abrir**, digite **cmd** e clique em **OK**.

4.  No prompt de comando, digite **nslookup** \<FQDN of the Front End pool\> ou \<FQDN of the Standard Edition server\> e pressione Enter.

5.  Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.

</div>

<span> </span>

</div>

</div>

</div>

