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
# <a name="access-monitoring-data-in-skype-for-business-server-2015"></a>Acessar dados de monitoramento no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre os dados de monitoramento usados no Skype para Business Server 2015.
  
Os dados de monitoramento são armazenados em um par de bancos de dados SQL Server: LcsCdr para registro de detalhes das chamadas e QoEMetrics para dados sobre a qualidade da experiência. Não há nada de especial nesses dois bancos de dados, o que significa que os dados armazenados neles podem ser acessados por meio das ferramentas que você usa normalmente para acessar e analisar dados do SQL Server.
  
Uma ferramenta que você deve considerar para acessar e analisar dados de monitoração é o Skype para relatórios de monitoramento de servidor de negócios. Os Relatórios de monitoramento são um conjunto de relatórios padrão publicados pelo Microsoft SQL Server Reporting Service. Esses relatórios, que podem ser acessados por meio de navegadores, fornecem informações de uso, diagnóstico de chamada e qualidade de mídia, com base em registros de detalhes das chamadas (CDR) e qualidade da experiência (QoE) armazenados nos bancos de dados de CDR e QoE. Relatórios de monitoramento acompanham o Skype para Business Server 2015 e podem ser instalados a partir do Skype para o Assistente de implantação de servidor de negócios depois Skype para Business Server foi instalado e monitoramento foi configurado.
  
Os Relatórios de monitoramento requerem o uso do SQL Server Reporting Service. O SQL Server Reporting Service pode ser instalado ao mesmo tempo que o SQL Server é instalado ou a qualquer momento após a instalação do próprio SQL Server.
  
Para obter mais informações, consulte o tópico [Instalar relatórios de monitoramento no Skype para Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) no Skype para guia de implantação de negócios Server 2015.
  

