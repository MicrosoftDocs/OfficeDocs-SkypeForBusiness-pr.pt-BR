---
title: SQL Server Reporting Services (Pré-requisitos não atendidos)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Você verá essa página se não houver um Servidor de Monitoramento implantado em sua infraestrutura. Isso indica que os requisitos mínimos para implantação do Servidor de Monitoramento não foram atendidos.
ms.openlocfilehash: 78bc27491c69f0532411567eded61ad3a9f17fa2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925170"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (Pré-requisitos não atendidos)

Você verá essa página se não houver um Servidor de Monitoramento implantado em sua infraestrutura. Isso indica que os requisitos mínimos para implantação do Servidor de Monitoramento não foram atendidos.

Para resolver esse problema, certifique-se de que você tenha um Monitoring Server ingressou no domínio, que ela é definida no construtor de topologia e que a topologia foi publicada. SQL Server Reporting Services também deve estar disponível no SQL Server e instalado como um recurso para o banco de dados do Monitoring Server no SQL Server.

Para obter detalhes, consulte [Instalar relatórios de monitoramento no Skype para Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).


