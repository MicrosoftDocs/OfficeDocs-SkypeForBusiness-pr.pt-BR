---
title: 'Lync Server 2013: Exclusões de verificação de antivírus'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Antivirus scanning exclusions for Lync Server 2013
ms:assetid: 71e1f1cc-2d16-4111-9864-9276bf24dfe0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440138(v=OCS.15)
ms:contentKeyID: 57793042
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f354b93bf21f054e9b5b24e3befd1787279bbe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="antivirus-scanning-exclusions-for-lync-server-2013"></a>Exclusões de verificação de antivírus para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-11-02_

Para garantir que o scanner antivírus não interfira com a operação do Lync Server 2013, você deve excluir processos e pastas específicos para cada função de servidor ou servidor do Lync Server 2013 na qual você executa um verificador de vírus. Os seguintes processos e diretórios devem ser excluídos:

<div>


> [!NOTE]  
> Os locais de pasta e arquivo listados abaixo são os locais padrão do Lync Server 2013. Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.



</div>

<div>


> [!IMPORTANT]  
> Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.



</div>

  - Processos do Lync Server 2013:
    
      - ABServer.exe
    
      - AcpMcuSvc. exe
    
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

  - Processos de Serviço de Host do Windows Fabric:
    
      - Fabric.exe
    
      - FabricDCA.exe
    
      - FabricHost.exe

  - Processos IIS:
    
      - % SystemRoot%\\system32\\inetsrv\\w3wp. exe
    
      - % SystemRoot%\\SysWOW64\\inetsrv\\w3wp. exe

  - Processos SQL Server Back-End:
    
      - % ProgramFiles\\% Microsoft SQL\\Server MSSQL11. MSSQLSERVER\\MSSQL\\Binn\\sqlservr. exe
    
      - % ProgramFiles\\% Microsoft SQL\\Server MSRS11. MSSQLSERVER\\Reporting\\Services\\\\ReportServer bin ReportingServicesService. exe
    
      - % ProgramFiles\\% Microsoft SQL\\Server MSAS11. Compartimento\\\\OLAP\\MSSQLSERVER. exe

  - Processos SQL Server Front-End:
    
      - % ProgramFiles\\% Microsoft SQL\\Server MSSQL11. LYNCLOCAL\\MSSQL\\Binn\\sqlservr. exe
    
      - % ProgramFiles\\% Microsoft SQL\\Server MSSQL11. RTCLOCAL\\MSSQL\\Binn\\sqlservr. exe

  - Diretórios e arquivos:
    
      - % SystemRoot%\\system32\\LogFiles
    
      - % SystemRoot%\\SysWOW64\\LogFiles
    
      - % SystemRoot%\\Microsoft.NET\\assembly\\GAC\_MSIL
    
      - % ProgramFiles\\% Microsoft Lync Server 2013
    
      - % ProgramFiles\\% arquivos\\comuns nó do Inspetor\\do Microsoft Lync Server 2013
    
      - % ProgramFiles\\% arquivos\\comuns Microsoft Lync Server 2013
    
      - % SystemDrive%\\RtcReplicaRoot
    
      - Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.
    
      - Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para obter detalhes sobre os dados e arquivos de log para cada banco de dados, incluindo nomes padrão, consulte [dados do SQL Server e posicionamento do arquivo de log para o Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md) na documentação de implantação.
    
      - Dados e arquivos de log do SQL Server, incluindo aqueles para o banco de dados front-end, a loja do Lync e a loja do RtcDatabase. Eles estão normalmente em% Unidade_Local%\\CSData.

</div>

<span> </span>

</div>

</div>

</div>

