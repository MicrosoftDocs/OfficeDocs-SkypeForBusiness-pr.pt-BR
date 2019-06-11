---
title: 'Lync Server 2013: Criando registros de DNS para o Serviço de Autodiscover'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5307251e9c3dea202b08b48bf45e109ef19449ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Criando registros de DNS para o Serviço de Autodiscover no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-20_

Os usuários do Lync Mobile precisarão que você habilite a descoberta automática, e uma parte dela envolve a criação de alguns registros DNS (sistema de nomes de domínio). Dependendo das suas necessidades, você precisará do seguinte:

  - Um registro DNS interno para dar suporte a usuários móveis que estão se conectando dentro da rede da sua organização.

  - Um registro DNS externo ou público para dar suporte a usuários móveis que estão se conectando pela Internet

Por que ambos? Você precisa criar um registro DNS interno e um registro DNS externo para cada domínio SIP.

Os registros DNS que você cria podem ser registros (host) ou registros CNAME. Para ajudá-lo, vamos examinar como criar esses registros DNS internos e externos abaixo. Se você precisar fazer mais informações sobre os requisitos de DNS para usuários móveis, confira [os requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Criando um registro CNAME DNS interno

1.  Para criar um registro DNS interno, você precisará fazer logon em um servidor DNS na sua rede com uma conta de domínio que seja membro do grupo Domain admins ou um membro do grupo DnsAdmins.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas administrativas**e em **DNS**.

3.  Na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para o domínio do Active Directory onde o pool de directors do Lync Server 2013 e o pool de front-end estão instalados. (por exemplo, contoso. local).

4.  Verifique se há um registro de host A (AAAA para IPv6) para o seu pool de directors para um registro DNS interno, deve haver um registro de host a para o nome de domínio totalmente qualificado dos serviços Web internos (FQDN) do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local). Se não estiver aqui, você pode não estar usando um pool de directors, e você precisará usar o FQDN para o seu pool Front-end ou mesmo para um único FQDN do servidor, se for a sua configuração.

5.  Lembre-se disso, verifique e veja se existe um registro do host A (AAAA para IPv6) para o seu pool de front-end para um registro DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local). Se não tiver, você precisará anotar o FQDN do servidor front-end ou do servidor Standard Edition.

6.  Quando souber o que os registros do host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda as **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).

7.  Clique com o botão direito do mouse no nome do domínio SIP e, em seguida, clique em **novo alias (CNAME)**.

8.  Em **nome do alias**, digite lyncdiscoverinternal como o nome do host para a URL do serviço de descoberta automática interna.

9.  Em **nome de domínio totalmente qualificado (FQDN) para o host de destino**, digite ou navegue até o FQDN de serviços Web internos para o seu pool de diretor (por exemplo, lyncwebdir01. contoso. local) e clique em **OK**.

10. Você deve criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP ao qual você dá suporte no ambiente do Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Criando um registro CNAME DNS externo

1.  Para criar um registro CNAME DNS externo, você precisará se conectar ao seu provedor de DNS público e seguir nossas etapas. Não podemos descrever exatamente onde você está no ambiente do seu provedor DNS, pois pode haver diferentes maneiras de gerenciar seu DNS externo, mas esperamos que estas etapas ajudem.

2.  Conecte-se ao seu provedor de DNS externo com uma conta que possa criar registros de DNS nesse ambiente.

3.  Você já deve ter um domínio SIP criado para esse ambiente. Expanda a **zona de pesquisa direta** para este domínio SIP ou selecione-o, dependendo da interface DNS externa sendo usada.

4.  Você já deve ver um registro do host A (AAAA para IPv6) para o seu pool de diretor (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá. Se não for, você pode não estar usando um pool de directors. Se for esse o caso, você precisará usar o FQDN do seu pool Front-end, ou se estiver fazendo isso para um único servidor, para o servidor front-end ou o servidor Standard Edition.

5.  Você também precisará confirmar que um registro do host A (AAAA para IPv6) existe para o seu nome de domínio totalmente qualificado dos serviços Web (FQDN) do seu pool Front-end (como lyncwebextpool01.contoso.com) ou um FQDN para o FQDN do servidor único, se você não tiver um pool de front-ends. Conforme observado na etapa anterior, você precisará disso abaixo se não tiver um pool de directors.

6.  Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo alias (CNAME)** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).

7.  Deve haver alguma forma de caixa de texto **nome do alias** , como com o DNS interno, você deve digitar lyncdiscover como o nome do host para a URL do serviço de descoberta automática externa.

8.  Também deve haver uma forma de um **FQDN (nome de domínio totalmente qualificado) para a caixa de texto de host de destino** , aqui você irá inserir o FQDN de serviços Web externos para o seu pool de diretor (por exemplo, lyncwebexdir01.contoso.com) e clicar em OK ou levar o que for ação no DNS externo para aceitar a criação dessa entrada. Conforme observado na etapa 4, acima, se você não tiver um pool de directors, será necessário usar o FQDN do pool de front-end ou o FQDN do servidor único que você configurou, conforme apropriado.

9.  Você precisará criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Criando um registro DNS interno A

1.  Para criar um registro DNS interno, faça logon em um servidor DNS na sua rede com uma conta de domínio que seja membro do grupo Domain admins ou um membro do grupo DnsAdmins.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas administrativas**e em **DNS**.

3.  Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para o seu domínio do Active Directory (por exemplo, contoso. local) onde o pool de directors do Lync Server 2013 e o pool de front-ends estão instalados.

4.  Verifique se há um registro de host A (AAAA para IPv6) para o seu pool de directors para um registro DNS interno, deve haver um registro de host a para o nome de domínio totalmente qualificado dos serviços Web internos (FQDN) do seu pool de diretor (por exemplo, lyncwebdir01. contoso. local). Se não estiver aqui, você pode não estar usando um pool de directors, e você precisará usar o endereço IP do seu pool Front-end ou até mesmo um único endereço IP de servidor, se for a sua configuração.

5.  Lembre-se disso, verifique e veja se existe um registro do host A (AAAA para IPv6) para o seu pool de front-end para um registro DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local). Se não tiver, você precisará anotar o endereço IP do servidor front-end ou do servidor Standard Edition.

6.  Quando souber o que os registros do host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda as **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).

7.  Clique com o botão direito do mouse no nome do domínio SIP e clique em **novo host (A ou aaaa)**.

8.  Em **nome**, digite lyncdiscoverinternal como o nome do host para a URL do serviço de descoberta automática interna.

9.  Em **endereço IP**, digite o endereço IP dos serviços Web internos do diretor (ou, se você usar um balanceador de carga, digite o IP virtual (VIP) do balanceador de carga do diretor). Conforme observado na etapa 4 acima, se você não estiver usando um director, talvez seja necessário inserir o endereço IP do servidor front-end ou o servidor Standard Edition ou, se você usar um balanceador de carga, digite o VIP do balanceador de carga do pool de front-end.

10. Clique em **Adicionar host**e, em seguida, clique em **OK**.

11. Para criar um registro adicional ou AAAA, repita as etapas de 8 a 10, lembrando-se de que você precisará criar novos registros de descoberta automática ou AAAA na zona de pesquisa direta de cada domínio SIP com suporte no ambiente do Lync Server 2013.

12. Quando terminar de criar os registros (para IPv6, AAAA), clique em **concluído**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Criando um registro DNS externo

1.  Para criar um registro DNS externo, conecte-se ao seu provedor de DNS público e siga nossas etapas. Não podemos descrever exatamente onde você está no ambiente do seu provedor DNS, pois pode haver diferentes maneiras de gerenciar seu DNS externo, mas esperamos que estas etapas ajudem.

2.  Você precisará estar conectado como uma conta que pode criar registros DNS nesse ambiente.

3.  Para um registro DNS externo, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com). Para um registro DNS externo, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).

4.  Você já deve ver um registro do host A (AAAA para IPv6) para o seu pool de diretor (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá e o endereço IP. Se não for, você pode não estar usando um pool de directors. Se for esse o caso, você precisará usar o endereço IP do seu pool de front-end ou, se estiver fazendo isso para um único servidor, para o servidor front-end ou o servidor Standard Edition. Lembre-se de que seus servidores também podem estar atrás de um balanceador de carga ou usando um proxy reverso. Anote os endereços IP também para seguir as etapas abaixo.

5.  Você também precisará confirmar que um registro do host A (AAAA para IPv6) existe para o nome de domínio totalmente qualificado de seus serviços Web (FQDN) para seu pool de front-end (como lyncwebextpool01.contoso.com) ou um endereço IP para a instalação do Lync de servidor único se você Não tem um pool de front-ends. Conforme observado na etapa anterior, você precisará disso abaixo se não tiver um pool de directors.

6.  Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo host a ou aaaa** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).

7.  Deve haver um local para inserir um **nome**, digite lyncdiscover como o nome do host para a URL do serviço de descoberta automática externa.

8.  Também deve haver uma caixa de texto de **endereço IP** , aqui está onde você digitará o IP para o seu pool de diretor (por exemplo, lyncwebexdir01.contoso.com) ou o IP do balanceador de carga do pool (ou um IP de proxy reverso que leva ao mesmo) e, em seguida, clique em OK ou execute qualquer ação no DNS externo para aceitar a criação dessa entrada. Conforme observado na etapa 4, acima, se você não tiver um pool de directors, será necessário usar o endereço IP do pool de front-end ou o endereço IP do servidor único que você configurou, conforme apropriado.

9.  Você precisará criar um novo registro de descoberta automática A ou AAAA na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

