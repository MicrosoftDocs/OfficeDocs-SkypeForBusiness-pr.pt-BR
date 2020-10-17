---
title: 'Lync Server 2013: Configurando o DNS para descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 249993e68930db1eb5dd5159633a73f80cef8c05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520048"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a>Configurando o DNS para descoberta automática no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-12_

Para dar suporte à descoberta automática para clientes do Lync, você precisa criar os seguintes registros DNS (sistema de nomes de domínio):

  - Um registro DNS interno para dar suporte aos clientes do Lync que se conectam de dentro da rede da sua organização

  - Um registro DNS externo ou público para suportar os clientes do Lync que se conectam a partir da Internet

Você deve um registro de DNS interno e um externo para cada domínio SIP.

Os registros DNS podem ser registros A (host) ou registros CNAME, com base na sua capacidade de criar novos certificados com o nome alternativo de entidade (SAN) adicional. Se você não conseguir solicitar e implantar um novo certificado externo (público) com o lyncdiscover.\<domain name\> SAN, use o procedimento para usar a porta 80 HTTP/TCP. Os procedimentos a seguir descrevem como criar registros de DNS internos e externos.

<div>

## <a name="to-create-dns-cname-records"></a>Para criar registros de DNS CNAME

1.  Faça o logon em um servidor de DNS conforme segue:
    
      - Para criar um registro de DNS interno, faça o logon em um servidor de DNS em sua rede como membro dos grupos Admins de Domínio ou DnsAdmins.
    
      - Para criar um registro de DNS externo, conecte-se ao provedor de DNS público.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.

3.  Siga um destes procedimentos:
    
      - Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do Active Directory (por exemplo, contoso.local).
        
        <div>
        

        > [!NOTE]  
        > Esse domínio é o domínio do Active Directory no qual o pool de diretores do Lync Server 2013 &nbsp; e o pool de front-ends estão instalados.

        
        </div>
    
      - Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).

4.  Verifique se existe um registro de host A para o pool de diretores da seguinte maneira:
    
      - Para um registro de DNS interno, um registro de host A deve existir para o FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para seu pool de diretores (por exemplo, lyncwebdir01. contoso. local).
    
      - Para um registro DNS externo, um registro de host A deve existir para o FQDN de serviços Web externos para seu pool de diretor (por exemplo, lyncwebextdir.contoso.com).

5.  Verifique se existe um registro de host A para o seu pool de front-ends da seguinte maneira:
    
      - Para um registro de DNS interno, um registro de host A deve existir para o FQDN de serviços Web internos para seu pool de front-ends (por exemplo, lyncwebpool01. contoso. local).
    
      - Para um registro DNS externo, um registro de host A deve existir para o FQDN de serviços Web externos para seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).

6.  Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Se você estiver criando um registro de DNS externo, <STRONG>Zonas de Pesquisa Direta</STRONG> já está expandido para o domínio SIP da etapa 3.

    
    </div>

7.  Clique com o botão direito no nome do domínio SIP e em **Novo Alias (CNAME)**.

8.  Em **Nome do alias**, digite uma das seguintes opções:
    
      - Para um registro de DNS interno, digite lyncdiscoverinternal como o nome de host para a URL do Serviço de Descoberta Automática interno.
    
      - Para um registro de DNS externo, digite lyncdiscover como o nome de host para a URL do Serviço de Descoberta Automática externo.

9.  Em **Nome de domínio totalmente qualificado (FQDN) para o host de destino**, siga um destes procedimentos:
    
      - Para um registro de DNS interno, digite ou procure o FQDN de serviços Web internos para o seu pool de diretor (por exemplo, lyncwebdir01. contoso. local) e clique em **OK**.
    
      - Para um registro DNS externo, digite ou procure o FQDN dos serviços Web externos para o seu pool de diretores (por exemplo, lyncwebextdir.contoso.com) e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Se você não usar um diretor, use o FQDN de serviços Web internos e externos para o pool de front-ends ou, para um único servidor, o FQDN para o servidor front-end ou servidor Standard Edition.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Você deve criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a>Para criar registros de DNS A

1.  Faça o logon em um servidor de DNS conforme segue:
    
      - Para criar um registro de DNS interno, faça o logon em um servidor de DNS em sua rede como membro dos grupos Admins de Domínio ou DnsAdmins.
    
      - Para criar um registro DNS externo, conecte-se ao seu provedor de DNS público ou servidor DNS externo.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.

3.  Siga um destes procedimentos:
    
      - Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do Active Directory (por exemplo, contoso.local).
        
        <div>
        

        > [!NOTE]  
        > Esse domínio é o domínio do Active Directory no qual o pool de diretores do Lync Server 2013 &nbsp; e o pool de front-ends estão instalados.

        
        </div>
    
      - Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).

4.  Verifique se existe um registro de host A (para IPv6, AAAA) para o pool de diretores da seguinte maneira:
    
      - Para um registro de DNS interno, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web internos do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local).
    
      - Para um registro DNS externo, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web externos para o seu pool de diretor (por exemplo, lyncwebextdir.contoso.com).

5.  Verifique se existe um registro de host A (para IPv6, AAAA) para o pool de front-ends da seguinte maneira:
    
      - Para um registro de DNS interno, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web internos para seu pool de front-ends (por exemplo, lyncwebpool01. contoso. local).
    
      - Para um registro DNS externo, um registro de host A (para IPv6, AAAA) deve existir para o FQDN de serviços Web externos para seu pool de front-ends (por exemplo, lyncwebextpool01.contoso.com).

6.  Para um registro de DNS interno, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).
    
    <div>
    

    > [!NOTE]  
    > Se você estiver criando um registro de DNS externo, <STRONG>Zonas de Pesquisa Direta</STRONG> já está expandido para o domínio SIP da etapa 3.

    
    </div>

7.  Clique com o botão direito no nome do domínio SIP e em **Novo Host (A ou AAAA)**.

8.  Em **Nome**, digite o nome do host conforme segue:
    
      - Para um registro de DNS interno, digite lyncdiscoverinternal como o nome de host para a URL do Serviço de Descoberta Automática interno.
    
      - Para um registro de DNS externo, digite lyncdiscover como o nome de host para a URL do Serviço de Descoberta Automática externo.
    
    <div>
    

    > [!NOTE]  
    > O nome de domínio é suposto a partir da zona em que o registro está definido e, portanto, não precisa ser inserido como parte do registro A.

    
    </div>

9.  Em **Endereço IP**, digite o endereço IP conforme segue:
    
      - Para um registro de DNS interno, digite o endereço IP dos serviços Web internos do diretor (ou, se você usar um balanceador de carga, digite o IP virtual (VIP) do balanceador de carga do diretor).
        
        <div>
        

        > [!NOTE]  
        > Se você não usar um diretor, digite o endereço IP do servidor front-end ou servidor Standard Edition, ou, se você usar um balanceador de carga, digite o VIP do balanceador de carga do pool de front-ends.

        
        </div>
    
      - Para um registro de DNS externo, digite o endereço IP externo ou público do proxy reverso.

10. Clique em **Adicionar Host** e, em seguida, clique em **OK**.

11. Para criar um registro A adicional, repita as etapas 8 a 10.
    
    <div>
    

    > [!IMPORTANT]  
    > Você deve criar um novo lyncdiscover e lyncdiscoverinternal registros a na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.

    
    </div>

12. Quando terminar de criar os registros A (para IPv6, AAAA), clique em **Concluído**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

