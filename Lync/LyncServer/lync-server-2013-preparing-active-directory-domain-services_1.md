---
title: 'Lync Server 2013: Preparando Serviços de Domínio do Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8abab29930e8b09d0642c84f1e02026d4c554637
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a><span data-ttu-id="c4fc7-102">Preparando Serviços de Domínio do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4fc7-102">Preparing Active Directory Domain Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4fc7-103">_**Tópico da última modificação:** 2014-02-19_</span><span class="sxs-lookup"><span data-stu-id="c4fc7-103">_**Topic Last Modified:** 2014-02-19_</span></span>

<span data-ttu-id="c4fc7-104">No Lync Server 2013, você pode usar o assistente de implantação do Lync Server para preparar os serviços de domínio do Active Directory, ou você pode usar os cmdlets do Shell de gerenciamento do Lync Server diretamente.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-104">In Lync Server 2013, you can use the Lync Server Deployment Wizard to prepare Active Directory Domain Services, or you can use Lync Server Management Shell cmdlets directly.</span></span> <span data-ttu-id="c4fc7-105">Você também pode usar a ferramenta de linha de comando ldifde. exe diretamente nos controladores de domínio, conforme descrito posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-105">You can also use the ldifde.exe command line tool directly on your domain controllers, as described later in this topic.</span></span>

<span data-ttu-id="c4fc7-106">O assistente de implantação do Lync Server orienta você por meio de cada tarefa de preparação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-106">The Lync Server Deployment Wizard guides you through each Active Directory preparation task.</span></span> <span data-ttu-id="c4fc7-107">O assistente de implantação executa cmdlets do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-107">The Deployment Wizard runs Lync Server Management Shell cmdlets.</span></span> <span data-ttu-id="c4fc7-108">Essa ferramenta é útil para ambientes com um único domínio e topologia de floresta única ou outra topologia semelhante.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-108">This tool is useful for environments with a single domain and single forest topology, or other similar topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c4fc7-109">Você pode implantar o Lync Server em uma floresta ou domínio em que os controladores de domínio executem versões de 32 bits de alguns sistemas operacionais (para obter detalhes, consulte <A href="lync-server-2013-active-directory-infrastructure-requirements.md">requisitos de infraestrutura do Active Directory para o Lync Server 2013</A>).</span><span class="sxs-lookup"><span data-stu-id="c4fc7-109">You can deploy Lync Server in a forest or domain where domain controllers run 32-bit versions of some operating systems (for details, see <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory infrastructure requirements for Lync Server 2013</A>).</span></span> <span data-ttu-id="c4fc7-110">No entanto, você não pode usar o assistente de implantação do Lync Server para executar o esquema, a floresta e a preparação do domínio nesses ambientes porque o assistente de implantação e os arquivos de suporte são apenas 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-110">However, you cannot use the Lync Server Deployment Wizard to run schema, forest, and domain preparation in these environments because the Deployment Wizard and supporting files are 64-bit only.</span></span> <span data-ttu-id="c4fc7-111">Em vez disso, você pode usar o LDIFDE. exe e os arquivos. ldf associados em um controlador de domínio de 32 bits para preparar o esquema, a floresta e o domínio.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-111">Instead, you can use ldifde.exe and the associated .ldf files on a 32-bit domain controller to prepare the schema, forest and domain.</span></span> <span data-ttu-id="c4fc7-112">Consulte a seção "usando cmdlets e Ldifde. exe" mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-112">See the section “Using Cmdlets and Ldifde.exe” later in this topic.</span></span>



</div>

<span data-ttu-id="c4fc7-113">Você pode usar os cmdlets do Shell de gerenciamento do Lync Server para executar tarefas remotamente ou para ambientes mais complexos.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-113">You can use Lync Server Management Shell cmdlets to run tasks remotely or for more complex environments.</span></span>

<div>

## <a name="active-directory-preparation-prerequisites"></a><span data-ttu-id="c4fc7-114">Pré-requisitos de preparação do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4fc7-114">Active Directory Preparation Prerequisites</span></span>

<span data-ttu-id="c4fc7-115">Você deve executar as etapas de preparação do Active Directory em um computador que esteja executando o Windows Server 2012, o Windows Server 2012 R2 ou o Windows Server 2008 R2 com SP1 (64 bits).</span><span class="sxs-lookup"><span data-stu-id="c4fc7-115">You must run Active Directory preparation steps on a computer running Windows Server 2012, Windows Server 2012 R2, or Windows Server 2008 R2 with SP1 (64-bit).</span></span> <span data-ttu-id="c4fc7-116">A preparação do Active Directory requer o Shell de gerenciamento do Lync Server e o OCSCore.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-116">Active Directory preparation requires Lync Server Management Shell and OCSCore.</span></span>

<span data-ttu-id="c4fc7-117">Os seguintes componentes são necessários para executar tarefas de preparação do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="c4fc7-117">The following components are required to run Active Directory preparation tasks:</span></span>

  - <span data-ttu-id="c4fc7-118">Componentes principais do Lync Server (OCScore. msi)</span><span class="sxs-lookup"><span data-stu-id="c4fc7-118">Lync Server Core components (OCScore.msi)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4fc7-119">Se você pretende usar o Shell de gerenciamento do Lync Server para a preparação do Active Directory, deve executar o assistente de implantação do Lync Server primeiro para instalar os componentes principais.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-119">If you plan to use Lync Server Management Shell for Active Directory preparation, you must run the Lync Server Deployment Wizard first to install Core components.</span></span>

    
    </div>

  - <span data-ttu-id="c4fc7-120">Microsoft.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c4fc7-120">Microsoft .NET Framework 4.5</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4fc7-121">Para o Windows Server 2012 e o Windows Server 2012 R2, instale e ative o .NET Framework 4,5 usando o Gerenciador de servidores.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-121">For Windows Server 2012 and Windows Server 2012 R2, you install and activate .NET Framework 4.5 by using Server Manager.</span></span> <span data-ttu-id="c4fc7-122">Para obter detalhes, consulte "Microsoft .NET Framework 4,5" em <A href="lync-server-2013-additional-software-requirements.md">requisitos adicionais de software para o Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-122">For details, see "Microsoft .NET Framework 4.5" in <A href="lync-server-2013-additional-software-requirements.md">Additional software requirements for Lync Server 2013</A>.</span></span> <span data-ttu-id="c4fc7-123">Para o Windows&nbsp;Server&nbsp;2008 R2, baixe e instale o <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> do site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-123">For Windows Server&nbsp;2008&nbsp;R2, download and install <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.Net Framework 4.5</A> from the Microsoft web site.</span></span>

    
    </div>

  - <span data-ttu-id="c4fc7-124">Ferramentas de administração de servidor remoto (RSAT)</span><span class="sxs-lookup"><span data-stu-id="c4fc7-124">Remote Server Administration Tools (RSAT)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4fc7-125">Algumas ferramentas do RSAT são necessárias se você executar etapas de preparação do Active Directory em um servidor membro em vez de em um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-125">Some RSAT tools are required if you run Active Directory preparation steps on a member server rather than on a domain controller.</span></span> <span data-ttu-id="c4fc7-126">Instale os snap-ins do AD DS e as ferramentas de linha de comando e o módulo do Active Directory para Windows PowerShell do nó AD DS e ferramentas do AD LDS no Gerenciador de servidores.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-126">Install the AD DS snap-ins and command-line tools and the Active Directory Module for Windows PowerShell from the AD DS and AD LDS Tools node in Server Manager.</span></span>

    
    </div>

  - <span data-ttu-id="c4fc7-127">Microsoft Visual C++ 11 Redistributable</span><span class="sxs-lookup"><span data-stu-id="c4fc7-127">Microsoft Visual C++ 11 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4fc7-128">A instalação solicitará que você instale esse pré-requisito se ele ainda não estiver instalado no computador.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-128">Setup prompts you to install this prerequisite if it is not already installed on the computer.</span></span> <span data-ttu-id="c4fc7-129">O pacote é fornecido para você, e você não precisa adquiri-lo separadamente.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-129">The package is supplied for you, and you will not have to acquire it separately.</span></span>

    
    </div>

  - <span data-ttu-id="c4fc7-130">Windows PowerShell 3,0 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="c4fc7-130">Windows PowerShell 3.0 (64-bit)</span></span>
    
    <span data-ttu-id="c4fc7-131">Para o Windows Server 2012 e o Windows Server 2012 R2, o Windows PowerShell 3,0 deve estar incluído na instalação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-131">For Windows Server 2012 and Windows Server 2012 R2, Windows PowerShell 3.0 should be included with your Lync Server 2013 installation.</span></span> <span data-ttu-id="c4fc7-132">Para o Windows Server 2008 R2, você precisa instalar ou atualizar para o Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-132">For Windows Server 2008 R2, you need to install or upgrade to Windows PowerShell 3.0.</span></span> <span data-ttu-id="c4fc7-133">Para obter detalhes, consulte [instalando o Windows PowerShell 3,0 para Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span><span class="sxs-lookup"><span data-stu-id="c4fc7-133">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)</span></span>

</div>

<div>

## <a name="administrator-rights-and-roles"></a><span data-ttu-id="c4fc7-134">Direitos e funções de administrador</span><span class="sxs-lookup"><span data-stu-id="c4fc7-134">Administrator Rights and Roles</span></span>

<span data-ttu-id="c4fc7-135">A tabela a seguir mostra os direitos administrativos e as funções necessárias para cada tarefa de preparação do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-135">The following table shows the administrative rights and roles required for each Active Directory preparation task.</span></span>

### <a name="user-rights-required-for-active-directory-preparation"></a><span data-ttu-id="c4fc7-136">Direitos de usuário necessários para a preparação do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4fc7-136">User Rights Required for Active Directory Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4fc7-137">Processo</span><span class="sxs-lookup"><span data-stu-id="c4fc7-137">Procedure</span></span></th>
<th><span data-ttu-id="c4fc7-138">Direitos ou funções</span><span class="sxs-lookup"><span data-stu-id="c4fc7-138">Rights or roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4fc7-139">Preparação do esquema</span><span class="sxs-lookup"><span data-stu-id="c4fc7-139">Schema preparation</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-140">Membro do grupo Administradores de esquemas para os direitos de domínio raiz da floresta e administrador no mestre de esquema</span><span class="sxs-lookup"><span data-stu-id="c4fc7-140">Member of Schema Admins group for the forest root domain and administrator rights on the schema master</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fc7-141">Preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="c4fc7-141">Forest preparation</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-142">Membro do grupo Administradores Corporativos para a floresta</span><span class="sxs-lookup"><span data-stu-id="c4fc7-142">Member of Enterprise Admins group for the forest</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fc7-143">Preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="c4fc7-143">Domain preparation</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-144">Membro do grupo administradores corporativos ou administradores de domínio do domínio especificado</span><span class="sxs-lookup"><span data-stu-id="c4fc7-144">Member of Enterprise Admins or Domain Admins group for the specified domain</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a><span data-ttu-id="c4fc7-145">Cmdlets de preparação do Active Directory</span><span class="sxs-lookup"><span data-stu-id="c4fc7-145">Active Directory Preparation Cmdlets</span></span>

<span data-ttu-id="c4fc7-146">A tabela a seguir compara os cmdlets do Shell de gerenciamento do Lync Server usados para preparar o AD DS para os comandos LcsCmd usados para preparar o AD DS no Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-146">The following table compares the Lync Server Management Shell cmdlets used to prepare AD DS to the LcsCmd commands used to prepare AD DS in Microsoft Office Communications Server 2007 R2.</span></span>

### <a name="cmdlets-compared-to-lcscmd"></a><span data-ttu-id="c4fc7-147">Cmdlets comparados ao LcsCmd</span><span class="sxs-lookup"><span data-stu-id="c4fc7-147">Cmdlets Compared to LcsCmd</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4fc7-148">Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c4fc7-148">Cmdlets</span></span></th>
<th><span data-ttu-id="c4fc7-149">LcsCmd</span><span class="sxs-lookup"><span data-stu-id="c4fc7-149">LcsCmd</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4fc7-150">Install-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="c4fc7-150">Install-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-151">LcsCmd/Forest/Action: SchemaPrep/SchemaType: Server</span><span class="sxs-lookup"><span data-stu-id="c4fc7-151">Lcscmd /forest /action:SchemaPrep /SchemaType:Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fc7-152">Get-CsAdServerSchema</span><span class="sxs-lookup"><span data-stu-id="c4fc7-152">Get-CsAdServerSchema</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-153">LcsCmd/Forest/Action: CheckSchemaPrepState</span><span class="sxs-lookup"><span data-stu-id="c4fc7-153">Lcscmd /forest /action:CheckSchemaPrepState</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fc7-154">Enable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="c4fc7-154">Enable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-155">LcsCmd/Forest/Action: ForestPrep</span><span class="sxs-lookup"><span data-stu-id="c4fc7-155">Lcscmd /forest /action:ForestPrep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fc7-156">Disable-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="c4fc7-156">Disable-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-157">LcsCmd/Forest/Action: ForestUnprep</span><span class="sxs-lookup"><span data-stu-id="c4fc7-157">Lcscmd /forest /action:ForestUnprep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fc7-158">Get-CsAdForest</span><span class="sxs-lookup"><span data-stu-id="c4fc7-158">Get-CsAdForest</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-159">LcsCmd/Forest/Action: CheckForestPrepState</span><span class="sxs-lookup"><span data-stu-id="c4fc7-159">Lcscmd /forest /action:CheckForestPrepState</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fc7-160">Enable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="c4fc7-160">Enable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-161">LcsCmd/Domain/Action: DomainPrep</span><span class="sxs-lookup"><span data-stu-id="c4fc7-161">Lcscmd /domain /action:DomainPrep</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4fc7-162">Disable-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="c4fc7-162">Disable-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-163">LcsCmd/Domain/Action: DomainUnprep</span><span class="sxs-lookup"><span data-stu-id="c4fc7-163">Lcscmd /domain /action: DomainUnprep</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4fc7-164">Get-CsAdDomain</span><span class="sxs-lookup"><span data-stu-id="c4fc7-164">Get-CsAdDomain</span></span></p></td>
<td><p><span data-ttu-id="c4fc7-165">LcsCmd/Domain/Action: CheckDomainPrepState</span><span class="sxs-lookup"><span data-stu-id="c4fc7-165">Lcscmd /domain /action:CheckDomainPrepState</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a><span data-ttu-id="c4fc7-166">Requisitos do Active Directory bloqueados</span><span class="sxs-lookup"><span data-stu-id="c4fc7-166">Locked Down Active Directory Requirements</span></span>

<span data-ttu-id="c4fc7-167">Se a herança de permissões estiver desabilitada ou as permissões de usuário autenticado tiverem que ser desabilitadas em sua organização, você deverá executar etapas adicionais durante a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-167">If permissions inheritance is disabled or authenticated user permissions must be disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="c4fc7-168">Para obter detalhes, consulte [preparando um serviço de domínio do Active Directory bloqueado no Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="c4fc7-168">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

</div>

<div>

## <a name="custom-container-permissions"></a><span data-ttu-id="c4fc7-169">Permissões de contêiner personalizado</span><span class="sxs-lookup"><span data-stu-id="c4fc7-169">Custom Container Permissions</span></span>

<span data-ttu-id="c4fc7-170">Se a sua organização usa recipientes personalizados em vez de três contêineres internos (ou seja, usuários, computadores e controladores de domínio), você deve conceder acesso de leitura aos recipientes personalizados para o grupo usuários autenticados.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-170">If your organization uses custom containers instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the custom containers for the Authenticated Users group.</span></span> <span data-ttu-id="c4fc7-171">O acesso de leitura aos recipientes é necessário para a preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-171">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="c4fc7-172">Para obter detalhes, consulte [preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md).</span><span class="sxs-lookup"><span data-stu-id="c4fc7-172">For details, see [Preparing domains for Lync Server 2013](lync-server-2013-preparing-domains.md).</span></span>

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a><span data-ttu-id="c4fc7-173">Usando cmdlets e Ldifde. exe</span><span class="sxs-lookup"><span data-stu-id="c4fc7-173">Using Cmdlets and Ldifde.exe</span></span>

<span data-ttu-id="c4fc7-174">A etapa **preparar esquema** no assistente de implantação do Lync Server e o cmdlet **install-CsAdServerSchema** ampliam o esquema do Active Directory em controladores de domínio que executam um sistema operacional de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-174">The **Prepare Schema** step in the Lync Server Deployment Wizard and the **Install-CsAdServerSchema** cmdlet extend the Active Directory schema on domain controllers running a 64-bit operating system.</span></span> <span data-ttu-id="c4fc7-175">Se você precisar estender o esquema do Active Directory em um controlador de domínio que executa um sistema operacional de 32 bits, poderá executar o cmdlet **install-CsAdServerSchema** remotamente de um servidor membro (abordagem recomendada).</span><span class="sxs-lookup"><span data-stu-id="c4fc7-175">If you need to extend the Active Directory schema on a domain controller running a 32-bit operating system, you can run the **Install-CsAdServerSchema** cmdlet remotely from a member server (recommended approach).</span></span> <span data-ttu-id="c4fc7-176">No entanto, se você precisar executar a preparação do esquema diretamente no controlador de domínio, poderá usar a ferramenta Ldifde. exe para importar os arquivos de esquema.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-176">If you need to run schema preparation directly on the domain controller, however, you can use the Ldifde.exe tool to import the schema files.</span></span> <span data-ttu-id="c4fc7-177">A ferramenta Ldifde. exe vem com a maioria das versões do sistema operacional Windows.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-177">The Ldifde.exe tool comes with most versions of the Windows operating system.</span></span>

<span data-ttu-id="c4fc7-178">Se você usar LDIFDE. exe para importar os arquivos de esquema, será necessário importar todos os quatro arquivos, independentemente de você estar migrando de uma versão anterior ou de uma instalação limpa.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-178">If you use Ldifde.exe to import the schema files, you must import all four files, regardless of whether you are migrating from a previous version or performing a clean installation.</span></span> <span data-ttu-id="c4fc7-179">Você deve importá-las na seguinte sequência:</span><span class="sxs-lookup"><span data-stu-id="c4fc7-179">You must import them in the following sequence:</span></span>

1.  <span data-ttu-id="c4fc7-180">ExternalSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="c4fc7-180">ExternalSchema.ldf</span></span>

2.  <span data-ttu-id="c4fc7-181">ServerSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="c4fc7-181">ServerSchema.ldf</span></span>

3.  <span data-ttu-id="c4fc7-182">BackCompatSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="c4fc7-182">BackCompatSchema.ldf</span></span>

4.  <span data-ttu-id="c4fc7-183">VersionSchema. ldf</span><span class="sxs-lookup"><span data-stu-id="c4fc7-183">VersionSchema.ldf</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c4fc7-184">Os quatro arquivos. ldf estão localizados no diretório \Support\Schema da mídia de instalação ou download.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-184">The four .ldf files are located in \Support\Schema directory of your installation media or download.</span></span>



</div>

<span data-ttu-id="c4fc7-185">Para usar o LDIFDE. exe para importar os quatro arquivos de esquema em um controlador de domínio que seja o mestre de esquema, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="c4fc7-185">To use Ldifde.exe to import the four schema files on a domain controller that is the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

<span data-ttu-id="c4fc7-186">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c4fc7-186">For example:</span></span>

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> <span data-ttu-id="c4fc7-187">Use o parâmetro b somente se você estiver conectado como um usuário diferente.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-187">Use the b parameter only if you are logged in as a different user.</span></span> <span data-ttu-id="c4fc7-188">Para obter detalhes sobre os direitos de usuário necessários, consulte a seção "direitos e funções de administrador" anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-188">For details about the required user rights, see the "Administrator Rights and Roles" section earlier in this topic.</span></span>



</div>

<span data-ttu-id="c4fc7-189">Para usar o LDIFDE. exe para importar os quatro arquivos de esquema em um controlador de domínio que não seja o mestre de esquema, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="c4fc7-189">To use Ldifde.exe to import the four schema files on a domain controller that is not the schema master, use the following format:</span></span>

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

<span data-ttu-id="c4fc7-190">Para obter detalhes sobre como usar o Ldifde, consulte o artigo 237677 da base de dados de conhecimento Microsoft, "usar o LDIFDE para importar e [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)exportar objetos de diretório para o Active Directory" em.</span><span class="sxs-lookup"><span data-stu-id="c4fc7-190">For details about using Ldifde, see Microsoft Knowledge Base article 237677, "Using LDIFDE to import and export directory objects to Active Directory," at [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204).</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c4fc7-191">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c4fc7-191">In This Section</span></span>

  - [<span data-ttu-id="c4fc7-192">Preparando o esquema do Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4fc7-192">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)

  - [<span data-ttu-id="c4fc7-193">Preparando a floresta para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4fc7-193">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)

  - [<span data-ttu-id="c4fc7-194">Preparando domínios para Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4fc7-194">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

