---
title: Exclusões de varredura Skype para Business Server de antivírus
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5d742259-ef3b-417a-920b-e1fa0e48f043
description: Visão geral do interoperação de scanner antivírus com Skype para Business Server.
ms.openlocfilehash: 2e85816b10a808224a79b065153ecf466c4911c8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009261"
---
# <a name="antivirus-scanning-exclusions-for-skype-for-business-server"></a>Exclusões de varredura Skype para Business Server de antivírus
 
Visão geral do interoperação de scanner antivírus com Skype para Business Server.

Este artigo contém recomendações que podem ajudar a um administrador determinar a causa do possível instabilidade em um computador que está executando uma versão compatível do Microsoft Windows quando ele é usado com o software antivírus em um domínio do Active Directory ambiente ou em um ambiente de negócios gerenciados.

É recomendável que você aplique temporariamente estes procedimentos para avaliar um sistema. Se o desempenho do sistema ou a estabilidade é aprimorada pelas recomendações feitas neste artigo, entre em contato com seu fornecedor de software antivírus para obter instruções ou para uma versão atualizada do software antivírus.

Este artigo contém informações que mostram como ajudar a diminuir as configurações de segurança ou como desativar temporariamente os recursos de segurança em um computador. Você pode fazer essas alterações para entender a natureza de um problema específico. Antes de fazer essas alterações, recomendamos que você avaliar os riscos associados à implementação dessa solução alternativa no ambiente específico. Se você implementar essa solução alternativa, execute quaisquer etapas apropriadas adicionais para ajudar a proteger os arquivos que não são mais estão sendo examinados pelo seu software antivírus no computador.
  
Para garantir que o scanner antivírus não interfere com a operação do Skype para Business Server, você deve excluir diretórios e processos específicos para cada Skype para servidor de Business Server ou função de servidor em que você executa um scanner antivírus. Os seguintes processos e diretórios devem ser excluídos:
  
> [!NOTE]
> Locais de arquivo e pasta listadas a seguir são os locais de padrão do Skype para Business Server. Para quaisquer locais, para os quais você não usa o padrão, exclua os locais que você especificou para a sua organização em vez dos locais padrão especificados neste tópico. 
  
> [!IMPORTANT]
> Observe que alguns programas antivírus podem precisar de caminhos absolutos e não relativos, para a sua lista de exclusão. 
  
- Skype para processos de negócios Server:
    
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

    > [!NOTE]
    > Observe que esses caminhos são específicos para Skype para a versão do servidor de negócios. 
    
  - %programfiles%\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Server 2015\Watcher Node
    
  - %programfiles%\Common Files\Skype for Business Server 2015
    
  - %programfiles%\Common Files\Skype for Business Online
    
  - %SystemDrive%\RtcReplicaRoot
    
  - Repositório de compartilhamento de arquivo(específico no Construtor de Topologias). Os repositórios de arquivos são especificados no Construtor de Topologias.
    
  - Os arquivos de logs e dados do SQL Server, incluindo aqueles para o banco de dados de back-end, armazenamento de usuário, arquivamento, monitoramento, e repositório de application. Os arquivos da base de dados e os logs podem ser especificados no Construtor de Topologias. Para obter detalhes sobre os arquivos de dados e log para cada banco de dados, incluindo nomes padrão, consulte a [localização do arquivo de Log e de dados do SQL Server](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) na documentação de implantação.
    
  - Arquivos do SQL Server dados e log, incluindo aqueles para o banco de dados front-end, Skype para repositório corporativo e RtcDatabase repositório. Normalmente, eles estão sob %localdrive%\CSData.
    

