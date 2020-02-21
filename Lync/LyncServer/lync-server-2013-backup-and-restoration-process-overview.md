---
title: 'Lync Server 2013: visão geral do processo de backup e restauração'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd6efce509283d59c5cecc7325c35c9cf1ab371e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Visão geral do processo de backup e restauração do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-26_

Esta seção fornece uma visão geral de como o processo de backup e restauração funciona para o Lync Server 2013. Você usa o mesmo processo para todos os servidores Standard Edition e servidores Enterprise Edition, independentemente do local.

Em geral, o processo de backup funciona da seguinte maneira:

  - Você cria um local de backup como uma pasta compartilhada em um computador autônomo que não faz parte de nenhum pool. O local do backup é referenciado no **$backup**.

  - Em uma base normal e agendada, você faz o backup de todos os bancos de dados do Lync Server e de todos os repositórios de arquivos descritos nos [requisitos de backup e restauração no Lync server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) , seguindo os procedimentos descritos em [backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) o repositório de gerenciamento central inclui todas as configurações e configurações do servidor.

  - Cada vez que você executar um backup subsequente, crie uma nova pasta compartilhada e altere o caminho que **$backup** referências.

Em geral, o processo de restauração funciona da seguinte maneira:

  - Quando ocorre uma falha ou uma interrupção, você restaura os dados no local referenciado por **$backup** para computadores novos ou limpos.
    
    <div>
    

    > [!IMPORTANT]  
    > Esse processo de restauração não restaura dados em um estado de servidor existente. Ou seja, esse processo requer que o servidor seja limpo ou novo.

    
    </div>

  - Para permitir que suas informações de usuário e conferência sejam recuperáveis para o ponto de falha, você pode implementar uma topologia de recuperação de desastre com pools de front-ends emparelhados, conforme descrito em [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - Toda configuração de sistema de nomes de domínio (DNS), configuração de protocolo de configuração dinâmica de host (DHCP), nomes de domínio, nomes de domínio totalmente qualificados (FQDNs) do computador, caminhos de repositório de arquivos e assim por diante deve ser o mesmo no momento da restauração que estavam no momento da backup.

Se um servidor que executa o Lync Server falhar, a recuperação inclui as seguintes etapas:

  - Instale o sistema operacional em um computador novo ou limpo com o mesmo FQDN que o computador com falha.

  - Reinstale os certificados.

  - Se o servidor hospedar um banco de dados, instale o Microsoft SQL Server 2012 ou o Microsoft SQL Server 2008 R2.

  - Em geral, se o servidor hospedar um banco de dados, execute o construtor de topologias para criar e instalar o banco de dados e configurar as listas de controle de acesso (ACLs).

  - Em geral, se o servidor hospedar uma função de servidor, execute a etapa 1 até a etapa 4 do assistente de implantação do Lync Server para instalar os arquivos de configuração local, instalar os componentes da função de servidor, atribuir certificados e iniciar os serviços.
    
    <div>
    

    > [!NOTE]  
    > Se o servidor hospedado por um banco de dados colocado com a função de servidor, a execução da etapa 2 do assistente de implantação do Lync Server recriará o banco de dados.

    
    </div>

  - Se o servidor hospedar um banco de dados, restaure os dados de backup.

</div>

<span> </span>

</div>

</div>

</div>

