---
title: Associar Relatórios de Monitoramento a um banco de dados espelho no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumo: Saiba como associar relatórios de monitoramento a um banco de dados espelho usado pelo Skype for Business Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802161"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Associar Relatórios de Monitoramento a um banco de dados espelho no Skype for Business Server 
 
**Resumo:** Saiba como associar relatórios de monitoramento a um banco de dados espelho usado pelo Skype for Business Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Monitorar relatórios com um banco de dados espelho

Se você configurar um espelho para o banco de dados de monitoramento, esse banco de dados espelho assumirá como o banco de dados principal se ocorrer um failover. No entanto, se você usar os Relatórios de Monitoramento do Skype for Business Server e ocorrer um failover, poderá descobrir que seus Relatórios de Monitoramento não estão se conectando ao banco de dados espelho. Isso acontece porque, ao instalar os Relatórios de Monitoramento, você especifica apenas o local do banco de dados primário; você não especifica o local do banco de dados espelho.
  
Para fazer com que os Relatórios de Monitoramento sejam automaticamente failover para o banco de dados espelho, você deve adicionar o banco de dados espelho como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados de Registro de Detalhe da Chamada e outro para dados de QoE (Qualidade da Experiência). (Observe que esta etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações do parceiro de failover editando manualmente os valores de sequência de conexão usados por esses dois bancos de dados. Para fazer isso, conclua o seguinte procedimento:
  
1. Use o Internet Explorer para abrir a **home page do SQL Server Reporting Services.** A URL da home page do Reporting Services inclui:
    
   - O **prefixo http:**
    
   - O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **atl-sql-001.litwareinc.com**).
    
   - A cadeia de **caracteres /Reports_**.
    
   - O nome da instância do banco de dados onde os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).
    
     Por exemplo, se o SQL Server Reporting Services tiver sido instalado no computador atl-sql-001.litwareinc.com e os Relatórios de Monitoramento usarem o arquivamento de instância de banco de dados, a URL da home page terá esta aparência:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Depois de acessar a home page do Reporting Services, clique em **ServerReports** e clique em **Reports_Content**. Isso levará você para a página **Reports_Content** para os Relatórios de Monitoramento do Skype for Business Server.
    
3. Na página **Reports_Content,** clique na fonte de dados **CDRDB.**
    
4. Na página **CDRDB,** na guia **Propriedades,** procure a caixa de texto rotulada **Sequência de** conexão. A cadeia de conexão atual será semelhante a esta:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Edite a cadeia de conexão para incluir o nome do servidor e a instância do banco de dados para o banco de dados espelho. Por exemplo, se o servidor for nomeado como atl-mirror-001 e o banco de dados espelho estiver na instância archinst, você precisará adicionar para especificar o banco de dados espelho usando esta sintaxe:
    
    Failover Partner=atl-mirror-001\archinst
    
    Sua sequência de conexão editada terá a aparência a seguir:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Depois de atualizar a cadeia de conexão, clique em **Aplicar.**
    
7. Na página **CDRDB,** clique **Reports_Content** link. Clique na **fonte de dados QMSDB** e edite a cadeia de conexão para o banco de dados de QoE. Por exemplo:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Clique em **Aplicar**.
    
## <a name="see-also"></a>Confira também

[Instalar relatórios de monitoramento no Skype for Business Server](install-monitoring-reports.md)
  
[Usando relatórios de monitoramento no Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
