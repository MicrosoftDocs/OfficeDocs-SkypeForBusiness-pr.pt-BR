---
title: Associar relatórios de monitoramento a um banco de dados espelho em Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumo: saiba como associar Relatórios de Monitoramento a um banco de dados espelho usado por Skype for Business Server.'
---

# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Associar relatórios de monitoramento a um banco de dados espelho em Skype for Business Server 
 
**Resumo:** Saiba como associar Relatórios de Monitoramento a um banco de dados espelho usado por Skype for Business Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Monitorar relatórios com um banco de dados espelho

Se você configurar um espelho para o banco de dados de monitoramento, esse banco de dados espelho assumirá como o banco de dados principal se ocorrer um failover. No entanto, se você usar Skype for Business Server Relatórios de Monitoramento e ocorrer um failover, você poderá descobrir que seus Relatórios de Monitoramento não estão se conectando ao banco de dados espelho. Isso acontece porque, ao instalar relatórios de monitoramento, você especifica apenas o local do banco de dados principal; você não especifica o local do banco de dados espelho.
  
Para fazer com que relatórios de monitoramento sejam automaticamente failover no banco de dados espelho, você deve adicionar o banco de dados espelho como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados do Registro de Detalhes de Chamada e o outro para dados de QoE (Qualidade da Experiência). (Observe que essa etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações do parceiro de failover editando manualmente os valores de cadeia de conexão usados por esses dois bancos de dados. Para fazer isso, conclua o seguinte procedimento:
  
1. Use o Internet Explorer para abrir a **SQL Server Reporting Services** página inicial. A URL da home page do Reporting Services inclui:
    
   - O **prefixo http:**
    
   - O FQDN (nome de domínio totalmente qualificado) do computador onde os Serviços de Relatório estão instalados (por exemplo, `atl-sql-001.litwareinc.com`).
    
   - A cadeia de **caracteres /Reports_**.
    
   - O nome da instância do banco de dados onde os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).
    
     Por exemplo, se SQL Server Reporting Services `atl-sql-001.litwareinc.com` foi instalado no computador e os Relatórios de Monitoramento usarem o archinst de instância do banco de dados, a URL da home page teria esta aparência:
    
     `http://atl-sql-001.litwareinc.com/Reports_archinst`
    
2. Depois de acessar a home page do Reporting Services, clique em **ServerReports** e clique **em Reports_Content**. Isso o levará **à página Reports_Content** para os relatórios Skype for Business Server monitoramento.
    
3. Na página **Reports_Content** , clique na fonte de dados **CDRDB** .
    
4. Na página **CDRDB** , na guia **Propriedades** , procure a caixa de texto rotulada **Cadeia de caracteres de conexão**. A cadeia de caracteres de conexão atual será semelhante a esta:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Edite a cadeia de caracteres de conexão para incluir o nome do servidor e a instância do banco de dados do espelho. Por exemplo, se o servidor for nomeado atl-mirror-001 e o banco de dados espelho estiver na instância archinst, você precisará adicionar para especificar o banco de dados espelho usando esta sintaxe:
    
    Failover Partner=atl-mirror-001\archinst
    
    Sua cadeia de caracteres de conexão editada será assim:
    
    Fonte de dados=(local)\archinst; Failover Partner=atl-mirror-001\archinst;catalog=LcsCDR
    
6. Depois de atualizar a cadeia de caracteres de conexão, clique em **Aplicar**.
    
7. Na página **CDRDB** , **clique no Reports_Content** link. Clique na **fonte de dados QMSDB** e edite a cadeia de conexão do banco de dados QoE. Por exemplo:
    
    `Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics`
    
8. Clique em **Aplicar**.
    
## <a name="see-also"></a>Confira também

[Instalar relatórios de monitoramento no Skype for Business Server](install-monitoring-reports.md)
  
[Usando relatórios de monitoramento no Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
