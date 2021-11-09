---
title: SQL Server Reporting Services (Pré-requisitos não atendidos)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Você verá esta página se não houver um Monitoring Server implantado na sua infraestrutura. Isso indica que os requisitos mínimos para a implantação de relatórios do Monitoring Server não foram atendidos.
ms.openlocfilehash: e35ff591b56549e7df350c0efc2898a11c9cf345
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832385"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (Pré-requisitos não atendidos)

Você verá esta página se não houver um Monitoring Server implantado na sua infraestrutura. Isso indica que os requisitos mínimos para a implantação de relatórios do Monitoring Server não foram atendidos.

Para resolver esse problema, certifique-se de que você tenha um Servidor de Monitoramento ingressado no domínio, que ele seja definido no Construtor de Topologias e que a topologia tenha sido publicada. SQL Server Reporting Services também deve estar disponível no SQL Server e instalado como um recurso no banco de dados do Monitoring Server no SQL Server.

Para obter detalhes, [consulte Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).