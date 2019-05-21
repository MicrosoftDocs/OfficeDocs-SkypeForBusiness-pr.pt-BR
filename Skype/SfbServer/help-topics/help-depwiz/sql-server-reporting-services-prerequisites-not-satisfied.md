---
title: SQL Server Reporting Services (Pré-requisitos não atendidos)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Você verá essa página se não houver um Servidor de Monitoramento implantado em sua infraestrutura. Isso indica que os requisitos mínimos para implantação do Servidor de Monitoramento não foram atendidos.
ms.openlocfilehash: af04fd438620bea32bcab95cdbca295c116773b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289551"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="07075-104">SQL Server Reporting Services (Pré-requisitos não atendidos)</span><span class="sxs-lookup"><span data-stu-id="07075-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="07075-p102">Você verá essa página se não houver um Servidor de Monitoramento implantado em sua infraestrutura. Isso indica que os requisitos mínimos para implantação do Servidor de Monitoramento não foram atendidos.</span><span class="sxs-lookup"><span data-stu-id="07075-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="07075-107">Para solucionar esse problema, verifique se você tem um servidor de monitoramento associado ao domínio, se ele está definido no construtor de topologias e se a topologia foi publicada.</span><span class="sxs-lookup"><span data-stu-id="07075-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="07075-108">O SQL Server Reporting Services também deve estar disponível no SQL Server e instalado como um recurso no banco de dados do Monitoring Server no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="07075-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="07075-109">Para obter detalhes, consulte [instalar relatórios de monitoramento no Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [implantar o monitoramento](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="07075-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


