---
title: Acessar dados de monitoramento em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Resumo: saiba mais sobre os dados de monitoramento usados em Skype for Business Server.'
ms.openlocfilehash: 416eeb0f1ec724b2d07200ce87d35a466336f9c1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763669"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Acessar dados de monitoramento em Skype for Business Server
 
**Resumo:** Saiba mais sobre os dados de monitoramento usados em Skype for Business Server.
  
Os dados de monitoramento são armazenados em um par de bancos de dados SQL Server databases: LcsCdr para registro de detalhes das chamadas e QoEMetrics para dados sobre a qualidade da experiência. Não há nada de especial nesses dois bancos de dados, o que significa que os dados armazenados neles podem ser acessados por meio das ferramentas que você usa normalmente para acessar e analisar dados do SQL Server.
  
Uma ferramenta que você deve considerar para acessar e analisar dados de monitoramento é a Skype for Business Server Relatórios de Monitoramento. Os Relatórios de monitoramento são um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service. Esses relatórios, que podem ser acessados por meio de navegadores, fornecem informações de uso, diagnóstico de camada e qualidade de mídia, todos com base em registros de detalhes das chamadas call detail recording (CDR) e qualidade da experiência (QoE) armazenados nos bancos de dados de CDR e QoE. Relatórios de monitoramento são Skype for Business Server e podem ser instalados Skype for Business Server Assistente de Implantação do Skype for Business Server após a instalação do Skype for Business Server e a configuração do monitoramento.
  
Os Relatórios de monitoreamente requerem o uso do SQL Server Reporting Service. O SQL Server Reporting Service pode ser instalado ao mesmo tempo que o SQL Server é instalado ou a qualquer momento após a instalação do próprio SQL Server.
  
Para obter mais informações, consulte o tópico [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

