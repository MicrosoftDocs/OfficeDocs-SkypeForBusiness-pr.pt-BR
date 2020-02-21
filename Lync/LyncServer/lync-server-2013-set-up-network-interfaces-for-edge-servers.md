---
title: 'Lync Server 2013: configurar interfaces de rede para servidores de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 267db7062c19a0b1344d11f27205a51bf1e750ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Configurar interfaces de rede para servidores de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Cada Servidor de Borda é um computador multihomed com interfaces externas e internas. As configurações de DNS do adaptador dependem da existência de servidores DNS na rede de perímetro. Se houver servidores DNS no perímetro, eles deverão ter uma zona contendo um ou mais registros A DNS para o servidor ou pool de próximo salto (ou seja, um Diretor ou um pool de Front-Ends designado) e, para consultas externas, eles farão referência a pesquisas de nome para outros servidores DNS públicos. Se não houver servidores DNS no perímetro, os Servidores de Borda usarão servidores DNS externos para resolver pesquisas de nome da Internet, e cada Servidor de Borda usará um HOST para resolver os nomes de servidor de próximo salto para endereços IP.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Por motivos de segurança, recomendamos que seus Servidores de Borda não acessem um servidor DNS localizado na rede interna.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces com os servidores DNS na rede de perímetro

1.  Instale dois adaptadores de rede para cada Servidor de Borda, um para a interface interna e outro para a interface externa.
    
    <div>
    

    > [!IMPORTANT]  
    > As sub-redes interna e externa não devem ser roteáveis ente si.

    
    </div>

2.  Na interface externa, configure três endereços IP estáticos na sub-rede da rede de perímetro externa (também conhecida como DMZ, zona desmilitarizada, e sub-rede filtrada), e aponte o gateway padrão à interface interna do firewall externo. Defina as configurações DNS do adaptador para apontar para um par de servidores DNS de perímetro.
    
    <div>
    

    > [!NOTE]  
    > É possível usar um endereço IP para essa interface, mas para fazer isso você precisa alterar as atribuições de porta para valores não padrão. Você determina isso ao criar a topologia no construtor de topologias.

    
    </div>

3.  Na interface interna, configure um endereço IP estático na sub-rede da rede de perímetro e não defina o gateway padrão. Defina as configurações DNS do adaptador a fim de apontar para pelo menos um servidor DNS, preferencialmente um par de servidores DNS de perímetro.

4.  Crie rotas estáticas persistentes na interface interna para todas as redes internas nas quais os clientes, o Lync Server 2013 e os servidores da UM (Unificação de mensagens) do Exchange residem.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces sem servidores DNS na rede de perímetro

1.  Instale dois adaptadores de rede para cada Servidor de Borda, um para a interface interna e outro para a interface externa.
    
    <div>
    

    > [!IMPORTANT]  
    > As sub-redes interna e externa não devem ser roteáveis ente si.

    
    </div>

2.  Na interface externa, configure três endereços IP estáticos na sub-rede da rede de perímetro externa. Também é possível configurar o gateway padrão na interface externa. Por exemplo, defina o roteador da Internet ou o firewall externo como o gateway padrão. Defina as configurações de DNS a fim de apontar para um servidor DNS, preferencialmente para um par de servidores DNS externos.
    
    <div>
    

    > [!NOTE]  
    > É possível, mas não recomendado, usar um endereço IP para a interface externa. Para que isso funcione, você precisa alterar as atribuições de porta para valores não padrão e para longe da porta padrão 443 que normalmente é “amigável com firewall” para a comunicações do cliente. Você determina a configuração de endereço IP e as configurações de porta ao criar a topologia no construtor de topologias.

    
    </div>

3.  Na interface interna, configure um endereço IP estático na sub-rede da rede de perímetro e não defina o gateway padrão. Deixe as configurações DNS do adaptador vazias.

4.  Crie rotas estáticas persistentes na interface interna para todas as redes internas nas quais os clientes do Lync ou servidores que executam o Lync Server 2013 residem.

5.  Edite o arquivo HOST em cada servidor de borda para que contenha um registro para o próximo servidor de salto ou IP virtual (VIP) (o registro será o diretor, servidor Standard Edition ou um pool de front-ends configurado como o endereço de próximo salto do servidor de borda no construtor de topologias). Se você estiver usando o balanceamento de carga DNS, inclua uma linha para cada membro do pool de próximo salto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

