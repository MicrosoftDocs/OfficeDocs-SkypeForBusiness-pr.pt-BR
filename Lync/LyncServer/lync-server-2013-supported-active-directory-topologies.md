---
title: 'Lync Server 2013: Topologias do Active Directory suportadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Topologias do Active Directory suportadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-10-02_

O Lync Server 2013 oferece suporte às mesmas topologias de serviços de domínio Active Directory que o Microsoft Lync Server 2010 e o Microsoft Office Communications Server 2007 R2. Há suporte para as seguintes topologias:

  - Floresta única com domínio único

  - Floresta única com uma única árvore e vários domínios

  - Floresta única com várias árvores e namespaces não contíguos

  - Várias florestas em uma topologia de floresta central

  - Várias florestas em uma topologia de floresta de recursos

  - Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online

A figura a seguir identifica os ícones usados nas ilustrações desta seção.

**Chave para ilustrações de topologia**

![Chave para ilustrações de topologia] (images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Chave para ilustrações de topologia")

<div>

## <a name="single-forest-single-domain"></a>Única floresta, único domínio

A topologia do Active Directory mais simples compatível com o Lync Server, uma floresta de domínio único, é uma topologia comum.

A figura a seguir ilustra uma implantação do Lync Server em uma única topologia de domínio do Active Directory.

**Topologia de domínio único**

![Topologia de domínio único] (images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologia de domínio único")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Única floresta, vários domínios

Outra topologia do Active Directory compatível com o Lync Server é uma única floresta que consiste em um domínio raiz e um ou mais domínios filho. Nesse tipo de topologia do Active Directory, o domínio em que você cria usuários pode ser diferente do domínio onde você implanta o Lync Server. No entanto, se você implantar um pool de front-end, deve implantar todos os servidores de front-end no pool dentro de um único domínio. O suporte do Lync Server para grupos de administradores universais do Windows permite a administração entre domínios.

A figura a seguir ilustra uma implantação em uma única floresta com vários domínios. Nesta figura, um ícone de usuário mostra o domínio no qual a conta de usuário é hospedada e a seta aponta para o domínio onde o pool do servidor do Lync reside. As contas de usuário incluem o seguinte:

  - Contas de usuário no mesmo domínio que o pool do Lync Server

  - Contas de usuário em um domínio diferente do pool do Lync Server

  - Contas de usuário em um domínio filho do domínio com o pool do Lync Server

**Floresta única com vários domínios**

![Floresta única com vários domínios] (images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Floresta única com vários domínios")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Única floresta, várias árvores

Uma topologia de floresta de várias árvores consiste em dois ou mais domínios que definem estruturas de árvore independentes e namespaces separados do Active Directory.

A figura a seguir ilustra uma única floresta com várias árvores. Nesta figura, um ícone de usuário mostra o domínio em que a conta de usuário é hospedada, uma linha sólida aponta para um pool do Lync Server que reside no mesmo domínio ou em um domínio diferente, e uma linha tracejada aponta para o pool do Lync Server que reside em uma árvore diferente. As contas de usuário incluem o seguinte:

  - Contas de usuário no mesmo domínio que o pool do Lync Server

  - Contas de usuário em um domínio diferente de (mas na mesma árvore que) o pool do servidor do Lync

  - Contas de usuário em uma árvore diferente do pool do Lync Server

**Floresta única com várias árvores**

![Floresta única com várias árvores] (images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Floresta única com várias árvores")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Várias florestas, floresta central

O Lync Server oferece suporte a várias florestas configuradas em uma topologia de floresta central. Topologias de floresta central usam objetos de contato na floresta central para representar usuários em outras florestas. A floresta central também hospeda contas de usuário para qualquer usuário dessa floresta. Um produto de sincronização de diretório, como o Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 ou Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida de contas de usuário em a organização: quando uma nova conta de usuário é criada em uma das florestas ou uma conta de usuário é excluída de uma floresta, o produto de sincronização de diretório sincroniza o contato correspondente na floresta central.

Uma floresta central tem as seguintes vantagens:

  - Os servidores que executam o Lync Server são centralizados em uma única floresta.

  - Os usuários podem pesquisar e se comunicar com outros usuários em qualquer floresta.

  - Os usuários podem ver a presença de outros usuários em qualquer floresta.

  - O produto de sincronização de diretório automatiza a adição e a exclusão de objetos de contato na floresta central, pois as contas de usuário são criadas ou removidas.

A figura a seguir ilustra uma topologia de floresta central. Nesta figura, há relações de confiança bidirecionais entre o domínio que hospeda o Lync Server, que está na floresta central, e cada domínio somente de usuário, que está em uma floresta separada. O esquema nas florestas de usuários separadas não precisa ser estendido.

**Topologia da floresta central**

![Topologia da floresta central] (images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologia da floresta central")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Várias florestas, floresta de recursos

Em uma topologia de floresta de recursos, uma floresta é dedicada à execução de aplicativos do servidor, como o Microsoft Exchange Server e o Lync Server. A floresta de recursos hospeda os aplicativos do servidor e uma representação sincronizada do objeto de usuário ativo, mas não contém contas de usuário habilitadas para logon. A floresta de recursos age como um ambiente de serviços compartilhados para as outras florestas em que os objetos do usuário residem. As florestas do usuário têm uma relação de confiança no nível da floresta com a floresta do recurso. Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário. Se o Microsoft Exchange já estiver implantado na floresta de recursos, talvez as contas de usuário desabilitadas já existam. Um produto de sincronização de diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário. Quando uma nova conta de usuário é criada em uma das florestas do usuário ou uma conta de usuário é excluída de uma floresta, o produto de sincronização de diretório sincroniza a representação de usuário correspondente na floresta de recursos.

Essa topologia pode ser usada para fornecer uma infraestrutura compartilhada para serviços nas organizações que gerenciam várias florestas ou para separar a administração de objetos do Active Directory de outras administração. As empresas que precisam isolar a administração do Active Directory por motivos de segurança muitas vezes escolhem essa topologia.

Essa topologia fornece a vantagem de limitar a necessidade de estender o esquema do Active Directory para uma única floresta (ou seja, a floresta de recursos).

O diagrama a seguir ilustra uma topologia de floresta de recursos.

**Topologia da floresta de recursos**

![Topologia da floresta de recursos do Active Directory] (images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologia da floresta de recursos do Active Directory")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online

Nessa topologia, uma ou mais florestas estão localizadas no local e são dedicadas à Hospedagem de contas de usuário do Active Directory. A floresta de recursos está localizada fora do local e é mantida por um provedor de Hospedagem de terceiros. A floresta de recursos contém somente a implantação do Lync Server e uma replicação sincronizada das contas de usuário da (s) floresta (s) contas de usuário local. Ele não contém contas de usuário habilitadas para logon. O Exchange é implantado na (s) floresta (s) da conta de usuário local integrada ao Exchange Online (híbrido) ou os serviços de email das contas de usuário locais são fornecidos exclusivamente pelo Exchange Online.

A floresta de recursos age como um ambiente de serviços compartilhados para a (s) floresta (s) do Active Directory local onde os objetos do usuário residem. A (s) floresta (s) da conta do usuário tem uma relação de confiança unidirecional de nível de floresta com a floresta de recursos. Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas do usuário. Um produto de sincronização de diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário. Quando uma nova conta de usuário é criada em uma das florestas do usuário ou uma conta de usuário é excluída de uma floresta, o produto de sincronização de diretório sincroniza a representação de usuário correspondente na floresta de recursos. Para obter mais informações sobre como configurar uma implantação de várias florestas, consulte Implantando o [Lync em uma arquitetura de várias florestas (Lync hospedado pelo parceiro com Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

