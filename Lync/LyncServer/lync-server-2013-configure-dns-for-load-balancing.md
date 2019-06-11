---
title: 'Lync Server 2013: Configurar DNS para balanceamento de carga'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Configurar DNS para balanceamento de carga no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio minimamente como membro do grupo Domain admins ou um membro do grupo DnsAdmins.

O balanceamento de carga de DNS (sistema de nomes de domínio) equilibra o tráfego de rede exclusivo para o Lync Server 2013, como tráfego SIP e tráfego de mídia. O balanceamento de carga de DNS tem suporte para pools de front-end, pools de borda, pools de diretor e pools de mediação autônomos. Um pool configurado para usar o balanceamento de carga de DNS deve ter dois nomes de domínio totalmente qualificados (FQDNs) definidos: o FQDN do pool regular que é usado pelo balanceamento de carga de DNS (por exemplo, pool1.contoso.com) e que é resolvido para o IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (por exemplo, web1.contoso.net), que é resolvido para o endereço IP virtual do pool. Para obter detalhes sobre o balanceamento de carga de DNS, consulte [balanceamento de carga de DNS no Lync Server 2013](lync-server-2013-dns-load-balancing.md) na documentação de planejamento.

<div>


> [!NOTE]  
> O balanceamento de carga de hardware ainda é necessário para o cliente para o tráfego HTTPS do cliente.



</div>

Antes de poder usar o balanceamento de carga de DNS, você deve fazer o seguinte:

1.  Substituir o FQDN do pool de serviços Web internos.
    
    <div>
    

    > [!WARNING]  
    > Se decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.

    
    </div>

2.  Crie registros de host DNS a para resolver o FQDN do pool para os endereços IP de todos os servidores do pool.

3.  Habilite a randomização de endereços IP ou, para o DNS do Windows Server, ative o rodízio.
    
    <div>
    

    > [!NOTE]  
    > O Round Robin deve ser habilitado por padrão.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>Para substituir FQDN de serviços Web internos

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na árvore de console, expanda o nó do pool de front-end do Enterprise Edition.

3.  Clique com o botão direito do mouse no pool, clique em **Editar propriedades**e, em seguida, clique em **Serviços Web**.

4.  Abaixo de **Serviços Web internos**, marque a caixa de seleção **substituir FQDN** .

5.  Digite o FQDN do pool que é resolvido para os endereços IP físicos dos servidores do pool.

6.  Abaixo de **Serviços Web externos**, digite o FQDN do pool externo que é resolvido para os endereços IP virtuais do pool e clique em **OK**.

7.  Na árvore de console, clique em **Lync Server 2013**e, em seguida, no painel **ações** , clique em **publicar topologia**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>Para criar registros de host DNS (A) para todos os servidores de pool interno

1.  Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e, em seguida, clique em **DNS**.

2.  No **Gerenciador DNS**, clique no servidor DNS que gerencia seus registros para expandi-lo.

3.  Clique em **zonas de pesquisa direta** para expandi-la.

4.  Clique com o botão direito do mouse no domínio DNS ao qual você precisa adicionar registros e, em seguida, clique em **novo host (A ou aaaa)**.

5.  Na caixa **Nome**, digite o nome do registro host (o nome do domínio será automaticamente acrescentado).

6.  Na caixa endereço IP, digite o endereço IP do servidor front-end individual e, em seguida, selecione **criar registro de ponteiro associado (PTR)** ou **permitir que qualquer usuário autenticado atualize registros de DNS com o mesmo nome de proprietário**, se aplicável.

7.  Continuar criando registros para todos os servidores de front-end do membro que participarão do balanceamento de carga de DNS.
    
    Por exemplo, se você tivesse um pool chamado pool1.contoso.com e três servidores front-end, você criaria as seguintes entradas DNS:
    
    
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
    
    Para obter detalhes sobre a criação de registros de host DNS (A), consulte [Configurar registros de host DNS para o Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>Para habilitar o rodízio para Windows Server

1.  Clique em **Iniciar**, em **todos os programas**, em **Ferramentas administrativas**e, em seguida, clique em **DNS**.

2.  Expanda **DNS**, clique com o botão direito do mouse no servidor DNS que você deseja configurar e, em seguida, clique em **Propriedades**.

3.  Clique na guia **avançado** , selecione **habilitar rodízio** e **Habilitar classificação de máscara de rede**e, em seguida, clique em **OK**.
    
    ![Caixa de diálogo rodízio de DNS] (images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "Caixa de diálogo rodízio de DNS")

<div>


> [!NOTE]  
> Esse recurso deve ser habilitado por padrão.



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

