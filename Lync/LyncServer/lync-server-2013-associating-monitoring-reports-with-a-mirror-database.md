---
title: 'Lync Server 2013: associando relatórios de monitoramento a um banco de dados espelho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Associando relatórios de monitoramento a um banco de dados espelho no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-07_

Se você configurar um espelho para o seu banco de dados de monitoramento, esse banco de dados espelho assumirá a função de banco de dados primário em caso de failover. No entanto, se você usar os relatórios de monitoramento do Lync Server e ocorrer um failover, pode ser que seus relatórios de monitoramento não estejam se conectando ao banco de dados espelho. Isso ocorre porque quando você instala os Relatórios de Monitoramento, apenas o local do banco de dados primário é especificado; você não especifica o local do banco de dados espelho.

Para que o failover dos Relatórios de Monitoramento seja executado automaticamente no banco de dados espelho, adicione esse banco de dados como um "parceiro de failover" aos dois bancos de dados usados pelos Relatórios de Monitoramento (um banco de dados para dados de Registro de Detalhe das Chamadas e o outro para dados de Qualidade da Experiência (QoE)). (Observe que essa etapa deve ser executada após a instalação dos Relatórios de Monitoramento.) Você pode adicionar as informações de parceiro de failover editando manualmente os valores da cadeia de conexão usados por esses dois bancos de dados. Para fazer isso, siga este procedimento:

1.  Use o Internet Explorer para abrir a home page do **SQL Server Reporting Services**. A URL dessa home page inclui:
    
      - O prefixo **http:**.
    
      - O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **atl-sql-001.litwareinc.com**).
    
      - A cadeia de **caracteres\_/Reports**.
    
      - O nome da instância de banco de dados em que os Relatórios de Monitoramento estão instalados (por exemplo, **archinst**).
    
    Por exemplo, se o SQL Server Reporting Services for instalado no computador atl-sql-001.litwareinc.com e os Relatórios de Monitoramento usarem a instância de banco de dados archinst, a URL da home page será parecida com esta:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Depois de acessar a página inicial do Reporting Services, clique em **LyncServerReports**e, em seguida, clique em **relatórios\_de conteúdo**. Isso o levará até a página de **conteúdo relatórios\_** dos relatórios de monitoramento do Lync Server.

3.  Na página **relatórios\_de conteúdo** , clique na fonte de dados **CDRDB** .

4.  Na página **CDRDB**, na guia **Propriedades**, procure a caixa de texto chamada **Cadeia de conexão**. A cadeia de conexão atual será semelhante a esta:
    
    **Dados fonte = (local)\\archinst; Initial Catalog = LcsCDR**

5.  Edite a cadeia de conexão para incluir o nome do servidor e a instância de banco de dados do banco de dados espelho. Por exemplo, se o servidor se chamar atl-mirror-001 e o banco de dados espelho estiver na instância archinst, será necessário especificar o banco de dados espelho usando esta sintaxe:
    
    **Parceiro de failover = ATL-Mirror-\\001 archinst**
    
    A cadeia de conexão editada será parecida com esta:
    
    **Dados fonte = (local)\\archinst; Parceiro de failover = ATL-Mirror-\\001 archinst; Initial Catalog = LcsCDR**

6.  Após a atualização da cadeia de conexão, clique em **Aplicar**.

7.  Na página **CDRDB** , clique no link **de\_conteúdo relatórios** . Clique na fonte de dados **QMSDB** e edite a cadeia de conexão do banco de dados de QoE. Por exemplo:
    
    **Dados fonte = (local)\\archinst; Parceiro de failover = ATL-Mirror-\\001 archinst; Initial Catalog = QoEMetrics**

8.  Clique em **Aplicar**.

<div>

## <a name="see-also"></a>Confira também


[Instalando relatórios de monitoramento do Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Usar relatórios de monitoramento no Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

