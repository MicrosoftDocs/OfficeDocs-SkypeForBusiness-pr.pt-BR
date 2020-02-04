---
title: 'Lync Server 2013: Noções básicas sobre relatórios criados pelo analisador de práticas recomendadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding reports created by Best Practices Analyzer
ms:assetid: 1386dd6c-7f3e-4da9-905b-cef1468bf14a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591344(v=OCS.15)
ms:contentKeyID: 48183471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2262c490d84ec6f93ff395a9c8ec38d81c82e7de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Noções básicas sobre relatórios criados pelo analisador de práticas recomendadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-10_

O analisador de práticas recomendadas fornece vários tipos de relatórios organizados para facilitar a análise e a resolução de problemas. O analisador de práticas recomendadas identifica problemas como erros, avisos e outras informações.

<div>

## <a name="reports"></a>Gerente

Você pode acessar os resultados de uma verificação exibindo cada um dos seguintes relatórios:

  - **** Relatórios de lista relatórios de lista são organizados por critérios específicos.    Você pode organizar os resultados por classe, severidade ou problema. Por exemplo, se você organizar os resultados por classe, os problemas relacionados a directors serão incluídos na seção directors do relatório. Você pode ver todos os problemas ou apenas os itens informativos. Você pode pesquisar um relatório de lista para itens específicos, como memória. Você também pode imprimir o relatório ou exportá-lo.

  - **** Relatórios de árvore relatórios em árvore são organizados por regras que são usadas para executar a verificação e outras opções que você especificou no momento em que a verificação foi executada.    Por exemplo, os problemas relacionados às regras de topologia de teste são incluídos na seção de topologia de teste do relatório. Você pode ver os detalhes de todos os problemas ou apenas um resumo dos problemas. Você pode pesquisar um relatório de árvore para itens específicos, como memória. Você também pode imprimir o relatório ou exportá-lo.

  - **Outros**   itens de relatórios em outros relatórios incluem o log de tarefas em tempo de execução que foram incluídos na verificação. Você pode pesquisar itens específicos, como memória, para pesquisar itens em outros relatórios. Você também pode imprimir o relatório ou exportá-lo.

</div>

<div>

## <a name="issues"></a>Assuntos

Os relatórios gerados pelo analisador de práticas recomendadas indicam problemas específicos identificados durante a verificação do seu ambiente, incluindo os seguintes tipos de problemas:

  - **Erros**   problemas críticos que exigem que você faça uma alteração no ambiente. Por exemplo, se os componentes principais do Lync Server 2013 não estiverem instalados, um erro será registrado.
    
    Os problemas classificados como erros são identificados no relatório por um símbolo X vermelho. Os erros são exibidos na guia **todos os problemas** do modo de exibição **relatórios de lista** e na guia modo de **exibição detalhado** e na guia modo de exibição de **Resumo** do modo de exibição relatórios em **árvore** . Se você não quiser ver um erro específico em um relatório, você pode especificar que o erro não seja mostrado para uma instância única ou para todas as instâncias desse erro no relatório. O erro é exibido apenas na guia **itens ocultos** do modo de exibição **outros relatórios** , a menos que você altere a configuração e especifique que o erro seja exibido no relatório.

  - **Avisos**   sobre problemas que não são consistentes com a implementação de uma prática recomendada. Isso pode ou não indicar a necessidade de uma alteração no ambiente. O problema pode ser um problema conhecido com uma configuração específica que você não precisa alterar. Por exemplo, os serviços que não são iniciados em um servidor são registrados como avisos.
    
    Os problemas classificados como avisos são identificados no relatório por um símbolo de aviso amarelo triangular. Os avisos são exibidos na guia **todos os problemas** do modo de exibição **relatórios de lista** , bem como na guia modo de **exibição detalhado** e na guia modo de exibição de **Resumo** do modo de exibição relatórios em **árvore** . Se você não quiser ver um erro específico em um relatório, você pode especificar que o erro não seja mostrado para uma instância única ou para todas as instâncias desse erro no relatório. O aviso é exibido apenas na guia **itens ocultos** do modo de exibição **outros relatórios** , a menos que você altere a configuração e especifique que o aviso seja exibido no relatório.

  - **As informações**   incluem todos os problemas não classificados como erros ou avisos. Por exemplo, o número de objetos do servidor do Lync Server 2013 Standard Edition nos serviços de domínio Active Directory é classificado como um problema de informações.
    
    Problemas de informações são exibidos na guia **todos os problemas** do modo de exibição **relatórios de lista** e na guia modo de **exibição detalhado** do modo de exibição **relatórios em árvore** .

O Lync Server 2013, o analisador de práticas recomendadas não faz alterações no seu ambiente para resolver problemas. A verificação detecta apenas possíveis problemas e fornece relatórios que contêm informações sobre como resolver cada problema.

Se você clicar em um problema, uma explicação e algumas opções serão exibidas para problemas específicos. Em seguida, você pode fazer o seguinte:

  - Encontre informações mais detalhadas sobre o problema e como resolvê-lo.

  - Parar de mostrar problemas nos relatórios:
    
      - Parar de mostrar problemas para a instância selecionada.
    
      - Pare de mostrar problemas para todas as ocorrências desse problema.
    
    Para ver os problemas que você parou de mostrar nos relatórios, acesse a guia **itens ocultos** do modo de exibição **outros relatórios** . A partir daí, você pode especificar para começar a mostrar problemas nos relatórios novamente.

Para obter detalhes sobre como resolver problemas específicos, consulte [analisando e resolvendo problemas identificados pelo analisador de práticas recomendadas no Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

