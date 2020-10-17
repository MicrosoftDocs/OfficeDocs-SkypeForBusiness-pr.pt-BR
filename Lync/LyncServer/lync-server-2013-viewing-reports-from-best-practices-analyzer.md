---
title: 'Lync Server 2013: exibindo relatórios do analisador de práticas recomendadas'
description: 'Lync Server 2013: exibindo relatórios do analisador de práticas recomendadas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44e0f1ed8d48f5c8fb7e35187ecdda2778091407
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542357"
---
# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Exibindo relatórios do Best Practices Analyzer no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Quando você usa o Analisador de Práticas Recomendadas para verificar o ambiente, um nome é especificado para a verificação. Depois que o Analisador de Práticas Recomendadas conclui uma verificação, ele armazena os resultados em relatórios e os salva com o nome da verificação. Após a conclusão da verificação, você pode visualizar os relatórios gerados clicando em **Exibir um relatório desta verificação das Práticas Recomendadas** diretamente na página **Verificação Concluída**. Você também pode visualizar relatórios dessa verificação ou de verificações anteriores posteriormente. Você pode visualizar relatórios no computador local no qual a verificação foi executada, importar resultados de verificações de outro computador ou exportar resultados de verificações para visualizar os relatórios em outro computador com o Analisador de Práticas Recomendadas instalado.

Os resultados da verificação são apresentados nos seguintes tipos de relatórios:

  - Relatórios de lista

  - Relatórios de árvore

  - Outros relatórios

Esses relatórios incluem erros, avisos e outras informações. Para obter detalhes sobre cada um desses tipos de relatórios e problemas, consulte [Understanding Reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Use o procedimento a seguir para visualizar resultados de verificações gerados anteriormente pelo Analisador de Práticas Recomendadas.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Para visualizar relatórios de uma verificação anterior

1.  Faça logon em um computador com o Analisador de Práticas Recomendadas instalado usando uma conta que seja membro da conta de usuário local.
    
    > [!NOTE]  
    > Você pode visualizar os resultados de uma verificação usando uma conta que seja membro do grupo Administradores local, mas não pode executar uma verificação a menos que tenha os direitos e permissões de usuário corretos. Para obter detalhes, consulte <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group Memberships and User Rights Requirements for Best Practices Analyzer in Lync Server 2013</A>.

2.  Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e em **analisador de práticas recomendadas**.

3.  Na tela **Bem-vindo**, clique em **Selecionar os resultados da verificação para exibir**.

4.  Na página **Selecionar uma Verificação de Práticas Recomendadas para Exibir**, realize um dos seguintes procedimentos:
    
      - Para exibir relatórios da lista de resultados de verificação armazenados localmente, clique no nome da verificação e clique em **Exibir um relatório desta verificação**.
        
        > [!NOTE]  
        > O analisador de práticas recomendadas cria a lista de arquivos locais da pasta &lt; systemDrive &gt; \\ Documents and Settings \\ &lt; user &gt; \Dados de Data\Microsoft\RtcBPA.
    
      - Para exibir os relatórios de resultados de uma verificação armazenados em outro local, clique em **Importar verificação**, localize o arquivo que contém os resultados da verificação e clique em **Abrir**.
        
        > [!NOTE]  
        > Caso a versão do Analisador de Práticas Recomendadas neste computador não corresponda à versão usada para coletar os dados no arquivo importado, a ferramenta no computador poderá analisar o arquivo novamente após a importação.

5.  Na página **Exibir Relatório das Práticas Recomendadas**, realize um dos seguintes procedimentos:
    
      - Para exibir relatórios em uma lista organizada por componente do servidor, clique em **Listar Relatórios** e, em seguida, clique na guia **Todos os Problemas** ou na guia **Itens Informativos**.
    
      - Para exibir relatórios como uma lista hierárquica organizada por tipo de resultado, clique em **Relatórios em Árvore** e, em seguida, clique na guia **Exibição Detalhada** ou na guia **Exibição Resumida**.
    
      - Para exibir outros relatórios, clique em **Outros Relatórios**.
    
    > [!NOTE]  
    > Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo Best Practices Analyzer no Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados pelo Best Practices Analyzer no Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>

