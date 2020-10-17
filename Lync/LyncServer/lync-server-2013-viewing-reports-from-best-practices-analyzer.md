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
# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="5429d-103">Exibindo relatórios do Best Practices Analyzer no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5429d-103">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5429d-104">_**Última modificação do tópico:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5429d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5429d-p101">Quando você usa o Analisador de Práticas Recomendadas para verificar o ambiente, um nome é especificado para a verificação. Depois que o Analisador de Práticas Recomendadas conclui uma verificação, ele armazena os resultados em relatórios e os salva com o nome da verificação. Após a conclusão da verificação, você pode visualizar os relatórios gerados clicando em **Exibir um relatório desta verificação das Práticas Recomendadas** diretamente na página **Verificação Concluída**. Você também pode visualizar relatórios dessa verificação ou de verificações anteriores posteriormente. Você pode visualizar relatórios no computador local no qual a verificação foi executada, importar resultados de verificações de outro computador ou exportar resultados de verificações para visualizar os relatórios em outro computador com o Analisador de Práticas Recomendadas instalado.</span><span class="sxs-lookup"><span data-stu-id="5429d-p101">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan. After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan. Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page. You can also view the reports from that scan or previous scans at a later time. You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="5429d-110">Os resultados da verificação são apresentados nos seguintes tipos de relatórios:</span><span class="sxs-lookup"><span data-stu-id="5429d-110">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="5429d-111">Relatórios de lista</span><span class="sxs-lookup"><span data-stu-id="5429d-111">List reports</span></span>

  - <span data-ttu-id="5429d-112">Relatórios de árvore</span><span class="sxs-lookup"><span data-stu-id="5429d-112">Tree reports</span></span>

  - <span data-ttu-id="5429d-113">Outros relatórios</span><span class="sxs-lookup"><span data-stu-id="5429d-113">Other reports</span></span>

<span data-ttu-id="5429d-114">Esses relatórios incluem erros, avisos e outras informações.</span><span class="sxs-lookup"><span data-stu-id="5429d-114">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="5429d-115">Para obter detalhes sobre cada um desses tipos de relatórios e problemas, consulte [Understanding Reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="5429d-115">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="5429d-116">Use o procedimento a seguir para visualizar resultados de verificações gerados anteriormente pelo Analisador de Práticas Recomendadas.</span><span class="sxs-lookup"><span data-stu-id="5429d-116">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="5429d-117">Para visualizar relatórios de uma verificação anterior</span><span class="sxs-lookup"><span data-stu-id="5429d-117">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="5429d-118">Faça logon em um computador com o Analisador de Práticas Recomendadas instalado usando uma conta que seja membro da conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="5429d-118">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="5429d-119">Você pode visualizar os resultados de uma verificação usando uma conta que seja membro do grupo Administradores local, mas não pode executar uma verificação a menos que tenha os direitos e permissões de usuário corretos.</span><span class="sxs-lookup"><span data-stu-id="5429d-119">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="5429d-120">Para obter detalhes, consulte <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group Memberships and User Rights Requirements for Best Practices Analyzer in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5429d-120">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="5429d-121">Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e em **analisador de práticas recomendadas**.</span><span class="sxs-lookup"><span data-stu-id="5429d-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="5429d-122">Na tela **Bem-vindo**, clique em **Selecionar os resultados da verificação para exibir**.</span><span class="sxs-lookup"><span data-stu-id="5429d-122">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="5429d-123">Na página **Selecionar uma Verificação de Práticas Recomendadas para Exibir**, realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5429d-123">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5429d-124">Para exibir relatórios da lista de resultados de verificação armazenados localmente, clique no nome da verificação e clique em **Exibir um relatório desta verificação**.</span><span class="sxs-lookup"><span data-stu-id="5429d-124">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="5429d-125">O analisador de práticas recomendadas cria a lista de arquivos locais da pasta &lt; systemDrive &gt; \\ Documents and Settings \\ &lt; user &gt; \Dados de Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="5429d-125">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="5429d-126">Para exibir os relatórios de resultados de uma verificação armazenados em outro local, clique em **Importar verificação**, localize o arquivo que contém os resultados da verificação e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5429d-126">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="5429d-127">Caso a versão do Analisador de Práticas Recomendadas neste computador não corresponda à versão usada para coletar os dados no arquivo importado, a ferramenta no computador poderá analisar o arquivo novamente após a importação.</span><span class="sxs-lookup"><span data-stu-id="5429d-127">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="5429d-128">Na página **Exibir Relatório das Práticas Recomendadas**, realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5429d-128">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="5429d-129">Para exibir relatórios em uma lista organizada por componente do servidor, clique em **Listar Relatórios** e, em seguida, clique na guia **Todos os Problemas** ou na guia **Itens Informativos**.</span><span class="sxs-lookup"><span data-stu-id="5429d-129">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="5429d-130">Para exibir relatórios como uma lista hierárquica organizada por tipo de resultado, clique em **Relatórios em Árvore** e, em seguida, clique na guia **Exibição Detalhada** ou na guia **Exibição Resumida**.</span><span class="sxs-lookup"><span data-stu-id="5429d-130">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="5429d-131">Para exibir outros relatórios, clique em **Outros Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="5429d-131">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="5429d-132">Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo Best Practices Analyzer no Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados pelo Best Practices Analyzer no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5429d-132">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>

