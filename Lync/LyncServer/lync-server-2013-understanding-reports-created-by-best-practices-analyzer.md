---
title: 'Lync Server 2013: Noções básicas sobre relatórios criados pelo Best Practices Analyzer'
description: 'Lync Server 2013: Noções básicas sobre relatórios criados pelo Best Practices Analyzer.'
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
ms.openlocfilehash: 5fbb84cdffe6e6e6f079c2d72aba4799f5538776
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542367"
---
# <a name="understanding-reports-created-by-best-practices-analyzer-in-lync-server-2013"></a>Noções básicas sobre relatórios criados pelo Best Practices Analyzer no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

O Analisador de Práticas Recomendadas fornece vários tipos de relatórios, organizados para facilitar a análise e a solução de problemas. O Analisador identifica problemas como erros, avisos e outras informações.

<div>

## <a name="reports"></a>Relatórios

Você pode acessar os resultados de uma varredura exibindo cada um dos seguintes relatórios:

  - **Listar relatórios**     Os relatórios de lista são organizados por critérios específicos. Você pode organizar os resultados por classe, severidade ou problema. Por exemplo, se você organizar os resultados por classe, os problemas relacionados aos diretores serão incluídos na seção diretores do relatório. Você pode exibir todos os problemas ou apenas os itens informativos. Você pode pesquisar itens específicos em um relatório de lista, como a memória. Você também pode imprimir o relatório ou exportá-lo.

  - **Relatórios**     de árvore Relatórios de árvore são organizados pelas regras que são usadas para executar a verificação e outras opções que você especificou no momento em que a verificação foi executada. Por exemplo, os problemas relacionados às regras de topologia de teste estão incluídos na seção de topologia de teste do relatório. Você pode exibir os detalhes de todos os problemas ou apenas um resumo dos problemas. Você pode pesquisar por itens específicos em um relatório de árvore, como a memória. Você também pode imprimir o relatório ou exportá-lo.

  - **Outros relatórios**     Os itens em outros relatórios incluem o log do tempo de execução das tarefas que foram incluídas na verificação. Você pode pesquisar itens específicos em outros relatórios, como a memória. Você também pode imprimir o relatório ou exportá-lo.

</div>

<div>

## <a name="issues"></a>Problemas

Os relatórios gerados pelo Analisador de Práticas Recomendadas indicam problemas específicos identificados durante a varredura do seu ambiente, incluindo os seguintes tipos:

  - **Erros**     Problemas críticos que exigem que você faça uma alteração no ambiente. Por exemplo, se os componentes principais do Lync Server 2013 não estiverem instalados, um erro será registrado.

    Problemas classificados como erros são identificados no relatório por um símbolo X vermelho. Erros são exibidos na guia **Todos os Problemas** do modo de exibição **Relatórios de Lista** e nas guias **Exibição Detalhada** e **Exibição de Resumo** do modo de exibição **Relatórios em Árvore**. Se você não deseja ver um erro específico em um relatório, pode especificar que o erro não seja exibido para uma única instância ou para todas as instâncias do erro no relatório. O erro é então exibido somente na guia **Itens Ocultos** do modo de exibição **Outros Relatórios**, a menos que você altere a configuração e especifique que o erro seja exibido no relatório.

  - **Avisos**     Problemas que não são consistentes com a implementação de uma prática recomendada. Isso pode ou não indicar a necessidade de uma alteração no ambiente. O problema pode ser conhecido com uma configuração específica que não precisa ser alterada. Por exemplo, serviços que não são iniciados em um servidor são registrados em log como avisos.

    Problemas classificados como avisos são identificados no relatório com um símbolo de aviso triangular amarelo. Avisos são exibidos na guia **Todos os Problemas** do modo de exibição **Relatórios de Lista**, bem como nas guias **Exibição Detalhada** e **Exibição de Resumo** do modo de exibição **Relatórios em Árvore**. Se você não deseja ver um erro específico em um relatório, pode especificar que o erro não seja exibido para uma única instância ou para todas as instâncias do erro no relatório. O aviso é então exibido somente na guia **Itens Ocultos** do modo de exibição **Outros Relatórios**, a menos que você altere a configuração e especifique que o aviso seja exibido no relatório.

  - **Informações sobre**     o Inclui todos os problemas não classificados como erros ou avisos. Por exemplo, o número de objetos de servidor do Lync Server 2013 Standard Edition nos serviços de domínio do Active Directory é classificado como um problema de informação.

    Informações são exibidas na guia **Todos os Problemas** do modo de exibição **Relatórios de Lista** e na guia **Exibição Detalhada** do modo de exibição **Relatórios em Árvore**.

O Lync Server 2013, Best Practices Analyzer não faz alterações no seu ambiente para resolver problemas. A varredura somente detecta possíveis problemas e fornece relatórios que contêm informações sobre como resolver cada um deles.

Ao clicar em um problema, uma explicação e algumas opções são exibidas para problemas específicos. Assim, você pode:

  - Encontrar informações mais detalhadas sobre o problema e sobre como resolvê-lo.

  - Interromper a exibição de problemas em relatórios:

      - Interromper a exibição de problemas para a instância selecionada.

      - Interromper a exibição de problemas para todas as instâncias daquele problema.

    Para ver os problemas para os quais a exibição nos relatórios foi interrompida, vá até a guia **Itens Ocultos** do modo de exibição **Outros Relatórios**. Neste local você pode especificar para iniciar a exibição de problemas nos relatórios novamente.

Para obter detalhes sobre como resolver problemas específicos, consulte [analisando e resolvendo problemas identificados pelo Best Practices Analyzer no Lync Server 2013](lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>
