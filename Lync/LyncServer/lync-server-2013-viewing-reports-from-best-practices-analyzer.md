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

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="e06c1-102">Exibindo relatórios do analisador de práticas recomendadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e06c1-102">Viewing reports from Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e06c1-103">_**Tópico da última modificação:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e06c1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e06c1-104">Ao usar o analisador de práticas recomendadas para verificar seu ambiente, especifique um nome para a verificação.</span><span class="sxs-lookup"><span data-stu-id="e06c1-104">When you use Best Practices Analyzer to scan your environment, you specify a name for the scan.</span></span> <span data-ttu-id="e06c1-105">Após o analisador de práticas recomendadas concluir uma verificação, ele armazena os resultados da verificação em relatórios e salva-os sob o nome da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e06c1-105">After Best Practices Analyzer completes a scan, it stores the scan results in reports and saves them under the name of the scan.</span></span> <span data-ttu-id="e06c1-106">Após a conclusão da verificação, você pode exibir os relatórios gerados para essa verificação clicando em **exibir um relatório desta análise de práticas recomendadas** diretamente da página digitalizando página **concluída** .</span><span class="sxs-lookup"><span data-stu-id="e06c1-106">Upon completion of the scan, you can view the reports generated for that scan by clicking **View a report of this Best Practices scan** directly from the **Scanning Completed** page.</span></span> <span data-ttu-id="e06c1-107">Você também pode exibir os relatórios dessa varredura ou de verificações anteriores mais tarde.</span><span class="sxs-lookup"><span data-stu-id="e06c1-107">You can also view the reports from that scan or previous scans at a later time.</span></span> <span data-ttu-id="e06c1-108">Você pode exibir relatórios no computador local em que a verificação foi executada, importar os resultados da verificação de outro computador ou exportar resultados da verificação para exibir os relatórios em outro computador no qual o Best Practices Analyzer está instalado.</span><span class="sxs-lookup"><span data-stu-id="e06c1-108">You can view reports on the local computer on which the scan was run, import scan results from another computer, or export scan results to view the reports on another computer on which Best Practices Analyzer is installed.</span></span>

<span data-ttu-id="e06c1-109">Os resultados da verificação são apresentados nos seguintes tipos de relatórios:</span><span class="sxs-lookup"><span data-stu-id="e06c1-109">Scan results are presented in the following types of reports:</span></span>

  - <span data-ttu-id="e06c1-110">Relatórios de lista</span><span class="sxs-lookup"><span data-stu-id="e06c1-110">List reports</span></span>

  - <span data-ttu-id="e06c1-111">Relatórios em árvore</span><span class="sxs-lookup"><span data-stu-id="e06c1-111">Tree reports</span></span>

  - <span data-ttu-id="e06c1-112">Outros relatórios</span><span class="sxs-lookup"><span data-stu-id="e06c1-112">Other reports</span></span>

<span data-ttu-id="e06c1-113">Esses relatórios incluem erros, avisos e outras informações.</span><span class="sxs-lookup"><span data-stu-id="e06c1-113">These reports include errors, warnings, and other information.</span></span> <span data-ttu-id="e06c1-114">Para obter detalhes sobre cada um desses tipos de relatórios e problemas, consulte [noções básicas sobre relatórios criados pelo analisador de práticas recomendadas no Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="e06c1-114">For details about each of these types of reports and issues, see [Understanding reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).</span></span>

<span data-ttu-id="e06c1-115">Use o procedimento a seguir para ver os resultados da verificação gerados anteriormente pelo analisador de práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="e06c1-115">Use the following procedure to view scan results previously generated by Best Practices Analyzer.</span></span>

<div>

## <a name="to-view-reports-from-a-previous-scan"></a><span data-ttu-id="e06c1-116">Para exibir relatórios de uma verificação anterior</span><span class="sxs-lookup"><span data-stu-id="e06c1-116">To view reports from a previous scan</span></span>

1.  <span data-ttu-id="e06c1-117">Faça logon em um computador no qual o analisador de práticas recomendadas está instalado usando uma conta que seja membro da conta de usuário local.</span><span class="sxs-lookup"><span data-stu-id="e06c1-117">Log on to a computer on which Best Practices Analyzer is installed using an account that is a member of the local User account.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="e06c1-118">Você pode exibir os resultados de uma verificação usando uma conta que seja membro do grupo Administradores local, mas não será possível executar uma verificação, a menos que você tenha direitos e permissões de usuário adequados.</span><span class="sxs-lookup"><span data-stu-id="e06c1-118">You can view the results of a scan using an account that is a member of the local Administrators group, but you cannot run a scan unless you have appropriate user rights and permissions.</span></span> <span data-ttu-id="e06c1-119">Para obter detalhes, consulte <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e06c1-119">For details, see <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</A>.</span></span>

2.  <span data-ttu-id="e06c1-120">Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e, em seguida, clique em analisador de **práticas recomendadas**.</span><span class="sxs-lookup"><span data-stu-id="e06c1-120">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="e06c1-121">Na tela de **boas-vindas** , clique em **selecionar os resultados da verificação a serem exibidos**.</span><span class="sxs-lookup"><span data-stu-id="e06c1-121">On the **Welcome** screen, click **Select the scan results to view**.</span></span>

4.  <span data-ttu-id="e06c1-122">Na página **selecionar uma verificação de práticas recomendadas para exibir** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e06c1-122">On the **Select a Best Practices Scan to View** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e06c1-123">Para exibir relatórios da lista de resultados de verificação armazenados localmente, clique no nome da verificação e em **exibir um relatório desta verificação**.</span><span class="sxs-lookup"><span data-stu-id="e06c1-123">To view reports from the list of locally stored scan results, click the name of scan, and then click **View a report of this scan**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="e06c1-124">O analisador de práticas recomendadas cria a lista de arquivos locais &lt;da&gt;\\pasta systemDrive Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span><span class="sxs-lookup"><span data-stu-id="e06c1-124">The Best Practices Analyzer creates the list of local files from the folder &lt;systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Application Data\Microsoft\RtcBPA.</span></span>
    
      - <span data-ttu-id="e06c1-125">Para exibir relatórios de resultados de uma verificação armazenada em outro local, clique em **importar verificação**, localize o arquivo que contém os resultados da verificação e, em seguida, clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="e06c1-125">To view reports for results of a scan that are stored at another location, click **Import scan**, locate the file containing the scan results, and then click **Open**.</span></span>
        
        > [!NOTE]  
        > <span data-ttu-id="e06c1-126">Se a versão do analisador de práticas recomendadas neste computador não corresponder à versão que foi usada para coletar os dados no arquivo importado, a ferramenta em seu computador poderá analisar o arquivo novamente depois que ele for importado.</span><span class="sxs-lookup"><span data-stu-id="e06c1-126">If the version of Best Practices Analyzer on this computer does not match the version that was used to collect the data in the imported file, the tool on your computer might analyze the file again, after it is imported.</span></span>

5.  <span data-ttu-id="e06c1-127">Na página **Exibir relatório de práticas recomendadas** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="e06c1-127">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="e06c1-128">Para exibir relatórios em uma lista organizada por componente de servidor, clique em **relatórios de lista**e, em seguida, clique na guia **todos os problemas** ou **itens** informativos.</span><span class="sxs-lookup"><span data-stu-id="e06c1-128">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="e06c1-129">Para exibir relatórios como uma lista hierárquica organizada por tipos de resultados, clique em **relatórios de árvore**e, em seguida, clique na guia modo de **exibição detalhado** ou na guia **modo de exibição de resumo** .</span><span class="sxs-lookup"><span data-stu-id="e06c1-129">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="e06c1-130">Para ver outros relatórios, clique em **outros relatórios**.</span><span class="sxs-lookup"><span data-stu-id="e06c1-130">To view other reports, click **Other Reports**.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="e06c1-131">Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo analisador de práticas recomendadas no Lync Server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados por práticas recomendadas Analyzer no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e06c1-131">For details about the Best Practices Analyzer reports and the issues that they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

</div>

</div>

</div>

</div>

</div>

