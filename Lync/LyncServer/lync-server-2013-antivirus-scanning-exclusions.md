---
title: 'Lync Server 2013: exclusões de verificação de antivírus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b67f1472bbb8225bf952b5b678bcae8401d211d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508968"
---
# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Exclusões de verificação antivírus para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-11-02_

Para garantir que o verificador antivírus não interfira na operação do Lync Server 2013, você deve excluir processos e diretórios específicos para cada função de servidor ou servidor do Lync Server 2013 em que você execute um scanner antivírus. Os seguintes processos e diretórios devem ser excluídos:

<div>


> [!NOTE]  
> Os locais de pasta e arquivo listados abaixo são os locais padrão para o Lync Server 2013. Para os locais nos quais você não usou o padrão, exclua os locais especificados para a sua organização em vez dos locais padrão especificados neste tópico.



</div>

<div>


> [!IMPORTANT]  
> Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a lista de exclusão.



</div>

  - Processos do Lync Server 2013:
    
      - ABServer.exe
    
      - AcpMcuSvc.exe
    
      - ASMCUSvc.exe
    
      - AVMCUSvc.exe
    
      - ChannelService.exe
    
      - ClsAgent.exe
    
      - ComplianceService.exe
    
      - DataMCUSvc.exe
    
      - DataProxy.exe
    
      - FileTransferAgent.exe
    
      - IMMCUSvc.exe
    
      - LysSvc.exe
    
      - MasterReplicatorAgent.exe
    
      - MediaRelaySvc.exe
    
      - MediationServerSvc.exe
    
      - MRASSvc.exe
    
      - OcsAppServerHost.exe
    
      - ReplicaReplicatorAgent.exe
    
      - ReplicationApp.exe
    
      - RtcHost.exe
    
      - RTCSrv.exe
    
      - XmppProxy.exe
    
      - XmppTGW.exe

  - Processos do serviço de host do Windows Fabric:
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - Processos do IIS:
    
      - % SystemRoot% \\ System32 \\ inetsrv \\w3wp.exe
    
      - % SystemRoot% \\ SysWOW64 \\ inetsrv \\w3wp.exe

  - Processos de Back-End do SQL Server:
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. MSSQLSERVER \\ MSSQL \\ Binn \\SQLServr.exe
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSRS11. O MSSQLSERVER \\ Reporting Services \\ ReportServer \\ bin \\ReportingServicesService.exe
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSAS11. \\ \\MSMDSrv.exe bin OLAP \\

  - Processos de Front-End do SQL Server:
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. LYNCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe
    
      - % ProgramFiles% \\ Microsoft SQL Server \\ MSSQL11. RTCLOCAL \\ MSSQL \\ Binn \\SQLServr.exe

  - Arquivos e diretórios:
    
      - % SystemRoot% \\ System32 \\ LogFiles
    
      - % de \\ LogFiles da raiz_do_sistema% \\
    
      - % de% \\ Microsoft.NET \\ assembly do \\ GAC \_
    
      - % ProgramFiles% \\ Microsoft Lync Server 2013
    
      - % ProgramFiles% \\ Arquivos comuns \\ \\ nó do Inspetor do Microsoft Lync Server 2013
    
      - % ProgramFiles% \\ Arquivos comuns \\ Microsoft Lync Server 2013
    
      - % SystemDrive% \\ RtcReplicaRoot
    
      - O repositório de compartilhamento de arquivo (especificado no Construtor de Topologias). Os repositórios de arquivo estão especificados no Construtor de Topologias.
    
      - Os dados e arquivos de log do  SQL Server, incluindo para o banco de dados de Back-End, repositório de usuários, repositório de arquivamento, repositório de monitoramento e repositório do aplicativo. Os arquivos de log e banco de dados podem ser especificados no Construtor de Topologias. Para obter detalhes sobre os dados e arquivos de log para cada banco de dados, incluindo nomes padrão, confira [dados do SQL Server e posicionamento de arquivos de log para o Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) na documentação de implantação.
    
      - Dados do SQL Server e arquivos de log, incluindo aqueles para o banco de dados front-end, o repositório do Lync e o repositório do RtcDatabase. Eles estão normalmente em% Unidade_Local% \\ CSData.

</div>

<span> </span>

</div>

</div>

</div>

