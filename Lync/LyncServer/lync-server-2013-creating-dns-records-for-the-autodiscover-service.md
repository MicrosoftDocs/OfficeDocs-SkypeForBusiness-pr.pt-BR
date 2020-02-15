---
title: 'Lync Server 2013: criar registros DNS para o serviço de descoberta automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a3c9e3b3aaecef519a2fbc23d5955a5be4fa0d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a>Criar registros DNS para o serviço de descoberta automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-20_

Seus usuários móveis do Lync precisarão que você habilite a descoberta automática e uma parte dele envolve a criação de alguns registros de DNS (sistema de nomes de domínio). Dependendo das suas necessidades, você precisará do seguinte:

  - Um registro DNS interno para dar suporte a usuários móveis que estão se conectando dentro da rede da sua organização.

  - Um registro DNS externo ou público para suportar usuários móveis que estão se conectando a partir da Internet

Por que ambos? Você precisa criar um registro de DNS interno e um registro de DNS externo para cada domínio SIP.

Os registros DNS que você cria podem ser registros A (host) ou registros CNAME. Para ajudá-lo, vamos examinar como criar esses registros de DNS internos e externos abaixo. Se você precisar fazer mais leituras sobre os requisitos de DNS para usuários móveis, confira [os requisitos técnicos de mobilidade no Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

<div>

## <a name="creating-an-internal-dns-cname-record"></a>Criando um registro CNAME de DNS interno

1.  Para criar um registro DNS interno, você precisará fazer logon em um servidor DNS na sua rede com uma conta de domínio que seja membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.

3.  Na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para o domínio do Active Directory onde o pool de diretores do Lync Server 2013 e o pool de front-ends estão instalados. (por exemplo, contoso. local).

4.  Verifique se existe um registro de host A (AAAA para IPv6) para o pool de diretores de um registro de DNS interno, um registro de host A deve existir para o FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para seu pool de diretores (por exemplo, lyncwebdir01. contoso. local). Se ele não estiver aqui, talvez você não esteja usando um pool de diretores e você precisará usar o FQDN para seu pool de front-ends ou até mesmo um único FQDN de servidor, se essa for sua configuração.

5.  Tendo isso em mente, verifique se existe um registro de host A (AAAA para IPv6) para o seu pool de front-ends de um registro de DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local). Caso contrário, você precisará anotar o FQDN do servidor front-end ou do servidor Standard Edition.

6.  Quando você souber quais registros de host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).

7.  Clique com o botão direito no nome do domínio SIP e em **Novo Alias (CNAME)**.

8.  Em **nome do alias**, digite lyncdiscoverinternal como o nome do host para a URL interna do serviço de descoberta automática.

9.  Em **nome de domínio totalmente qualificado (FQDN) para o host de destino**, digite ou procure o FQDN dos serviços Web internos para o seu pool de diretores (por exemplo, lyncwebdir01. contoso. local) e clique em **OK**.

10. Você deve criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a>Criando um registro CNAME de DNS externo

1.  Para criar um registro CNAME de DNS externo, você precisará se conectar ao seu provedor de DNS público e seguir as etapas. Não é possível descrever exatamente onde você está no ambiente de seu provedor de DNS, já que pode haver maneiras diferentes de gerenciar seu DNS externo, mas esperamos que essas etapas ajudem.

2.  Faça logon no provedor de DNS externo com uma conta que possa criar registros DNS nesse ambiente.

3.  Você já deve ter um domínio SIP criado para esse ambiente. Expanda a **zona de pesquisa direta** para este domínio SIP ou selecione-a, dependendo da interface DNS externa que está sendo usada.

4.  Você já deve ter um registro de host A (AAAA para IPv6) para o seu pool de diretores (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá. Caso contrário, talvez você não esteja usando um pool de diretores. Se esse for o caso, você precisará usar o FQDN do seu pool de front-ends ou se estiver fazendo isso para um único servidor, para o servidor front-end ou servidor Standard Edition.

5.  Você também precisará confirmar se um registro de host A (AAAA para IPv6) existe para o nome de domínio totalmente qualificado (FQDN) dos serviços Web externos para seu pool de front-ends (como lyncwebextpool01.contoso.com) ou um FQDN para o FQDN de servidor único, se não houver pool de front-ends. Conforme observado na etapa anterior, você precisará disso, se não tiver um pool de diretores.

6.  Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo alias (CNAME)** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).

7.  Deve haver alguma forma de caixa de texto **nome do alias** como com o DNS interno, você deve inserir lyncdiscover como o nome do host para a URL externa do serviço de descoberta automática.

8.  Também deve haver alguma forma de um **FQDN (nome de domínio totalmente qualificado) para** a caixa de texto host de destino, aqui, onde você inserirá o FQDN de serviços Web externos para o seu pool de diretores (por exemplo, lyncwebexdir01.contoso.com) e clicará em OK ou executará qualquer ação no DNS externo para aceitar a criação dessa entrada. Conforme observado na etapa 4, acima, se você não tiver um pool de diretores, será necessário usar o FQDN do pool de front-ends ou o FQDN do servidor único que você configurou, conforme apropriado.

9.  Você precisará criar um novo registro CNAME de descoberta automática na zona de pesquisa direta de cada domínio SIP suportado em seu ambiente do Lync 2013.

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a>Criando um registro de DNS interno

1.  Para criar um registro DNS interno, faça logon em um servidor DNS da sua rede com uma conta de domínio que seja membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.

2.  Abra o snap-in administrativo do DNS: clique em **Iniciar**, em **Ferramentas Administrativas** e **DNS**.

3.  Para um registro DNS interno, na árvore de console do servidor DNS, expanda **zonas de pesquisa direta** para seu domínio do Active Directory (por exemplo, contoso. local) onde o pool de diretor do Lync Server 2013 e o pool de front-ends estão instalados.

4.  Verifique se existe um registro de host A (AAAA para IPv6) para o pool de diretores de um registro de DNS interno, um registro de host A deve existir para o FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para seu pool de diretores (por exemplo, lyncwebdir01. contoso. local). Se ele não estiver aqui, talvez você não esteja usando um pool de diretores e você precisará usar o endereço IP para seu pool de front-ends ou mesmo um endereço IP de servidor único, se essa for sua configuração.

5.  Tendo isso em mente, verifique se existe um registro de host A (AAAA para IPv6) para o seu pool de front-ends de um registro de DNS interno, um registro de host A (ou AAAA) deve existir para o FQDN de serviços Web internos do seu pool de front-ends (por exemplo, , lyncwebpool01. contoso. local). Caso contrário, você precisará anotar o endereço IP do servidor front-end ou do servidor Standard Edition.

6.  Quando você souber quais registros de host A (ou AAAA) existem, na árvore de console do seu servidor DNS, expanda **zonas de pesquisa direta** para seu domínio SIP (por exemplo, contoso.com).

7.  Clique com o botão direito no nome do domínio SIP e em **Novo Host (A ou AAAA)**.

8.  Em **nome**, digite lyncdiscoverinternal como o nome do host para a URL interna do serviço de descoberta automática.

9.  Em **endereço IP**, digite o endereço IP do serviço Web interno do diretor (ou, se você usar um balanceador de carga, digite o IP virtual (VIP) do balanceador de carga do diretor). Conforme observado na etapa 4 acima, se você não estiver usando um diretor, talvez seja necessário inserir o endereço IP do servidor front-end ou servidor Standard Edition ou, se você usar um balanceador de carga, digite o VIP do balanceador de carga do pool de front-ends.

10. Clique em **Adicionar Host** e, em seguida, clique em **OK**.

11. Para criar um registro A ou AAAA adicional, repita as etapas de 8 a 10, lembrando que você precisará criar novos registros de descoberta automática ou AAAA na zona de pesquisa direta de cada domínio SIP com suporte no seu ambiente do Lync Server 2013.

12. Quando terminar de criar os registros A (para IPv6, AAAA), clique em **Concluído**.

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a>Criando um registro de DNS externo

1.  Para criar um registro de DNS externo, conecte-se ao seu provedor de DNS público e siga nossas etapas. Não é possível descrever exatamente onde você está no ambiente de seu provedor de DNS, já que pode haver maneiras diferentes de gerenciar seu DNS externo, mas esperamos que essas etapas ajudem.

2.  Você precisará estar conectado como uma conta que pode criar registros DNS nesse ambiente.

3.  Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com). Para um registro de DNS externo, na árvore de console do servidor de DNS, expanda **Zonas de Pesquisa Direta** para seu domínio do SIP (por exemplo, contoso.com).

4.  Você já deve ter um registro de host A (AAAA para IPv6) para o seu pool de diretores (como lyncwebexdir01.contoso.com), portanto, confirme se ele está lá e o endereço IP. Caso contrário, talvez você não esteja usando um pool de diretores. Se esse for o caso, você precisará usar o endereço IP do seu pool de front-ends ou se estiver fazendo isso para um único servidor, para o servidor front-end ou servidor Standard Edition. Tenha em mente que seus servidores também podem estar atrás de um balanceador de carga ou usando um proxy reverso. Anote os endereços IP também para seguir as etapas abaixo.

5.  Você também precisará confirmar se um registro de host A (AAAA para IPv6) existe para seu nome de domínio totalmente qualificado (FQDN) dos serviços Web externos para seu pool de front-ends (como lyncwebextpool01.contoso.com) ou um endereço IP para a sua instalação do Lync de servidor único se você Não têm pool de front-ends. Conforme observado na etapa anterior, você precisará disso, se não tiver um pool de diretores.

6.  Agora, no formato apropriado para seu provedor de DNS externo, escolha a opção para criar um **novo host a ou aaaa** (isso pode ser uma opção de menu ou um link, dependendo do formato do provedor de DNS).

7.  Deve haver um local para inserir um **nome**, digite lyncdiscover como o nome do host para a URL externa do serviço de descoberta automática.

8.  Também deve haver uma caixa de texto de **endereço IP** , aqui, onde você inserirá o IP para o seu pool de diretores (por exemplo, lyncwebexdir01.contoso.com) ou, possivelmente, o IP do balanceador de carga do pool (ou um IP de proxy reverso que leva ao mesmo) e clique em OK ou executar qualquer ação no DNS externo para aceitar a criação dessa entrada. Conforme observado na etapa 4, acima, se você não tiver um pool de diretores, será necessário usar o endereço IP do pool de front-ends ou o endereço IP do servidor único que você configurou, conforme apropriado.

9.  Você precisará criar um novo registro de descoberta automática ou AAAA na zona de pesquisa direta de cada domínio SIP suportado em seu ambiente do Lync 2013.

</div>

</div>

<span> </span>

</div>

</div>

</div>

