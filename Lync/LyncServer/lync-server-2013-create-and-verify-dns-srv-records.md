---
title: 'Lync Server 2013: Criar e verificar registros DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Criar e verificar registros DNS SRV no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio minimamente como membro do grupo Domain admins ou um membro do grupo DnsAdmins.

Este tópico descreve como configurar os registros de DNS (sistema de nomes de domínio) que você precisa criar nas implantações do Lync Server 2013 e aqueles necessários para a entrada automática do cliente. Quando você cria um pool de front-end, o programa de instalação cria objetos e configurações do Active Directory para o pool, incluindo o nome de domínio totalmente qualificado (FQDN) do pool. Objetos e configurações semelhantes são criados para um servidor Standard Edition. Para que os clientes possam se conectar ao servidor do pool ou da edição Standard, o FQDN do pool ou do servidor Standard Edition deve ser registrado no DNS. Você deve criar registros SRV DNS no seu DNS interno para cada domínio SIP. Este procedimento pressupõe que o seu DNS interno tem zonas para seus domínios de usuário SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Para configurar um registro SRV DNS

1.  No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.

2.  Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio SIP no qual o Lync Server 2013 será instalado.

3.  Clique em **outros novos registros**.

4.  Em **Selecionar um tipo de registro de recurso**, clique em **Local do serviço(SRV)**, e depois clique em **Criar registro**.

5.  Clique em **serviço**e, em seguida, digite ** \_sipinternaltls**.

6.  Clique em **protocolo**e digite ** \_TCP**.

7.  Clique em **Número da porta** e digite **5061**.

8.  Clique em **Host que oferece este serviço** e digite o FQDN do pool ou o servidor Standard Edition.

9.  Clique em **OK** e em **Concluído**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Para verificar a criação de um registro SRV DNS

1.  Faça logon em um computador cliente do domínio com uma conta que seja membro do grupo Usuários autenticados ou que tenha permissões equivalentes.

2.  Clique em  **Iniciar ** e em  **Executar **.

3.  Na caixa **abrir** , digite **cmd**e clique em **OK**.

4.  No prompt de comando, digite **nslookup**e pressione Enter.

5.  Digite **set type = SRV**e pressione Enter.

6.  Digite ** \_sipinternaltls.\_ tcp.contoso.com**e, em seguida, pressione Enter. A saída exibida para o registro do Transport Layer Security (TLS) é a seguinte:
    
    Servidor: \<DNS server\>. contoso.com
    
    Endereço: \<endereço IP do servidor DNS\>
    
    Resposta não autoritativa:
    
    \_sipinternaltls. \_localização do serviço SRV TCP.contoso.com:
    
    prioridade = 0
    
    Weight = 0
    
    porta = 5061
    
    SVR hostname = poolname.contoso.com (ou Standard Edition Server A um registro)
    
    Endereço de Internet poolname.contoso.com \<= endereço IP virtual do balanceador de\> carga \<ou endereço IP de um único servidor Enterprise Edition para pools com apenas um servidor\> Enterprise \<Edition ou endereço IP do padrão Servidor de edição\>

7.  Quando tiver terminado, no prompt de comando, digite **Exit**e pressione Enter.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Para verificar se o FQDN do servidor de front-end ou do servidor Standard Edition pode ser resolvido

1.  Faça logon em um computador cliente no domínio.

2.  Clique em  **Iniciar ** e em  **Executar **.

3.  Na caixa **abrir** , digite **cmd**e clique em **OK**.

4.  No prompt de comando, digite FQDN do **nslookup** \<do pool\> de front- \<end ou FQDN do servidor\>Standard Edition e, em seguida, pressione Enter.

5.  Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.

</div>

</div>

<span> </span>

</div>

</div>

</div>

