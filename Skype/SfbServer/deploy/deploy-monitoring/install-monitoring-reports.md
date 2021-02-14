---
title: Instalar relatórios de monitoramento no Skype for Business Server
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
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Resumo: Saiba como instalar um serviço que gerará relatórios de Monitoramento no Skype for Business Server.'
ms.openlocfilehash: 10a98bea4af3511c50a0b2b814f8b44911f3742f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802251"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Instalar relatórios de monitoramento no Skype for Business Server
 
**Resumo:** Saiba como instalar um serviço que gerará relatórios de monitoramento no Skype for Business Server.
  
Os Relatórios de Monitoramento do Skype for Business Server fornecem uma grande variedade de informações sobre a qualidade e a quantidade de sessões de comunicação que ocorrem em sua organização. 
  
## <a name="install-monitoring-reports"></a>Instalar relatórios de monitoramento

Os Relatórios de Monitoramento não são instalados automaticamente quando você instala o Skype for Business Server; em vez disso, você deve instalar os Relatórios de Monitoramento separadamente e somente depois que o Skype for Business Server tiver sido instalado no computador.
  
> [!NOTE]
> Recomenda-se a instalação dos relatórios de monitoramento no mesmo computador em que o banco de dados de monitoramento está instalado. Isso simplifica o processo de atribuição de permissões para acessar os relatórios: a com a instalação dos relatórios de monitoramento no computador que hospeda o repositório de monitoramento, você não precisará configurar permissões que permitam que um banco de dados em um computador interaja com os Reporting Services em execução em outro computador. 
  
Os Relatórios de Monitoramento do Skype for Business Server incluem mais de 30 relatórios projetados para fornecer informações detalhadas sobre conferências, sessões de IM ponto a ponto, registros de usuário, o aplicativo Grupo de Resposta e muito mais. Para a versão 2013, os Relatórios de Monitoramento do Skype for Business Server incluem vários aprimoramentos:
  
- **Novos relatórios de qualidade de voz**. Esses novos relatórios incluem o Relatório de Comparação de Qualidade de Mídia no [Skype for Business Server](../../manage/health-and-monitoring/comparison.md), que compara a qualidade entre diferentes tipos de chamadas (por exemplo, entre chamadas com fio e chamadas sem fio); e o Relatório de Tempo de Ingressar em Conferência no [Skype for Business Server](../../manage/health-and-monitoring/join-time-report.md), que fornece informações sobre o tempo necessário para os usuários ingressarem em uma conferência. 
    
- **Relatórios aprimorados para analisar e solucionar problemas de sessões de vídeo e compartilhamento de aplicativos.** O Relatório de Resumo de Qualidade de Mídia no [Skype for Business Server](../../manage/health-and-monitoring/summary.md) oferece uma maneira de analisar chamadas de vídeo e compartilhamento de aplicativos, enquanto o Relatório de Desempenho do Servidor no Skype for Business [Server](../../manage/health-and-monitoring/server-performance.md) detalha o desempenho dos servidores que geram essas chamadas. As métricas de vídeo e compartilhamento de aplicativos também são relatadas pelo Relatório detalhado de sessão ponto a ponto no [Skype for Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) e pelo Relatório de Detalhes da Conferência no Skype for Business [Server.](../../manage/health-and-monitoring/detail-report.md)
    
- **Desempenho de relatórios aprimorado**. Inclui tempos menores de resposta e recuperação de dados, bem como navegação mais rápida e fácil pelos relatórios.
    
Encontre mais informações sobre os relatórios individuais na documentação dos relatórios de monitoramento.
  
> [!NOTE]
> Há outro relatório - Sub-relatório de detalhes de chamada de QoE - incluído no Skype for Business Server. Porém, seu uso é principalmente interno e o acesso a ele não pode ser feito diretamente. 
  
Há duas maneiras de instalar os Relatórios de Monitoramento do Skype for Business Server: você pode usar o Assistente de Implantação do Skype for Business Server ou usar um script do Windows PowerShell incluído nos arquivos de instalação do Skype for Business Server. Independente do método usado para instalar os relatórios, primeiro você deve certificar-se de:
  
- Ter o direito de adicionar uma função de banco de dados a uma conta de usuário no banco de dados de monitoramento.
    
- Possuir a função Gerenciador de Conteúdo no SQL Server Reporting Services. Essa função concede o direito de implantar relatórios no SQL Server Reporting Services.
    
Para instalar os relatórios de monitoramento usando o Assistente de Implantação, siga as etapas a seguir:
  
1. Clique **em** Iniciar, em **Todos os Programas,** **no Skype for Business Server** e no Assistente de Implantação do Skype for **Business Server.**
    
2. No Assistente de Implantação, clique em **Implantar Relatórios de Monitoramento** para iniciar o assistente Implantar Relatórios de Monitoramento.
    
3. No assistente Implantar Relatórios de Monitoramento, na página **Especificar Banco de Dados de Monitoramento**, certifique-se de que o nome de domínio totalmente qualificado do computador que hospeda o repositório de monitoramento apareça na lista suspensa **Banco de dados de monitoramento** (caso tenha vários repositórios de monitoramento, será necessário selecionar o servidor correto na lista suspensa). Verifique se a instância correta do SQL Server aparece na caixa **Instância do SSRS (SQL Server Reporting Services)** (por exemplo, **atl-sql-001.litwareinc.com/archinst**) e clique em **Avançar**.
    
4. Na página **Especificar Credenciais**, na caixa **Nome de usuário**, digite o nome de domínio e nome de usuário da conta a ser usada ao acessar os relatórios de monitoramento (por exemplo, **litwareinc\kenmyer**). Se você não usar esse formato (domínio \nome de usuário), ocorrerá um erro.
    
    Digite a senha da conta de usuário na caixa **Senha** e clique em **Avançar**. Observe que nenhum direito especial é necessário para essa conta. A conta receberá automaticamente as permissões necessárias de logon e banco de dados quando a instalação for concluída.
    
5. Na página **Especificar Grupo Somente Leitura**, informe o nome de um grupo de segurança ao qual será concedido acesso somente leitura ao SQL Server Reporting Services na caixa Grupo de usuários. Por exemplo, para conceder aos administradores acesso somente leitura aos relatórios, digite **RTCUniversalReadOnlyAdmins**. Clique em **Avançar**.
    
6. Na página **Executando Comandos**, clique em **Concluir**.
    
Os Relatórios de Monitoramento também podem ser instalados a partir do Shell de Gerenciamento do Skype for Business Server executando o script DeployReports.ps1; esse script do Windows PowerShell pode ser encontrado na pasta \<install location\> \Skype for Business Server 2015\Deployment\Setup. Para instalar os relatórios de monitoramento usando DeployReports.ps1, digite um comando semelhante a este no prompt do Shell de Gerenciamento:
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

Os parâmetros usados no comando anterior são descritos na tabela a seguir:
  
|**Nome do Parâmetro**|**Obrigatório**|**Descrição**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Sim  <br/> |Conta de usuário (no formato domínio\nome_de_usuário) usada para acessar o repositório de monitoramento; por exemplo:  <br/> ```-storedUserName "litwareinc\kenmyer"``` Essa conta deve ter as permissões do SQL Server e do SQL Server Reporting Services especificadas anteriormente, ou o script falhará.  <br/> |
|storedPassword  <br/> |Sim  <br/> |Senha da conta de usuário usada para acessar o repositório de monitoramento.  <br/> |
|readOnlyGroupName  <br/> |Não  <br/> |Grupo de segurança local ou domínio cujos membros receberão acesso somente leitura aos relatórios de monitoramento. Observe que o script falhará se o grupo especificado não existir. Caso decida revogar as permissões posteriormente ou se decidir conceder permissão de acesso a outros usuários ou grupos, faça isso usando o gerenciador de relatórios do SQL Server Reporting Services.  <br/> |
|reportSqlServerInstance  <br/> |Não  <br/> |Instância do SQL Server que hospeda o Reporting Service. A instância de relatório deve ser especificada usando o nome de domínio totalmente qualificado do servidor de relatório. Por exemplo:<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com``` Se esse parâmetro não for incluído, o script assumirá que os serviços de relatório são hospedados pela mesma instância do SQL Server que hospeda o banco de dados de monitoramento.  <br/> |
|monitoringDatabaseId  <br/> |Não  <br/> |Identidade de serviço do banco de dados de monitoramento. Você pode retornar as identidades dos bancos de dados de monitoramento executando este comando:<br/> ```Get-CsService -MonitoringDatabase```|
   
Após a instalação dos Relatórios de Monitoramento, você deve usar o cmdlet New-CsReportingConfiguration para configurar a URL usada para acessar esses relatórios. Essa tarefa pode ser realizada no Shell de Gerenciamento do Skype for Business Server executando o seguinte comando do Windows PowerShell. Observe que, apesar de recomendado, não é obrigatório usar o protocolo HTTPS ao configurar o URL do relatório:
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

No comando anterior, a propriedade ReportingUrl deve ser definida como o URL do Gerenciador de Relatórios usado pelo  SQL Server 2008 R2 Reporting Services. Você pode determinar o URL do Gerenciador de Relatórios concluindo as etapas a seguir no computador onde o  SQL Server Reporting Services foi instalado:
  
1. Clique em Iniciar, Todos os Programas,  Microsoft SQL Server 2008 R2, Ferramentas de Configuração e Gerenciador de Configuração do Reporting Services.
    
2. Na caixa de diálogo Conexão de Configuração do Reporting Services, certifique-se de que o nome do computador do Reporting Services apareça na caixa Nome do Servidor. Selecione a instância do SQL Server na lista suspensa Instância do Servidor de Relatório e clique em Conectar.
    
3. no Gerenciador de Configuração do Reporting Services, clique em URL do Gerenciador de Relatório. Um ou mais URLs devem aparecer no painel URL do Gerenciador de Relatório. Todos esses URLs podem ser usados como URL de relatório, embora, mais uma vez, seja recomendado que ReportingUrl use o protocolo HTTPS.
    
Se você tiver definido um banco de dados espelho para seu banco de dados de monitoramento, também deverá associar os Relatórios de Monitoramento ao banco de dados espelho. Consulte o artigo [Associate Monitoring Reports with a mirror database in Skype for Business Server](monitoring-reports-with-a-mirror-database.md) for details.
  

