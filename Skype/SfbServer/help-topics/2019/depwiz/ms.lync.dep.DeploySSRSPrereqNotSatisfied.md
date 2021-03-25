---
title: SQL Server Reporting Services (Pré-requisitos não atendidos)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: Você verá esta página se não houver um Monitoring Server implantado na sua infraestrutura. Isso indica que os requisitos mínimos para a implantação de relatórios do Monitoring Server não foram atendidos.
ms.openlocfilehash: 657c1b203dd5d01fedde9ad0c5b08c6775f4bd4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118900"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="7775c-104">SQL Server Reporting Services (Pré-requisitos não atendidos)</span><span class="sxs-lookup"><span data-stu-id="7775c-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="7775c-p102">Você verá esta página se não houver um Monitoring Server implantado na sua infraestrutura. Isso indica que os requisitos mínimos para a implantação de relatórios do Monitoring Server não foram atendidos.</span><span class="sxs-lookup"><span data-stu-id="7775c-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="7775c-107">Para resolver esse problema, certifique-se de que você tenha um Servidor de Monitoramento ingressado no domínio, que ele seja definido no Construtor de Topologias e que a topologia tenha sido publicada.</span><span class="sxs-lookup"><span data-stu-id="7775c-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="7775c-108">SQL Server Os Serviços de Relatório também devem estar disponíveis no SQL Server e instalados como um recurso no banco de dados do Monitoring Server no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7775c-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="7775c-109">Para obter detalhes, [consulte Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span><span class="sxs-lookup"><span data-stu-id="7775c-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>