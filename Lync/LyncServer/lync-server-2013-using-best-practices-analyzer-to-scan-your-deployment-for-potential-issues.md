---
title: Usar o analisador de práticas recomendadas para verificar a implantação em busca de possíveis problemas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Best Practices Analyzer to scan your deployment for potential issues
ms:assetid: 09c84509-dc91-4e7b-882b-3c467b6b026d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591343(v=OCS.15)
ms:contentKeyID: 48183359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f787268301570d4440240289c19fdd1e266a607
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="7b8cd-102">Usar o analisador de práticas recomendadas para verificar a implantação do Lync Server 2013 em busca de possíveis problemas</span><span class="sxs-lookup"><span data-stu-id="7b8cd-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b8cd-103">_**Tópico da última modificação:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="7b8cd-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="7b8cd-104">Para executar uma verificação do analisador de práticas recomendadas, você deve especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7b8cd-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="7b8cd-105">**Credenciais**   para executar uma verificação, você deve fazer logon em um computador no qual o Best Practices Analyzer está instalado usando uma conta que seja membro do grupo Administradores local.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="7b8cd-106">Além disso, você precisa fazer logon usando uma conta de usuário que tenha os direitos de usuário e as permissões necessárias para executar as verificações adequadas ou especificar as credenciais que têm direitos e permissões de usuário apropriados ao executar o analisador de práticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="7b8cd-107">Para obter detalhes, consulte [associações de grupo e requisitos de direitos de usuário para o analisador de práticas recomendadas no Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="7b8cd-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="7b8cd-108">**Escopo da verificação**   para especificar o escopo da verificação, selecione as categorias e os servidores que você deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="7b8cd-109">Você pode selecionar todas as categorias, uma ou mais categorias ou um ou mais servidores em uma categoria específica em seu ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="7b8cd-110">**Tipo de verificação**   atualmente, a verificação de verificação de integridade é o único tipo de verificação disponível (selecionada por padrão).</span><span class="sxs-lookup"><span data-stu-id="7b8cd-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="7b8cd-111">A verificação de verificação de integridade gera um relatório que inclui erros, avisos e outras informações para todos os servidores especificados no escopo.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="7b8cd-112">\*\*\*\*   Opções de velocidade de rede de velocidade de rede incluem LAN rápida (100 Mbps ou mais), LAN (10 Mbps), rede remota rápida (1,5 Mbps) ou WAN (64 Kbps).</span><span class="sxs-lookup"><span data-stu-id="7b8cd-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="7b8cd-113">O tempo estimado para concluir a verificação é baseado nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="7b8cd-114">Essa configuração também é usada para definir o período de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="7b8cd-115">Durante a verificação, o analisador de práticas recomendadas aguarda uma resposta de um servidor por um período especificado.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="7b8cd-116">Se não receber uma resposta dentro do período de tempo limite especificado, ela será movida para o próximo servidor na verificação.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="7b8cd-117">Em redes mais lentas, esse período de tempo limite especificado está mais em conta com latências de rede mais longas.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="7b8cd-118">Recomendamos que você selecione o link mais lento na sua topologia para esse parâmetro, para que a ferramenta não tenha tempo limite muito rápido.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="7b8cd-119">Para verificar a implantação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b8cd-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="7b8cd-120">Faça logon em um computador no qual o analisador de práticas recomendadas está instalado usando uma conta que é membro do grupo Administradores local e tem outros direitos e permissões de usuário necessários.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="7b8cd-121">Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e, em seguida, clique em **analisador de práticas recomendadas**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="7b8cd-122">Na tela de **boas-vindas** , clique em **selecionar opções para uma nova digitalização**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="7b8cd-123">Na página **conectar-se ao Active Directory** , verifique o nome especificado no **servidor do Active Directory**e siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7b8cd-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="7b8cd-124">Para executar uma verificação usando as credenciais que você usou para fazer logon no computador, clique em **conectar-se ao servidor do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="7b8cd-125">Para especificar credenciais diferentes que você deseja usar nos serviços de domínio Active Directory, no servidor de borda ou no Exchange Server, clique em **Mostrar opções de logon avançadas**, marque cada caixa de seleção para a qual as credenciais separadas são necessárias, especifique as credenciais para cada caixa de seleção e clique em **conectar ao servidor do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7b8cd-126">Antes de iniciar a verificação, o analisador de práticas recomendadas executa uma verificação de rede e permissões para garantir que as credenciais de conta especificadas sejam válidas e que o analisador de práticas recomendadas possa se conectar aos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-126">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services.</span></span> <span data-ttu-id="7b8cd-127">Se a ferramenta estiver em execução em um servidor de grupo de trabalho, a ferramenta também verificará se ela pode se conectar a servidores de borda na rede de perímetro (isto é, se estiverem incluídos na verificação).</span><span class="sxs-lookup"><span data-stu-id="7b8cd-127">If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="7b8cd-128">Na página **iniciar uma nova verificação de práticas recomendadas** , selecione as opções que você deseja incluir na verificação, especifique a velocidade da rede e clique em **Iniciar verificação**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="7b8cd-129">Na página **scanning Completed Completed** , clique em **exibir um relatório desta análise de práticas recomendadas**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="7b8cd-130">Na página **Exibir relatório de práticas recomendadas** , siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="7b8cd-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7b8cd-131">Para exibir relatórios em uma lista organizada por componente de servidor, clique em **relatórios de lista**e, em seguida, clique na guia **todos os problemas** ou **itens informativos** .</span><span class="sxs-lookup"><span data-stu-id="7b8cd-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="7b8cd-132">Para exibir relatórios como uma lista hierárquica organizada por tipos de resultados, clique em **relatórios de árvore**e, em seguida, clique na guia modo de **exibição detalhado** ou na guia **modo de exibição de resumo** .</span><span class="sxs-lookup"><span data-stu-id="7b8cd-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="7b8cd-133">Para ver outros relatórios, clique em **outros relatórios**.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="7b8cd-134">Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo analisador de práticas recomendadas no Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados pelo analisador de práticas recomendadas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

