---
title: SQL Server Reporting Services (Pré-requisitos não atendidos)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: Você verá esta página se não houver um Monitoring Server implantado na sua infraestrutura. Isso indica que os requisitos mínimos para a implantação de relatórios do Monitoring Server não foram atendidos.
ms.openlocfilehash: 36b9270f5046c1bd784d87c10f41a64dfcc41e2e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387199"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (Pré-requisitos não atendidos)

Você verá esta página se não houver um Monitoring Server implantado na sua infraestrutura. Isso indica que os requisitos mínimos para a implantação de relatórios do Monitoring Server não foram atendidos.

Para resolver esse problema, certifique-se de que você tenha um Servidor de Monitoramento ingressado no domínio, que ele seja definido no Construtor de Topologias e que a topologia tenha sido publicada. SQL Server Reporting Services também deve estar disponível no SQL Server e instalado como um recurso no banco de dados do Monitoring Server no SQL Server.

Para obter detalhes, [consulte Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).