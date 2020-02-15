---
title: Restaurando um servidor back-end Enterprise Edition espelhado-primário
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b895a5071a3844e755fe453f92959f98ec0fbff5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Restaurando um servidor back-end Enterprise Edition espelhado no Lync Server 2013-principal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

Se você tiver um servidor back-end Enterprise Edition em uma configuração espelhada e apenas o banco de dados primário falhar, siga os procedimentos desta seção. Se o banco de dados primário e o espelho falharem, consulte [restaurando um servidor de back-end Enterprise Edition no Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Se apenas o espelho falhar, consulte [restaurando um servidor back-end do Enterprise Edition espelhado no Lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Se o banco de dados que hospeda o repositório de gerenciamento central falhar, consulte [restaurando o servidor que hospeda o repositório de gerenciamento central no Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Se um servidor membro Enterprise Edition que não seja o servidor back-end falhar, consulte [restaurando um servidor membro Enterprise Edition no Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Recomendamos que você faça uma cópia de imagem do sistema antes de iniciar a restauração. Você pode usar essa imagem como um ponto de reversão, caso algo dê errado durante a restauração. Você pode querer fazer a cópia da imagem depois de instalar o sistema operacional e o SQL Server e restaurar ou registrar novamente os certificados.

Neste tópico, o banco de dados primário de exemplo terá um FQDN (nome de domínio totalmente qualificado) do BE1.contoso.com e o banco de dados espelho terá um FQDN de BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Para restaurar um banco de dados primário do servidor back-end Enterprise Edition

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Forçar o failover de todos os bancos de dados configurados para o espelho. Para cada um dos tipos de banco de dados que você configurou neste servidor, digite o seguinte cmdlet:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Por exemplo:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Caso tenha configurado o banco de dados back-end para usar espelhamento sincronizado com uma testemunha, o failover será automático.

    
    </div>

4.  Após concluir o failover, execute o seguinte:
    
      - Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.
    
      - Desabilitar o espelhamento no servidor back-end: clique com o botão direito do mouse no pool em **pools de front-ends do Enterprise Edition** e selecione **Editar propriedades**. Na guia **geral** , em **associações**, desmarque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** . Faça isso para arquivamento e monitoramento, conforme necessário. Clique em **OK**.
    
      - Clique com o botão direito do mouse no nó Lync Server 2013, clique em **topologia**e em **publicar**.
    
      - Selecione o back-end (BE2.contoso.com) ainda funcional para ser o novo repositório do SQL. Para fazer isso, clique com o botão direito do mouse no pool em **pools de front-ends do Enterprise Edition** e selecione **Editar propriedades**. Na guia **geral** , em **associações**, digite o FQDN do back-end em funcionamento no campo **repositório do SQL Server** (no nosso exemplo, BE2.contoso.com).
    
      - Clique com o botão direito do mouse no nó Lync Server 2013, clique em **topologia**e em **publicar**.
    
      - Reinicie os serviços para que cada servidor possa ler a nova topologia. A partir de um shell de gerenciamento do Lync Server, execute os seguintes cmdlets em cada servidor de front-end que pertença a este pool:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Desinstale o espelhamento. A partir de um shell de gerenciamento do Lync Server, execute o seguinte cmdlet:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por exemplo:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Faça isso para todos os tipos de banco de dados neste servidor.

6.  Crie um servidor limpo ou novo que tenha o mesmo FQDN (neste exemplo, DB1.contoso.com) como o computador com falha, instale o sistema operacional e, em seguida, restaure ou registre novamente os certificados. Este servidor funcionará como o novo espelho.

7.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon no novo servidor.

8.  Instale o SQL Server 2012 ou o SQL Server 2008 R2, mantendo os nomes de instância o mesmo que antes da falha.

9.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins, faça logon em um servidor front-end.

10. Use o construtor de topologias para instalar o banco de BD espelho. Execute as etapas a seguir:
    
      - Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.
    
      - Habilite o espelhamento no servidor back-end. Para fazer isso, clique com o botão direito do mouse no pool em **pools de front-ends do Enterprise Edition** e selecione **Editar propriedades**. Na guia **geral** , em **associações**, marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** . Além disso, faça isso para arquivamento e monitoramento, se necessário.
        
        Em seguida, no campo **espelhamento do SQL Server Store** , digite o FQDN do novo servidor (n este exemplo, BE1.contoso.com). Clique em **OK**.
    
      - Clique com o botão direito do mouse no nó Lync Server 2013, clique em **topologia**e em **instalar banco de dados**.
    
      - Siga o assistente de **instalação de banco de dados** . Na página **criar bancos de dados** , selecione os bancos de dados que você deseja recriar.
    
      - Siga o assistente até chegar ao prompt, criar um **banco de dados espelho**. Selecione o banco de dados que você deseja instalar e conclua o processo.

</div>

</div>

<span> </span>

</div>

</div>

</div>

