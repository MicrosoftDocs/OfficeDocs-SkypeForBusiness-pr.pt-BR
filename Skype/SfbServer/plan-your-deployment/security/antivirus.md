---
title: Exclusões de verificação antivírus do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral da interoperação do scanner antivírus com o Skype for Business Server.
ms.openlocfilehash: b59a5c474a96d312ebe3a648536ebe827e684931
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832261"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusões de verificação antivírus do Skype for Business Server

Visão geral da interoperação do scanner antivírus com o Skype for Business Server.

Para garantir que o scanner antivírus não interfira com a operação do Skype for Business Server, você deve excluir processos e diretórios específicos para cada servidor ou função de servidor do Skype for Business Server no qual você executar um scanner antivírus. Os seguintes processos e diretórios devem ser excluídos:

> [!NOTE]
> Os locais de pasta e arquivo listados abaixo são os locais padrão do Skype for Business Server. Para os locais nos quais você não usou o padrão, exclua os locais especificados para a sua organização em vez dos locais padrão especificados neste tópico.

> [!IMPORTANT]
> Observe que alguns programas antivírus podem precisar de caminhos absolutos, não relativos, para sua lista de exclusão.

- Processos do Skype for Business Server:

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

- Processos do Windows Fabric Host Service:

  - Fabric.exe

  - FabricDCA.exe

  - FabricHost.exe

- Processos do IIS:

  - %systemroot%\system32\inetsrv\w3wp.exe

  - %systemroot%\SysWOW64\inetsrv\w3wp.exe

- Processos de Back-End SQL Server:

    > [!NOTE]
    > Observe que esses caminhos são específicos da versão do SQL Server.

  - %ProgramFiles%\Microsoft SQL Server\MSSQL11.MSSQLSERVER\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSRS11. MSSQLSERVER\Relatórios Services\ReportServer\Bin\ReportingServicesService.exe

  - %ProgramFiles%\Microsoft SQL Server\MSAS11.MSSQLSERVER\OLAP\Bin\MSMDSrv.exe

- Processos de Front-End SQL Server:

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.LYNCLOCAL\MSSQL\Binn\SQLServr.exe

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTCLOCAL\MSSQL\Binn\SQLServr.exe

  - Instância RTC de Instalação Standard Edition

  - %ProgramFiles%\Microsoft SQL Server\MSSQL12.RTC\MSSQL\Binn\SQLServr.exe

- Arquivos e diretórios:

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Observe que esses caminhos são específicos da versão do Skype for Business Server.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - O repositório de compartilhamento de arquivo (especificado no Construtor de Topologias). Os repositórios de arquivo estão especificados no Construtor de Topologias.

  - Os dados e arquivos de log do  SQL Server, incluindo para o banco de dados de Back-End, repositório de usuários, repositório de arquivamento, repositório de monitoramento e repositório do aplicativo. Os arquivos de log e banco de dados podem ser especificados no Construtor de Topologias. Para obter detalhes sobre os arquivos de dados e de log para cada banco de dados, incluindo nomes padrão, consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de Implantação.

  - Arquivos de log e dados do SQL Server, incluindo aqueles para o banco de dados front-end, o armazenamento do Skype for Business e o armazenamento RtcDatabase. Normalmente, eles estão em %localdrive%\CSData.


