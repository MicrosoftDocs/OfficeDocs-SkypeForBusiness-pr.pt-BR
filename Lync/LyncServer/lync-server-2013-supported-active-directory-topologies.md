---
title: 'Lync Server 2013: topologias do Active Directory com suporte'
description: 'Lync Server 2013: topologias do Active Directory com suporte.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ce820a36cb033933b423e01deb5a3049ed3ea2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575307"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Topologias do Active Directory com suporte no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-10-02_

O Lync Server 2013 oferece suporte às mesmas topologias de serviços de domínio do Active Directory que o Microsoft Lync Server 2010 e o Microsoft Office Communications Server 2007 R2. s topologias abaixo têm suporte:

  - Floresta única com domínio único

  - Floresta única com uma única árvore e vários domínios

  - Floresta única com várias árvores e namespaces não contíguos

  - Várias florestas em uma topologia de floresta central

  - Várias florestas em uma topologia de floresta de recursos

  - Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online

A figura a seguir identifica os ícones usados nas ilustrações desta seção.

**Chave para ilustrações de topologia**

![Chave para ilustrações de topologia](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Chave para ilustrações de topologia")

<div>

## <a name="single-forest-single-domain"></a>Floresta única, domínio único

A topologia mais simples do Active Directory com suporte no Lync Server, uma floresta de domínio único, é uma topologia comum.

A figura a seguir ilustra uma implantação do Lync Server em uma única topologia de domínio do Active Directory.

**Topologia de domínio único**

![Topologia de domínio único](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologia de domínio único")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>Floresta única, vários domínios

Outra topologia do Active Directory com suporte no Lync Server é uma única floresta que consiste em um domínio raiz e um ou mais domínios filho. Nesse tipo de topologia do Active Directory, o domínio em que você cria usuários pode ser diferente do domínio no qual você está implantando o Lync Server. Porém, se você implantar um pool de Front-Ends, você deve implantar todos os Servidores de Front-Ends no pool com um único domínio. O suporte do Lync Server para grupos de administradores universais do Windows permite a administração entre domínios.

A figura a seguir ilustra uma implantação em uma floresta única com vários domínios. Nesta figura, um ícone de usuário mostra o domínio no qual a conta de usuário está hospedada e a seta aponta para o domínio onde reside o pool do Lync Server. As contas de usuário incluem:

  - Contas de usuário no mesmo domínio que o pool do Lync Server

  - Contas de usuário em um domínio diferente do pool do Lync Server

  - Contas de usuário em um domínio filho do domínio com o pool do Lync Server

**Floresta única com vários domínios**

![Floresta única com vários domínios](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Floresta única com vários domínios")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>Floresta única, várias árvores

Uma topologia de floresta com várias árvores consiste em dois ou mais domínios que definem estruturas de árvore independentes e namespaces do Active Directory separados.

A figura a seguir ilustra uma floresta única com várias árvores. Nesta figura, um ícone de usuário mostra o domínio no qual a conta de usuário está hospedada, uma linha sólida aponta para um pool do Lync Server que reside no mesmo domínio ou em um domínio diferente, e uma linha tracejada aponta para o pool do Lync Server que reside em uma árvore diferente. As contas de usuário incluem:

  - Contas de usuário no mesmo domínio que o pool do Lync Server

  - Contas de usuário em um domínio diferente de (mas a mesma árvore que) o pool do Lync Server

  - Contas de usuário em uma árvore diferente do pool do Lync Server

**Floresta única com várias árvores**

![Floresta única com várias árvores](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Floresta única com várias árvores")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>Várias florestas, floresta central

O Lync Server oferece suporte a várias florestas configuradas em uma topologia de floresta central. Topologias de floresta central usam objetos de contato na floresta central para representar os usuários nas outras florestas. A floresta central também hospeda contas de usuário para os usuários dessa floresta. Um produto da sincronização do diretório, como um Microsoft Identity Integration Server (MIIS), um Microsoft Forefront Identity Manager (FIM) 2010 ou um Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário dentro da organização: quando um novo usuário é criado em uma das florestas ou quando uma conta de usuário é excluída de uma floresta, o produto de sincronização do diretório sincroniza o contato correspondente na floresta central.

Uma floresta central tem as seguintes vantagens:

  - Os servidores que executam o Lync Server são centralizados em uma única floresta.

  - Os usuários podem procurar outros usuários em qualquer floresta e se comunicar com eles.

  - Os usuários podem visualizar a presença de outros usuários em qualquer floresta.

  - O produto da sincronização do diretório automatiza a adição e a exclusão de objetos de contato na floresta central à medida que as contas de usuários são criadas ou removidas.

A figura a seguir ilustra a topologia de floresta central. Nesta figura, há relações de confiança de duas vias entre o domínio que hospeda o Lync Server, que está na floresta central e cada domínio somente usuário, que está em uma floresta separada. O esquema nas florestas de usuários separadas não precisa ser estendido.

**Topologia de floresta central**

![Topologia de floresta central](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologia de floresta central")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>Várias florestas, floresta de recursos

Em uma topologia de floresta de recursos, uma floresta é dedicada à execução de aplicativos de servidor, como o Microsoft Exchange Server e o Lync Server. A floresta de recursos hospeda os aplicativos de servidor e uma representação sincronizada do objeto de usuário ativo, mas não inclui contas de usuário habilitadas para logon. A floresta de recursos atua como um ambiente de serviços compartilhado para as outras florestas em que os objetos de usuário residem. As florestas de usuários têm uma relação de confiança no nível de floresta com a floresta de recursos. Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuários. Se o Microsoft Exchange já estiver implantado na floresta de recursos, talvez as contas de usuário desabilitadas já existam. Um produto de sincronização do diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário. Quando uma nova conta de usuário é criada em uma das florestas do usuário ou quando uma conta de usuário é excluída de uma floresta, o produto de sincronização do diretório sincroniza a representação do usuário correspondente na floresta de recurso.

Essa topologia pode ser usada para fornecer uma infraestrutura compartilhada para os serviços nas organizações que gerenciam várias florestas ou para separar a administração de objetos do Active Directory de outros tipos de administração. As empresas que precisam isolar a administração do Active Directory por motivos de segurança escolhem essa topologia com frequência.

Essa topologia proporciona a vantagem de limitar a necessidade de estender o esquema do Active Directory a uma única floresta (a saber, a floresta de recursos).

O diagrama a seguir ilustra uma topologia de floresta de recursos.

**Topologia da floresta de recursos**

![Topologia de floresta de recursos do Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologia de floresta de recursos do Active Directory")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>Várias florestas em uma topologia de floresta de recursos do Lync com o Exchange Online

Nesta topologia, uma ou mais florestas estão localizadas no local e são dedicadas à Hospedagem de contas de usuário do Active Directory. A floresta de recursos está localizada fora do local e é mantida por um provedor de Hospedagem de terceiros. A floresta de recursos contém apenas a implantação do Lync Server e uma replicação sincronizada das contas de usuário da (s) floresta (s) contas de usuário local. Ele não contém contas de usuário habilitadas para logon. O Exchange é implantado na (s) floresta (s) de contas de usuário local integrada junto com o Exchange Online (híbrido) ou os serviços de email para as contas de usuário locais são fornecidos exclusivamente pelo Exchange Online.

A floresta de recursos atua como um ambiente de serviços compartilhados para a (s) floresta (s) do Active Directory local onde os objetos de usuário residem. As florestas de contas de usuário têm uma relação de confiança de nível de floresta unidirecional com a floresta de recursos. Ao implantar o Lync Server nesse tipo de topologia, você cria um objeto de usuário desabilitado na floresta de recursos para cada conta de usuário nas florestas de usuários. Um produto de sincronização do diretório, como o MIIS, o Microsoft Forefront Identity Manager (FIM) 2010 ou o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gerencia o ciclo de vida das contas de usuário. Quando uma nova conta de usuário é criada em uma das florestas do usuário ou quando uma conta de usuário é excluída de uma floresta, o produto de sincronização do diretório sincroniza a representação do usuário correspondente na floresta de recurso. Para obter mais informações sobre como configurar uma implantação de várias florestas, consulte [Deploying Lync in a multi-Forest Architecture (Lync Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).

</div>

</div>

<span> </span>

</div>

</div>

</div>

