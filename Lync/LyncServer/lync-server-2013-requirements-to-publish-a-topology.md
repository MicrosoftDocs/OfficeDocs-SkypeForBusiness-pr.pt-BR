---
title: 'Lync Server 2013: requisitos para publicar uma topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5dac78de6d6cf0f86f0411b8085e6f8172b0f2f9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Requisitos para publicar uma topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Este tópico descreve os requisitos de infraestrutura e software específicos à publicação de uma topologia, seja usando o construtor de topologias ou a interface de linha de comando do Shell de gerenciamento do Lync Server 2013. Esses requisitos são além dos requisitos gerais de sistema operacional, software e permissões aplicáveis a todas as ferramentas administrativas do Lync Server 2013. Certifique-se de atender a todos os requisitos de ferramentas administrativas antes de publicar uma topologia.

  - Você deve executar o construtor de topologias em um computador que ingressou no mesmo domínio ou floresta da implantação do Lync Server 2013 que você está criando para que as etapas de preparação dos serviços de domínio Active Directory já tenham sido concluídas, permitindo que você use as ferramentas administrativas em esse computador para publicar sua topologia com êxito.

  - Os computadores definidos na topologia devem ingressar no domínio e no AD DS, exceto os Servidores de Borda. No entanto, os computadores não precisam estar online quando você publica a topologia.

  - O compartilhamento de arquivo para o pool deve ser criado e está disponível para usuários remotos.

  - Para publicar um pool de front-ends Enterprise Edition, o servidor back-end baseado em SQL Server deve ser associado ao domínio no qual você está implantando os servidores, online e configurado com as regras de firewall apropriadas para torná-lo disponível aos usuários remotos. Para obter detalhes sobre como especificar exceções de firewall, consulte [Understanding firewall Requirements for SQL Server with Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Para obter outros detalhes sobre a configuração do SQL Server, consulte [Configurar o SQL Server para Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > O servidor Standard Edition tem um banco de dados colocado que aceitará a configuração publicada. Você deve primeiro executar a tarefa de configuração <STRONG>preparar primeiro servidor Standard Edition</STRONG> no assistente de implantação do Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>Confira também


[Publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Requisitos de software de ferramentas administrativas no Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Direitos e permissões de administrador necessários para a instalação e administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

