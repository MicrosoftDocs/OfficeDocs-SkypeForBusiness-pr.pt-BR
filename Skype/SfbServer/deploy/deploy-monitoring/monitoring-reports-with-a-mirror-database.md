---
title: Associar relatórios de monitoramento a um banco de dados de espelho em Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumo: Saiba como associar relatórios de monitoramento de um banco de dados de espelho usado pelo Skype para Business Server.'
ms.openlocfilehash: c598e8c14c5a592203501ca40264232ce344b2bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894532"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Associar relatórios de monitoramento a um banco de dados de espelho em Skype para Business Server 
 
**Resumo:** Saiba como associar relatórios de monitoramento de um banco de dados de espelho usado pelo Skype para Business Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Monitoramento de relatórios com um banco de dados espelho

Se você configurar um espelho para o seu banco de dados de monitoramento, esse banco de dados espelho assumirá a função de banco de dados primário em caso de failover. No entanto, se você usar o Skype para relatórios de monitoramento de servidor de negócios e ocorre um failover, você pode achar que seus relatórios de monitoramento não estiver se conectando ao banco de dados espelho. Isso ocorre porque quando você instala os Relatórios de Monitoramento, apenas o local do banco de dados primário é especificado; você não especifica o local do banco de dados espelho.
  
Para que o failover dos Relatórios de Monitoramento seja executado automaticamente no banco de dados espelho, adicione esse banco de dados como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados de Registro de Detalhe das Chamadas e o outro para dados de Qualidade da Experiência (QoE)). (Observe que essa etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações de parceiro de failover editando manualmente os valores da cadeia de conexão usados por esses dois bancos de dados. Para fazer isso, siga este procedimento:
  
1. Use o Internet Explorer para abrir a home page do **SQL Server Reporting Services**. A URL dessa home page inclui:
    
   - O prefixo **http:**.
    
   - O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **atl-sql-001.litwareinc.com**).
    
   - A cadeia de caracteres **/Reports_**.
    
   - O nome da instância de banco de dados em que os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).
    
     Por exemplo, se o SQL Server Reporting Services for instalado no computador atl-sql-001.litwareinc.com e os Relatórios de Monitoramento usarem a instância de banco de dados archinst, a URL da home page será parecida com esta:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Depois que você acessar a home page do Reporting Services, clique em **ServerReports** e em **Reports_Content**. Isso levará você à página **Reports_Content** para o Skype para relatórios de monitoramento de servidor de negócios.
    
3. Na página **Reports_Content**, clique na fonte de dados **CDRDB**.
    
4. Na página **CDRDB**, na guia **Propriedades**, procure a caixa de texto chamada **Cadeia de conexão**. A cadeia de conexão atual será semelhante a esta:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Edite a cadeia de conexão para incluir o nome do servidor e a instância de banco de dados do banco de dados espelho. Por exemplo, se o servidor se chamar atl-mirror-001 e o banco de dados espelho estiver na instância archinst, será necessário especificar o banco de dados espelho usando esta sintaxe:
    
    Failover Partner=atl-mirror-001\archinst
    
    A cadeia de conexão editada será parecida com esta:
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Após a atualização da cadeia de conexão, clique em **Aplicar**.
    
7. Na página **CDRDB**, clique no link **Reports_Content**. Clique na fonte de dados **QMSDB** e edite a cadeia de conexão do banco de dados de QoE. Por exemplo:
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Clique em **Aplicar**.
    
## <a name="see-also"></a>Confira também

[Instalar os relatórios de monitoramento em Skype para Business Server](install-monitoring-reports.md)
  
[Usando relatórios de monitoramento no Skype para Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
