---
title: 'Lync Server 2013: Configurar interfaces de rede para Servidores de Borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7263c2d7cad3cf1339351f2cb5f90b15a9fa0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a>Configurar interfaces de rede para Servidores de Borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Cada servidor de borda é um computador com várias bases, com interfaces opostas externas e internas. As configurações de DNS (sistema de nomes de domínio) de adaptador dependem se há servidores DNS na rede de perímetro. Se houver servidores DNS no perímetro, eles devem ter uma zona contendo um ou mais registros DNS A para o próximo servidor ou pool de salto (ou seja, um diretor ou um pool Front-end designado) e para consultas externas, elas fazem referência a nomes de pesquisa para outros servidores DNS públicos. Se não existirem servidores DNS no perímetro, o (s) servidor (es) de borda usará servidores DNS externos para resolver pesquisas de nomes de Internet, e cada servidor de borda usará um HOST para resolver os nomes de servidor de salto seguinte para endereços IP.

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Por motivos de segurança, recomendamos que você não tenha seus servidores de borda acessarem um servidor DNS localizado na rede interna.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces com servidores DNS na rede de perímetro

1.  Instale dois adaptadores de rede para cada servidor de borda, um para a interface de face interna e outro para a interface de face externa.
    
    <div>
    

    > [!IMPORTANT]  
    > As sub-redes interna e externa não devem ser roteáveis ente si.

    
    </div>

2.  Na interface externa, configure três endereços IP estáticos na sub-rede externa de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada) e aponte o gateway padrão para a interface interna do firewall externo. Defina as configurações de DNS do adaptador para apontar para um par de servidores DNS do perímetro.
    
    <div>
    

    > [!NOTE]  
    > É possível usar o mínimo de um endereço IP para essa interface, mas para fazer isso, você precisa mudar as atribuições de porta para valores não padrão. Você determina isso quando cria a topologia no construtor de topologias.

    
    </div>

3.  Na interface interna, configure um endereço IP estático na sub-rede de rede de perímetro interna e não defina um gateway padrão. Defina as configurações de DNS do adaptador para apontar para pelo menos um servidor DNS, de preferência um par de servidores DNS de perímetro.

4.  Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes, o Lync Server 2013 e os servidores Exchange Unified Messaging (UM) residem.

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a>Para configurar interfaces sem servidores DNS na rede de perímetro

1.  Instale dois adaptadores de rede para cada servidor de borda, um para a interface de face interna e outro para a interface de face externa.
    
    <div>
    

    > [!IMPORTANT]  
    > As sub-redes interna e externa não devem ser roteáveis ente si.

    
    </div>

2.  Na interface externa, configure três endereços IP estáticos na sub-rede de rede do perímetro externo. Você também pode configurar o gateway padrão na interface externa. Por exemplo, defina o roteador voltado para a Internet ou o firewall externo como o gateway padrão. Defina as configurações de DNS para apontar para um servidor DNS, de preferência a um par de servidores DNS externos.
    
    <div>
    

    > [!NOTE]  
    > É possível, mas não recomendado, usar o mesmo que um endereço IP para a interface externa. Para permitir que isso funcione, você precisa mudar as atribuições de porta para valores não padrão e para longe da porta padrão 443 que geralmente é "compatível com firewall" para a comunicação do cliente. Você determina a configuração de endereço IP e as configurações de porta ao criar a topologia no construtor de topologias.

    
    </div>

3.  Na interface interna, configure um endereço IP estático na sub-rede de rede de perímetro interna e não defina um gateway padrão. Deixe as configurações de DNS do adaptador vazias.

4.  Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes ou servidores do Lync que executam o Lync Server 2013 se encontram.

5.  Edite o arquivo de HOST em cada servidor de borda para conter um registro para o próximo servidor de salto ou IP virtual (VIP) (o registro será o diretor, Standard Edition Server ou um pool de front-ends configurado como o próximo endereço de salto do servidor de borda no construtor de topologias). Se você estiver usando o balanceamento de carga de DNS, inclua uma linha para cada membro do próximo pool de saltos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

