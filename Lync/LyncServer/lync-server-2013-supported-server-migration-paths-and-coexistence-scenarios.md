---
title: 'Lync Server 2013: caminhos de migração de servidor suportados e cenários de coexistência'
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
ms.openlocfilehash: 8ed7689931cf917c77527266918832ead8bd0a27
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523968"
---
# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Caminhos de migração de servidor suportados e cenários de coexistência no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-16_

O Lync Server 2013 oferece suporte à migração de um dos seguintes:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

A migração de um ambiente executando ambas as versões anteriores não é suportada. A migração de versões anteriores, como o Microsoft Office Communications Server 2007 ou o Live Communications Server 2005, não é suportada. Se sua implantação anterior incluiu o chat de grupo, você deve migrá-lo separadamente.

<div>

## <a name="migration-methods"></a>Métodos de migração

Há suporte para a migração de todas as topologias do Lync Server e funções de servidor. É possível migrar de uma topologia para uma topologia diferente, incluindo do servidor Standard Edition para o servidor Enterprise Edition.

O Lync Server 2013 suporta apenas o seguinte método de migração:

  - <span></span>  
    **Migração lado a lado.** Na migração lado a lado, o Lync Server 2013 é implantado junto com uma implantação existente do Microsoft Lync Server 2010 ou do Office Communications Server 2007 R2 e, em seguida, transfere operações para os novos servidores e move os usuários para o Lync Server 2013. Esse método exige plataformas de servidor adicionais, incluindo hardware e software, durante a migração, e nomes de sistema e de pool são diferentes na nova configuração. Se for necessário reverter para a versão anterior, você poderá retornar as operações para os servidores anteriores.

Não há suporte para a migração entre florestas de serviços de domínio do Active Directory.

O caminho de migração recomendado é uma abordagem de base. Para obter detalhes sobre a migração de uma versão anterior, incluindo a fase adequada da implantação de componente, consulte os seguintes tópicos na documentação de Migração:

  - [Migração do Lync Server 2010 para o Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migração do Office Communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migração do Lync Server 2010, Chat em Grupo ou Office Communications Server 2007 R2 Group Chat para Lync Server 2013, Servidor de Chat Persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Cenários de coexistência

O Lync Server 2013 pode coexistir com componentes de uma implantação do Lync Server 2010 ou uma implantação do Office Communications Server 2007 R2. A implantação simultânea do Lync Server 2013 com o Lync Server 2010 e o Office Communications Server 2007 R2 (implantação simultânea de todas as três versões) não é suportada.

Durante uma migração em fases na qual uma implantação anterior do Lync Server 2010 ou do Office Communications Server 2007 R2 coexiste temporariamente com a nova implantação do Lync Server 2013, o suporte para roteamento de versão mista é limitado. Para obter detalhes, consulte a documentação Migração.

Você deve usar computadores separados e distintos que executam o Microsoft SQL Server 2008 R2 ou o Microsoft SQL Server 2012 para suas instâncias de banco de dados do Lync Server 2013. Não é possível usar a mesma instância do SQL Server para um pool de front-ends do Lync Server 2013 que você usa para um pool de front-ends do Lync Server 2010 ou do Office Communications Server 2007 R2. Se você definir e configurar o Lync Server 2013 no construtor de topologias para uma implantação que já tem o Lync Server 2010 ou o Office Communications Server 2007 R2 implantado, o construtor de topologias não permitirá que você defina uma instância de um Lync Server 2013 que já esteja em uso na topologia.

O construtor de topologia exibirá a seguinte mensagem para informá-lo sobre esse problema: "o \[ FQDN do SQL Server do servidor \] já contém uma instância do SQL que hospeda a função" repositório do usuário ".

<div>


> [!NOTE]  
> Se você pretende implantar funções de servidor que são novas na sua implantação do Lync Server 2013, deve primeiro atualizar sua implantação existente conforme descrito na documentação de migração e na documentação de implantação e, em seguida, implantar as novas funções de servidor, conforme descrito na documentação de planejamento e documentação de implantação. Se você estiver migrando uma versão anterior do chat de grupo, migre-a por último, após concluir o processo de migração de todos os outros componentes do Lync Server 2010 ou do Office Communications Server 2007 R2.



</div>

Para obter requisitos específicos de coexistência e outros detalhes sobre a coexistência e a migração de componentes do Lync Server 2010 ou do Office Communications Server 2007 R2 e do Lync Server 2013, consulte [migração do Lync server 2010 para o Lync server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) e [migração do Office communications Server 2007 R2 para o Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) na documentação de migração. Para obter detalhes sobre o suporte de versão mista para clientes, consulte [clientes com suporte de implantações anteriores no Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

