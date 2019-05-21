---
title: Acessar os dados de monitoramento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Resumo: Saiba mais sobre os dados de monitoramento usados no Skype for Business Server.'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303877"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Acessar os dados de monitoramento no Skype for Business Server
 
**Resumo:** Saiba mais sobre os dados de monitoramento usados no Skype for Business Server.
  
Os dados de monitoramento são armazenados em um par de bancos de dados SQL Server: LcsCdr para registro de detalhes das chamadas e QoEMetrics para dados sobre a qualidade da experiência. Não há nada de especial nesses dois bancos de dados, o que significa que os dados armazenados neles podem ser acessados por meio das ferramentas que você usa normalmente para acessar e analisar dados do SQL Server.
  
Uma ferramenta que você deve considerar para acessar e analisar os dados de monitoramento são os relatórios de monitoramento do Skype for Business Server. Os Relatórios de monitoramento são um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service. Esses relatórios, que podem ser acessados por meio de navegadores, fornecem informações de uso, diagnóstico de chamada e qualidade de mídia, com base em registros de detalhes das chamadas (CDR) e qualidade da experiência (QoE) armazenados nos bancos de dados de CDR e QoE. Os relatórios de monitoramento são fornecidos com o Skype for Business Server e podem ser instalados no assistente de implantação do Skype for Business Server após a instalação do Skype for Business Server e o monitoramento ter sido configurado.
  
Os Relatórios de monitoramento requerem o uso do SQL Server Reporting Service. O SQL Server Reporting Service pode ser instalado ao mesmo tempo que o SQL Server é instalado ou a qualquer momento após a instalação do próprio SQL Server.
  
Para obter mais informações, consulte o tópico [instalar relatórios de monitoramento no Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

