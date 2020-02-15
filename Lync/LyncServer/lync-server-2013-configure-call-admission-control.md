---
title: 'Lync Server 2013: configurar controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ebe3fbdd60409523755c865f4b4f34025acf15d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Configurar o controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O controle de admissão de chamadas é uma solução que determina se uma sessão em tempo real pode ou não ser estabelecida com base na largura de banda disponível, para ajudar a evitar uma qualidade audiovisual ruim para os usuários em redes congestionadas. O controle de admissão de chamadas controla o tráfego em tempo real somente de áudio e vídeo e não afeta o tráfego de dados. O controle de admissão de chamadas pode rotear a chamada através de um caminho da Internet quando o caminho WAN padrão não tem a largura de banda necessária. Para obter detalhes, consulte [Planning for Call Admission Control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) na documentação de planejamento.

Esta seção fornece um conjunto de procedimentos de exemplo que ilustram como implantar e gerenciar o CAC em sua rede.

<div>


> [!IMPORTANT]  
> Antes de implantar o CAC, você deve coletar todas as informações necessárias para sua topologia de rede corporativa, conforme descrito em <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">exemplo: reunindo seus requisitos para controle de admissão de chamadas no Lync Server 2013</A> na documentação de planejamento. Além disso, certifique-se de que os componentes do CAC foram instalados e ativados, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um pool de front-ends ou servidor Standard Edition no Lync server 2013</A> na documentação de implantação.



</div>

<div>


> [!NOTE]  
> Todos os exemplos de implantação e gerenciamento do CAC nesta seção são executados usando o Shell de gerenciamento do Lync Server. Como alternativa, você também pode usar a seção <STRONG>configuração de rede</STRONG> do painel de controle do Lync Server para gerenciar o CAC.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurar regiões de rede para CAC no Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Criar perfis de política de largura de banda no Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Configurar sites de rede para CAC no Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Associar sub-redes a sites de rede para CAC no Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Criar links de região de rede no Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Criar rotas entre regiões de rede no Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Criar políticas entre sites de rede no Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Habilitar controle de admissão de chamadas no Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Lista de verificação de implantação do controle de admissão de chamadas para Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

