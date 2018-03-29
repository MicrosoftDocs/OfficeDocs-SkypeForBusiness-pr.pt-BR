---
title: Exclusões de escaneamento de antivírus para Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/24/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral do interoperação de scanner antivírus com Skype para Business Server 2015.
ms.openlocfilehash: bb188b25c61269ee7c38829e1887a3443a0f77c4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server-2015"></a>Exclusões de escaneamento de antivírus para Skype for Business Server 2015
 
Visão geral do interoperação de scanner antivírus com Skype para Business Server 2015. 
  
Para garantir que o scanner antivírus não interfere com a operação do Skype para Business Server 2015, você deve excluir diretórios e processos específicos para cada Skype para Business Server 2015 server ou função de servidor em que você executa um scanner antivírus. Os seguintes processos e diretórios devem ser excluídos:
  
> [!NOTE]
> Locais de arquivo e pasta listadas a seguir são os locais de padrão do Skype para Business Server 2015. Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico. 
  
> [!IMPORTANT]
> Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão. 
  
- Skype para processos de negócios Server 2015:
    
  - ABServer.exe
    
  - ASMCUSvc.exe
    
  - AVMCUSvc.exe
    
  - ChannelService.exe
    
  - ClsAgent.exe
    
  - ComplianceService.exe
    
  - DataMCUSvc.exe
    
  - DataProxy.exe
    
  - FileTransferAgent.exe
    
  - HealthAgent.exe
    
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
    
  - %systemroot%\system32\inetsrv\w3wp.exe
    
  - %systemroot%\SysWOW64\inetsrv\w3wp.exe
    
- Processos SQL Server Back-End:
    
    > [!NOTE]
    > Observe que estes caminhos são específicos para versão do SQL Server. 
  
  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSRS11.MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe
    
- Processos SQL Server Front-End:
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe
    
  - Instância RTC de Instalação Padrão de Edição 
    
  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe
    
- Diretórios e arquivos:
    
  - %systemroot%\system32\LogFiles
    
  - %systemroot%\SysWow64\LogFiles
    
  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL
    
  - %programfiles%\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node
    
  - %programfiles%\Common Files\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.
    
  - Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para obter detalhes sobre os arquivos de dados e log para cada banco de dados, incluindo nomes padrão, consulte a [localização do arquivo de Log e de dados do SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação.
    
  - Arquivos do SQL Server dados e log, incluindo aqueles para o banco de dados front-end, Skype para repositório corporativo e RtcDatabase repositório. Normalmente, eles estão sob %localdrive%\CSData.
    

