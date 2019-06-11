---
title: 'Lync Server 2013: exibindo relatórios do analisador de práticas recomendadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Exibindo relatórios do analisador de práticas recomendadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Ao usar o analisador de práticas recomendadas para verificar seu ambiente, especifique um nome para a verificação. Após o analisador de práticas recomendadas concluir uma verificação, ele armazena os resultados da verificação em relatórios e salva-os sob o nome da pesquisa. Após a conclusão da verificação, você pode exibir os relatórios gerados para essa verificação clicando em **exibir um relatório desta análise de práticas recomendadas** diretamente da página digitalizando página **concluída** . Você também pode exibir os relatórios dessa varredura ou de verificações anteriores mais tarde. Você pode exibir relatórios no computador local em que a verificação foi executada, importar os resultados da verificação de outro computador ou exportar resultados da verificação para exibir os relatórios em outro computador no qual o Best Practices Analyzer está instalado.

Os resultados da verificação são apresentados nos seguintes tipos de relatórios:

  - Relatórios de lista

  - Relatórios em árvore

  - Outros relatórios

Esses relatórios incluem erros, avisos e outras informações. Para obter detalhes sobre cada um desses tipos de relatórios e problemas, consulte [noções básicas sobre relatórios criados pelo analisador de práticas recomendadas no Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Use o procedimento a seguir para ver os resultados da verificação gerados anteriormente pelo analisador de práticas recomendadas.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Para exibir relatórios de uma verificação anterior

1.  Faça logon em um computador no qual o analisador de práticas recomendadas está instalado usando uma conta que seja membro da conta de usuário local.
    
    > [!NOTE]  
    > Você pode exibir os resultados de uma verificação usando uma conta que seja membro do grupo Administradores local, mas não será possível executar uma verificação, a menos que você tenha direitos e permissões de usuário adequados. Para obter detalhes, consulte <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas no Lync Server 2013</A>.

2.  Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e, em seguida, clique em analisador de **práticas recomendadas**.

3.  Na tela de **boas-vindas** , clique em **selecionar os resultados da verificação a serem exibidos**.

4.  Na página **selecionar uma verificação de práticas recomendadas para exibir** , siga um destes procedimentos:
    
      - Para exibir relatórios da lista de resultados de verificação armazenados localmente, clique no nome da verificação e em **exibir um relatório desta verificação**.
        
        > [!NOTE]  
        > O analisador de práticas recomendadas cria a lista de arquivos locais &lt;da&gt;\\pasta systemDrive Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.
    
      - Para exibir relatórios de resultados de uma verificação armazenada em outro local, clique em **importar verificação**, localize o arquivo que contém os resultados da verificação e, em seguida, clique em **abrir**.
        
        > [!NOTE]  
        > Se a versão do analisador de práticas recomendadas neste computador não corresponder à versão que foi usada para coletar os dados no arquivo importado, a ferramenta em seu computador poderá analisar o arquivo novamente depois que ele for importado.

5.  Na página **Exibir relatório de práticas recomendadas** , siga um destes procedimentos:
    
      - Para exibir relatórios em uma lista organizada por componente de servidor, clique em **relatórios de lista**e, em seguida, clique na guia **todos os problemas** ou **itens** informativos.
    
      - Para exibir relatórios como uma lista hierárquica organizada por tipos de resultados, clique em **relatórios de árvore**e, em seguida, clique na guia modo de **exibição detalhado** ou na guia **modo de exibição de resumo** .
    
      - Para ver outros relatórios, clique em **outros relatórios**.
    
    > [!NOTE]  
    > Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo analisador de práticas recomendadas no Lync Server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados por práticas recomendadas Analyzer no Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>

