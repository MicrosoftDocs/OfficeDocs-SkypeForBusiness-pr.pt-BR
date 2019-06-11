---
title: Mover o servidor de gerenciamento central do Lync Server 2010 para o Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Mover o servidor de gerenciamento central do Lync Server 2010 para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-25_

Após a migração do Lync Server 2010 para o Lync Server 2013, você precisa mover o servidor de gerenciamento central do Lync Server 2010 para o servidor ou o pool de front-end do Lync Server 2013 para poder remover o servidor herdado do Lync Server 2010.

O servidor de gerenciamento central é um único sistema de réplica mestra/múltipla, em que a cópia de leitura/gravação do banco de dados é mantida pelo servidor front-end que contém o servidor de gerenciamento central. Cada computador na topologia, incluindo o servidor front-end que contém o servidor de gerenciamento central, tem uma cópia somente leitura dos dados do repositório de gerenciamento central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalados no computador durante a instalação e implementação. O banco de dados local recebe atualizações de réplica por meio do agente duplicador de réplica do Lync Server que é executado como um serviço em todos os computadores. O nome do banco de dados real no servidor de gerenciamento central e na réplica local é XDS, que é composto pelos arquivos XDS. MDF e XDS. ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory. Todas as ferramentas que usam o servidor de gerenciamento central para gerenciar e configurar o Lync Server usam o SCP para localizar o repositório de gerenciamento central.

Depois de mover com êxito o servidor de gerenciamento central, você deve remover os bancos de dados do servidor de gerenciamento central do servidor front-end original. Para obter informações sobre como remover os bancos de dados do servidor de gerenciamento central, consulte [remover o banco de dados do SQL Server de um pool de front-ends](remove-the-sql-server-database-for-a-front-end-pool.md).

Você usa o cmdlet **move-CsManagementServer** do Windows PowerShell no Shell de gerenciamento do Lync Server para mover o banco de dados do banco de dados do SQL Server do lync Server 2010 para o banco de dados do lync Server 2013 SQL Server e, em seguida, atualizar o scp para apontar para o Lync Local do servidor de gerenciamento central do servidor 2013.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Preparando os servidores de front-end do Lync Server 2013 antes de mover o servidor central de gerenciamento

Use os procedimentos desta seção para preparar os servidores front-end do Lync Server 2013 antes de mover o servidor de gerenciamento central do Lync Server 2010.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Para preparar um pool de front-end do Enterprise Edition

1.  No pool de front-ends do Lync Server 2013 Enterprise Edition onde você deseja realocar o servidor de gerenciamento central: faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos de usuário e permissões do banco de dados do SQL Server sysadmin no banco de dados onde deseja instalar o repositório de gerenciamento central.

2.  Abra o Shell de gerenciamento do Lync Server.

3.  Para criar o novo repositório de gerenciamento central no banco de dados do SQL Server do Lync Server 2013, no Shell de gerenciamento do Lync Server, digite:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Confirme se o status do serviço **front-end do Lync Server** foi **iniciado**.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Para preparar um servidor front-end padrão da edição

1.  No servidor front-end do Lync Server 2013 Standard Edition no qual você deseja realocar o servidor de gerenciamento central: faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo **RTCUniversalServerAdmins** .

2.  Abra o assistente de implantação do Lync Server.

3.  No assistente de implantação do Lync Server, clique em **preparar primeiro servidor Standard Edition**.

4.  Na página **comandos em execução** , o SQL Server Express é instalado como o servidor de gerenciamento central. Regras de firewall necessárias são criadas. Quando a instalação do banco de dados e do software de pré-requisito estiver concluída, clique em **concluir**.
    
    <div>
    

    > [!NOTE]  
    > A instalação inicial pode levar algum tempo sem atualizações visíveis para a tela Resumo da saída do comando. Isso se deve à instalação do SQL Server Express. Se você precisar monitorar a instalação do banco de dados, use o Gerenciador de tarefas para monitorar a configuração.

    
    </div>

5.  Para criar o novo repositório de gerenciamento central no servidor front-end do Lync Server 2013 Standard Edition, no Shell de gerenciamento do Lync Server, digite:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Confirme se o status do serviço **front-end do Lync Server** foi **iniciado**.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Para mover o servidor de gerenciamento central do Lync Server 2010 para o Lync Server 2013

1.  No servidor do Lync Server 2013 que será o servidor de gerenciamento central: faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos de usuário e permissões de administrador de banco de dados do SQL Server.

2.  Abra o Shell de Gerenciamento do Lync Server.

3.  No Shell de gerenciamento do Lync Server, digite:
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Se <CODE>Enable-CsTopology</CODE> o problema não for bem-sucedido, resolva o problema para impedir que o comando seja concluído antes de continuar. Se <STRONG>Enable-CsTopology</STRONG> não for bem-sucedido, a mudança falhará e poderá deixar a sua topologia em um estado em que não haja repositório de gerenciamento central.

    
    </div>

4.  No servidor front-end do Lync Server 2013 ou no pool de front-end, no Shell de gerenciamento do Lync Server, digite:
    
        Move-CsManagementServer

5.  O Shell de gerenciamento do Lync Server exibe os servidores, armazenamentos de arquivos, repositórios de banco de dados e os pontos de conexão de serviço do estado atual e o Estado proposto. Leia as informações com atenção e confirme se essa é a origem e o destino pretendidos. Digite **Y** para continuar ou **N** para interromper a movimentação.

6.  Revise todos os avisos ou erros gerados pelo comando **mover-CsManagementServer** e resolva-os.

7.  No servidor do Lync Server 2013, abra o assistente de implantação do Lync Server.

8.  No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server**, clique em **etapa 2: configurar ou remover componentes do Lync Server**, clique em **Avançar**, examine o resumo e clique em **concluir**.

9.  No servidor do Lync Server 2010, abra o assistente de implantação do Lync Server.

10. No assistente de implantação do Lync Server, clique em **instalar ou atualizar o sistema do Lync Server**, clique em **etapa 2: configurar ou remover componentes do Lync Server**, clique em **Avançar**, examine o resumo e clique em **concluir**.

11. Reinicie o servidor do Lync Server 2013. Isso é necessário devido a uma alteração de associação do grupo para acessar o banco de dados do servidor de gerenciamento central.

12. Para confirmar se a replicação com o novo repositório de gerenciamento central está ocorrendo, no Shell de gerenciamento do Lync Server, digite:
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > A replicação pode levar algum tempo para atualizar todas as réplicas atuais.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>Para remover arquivos do repositório central de gerenciamento do Lync Server 2010 após uma mudança

1.  No servidor do Lync Server 2010: faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo **RTCUniversalServerAdmins** . Você também deve ter direitos de usuário e permissões de administrador de banco de dados do SQL Server.

2.  Abrir o Shell de gerenciamento do Lync Server
    
    <div>
    

    > [!WARNING]  
    > Não prossiga com a remoção dos arquivos de banco de dados anteriores até que a replicação seja concluída e seja estável. Se você remover os arquivos antes de concluir a replicação, irá interromper o processo de replicação e deixar o servidor de gerenciamento central recentemente movido em um estado desconhecido. Use o cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> para confirmar o status de replicação.

    
    </div>

3.  Para remover os arquivos de banco de dados do repositório de gerenciamento central do servidor do Lync Server 2010 central Management, digite:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Por exemplo:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Onde o \<FQDN do SQL Server\> é o servidor Back-End do Lync Server 2010 em uma implantação Enterprise Edition ou o FQDN do servidor Standard Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

