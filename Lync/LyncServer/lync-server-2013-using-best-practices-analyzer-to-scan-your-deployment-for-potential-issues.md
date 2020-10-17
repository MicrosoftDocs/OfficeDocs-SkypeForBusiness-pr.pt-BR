---
title: Usando o analisador de práticas recomendadas para examinar sua implantação em busca de possíveis problemas
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
ms.openlocfilehash: 20a7b43056071ddc2322ff5147de72d818548b86
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535878"
---
# <a name="using-best-practices-analyzer-to-scan-your-lync-server-2013-deployment-for-potential-issues"></a><span data-ttu-id="550e9-102">Usando o analisador de práticas recomendadas para verificar a implantação do Lync Server 2013 em busca de possíveis problemas</span><span class="sxs-lookup"><span data-stu-id="550e9-102">Using Best Practices Analyzer to scan your Lync Server 2013 deployment for potential issues</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="550e9-103">_**Última modificação do tópico:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="550e9-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="550e9-104">Para executar um exame do Analisador de Práticas Recomendadas, é necessário especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="550e9-104">To run a Best Practices Analyzer scan, you must specify the following:</span></span>

  - <span data-ttu-id="550e9-105">**Credenciais**     Para executar uma verificação, você deve fazer logon em um computador no qual o Best Practices Analyzer está instalado, usando uma conta que seja membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="550e9-105">**Credentials**   To run a scan, you must log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group.</span></span> <span data-ttu-id="550e9-106">Além disso, é necessário fazer logon usando uma conta de usuário que tenha os direitos e permissões necessários para executar os exames apropriados, ou é necessário especificar credenciais que tenham os direitos e permissões de usuário apropriados ao executar o Analisador de Práticas Recomendadas.</span><span class="sxs-lookup"><span data-stu-id="550e9-106">Additionally, you need to log on by using a user account that has the user rights and permissions required to run the appropriate scans, or you must specify credentials that have the appropriate user rights and permissions when you run Best Practices Analyzer.</span></span> <span data-ttu-id="550e9-107">Para obter detalhes, consulte [Group Memberships and User Rights Requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="550e9-107">For details, see [Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013](lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md).</span></span>

  - <span data-ttu-id="550e9-108">**Escopo da verificação**     Para especificar o escopo da verificação, selecione as categorias e servidores que você deseja verificar.</span><span class="sxs-lookup"><span data-stu-id="550e9-108">**Scope of scan**   To specify the scope of the scan, select the categories and servers that you want to scan.</span></span> <span data-ttu-id="550e9-109">Você pode selecionar todas as categorias, uma ou mais categorias ou um ou mais servidores dentro de uma categoria específica no seu ambiente do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="550e9-109">You can select all categories, one or more categories, or one or more servers within a specific category in your Lync Server environment.</span></span>

  - <span data-ttu-id="550e9-110">**Tipo de verificação**     No momento, a verificação de verificação de integridade é o único tipo de verificação disponível (selecionada por padrão).</span><span class="sxs-lookup"><span data-stu-id="550e9-110">**Type of scan**   Currently, the Health Check scan is the only type of scan available (selected by default).</span></span> <span data-ttu-id="550e9-111">A Verificação de Integridade pode gerar um relatório que inclui erros, avisos e outras informações para todos os servidores especificados no escopo.</span><span class="sxs-lookup"><span data-stu-id="550e9-111">The Health Check scan generates a report that includes errors, warnings, and other information for all servers specified in the scope.</span></span>

  - <span data-ttu-id="550e9-112">**Velocidade**     da rede As opções de velocidade de rede incluem LAN rápida (100 Mbps ou mais), LAN (10 Mbps), WAN rápida (1,5 Mbps) ou WAN (64 Kbps).</span><span class="sxs-lookup"><span data-stu-id="550e9-112">**Network speed**   Network speed options include Fast LAN (100 Mbps or more), LAN (10 Mbps), Fast WAN (1.5 Mbps), or WAN (64 kbps).</span></span> <span data-ttu-id="550e9-113">O tempo estimado para completar o exame tem base nessa configuração.</span><span class="sxs-lookup"><span data-stu-id="550e9-113">The estimated time to complete the scan is based on this setting.</span></span> <span data-ttu-id="550e9-114">Essa configuração também é usada para definir o período de tempo limite.</span><span class="sxs-lookup"><span data-stu-id="550e9-114">This setting is also used to set the time-out period.</span></span> <span data-ttu-id="550e9-115">Durante o exame, o Analisador de Práticas Recomendadas espera uma resposta de um servidor durante um tempo especificado.</span><span class="sxs-lookup"><span data-stu-id="550e9-115">During the scan, the Best Practices Analyzer waits for a response from a server for a specified time.</span></span> <span data-ttu-id="550e9-116">Se não receber uma resposta dentro do período de tempo limite especificado, ele vai para o próximo servidor no exame.</span><span class="sxs-lookup"><span data-stu-id="550e9-116">If it does not receive a response within the specified time-out period, it moves to the next server in the scan.</span></span> <span data-ttu-id="550e9-117">Em redes mais lentas, esse período de tempo limite especificado é maior para acomodar latências de rede maiores.</span><span class="sxs-lookup"><span data-stu-id="550e9-117">On slower networks, this specified time-out period is longer to account for longer network latencies.</span></span> <span data-ttu-id="550e9-118">Recomendamos a seleção do link mais lento em sua topologia para esse parâmetro de modo que a ferramenta não ultrapasse o tempo limite muito rápido.</span><span class="sxs-lookup"><span data-stu-id="550e9-118">We recommend that you select the slowest link in your topology for this parameter so that the tool does not time out too quickly.</span></span>

<div>

## <a name="to-scan-your-lync-server-2013-deployment"></a><span data-ttu-id="550e9-119">Para examinar sua implantação do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="550e9-119">To scan your Lync Server 2013 deployment</span></span>

1.  <span data-ttu-id="550e9-120">Faça logon em um computador no qual o Analisador de Práticas Recomendadas está instalado usando uma conta membro do grupo local Administradores, e com outros direitos e permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="550e9-120">Log on to a computer on which Best Practices Analyzer is installed by using an account that is a member of the local Administrators group, and has other required user rights and permissions.</span></span>

2.  <span data-ttu-id="550e9-121">Clique em **Iniciar**, aponte para **todos os programas**, clique em **Microsoft Lync Server 2013**e em **analisador de práticas recomendadas**.</span><span class="sxs-lookup"><span data-stu-id="550e9-121">Click **Start**, point to **All Programs**, click **Microsoft Lync Server 2013**, and then click **Best Practices Analyzer**.</span></span>

3.  <span data-ttu-id="550e9-122">Na tela **Boas-vindas**, clique em **Selecionar opções para uma nova verificação**.</span><span class="sxs-lookup"><span data-stu-id="550e9-122">On the **Welcome** screen, click **Select options for a new scan**.</span></span>

4.  <span data-ttu-id="550e9-123">Na página **Conectar ao Active Directory**, verifique o nome especificado em **Servidor Active Directory** e execute uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="550e9-123">On the **Connect to Active Directory** page, verify the name specified in **Active Directory Server**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="550e9-124">Para executar um exame usando as credenciais usadas para fazer logon no computador, clique em **Conectar ao servidor do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="550e9-124">To run a scan using the credentials that you used to log on to the computer, click **Connect to the Active Directory server**.</span></span>
    
      - <span data-ttu-id="550e9-125">Para especificar credenciais diferentes que você deseja usar para os Serviços de Domínio do Active Directory, Servidor de Borda ou Exchange Server, clique em **Mostrar opções avançadas de logon**, marca cada caixa de seleção para a qual as credenciais separadas são necessárias, especifique as credenciais para cada caixa de seleção marcada e clique em **Conectar ao servidor do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="550e9-125">To specify different credentials that you want to use for Active Directory Domain Services, Edge Server, or Exchange Server, click **Show advanced logon options**, select each check box for which separate credentials are required, specify the credentials for each selected check box, and then click **Connect to the Active Directory server**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="550e9-p105">Antes de começar o exame, o Analisador de Práticas Recomendadas executa uma verificação de rede e de permissões a fim de assegurar que as credenciais de conta especificadas sejam válidas e que o Analisador de Práticas Recomendadas possa se conectar aos Serviços de Domínio do Active Directory. Se a ferramenta estiver em execução em um servidor de grupo de trabalho, a ferramenta também verificará se pode se conectar aos Servidores de Borda na rede de perímetro (ou seja, se estiverem incluídos no exame).</span><span class="sxs-lookup"><span data-stu-id="550e9-p105">Before beginning the scan, Best Practices Analyzer performs a network and permissions check to ensure that the specified account credentials are valid and that Best Practices Analyzer can connect to Active Directory Domain Services. If the tool is running on a workgroup server, the tool also verifies that it can connect to Edge Servers in the perimeter network (that is, if they are included in the scan).</span></span>

    
    </div>

5.  <span data-ttu-id="550e9-128">Na página **Iniciar uma nova verificação das Práticas Recomendadas**, selecione as opções que você deseja incluir no exame, especifique a velocidade da rede e clique em **Iniciar exame**.</span><span class="sxs-lookup"><span data-stu-id="550e9-128">On the **Start a new Best Practices scan** page, select the options that you want to include in the scan, specify the network speed, and then click **Start scanning**.</span></span>

6.  <span data-ttu-id="550e9-129">Na página **Verificação concluída**, clique em **Exibir um relatório desta verificação das Práticas Recomendadas**.</span><span class="sxs-lookup"><span data-stu-id="550e9-129">On the **Scanning Completed** page, click **View a report of this Best Practices scan**.</span></span>

7.  <span data-ttu-id="550e9-130">Na página **Exibir Relatório das Práticas Recomendadas**, execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="550e9-130">On the **View Best Practices Report** page, do one of the following:</span></span>
    
      - <span data-ttu-id="550e9-131">Para exibir relatórios em uma lista organizada por componente do servidor, clique em **Listar Relatórios** e, em seguida, clique na guia **Todos os Problemas** ou na guia **Itens Informativos**.</span><span class="sxs-lookup"><span data-stu-id="550e9-131">To view reports in a list organized by server component, click **List Reports**, and then click either the **All Issues** tab or the **Informational Items** tab.</span></span>
    
      - <span data-ttu-id="550e9-132">Para exibir relatórios como uma lista hierárquica organizada por tipo de resultado, clique em **Relatórios em Árvore** e, em seguida, clique na guia **Exibição Detalhada** ou na guia **Exibição Resumida**.</span><span class="sxs-lookup"><span data-stu-id="550e9-132">To view reports as a hierarchical list organized by types of results, click **Tree Reports**, and then click either the **Detailed View** tab or the **Summary View** tab.</span></span>
    
      - <span data-ttu-id="550e9-133">Para exibir outros relatórios, clique em **Outros Relatórios**.</span><span class="sxs-lookup"><span data-stu-id="550e9-133">To view other reports, click **Other Reports**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="550e9-134">Para obter detalhes sobre os relatórios do analisador de práticas recomendadas e os problemas que eles identificam, consulte <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">exibindo e trabalhando com relatórios criados pelo Best Practices Analyzer no Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisando e resolvendo problemas identificados pelo Best Practices Analyzer no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="550e9-134">For details about the Best Practices Analyzer reports and the issues they identify, see <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">Viewing and working with reports created by Best Practices Analyzer in Lync Server 2013</A> and <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">Analyzing and resolving issues identified by Best Practices Analyzer in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

