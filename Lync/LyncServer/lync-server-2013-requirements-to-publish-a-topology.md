---
title: 'Lync Server 2013: Requisitos para publicar uma topologia'
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
ms.openlocfilehash: 0f1422df35ebbe9f368dc8aa3d121caf740e7033
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>Requisitos para publicar uma topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Este tópico descreve os requisitos de infraestrutura e software que são específicos para a publicação de uma topologia, seja usando o construtor de topologias ou a interface de linha de comando do Shell de gerenciamento do Lync Server 2013. Esses requisitos são além dos requisitos gerais do sistema operacional, do software e das permissões aplicáveis a todas as ferramentas administrativas do Lync Server 2013. Certifique-se de satisfazer todos os requisitos de ferramentas administrativas antes de publicar uma topologia.

  - Você deve executar o construtor de topologias em um computador que esteja associado ao mesmo domínio ou floresta da implantação do Lync Server 2013 que você está criando para que as etapas de preparação dos serviços de domínio Active Directory sejam concluídas, permitindo que você use as ferramentas administrativas em esse computador para publicar sua topologia com êxito.

  - Os computadores definidos na topologia devem ser associados ao domínio, exceto para servidores de borda e no AD DS. No entanto, os computadores não precisam estar online quando você publica a topologia.

  - O compartilhamento de arquivos do pool deve ser criado e disponibilizado para usuários remotos.

  - Para publicar um pool de front-end do Enterprise Edition, o servidor back-end baseado no SQL Server deve estar associado ao domínio no qual você está implantando os servidores, online e configurado com as regras de firewall adequadas para disponibilizá-lo para usuários remotos. Para obter detalhes sobre como especificar exceções de firewall, consulte [noções básicas sobre requisitos de firewall do SQL Server com o Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md). Para obter mais detalhes sobre a configuração do SQL Server, consulte [Configurar o SQL Server para Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).
    
    <div>
    

    > [!NOTE]  
    > O servidor Standard Edition tem um banco de dados posicionado que aceitará a configuração publicada. Você deve primeiro executar a tarefa de configuração <STRONG>preparar primeiro o servidor Standard Edition</STRONG> no assistente de implantação do Lync Server.

    
    </div>

<div>

## <a name="see-also"></a>Confira também


[Publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md)  
[Delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md)  


[Requisitos de software de ferramentas administrativas no Lync Server 2013](lync-server-2013-administrative-tools-software-requirements.md)  
[Suporte a sistemas operacionais de servidor e de ferramentas no Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md)  


[Direitos e permissões de administrador necessários para configuração e administração do Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

