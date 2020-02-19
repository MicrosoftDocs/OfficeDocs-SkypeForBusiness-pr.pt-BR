---
title: 'Lync Server 2013: configurar DNS para balanceamento de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 257bd8d1d4874bb2483c16c2216c4b76b178a881
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Configurar DNS para balanceamento de carga no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.

O balanceamento de carga do DNS (sistema de nomes de domínio) balanceia o tráfego de rede exclusivo do Lync Server 2013, como tráfego SIP e tráfego de mídia. O balanceamento de carga DNS é suportado para pools de Front-Ends, pools de Borda, pools de Diretores e pools de Mediação autônomos. Um pool configurado para usar o balanceamento de carga DNS deve ter dois nomes de domínio totalmente qualificados (FQDNs) definidos: o FQDN do pool regular que é usado pelo balanceamento de carga DNS (por exemplo, pool1.contoso.com) e que resolve para o IPs físico dos servidores no pool e outro FQDN para os serviços Web do pool (por exemplo, web1.contoso.net), que resolve para o endereço IP virtual do pool. Para obter detalhes sobre o balanceamento de carga DNS, consulte [DNS Load Balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

<div>


> [!NOTE]  
> O balanceamento de carga de hardware ainda é exigido para tráfego HTTPS de cliente para servidor.



</div>

Antes que possa usar o balanceamento de carga DNS, você deve fazer o seguuinte:

1.  Substitua o FQDN do pool de serviços Web interno.
    
    <div>
    

    > [!WARNING]  
    > Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.

    
    </div>

2.  Create DNS A host records to resolve the pool FQDN to the IP addresses of all the servers in the pool.

3.  Enable IP Address randomization or, for Windows Server DNS, enable round robin.
    
    <div>
    

    > [!NOTE]  
    > Round robin deve ser habilitado por padrão.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>To override internal Web services FQDN

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  From the console tree, expand the Enterprise Edition Front End pools node.

3.  Right-click the pool, click **Edit Properties**, and then click **Web Services**.

4.  Below **Internal web services**, select the **Override FQDN** check box.

5.  Type the pool FQDN that resolves to the physical IP addresses of the servers in the pool.

6.  Below **External web services**, type the external pool FQDN that resolves to the virtual IP addresses of the pool, and then click **OK**.

7.  Na árvore de console, clique em **Lync Server 2013**e, em seguida, no painel **ações** , clique em **publicar topologia**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>To create DNS Host (A) Records for all internal pool servers

1.  Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.

2.  In **DNS Manager**, click the DNS Server that manages your records to expand it.

3.  Click **Forward Lookup Zones** to expand it.

4.  Right-click the DNS domain that you need to add records to, and then click **New Host (A or AAAA)**.

5.  Na caixa **nome** , digite o nome do registro do host (o nome do domínio será anexado automaticamente).

6.  In the IP Address box, type the IP address of the individual Front End Server and then select **Create associated pointer (PTR) record** or **Allow any authenticated user to update DNS records with the same owner name**, if applicable.

7.  Continue creating records for all member Front End Servers that will participate in DNS Load Balancing.
    
    For example, if you had a pool named pool1.contoso.com and three Front End Servers, you would create the following DNS entries:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>Tipo</th>
    <th>Dados</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    Para obter detalhes sobre como criar registros de host DNS (A), consulte [Configure DNS host Records for Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>To enable round robin for Windows Server

1.  Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **DNS**.

2.  Expand **DNS**, right-click the DNS server you want to configure, and then click **Properties**.

3.  Click the **Advanced** tab, select **Enable round robin** and **Enable netmask ordering**, and then click **OK**.
    
    ![Caixa de diálogo Round Robin DNS](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Caixa de diálogo Round Robin DNS")

<div>


> [!NOTE]  
> Este recurso deve ser habilitado por padrão.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

