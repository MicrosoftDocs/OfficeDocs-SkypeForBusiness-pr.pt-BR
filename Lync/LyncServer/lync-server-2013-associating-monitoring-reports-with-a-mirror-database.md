---
title: 'Lync Server 2013: associando relatórios de monitoramento a um banco de dados espelho'
description: 'Lync Server 2013: associando relatórios de monitoramento a um banco de dados espelho.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64b37901e7939b5e904dec73caac2d3483e2d71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568797"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Associando relatórios de monitoramento a um banco de dados espelho no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-07_

Se você configurar um espelho para seu banco de dados de monitoramento, o banco de dados espelho assumirá o controle como o banco de dados primário se ocorrer um failover. No entanto, se você usar os relatórios de monitoramento do Lync Server e ocorrer um failover, poderá achar que seus relatórios de monitoramento não estão se conectando ao banco de dados espelho. Isso ocorre porque, quando você instala relatórios de monitoramento, você especifica apenas o local do banco de dados primário; Você não especifica o local do banco de dados espelho.

Para obter relatórios de monitoramento para failover automático para o banco de dados espelho, você deve adicionar o banco de dados espelho como um "parceiro de failover" aos dois bancos de dados usados pelos relatórios de monitoramento (um banco de dados para dados de registro de detalhes de chamadas e o outro para dados de qualidade da experiência (QoE)). (Observe que esta etapa deve ser executada após a instalação dos relatórios de monitoramento.) Você pode adicionar as informações do parceiro de failover editando manualmente os valores da cadeia de caracteres de conexão usados por esses dois bancos de dados. Para fazer isso, conclua o seguinte procedimento:

1.  Use o Internet Explorer para abrir a página inicial do **SQL Server Reporting Services** . A URL da home page do Reporting Services inclui:
    
      - O prefixo **http:** .
    
      - O FQDN (nome de domínio totalmente qualificado) do computador em que o Reporting Services está instalado (por exemplo, **ATL-SQL-001.litwareinc.com**).
    
      - A cadeia de **caracteres \_ /reports**.
    
      - O nome da instância do banco de dados onde os relatórios de monitoramento são instalados (por exemplo, **archinst**).
    
    Por exemplo, se o SQL Server Reporting Services foi instalado no computador atl-sql-001.litwareinc.com e os relatórios de monitoramento usam a instância de banco de archinst, a URL da página inicial teria a seguinte aparência:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Após acessar a página inicial do Reporting Services, clique em **LyncServerReports**e em **relatórios de \_ conteúdo**. Isso levará você à página **de \_ conteúdo de relatórios** dos relatórios de monitoramento do Lync Server.

3.  Na página **de \_ conteúdo relatórios** , clique na fonte de dados **CDRDB** .

4.  Na página **CDRDB** , na guia **Propriedades** , procure a caixa de texto chamada **sequência de conexão**. A cadeia de caracteres de conexão atual terá uma aparência semelhante a esta:
    
    **Fonte de dados = (local) \\ archinst; Initial Catalog = LcsCDR**

5.  Edite a cadeia de conexão para incluir o nome do servidor e a instância de banco de dados para o banco de dados espelho. Por exemplo, se o servidor se chamar ATL-Mirror-001 e o banco de dados espelho estiver na instância do archinst, você precisará adicionar para especificar o banco de dados espelho usando esta sintaxe:
    
    **Parceiro de failover = ATL-Mirror-001 \\ archinst**
    
    A cadeia de conexão editada terá a seguinte aparência:
    
    **Fonte de dados = (local) \\ archinst; Parceiro de failover = ATL-Mirror-001 \\ archinst; Initial Catalog = LcsCDR**

6.  Depois de atualizar a cadeia de conexão, clique em **aplicar**.

7.  Na página **CDRDB** , clique no link **relatórios de \_ conteúdo** . Clique na fonte de dados do **QMSDB** e edite a cadeia de caracteres de conexão para o banco de dados de QoE. Por exemplo:
    
    **Fonte de dados = (local) \\ archinst; Parceiro de failover = ATL-Mirror-001 \\ archinst; Initial Catalog = QoEMetrics**

8.  Clique em **Aplicar**.

<div>

## <a name="see-also"></a>Confira também


[Instalando Relatórios de Monitoramento do Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Usando relatórios de monitoramento no Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

