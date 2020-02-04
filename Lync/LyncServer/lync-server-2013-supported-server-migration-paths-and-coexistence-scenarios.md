---
title: 'Lync Server 2013: Caminhos de migração de servidor suportado e cenários de coexistência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Caminhos de migração de servidor suportado e cenários de coexistência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-16_

O Lync Server 2013 oferece suporte à migração de qualquer um dos seguintes:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

Não há suporte para a migração de um ambiente que executa ambas as versões anteriores. Não há suporte para a migração de versões anteriores, como o Microsoft Office Communications Server 2007 ou o Live Communications Server 2005. Se sua implantação anterior incluiu o chat em grupo, você deve migrá-la separadamente.

<div>

## <a name="migration-methods"></a>Métodos de migração

Há suporte para a migração de todas as topologias do Lync Server e funções de servidor. Você pode migrar de uma topologia para uma topologia diferente, incluindo do servidor Standard Edition para o servidor Enterprise Edition.

O Lync Server 2013 só oferece suporte ao seguinte método de migração:

  - <span></span>  
    **Migração lado a lado.** Na migração lado a lado, o Lync Server 2013 é implantado juntamente com uma implantação existente do Microsoft Lync Server 2010 ou do Office Communications Server 2007 R2 e, em seguida, transfere operações para os novos servidores e move usuários para o Lync Server 2013. Esse método requer plataformas de servidor adicionais, incluindo hardware e software, durante a migração, e nomes de sistema e nomes de pool são diferentes na nova configuração. Se for necessário reverter para a versão anterior, você poderá mudar as operações de volta para os servidores anteriores.

Não há suporte para a migração entre florestas dos serviços de domínio Active Directory.

O caminho de migração recomendado é uma abordagem em fases. Para obter detalhes sobre a migração de uma versão anterior, incluindo o atributo Phase apropriado de implantação de componentes, consulte os seguintes tópicos na documentação de migração:

  - [Migração do Lync Server 2010 para o Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migração do Office Communications Server 2007 R2 para Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migração do Lync Server 2010, Chat em Grupo ou Office Communications Server 2007 R2 Group Chat para Lync Server 2013, Servidor de Chat Persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Cenários de coexistência

O Lync Server 2013 pode coexistir com componentes de uma implantação do Lync Server 2010 ou uma implantação do Office Communications Server 2007 R2. A implantação simultânea do Lync Server 2013 com o Lync Server 2010 e o Office Communications Server 2007 R2 (implantação simultânea de todas as três versões) não é suportada.

Durante uma migração em fases na qual uma implantação do Lync Server 2010 ou do Office Communications Server 2007 R2 anterior coexiste temporariamente com a nova implantação do Lync Server 2013, o suporte para o roteamento de versão mista é limitado. Para obter detalhes, consulte a documentação de migração.

Você deve usar computadores separados e distintos que executam o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 para suas instâncias de banco de dados do Lync Server 2013. Não é possível usar a mesma instância do SQL Server para um pool de front-end do Lync Server 2013 que você usa para um pool de front-end do Lync Server 2010 ou do Office Communications Server 2007 R2. Se você definir e configurar o Lync Server 2013 no construtor de topologias para uma implantação que já tenha o Lync Server 2010 ou o Office Communications Server 2007 R2 implantado, o construtor de topologias não permitirá que você defina uma instância de uma 2013 do Lync Server que já esteja em uso no a topologia.

O construtor de topologias exibirá a seguinte mensagem para informá-lo sobre esse \[problema: "o\] FQDN do SQL Server do servidor já contém uma função de hospedagem da função do SQL ' repositório de usuários". "

<div>


> [!NOTE]  
> Se você pretende implantar funções de servidor que são novas na implantação do Lync Server 2013, primeiro atualize a implantação existente, conforme descrito na documentação de migração e a documentação de implantação e, em seguida, implante as novas funções de servidor, conforme descrito em documentação de planejamento e documentação de implantação. Se você estiver migrando uma versão anterior do chat em grupo, migre-a por último, depois de concluir o processo de migração de todos os outros componentes do Lync Server 2010 ou do Office Communications Server 2007 R2.



</div>

Para obter requisitos de coexistência específicos e outros detalhes sobre a coexistência e a migração dos componentes do Lync Server 2010 ou do Office Communications Server 2007 R2 e do Lync Server 2013, consulte [migração do Lync server 2010 para o Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) e [migração do Office communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) na documentação de migração. Para obter detalhes sobre o suporte a versões mistas para clientes, consulte [clientes compatíveis de implantações anteriores no Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

