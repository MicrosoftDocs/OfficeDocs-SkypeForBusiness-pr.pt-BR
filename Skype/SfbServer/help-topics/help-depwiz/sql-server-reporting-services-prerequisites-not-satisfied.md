---
title: SQL Server Reporting Services (Pré-requisitos não atendidos)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Você verá essa página se não houver um Servidor de Monitoramento implantado em sua infraestrutura. Isso indica que os requisitos mínimos para implantação do Servidor de Monitoramento não foram atendidos.
ms.openlocfilehash: 94a20ce6f1a48e5eeed098777494e2d1f16597c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687301"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="ad6c0-104">SQL Server Reporting Services (Pré-requisitos não atendidos)</span><span class="sxs-lookup"><span data-stu-id="ad6c0-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="ad6c0-p102">Você verá essa página se não houver um Servidor de Monitoramento implantado em sua infraestrutura. Isso indica que os requisitos mínimos para implantação do Servidor de Monitoramento não foram atendidos.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="ad6c0-107">Para solucionar esse problema, verifique se você tem um servidor de monitoramento associado ao domínio, se ele está definido no construtor de topologias e se a topologia foi publicada.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="ad6c0-108">O SQL Server Reporting Services também deve estar disponível no SQL Server e instalado como um recurso no banco de dados do Monitoring Server no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ad6c0-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="ad6c0-109">Para obter detalhes, consulte [instalar relatórios de monitoramento no Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [implantar o monitoramento](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="ad6c0-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


