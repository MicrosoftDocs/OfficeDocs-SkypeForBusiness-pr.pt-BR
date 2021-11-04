---
title: Exclusões de verificação de antivírus para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral da interoperação do scanner antivírus com Skype for Business Server.
ms.openlocfilehash: 105abd3618c5e869681edc31321a07ab0bce9d57
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737647"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusões de verificação de antivírus para Skype for Business Server

Visão geral da interoperação do scanner antivírus com Skype for Business Server.

Para garantir que o scanner antivírus não interfira na operação do Skype for Business Server, exclua processos e diretórios específicos para cada servidor Skype for Business Server ou função de servidor na qual você execute um scanner antivírus. Os seguintes processos e diretórios devem ser excluídos:

> [!NOTE]
> Os locais de pasta e arquivo listados abaixo são os locais padrão para Skype for Business Server. Para os locais nos quais você não usou o padrão, exclua os locais especificados para a sua organização em vez dos locais padrão especificados neste tópico.

> [!IMPORTANT]
> Observe que alguns programas antivírus podem precisar de caminhos absolutos, não relativos, para sua lista de exclusão.

- Skype for Business Server processos:

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
  
  - LyncBackupService.exe

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

- Windows Fabric Processos de Serviço host:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Processos do IIS:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- SQL Server Back-End processos:

    > [!NOTE]
    > Observe que esses caminhos são específicos para SQL Server versão.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Reporting Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- SQL Server Front-End processos:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Edição Standard Instância RTC de instalação

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Arquivos e diretórios:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Observe que esses caminhos são específicos para Skype for Business Server versão.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Nó do Watcher

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - O repositório de compartilhamento de arquivo (especificado no Construtor de Topologias). Os repositórios de arquivo estão especificados no Construtor de Topologias.

  - Os dados e arquivos de log do  SQL Server, incluindo para o banco de dados de Back-End, repositório de usuários, repositório de arquivamento, repositório de monitoramento e repositório do aplicativo. Os arquivos de log e banco de dados podem ser especificados no Construtor de Topologias. Para obter detalhes sobre os arquivos de dados e de log para cada banco de dados, incluindo nomes padrão, consulte [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) na documentação de Implantação.

  - SQL Server dados e arquivos de log, incluindo aqueles para o banco de dados front-end, o Skype for Business store e o armazenamento RtcDatabase. Eles normalmente estão em %localdrive%\CSData.