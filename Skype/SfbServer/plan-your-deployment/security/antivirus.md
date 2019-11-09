---
title: Exclusões de verificação antivírus para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral da interoperação do verificador de antivírus com o Skype for Business Server.
ms.openlocfilehash: 69fb02d04f27b7444a3b8cadaacafc05654a1c9f
ms.sourcegitcommit: 1aa98e3865d5a0f7be5e1cba497dea4ac7b9c607
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2019
ms.locfileid: "38074623"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusões de verificação antivírus para o Skype for Business Server

Visão geral da interoperação do verificador de antivírus com o Skype for Business Server.

Para garantir que o verificador de vírus não interfira com a operação do Skype for Business Server, você deve excluir processos e diretórios específicos para cada função de servidor ou servidor do Skype for Business Server na qual você executa um scanner antivírus. Os seguintes processos e diretórios devem ser excluídos:

> [!NOTE]
> Os locais de pasta e arquivo listados abaixo são os locais padrão do Skype for Business Server. Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico.

> [!IMPORTANT]
> Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão.

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
  
  - LyncBackupService. exe

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

  - %systemroot%\System32\LogFiles

  - %systemroot%\SysWow64\LogFiles

  - %systemroot%\Microsoft.NET\assembly\GAC_MSIL

    > [!NOTE]
    > Observe que esses caminhos são específicos para a versão do Skype for Business Server.

  - %programfiles%\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node

  - %programfiles%\Common Files\Skype for Business Server 2015

  - %programfiles%\Common Files\Skype for Business Online

  - %SystemDrive%\RtcReplicaRoot

  - Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.

  - Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para mais detalhes sobre os dados e arquivos de log para cada base de dados, incluindo os nomes padrão, consulte [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na Documentação de implantação.

  - Dados do SQL Server e arquivos de log, incluindo aqueles para o banco de dados front-end, a loja do Skype for Business e a loja do RtcDatabase. Normalmente, eles estão sob %localdrive%\CSData.


