---
title: 'Lync Server 2013: Configurando o DNS para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c490cac475f3b9a9c8038636f4ac7f6670f22637
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configurando o DNS para descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-12_

Para dar suporte à descoberta automática de clientes do Lync, você precisa criar os seguintes registros de sistema de nome de domínio (DNS):

  - Um registro DNS interno para dar suporte a clientes do Lync que se conectam dentro da rede da sua organização

  - Um registro DNS externo ou público para dar suporte a clientes do Lync que se conectam pela Internet

Você deve criar um registro DNS interno e um registro DNS externo para cada domínio SIP.

Os registros DNS podem ser registros (host) ou registros CNAME, com base na sua capacidade de criar novos certificados com o nome alternativo de requerente (SAN) adicional. Se não for possível solicitar e implantar um novo certificado externo (público) com o lyncdiscover. \<nome\> de domínio San, use o procedimento para usar a porta http/TCP 80. Os procedimentos a seguir descrevem como criar registros DNS internos e externos.

<div>

## <a name="to-create-dns-cname-records"></a>Para criar registros CNAME DNS

1.  Faça logon em um servidor DNS da seguinte forma:
    
      - Para criar um registro DNS interno, faça logon em um servidor DNS na sua rede como membro do grupo Domain admins ou um membro do grupo DnsAdmins.
    
      - Para criar um registro DNS externo, conecte-se ao seu provedor de DNS público.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas administrativas**e em **DNS**.

3.  Siga um destes procedimentos:
    
      - Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio do Active Directory (por exemplo, contoso. local).
        
        <div>
        

        > [!NOTE]  
        > Este domínio é o domínio do Active Directory onde o pool de&nbsp;directors e o pool de front-ends do Lync Server 2013 estão instalados.

        
        </div>
    
      - Para um registro DNS externo, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).

4.  Verifique se existe um registro de host para o pool de diretor da seguinte maneira:
    
      - Para um registro DNS interno, deve haver um registro de host a para o nome de domínio totalmente qualificado dos serviços Web (FQDN) do seu pool de directors (por exemplo, lyncwebdir01. contoso. local).
    
      - Para um registro DNS externo, deve haver um registro de host a para o FQDN de serviços Web externos para o seu pool de diretor (por exemplo, lyncwebextdir.contoso.com).

5.  Verifique se existe um registro de host para o seu pool Front-end da seguinte maneira:
    
      - Para um registro DNS interno, deve haver um registro de host a para o FQDN de serviços Web internos do seu pool de front-end (por exemplo, lyncwebpool01. contoso. local).
    
      - Para um registro DNS externo, deve haver um registro de host a para o FQDN de serviços Web externos para o seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).

6.  Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Se você estiver criando um registro DNS externo, as <STRONG>zonas de pesquisa direta</STRONG> já estão expandidas para seu domínio SIP da etapa 3.

    
    </div>

7.  Clique com o botão direito do mouse no nome do domínio SIP e, em seguida, clique em **novo alias (CNAME)**.

8.  Em **nome do alias**, digite um destes procedimentos:
    
      - Para um registro DNS interno, digite lyncdiscoverinternal como o nome de host para a URL do serviço de descoberta automática interna.
    
      - Para um registro DNS externo, digite lyncdiscover como o nome de host para a URL do serviço de descoberta automática externa.

9.  Em **nome de domínio totalmente qualificado (FQDN) do host de destino**, siga um destes procedimentos:
    
      - Para um registro DNS interno, digite ou navegue até o FQDN de serviços Web internos do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local) e clique em **OK**.
    
      - Para um registro DNS externo, digite ou navegue até o FQDN de serviços Web externos para o seu pool de diretor (por exemplo, lyncwebextdir.contoso.com) e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se você não usar um director, use o FQDN de serviços Web internos e externos para o pool de front-ends ou, para um único servidor, o FQDN para o servidor front-end ou o servidor Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Você deve criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP ao qual você dá suporte no ambiente do Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Para criar registros DNS A

1.  Faça logon em um servidor DNS da seguinte forma:
    
      - Para criar um registro DNS interno, faça logon em um servidor DNS na sua rede como membro do grupo Domain admins ou um membro do grupo DnsAdmins.
    
      - Para criar um registro DNS externo, conecte-se ao seu provedor DNS público ou servidor DNS externo.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas administrativas**e em **DNS**.

3.  Siga um destes procedimentos:
    
      - Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio do Active Directory (por exemplo, contoso. local).
        
        <div>
        

        > [!NOTE]  
        > Este domínio é o domínio do Active Directory onde o pool de&nbsp;directors e o pool de front-ends do Lync Server 2013 estão instalados.

        
        </div>
    
      - Para um registro DNS externo, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).

4.  Verifique se há um registro do host A (para IPv6, AAAA) para o seu pool de directors da seguinte maneira:
    
      - Para um registro DNS interno, deve haver um registro de host A (para IPv6, AAAA) para o FQDN de serviços Web internos do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local).
    
      - Para um registro DNS externo, deve haver um registro de host A (para IPv6, AAAA) para o FQDN de serviços Web externos para o seu pool de diretor (por exemplo, lyncwebextdir.contoso.com).

5.  Verifique se há um registro do host A (para IPv6, AAAA) para o seu pool Front-end da seguinte maneira:
    
      - Para um registro DNS interno, deve haver um registro de host A (para IPv6, AAAA) para o FQDN de serviços Web internos para o seu pool de front-end (por exemplo, lyncwebpool01. contoso. local).
    
      - Para um registro DNS externo, deve haver um registro de host A (para IPv6, AAAA) para o FQDN de serviços Web externos para o seu pool de front-end (por exemplo, lyncwebextpool01.contoso.com).

6.  Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Se você estiver criando um registro DNS externo, as <STRONG>zonas de pesquisa direta</STRONG> já estão expandidas para seu domínio SIP da etapa 3.

    
    </div>

7.  Clique com o botão direito do mouse no nome do domínio SIP e clique em **novo host (A ou aaaa)**.

8.  Em **nome**, digite o nome do host da seguinte maneira:
    
      - Para um registro DNS interno, digite lyncdiscoverinternal como o nome de host para a URL do serviço de descoberta automática interna.
    
      - Para um registro DNS externo, digite lyncdiscover como o nome de host para a URL do serviço de descoberta automática externa.
    
    <div>
    

    > [!NOTE]  
    > O nome do domínio é presumido na zona na qual o registro é definido e, portanto, não precisa ser inserido como parte do registro A.

    
    </div>

9.  Em **endereço IP**, digite o endereço IP da seguinte maneira:
    
      - Para um registro DNS interno, digite o endereço IP dos serviços Web internos do diretor (ou, se você usar um balanceador de carga, digite o IP virtual (VIP) do balanceador de carga do diretor).
        
        <div>
        

        > [!NOTE]  
        > Se você não usar um director, digite o endereço IP do servidor front-end ou do servidor Standard Edition, ou, se usar um balanceador de carga, digite o VIP do balanceador de carga do pool de front-end.

        
        </div>
    
      - Para um registro DNS externo, digite o endereço IP externo ou público do proxy reverso.

10. Clique em **Adicionar host**e, em seguida, clique em **OK**.

11. Para criar um registro adicional adicional, repita as etapas 8 a 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Você deve criar um novo lyncdiscover e lyncdiscoverinternal registros na zona de pesquisa direta de cada domínio SIP para o qual você dá suporte no ambiente do Lync Server 2013.

    
    </div>

12. Quando terminar de criar os registros (para IPv6, AAAA), clique em **concluído**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

