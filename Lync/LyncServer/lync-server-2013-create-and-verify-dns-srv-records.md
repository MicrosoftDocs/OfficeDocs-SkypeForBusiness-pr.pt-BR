---
title: 'Lync Server 2013: criar e verificar registros DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677b657f5bb7dacad6f1379aa4923052ba4ab1c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Criar e verificar registros DNS SRV no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.

Este tópico descreve como configurar os registros de DNS (sistema de nomes de domínio) que você precisa criar nas implantações do Lync Server 2013 e aqueles necessários para entrar no cliente automático. Quando você cria um pool de front-ends, a instalação cria objetos e configurações do Active Directory para o pool, incluindo o nome de domínio totalmente qualificado (FQDN) do pool. São criados objetos e configurações semelhantes para um servidor Standard Edition. Para que os clientes possam se conectar ao pool ou ao servidor Standard Edition, o FQDN do pool ou do servidor Standard Edition deve ser registrado no DNS. Você deve criar registros SRV de DNS no DNS interno para cada domínio SIP. Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Para configurar um registro SRV de DNS

1.  No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.

2.  Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio SIP no qual o Lync Server 2013 será instalado.

3.  Clique em **Outros Registros Novos**.

4.  Em **Selecione um tipo de registro de recurso**, clique em **Local do Serviço (SRV)** e, em seguida, clique em **Criar Registro**.

5.  Clique em **serviço**e digite ** \_sipinternaltls**.

6.  Clique em **protocolo**e digite ** \_TCP**.

7.  Clique em **Número da Porta** e digite **5061**.

8.  Clique em **host que oferece este serviço**e digite o FQDN do pool ou servidor Standard Edition.

9.  Clique em **OK** e em **Concluído**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Para verificar a criação de um registro SRV de DNS

1.  Faça logon em um computador cliente do domínio com uma conta que seja membro do grupo Usuários autenticados ou que tenha permissões equivalentes.

2.  Clique em **Iniciar** e em **Executar**.

3.  Na caixa **Abrir**, digite **cmd** e clique em **OK**.

4.  No prompt de comando, digite **nslookup** e pressione ENTER.

5.  Digite **set type=srv** e pressione ENTER.

6.  Digite ** \_sipinternaltls.\_ tcp.contoso.com**e pressione Enter. A saída exibida para o registro de TLS (segurança de camada de transporte) é a seguinte:
    
    Servidor: \<servidor\>DNS. contoso.com
    
    Endereço: \<endereço IP do servidor DNS\>
    
    Resposta não-autorizada:
    
    \_sipinternaltls. \_local do serviço SRV do TCP.contoso.com:
    
    prioridade = 0
    
    Weight = 0
    
    porta = 5061
    
    nome da SVR = poolname.contoso.com (ou um registro do servidor Standard Edition A)
    
    poolname.contoso.com Internet address = \<endereço IP virtual do balanceador de carga\> ou \<endereço IP de um único servidor Enterprise Edition para pools com apenas um servidor\> Enterprise Edition \<ou endereço IP do servidor Standard Edition\>

7.  Quando terminar, no prompt de comando, digite **exit** e pressione ENTER.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido

1.  Faça logon em um computador cliente no domínio.

2.  Clique em **Iniciar** e em **Executar**.

3.  Na caixa **Abrir**, digite **cmd** e clique em **OK**.

4.  No prompt de comando, digite FQDN do **nslookup** \<do pool\> de front- \<ends ou FQDN do servidor\>Standard Edition e pressione Enter.

5.  Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.

</div>

</div>

<span> </span>

</div>

</div>

</div>

