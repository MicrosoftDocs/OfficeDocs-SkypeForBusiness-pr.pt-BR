---
title: SQL Server Reporting Services (Invocar)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: Depois de fornecer as informações necessárias para a implantação dos relatórios do Monitoring Server para o Microsoft SQL Server 2008 R2 ou para os Serviços de Relatório do Microsoft SQL Server 2012, a página Execute Commands exibe um resumo dos comandos emitidos para instalar os relatórios no SQL Server Reporting Services.
ms.openlocfilehash: b861db053a8851b05ce72a08de6dfae39b9d3bfc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096847"
---
# <a name="sql-server-reporting-services-invoke"></a>SQL Server Reporting Services (Invocar)
 
Depois de fornecer as informações necessárias para a implantação dos relatórios do Monitoring Server para o Microsoft SQL Server 2008 R2 ou para os Serviços de Relatório do Microsoft SQL Server 2012, a página Execute Commands exibe um resumo dos comandos emitidos para instalar os relatórios no SQL Server Reporting Services.
  
Revise o resumo de comandos e anote qualquer erro ou mensagem de aviso exibido pelos comandos. Se um arquivo de log for gerado, selecione o arquivo de log na lista suspensa na janela de resumo e clique em **Exibir Log** para exibir o arquivo de log.
  
> [!IMPORTANT]
> Para que os relatórios do Reporting Services implantem com êxito e para acessar os relatórios após a conclusão da implantação, você deve ter a porta TCP/IP 80 (e, opcionalmente, a porta TCP 443 para SSL, se você atribuir um certificado aos Serviços de Relatórios) aberta no Firewall do Windows com Segurança Avançada no SQL Server. Para obter detalhes, [consulte Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.
  
Depois de analisar o resumo, clique em **Concluir** para concluir a instalação dos relatórios para o SQL Server Reporting Services.
