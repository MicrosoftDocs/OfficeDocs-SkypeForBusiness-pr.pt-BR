---
title: Acessar dados de monitoramento no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Resumo: Saiba mais sobre os dados de monitoramento usados no Skype para Business Server 2015.'
ms.openlocfilehash: 908ebbff4e88985cdba606098dc5a5ace271e30d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="access-monitoring-data-in-skype-for-business-server-2015"></a><span data-ttu-id="f6342-103">Acessar dados de monitoramento no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f6342-103">Access monitoring data in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f6342-104">**Resumo:** Saiba mais sobre os dados de monitoramento usados no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6342-104">**Summary:** Learn about the monitoring data used in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f6342-p101">Os dados de monitoramento são armazenados em um par de bancos de dados SQL Server: LcsCdr para registro de detalhes das chamadas e QoEMetrics para dados sobre a qualidade da experiência. Não há nada de especial nesses dois bancos de dados, o que significa que os dados armazenados neles podem ser acessados por meio das ferramentas que você usa normalmente para acessar e analisar dados do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f6342-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="f6342-107">Uma ferramenta que você deve considerar para acessar e analisar dados de monitoração é o Skype para relatórios de monitoramento de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="f6342-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="f6342-108">Os Relatórios de monitoramento são um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="f6342-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="f6342-109">Esses relatórios, que podem ser acessados por meio de navegadores, fornecem informações de uso, diagnóstico de chamada e qualidade de mídia, com base em registros de detalhes das chamadas (CDR) e qualidade da experiência (QoE) armazenados nos bancos de dados de CDR e QoE.</span><span class="sxs-lookup"><span data-stu-id="f6342-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="f6342-110">Relatórios de monitoramento acompanham o Skype para Business Server 2015 e podem ser instalados a partir do Skype para o Assistente de implantação de servidor de negócios depois Skype para Business Server foi instalado e monitoramento foi configurado.</span><span class="sxs-lookup"><span data-stu-id="f6342-110">Monitoring Reports ship with Skype for Business Server 2015 and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="f6342-p103">Os Relatórios de monitoramento requerem o uso do SQL Server Reporting Service. O SQL Server Reporting Service pode ser instalado ao mesmo tempo que o SQL Server é instalado ou a qualquer momento após a instalação do próprio SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f6342-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="f6342-113">Para obter mais informações, consulte o tópico [Instalar relatórios de monitoramento no Skype para Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) no Skype para guia de implantação de negócios Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6342-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) in the Skype for Business Server 2015 deployment guide.</span></span>
  

