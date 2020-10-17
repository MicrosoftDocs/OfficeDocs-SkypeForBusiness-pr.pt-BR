---
title: Ferramentas do kit de recursos de chat persistente do Lync Server 2013
description: Ferramentas do kit de recursos de chat persistente do Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542347"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="1f9ed-103">Ferramentas do kit de recursos de chat persistente do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f9ed-103">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f9ed-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="1f9ed-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="1f9ed-105">As ferramentas do kit de recursos de chat persistente do Lync Server 2013 ajudam a tornar tarefas rotineiras mais fáceis para os administradores de ti que implantam e gerenciam o servidor de chat persistente do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-105">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="1f9ed-106">Além das instruções de instalação, este tópico descreve a finalidade de cada ferramenta e exemplos de uso.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-106">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="1f9ed-107">Instalação das ferramentas do kit de recursos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-107">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="1f9ed-108">Para instalar o Lync Server 2013, ferramentas do kit de recursos, **PersistentChatReskit.msi**de download.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-108">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="1f9ed-109">Execute **PersistentChatReskit.msi** para fazer uma instalação simples.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-109">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="1f9ed-110">O. msi instala todas as ferramentas no seguinte caminho: \\ **arquivos de programa \\ Microsoft Lync Server 2013 \\ persistent chat Server Resource Kit**.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-110">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="1f9ed-111">As ferramentas que são executáveis independentes estão nessa pasta.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-111">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="1f9ed-112">As ferramentas que também têm arquivos estão em suas próprias subpastas.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-112">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1f9ed-113">Após a instalação do Lync Server 2013, ferramentas do Resource Kit, você deve instalar <STRONG>PsExec.exe</STRONG> e copiar <STRONG>PsExec.exe</STRONG> para o seguinte caminho: \\ <STRONG>arquivos de programa \ Microsoft Lync Server 2013 \ persistent chat Server Resource Kit\ChatStressTool</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-113">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="1f9ed-114">Se você não copiar <STRONG>PsExec.exe</STRONG>, a ferramenta de estresse de chat persistente lançará uma exceção de erro e não será executada corretamente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-114">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="1f9ed-115">Certifique-se de atender a esse requisito de pré-requisito antes de executar a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-115">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="1f9ed-116">Para obter detalhes sobre como instalar o <STRONG>PsExec.exe</STRONG>, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> .</span><span class="sxs-lookup"><span data-stu-id="1f9ed-116">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="1f9ed-117">Ambientes com suporte</span><span class="sxs-lookup"><span data-stu-id="1f9ed-117">Supported Environments</span></span>

<span data-ttu-id="1f9ed-118">Para obter o desempenho ideal, o Lync Server 2013, ferramentas do Resource Kit devem ser instalados no mesmo ambiente e com as mesmas especificações necessárias para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-118">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="1f9ed-119">Visão geral das ferramentas do kit de recursos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-119">Resource Kit Tools Overview</span></span>

<span data-ttu-id="1f9ed-120">Aqui estão as ferramentas fornecidas no kit de recursos de chat persistente do Lync Server 2013 persistent.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-120">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="1f9ed-121">A seção a seguir fornece uma descrição de cada ferramenta, incluindo os requisitos e o uso de exemplos.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-121">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="1f9ed-122">AffCheck</span><span class="sxs-lookup"><span data-stu-id="1f9ed-122">AffCheck</span></span>

  - <span data-ttu-id="1f9ed-123">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="1f9ed-123">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="1f9ed-124">Ferramenta ChatStress</span><span class="sxs-lookup"><span data-stu-id="1f9ed-124">ChatStress Tool</span></span>

  - <span data-ttu-id="1f9ed-125">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="1f9ed-125">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="1f9ed-126">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="1f9ed-126">ChatUsageReport</span></span>

  - <span data-ttu-id="1f9ed-127">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="1f9ed-127">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="1f9ed-128">AffCheck</span><span class="sxs-lookup"><span data-stu-id="1f9ed-128">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1f9ed-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f9ed-129">Description</span></span>

<span data-ttu-id="1f9ed-130">A ferramenta AffCheck confirma que o usuário do banco de dados de back-end de chat persistente e os registros de afiliação de grupo correspondem aos dos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-130">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1f9ed-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-131">Requirements</span></span>

<span data-ttu-id="1f9ed-132">A ferramenta é instalada com o instalador do PersistentChatResKit em um computador ingressado no domínio.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-132">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="1f9ed-133">A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura ao banco de dados de back-end do chat persistente e aos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-133">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="1f9ed-134">Uso</span><span class="sxs-lookup"><span data-stu-id="1f9ed-134">Usage</span></span>

<span data-ttu-id="1f9ed-135">Configure o arquivo de AffCheck.exe.config de acordo com as instruções no arquivo de configuração e execute a ferramenta AffCheck sem parâmetros de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-135">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="1f9ed-136">Veja a seguir o conteúdo do AffCheck.exe.config padrão.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-136">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="1f9ed-137">**AffCheck.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="1f9ed-137">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="1f9ed-138">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="1f9ed-138">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1f9ed-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f9ed-139">Description</span></span>

<span data-ttu-id="1f9ed-140">A ferramenta PersistentChatMonitoringSummary move as informações de monitoramento de chat persistente do banco de dados de monitoramento para um arquivo de log CSV especificado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-140">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="1f9ed-141">O arquivo CSV conterá uma divisão de sessões de chat persistentes pelo número total de sessões, sessões bem-sucedidas, falhas inesperadas, falhas esperadas e uma divisão das falhas inesperadas por ID de diagnóstico, número de falhas e descrição de falha.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-141">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1f9ed-142">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-142">Requirements</span></span>

<span data-ttu-id="1f9ed-143">Instale as ferramentas do kit de recursos de chat persistente em uma máquina associada a um domínio que tenha acesso ao banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-143">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="1f9ed-144">A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura ao banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-144">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="1f9ed-145">O arquivo, PersistentChatMonitoringSummary.exe.config, deve conter uma \<connectionStrings\> seção que define a cadeia de caracteres de conexão com o banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-145">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="1f9ed-146">Ele também deve conter uma chave para o PersistentChatEndpointUri para o qual os dados de monitoramento serão coletados e um caminho de arquivo para um local para o arquivo CSV que será gerado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-146">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="1f9ed-147">Consulte o arquivo de configuração instalado para obter exemplos.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-147">Refer to the installed config file for examples.</span></span> <span data-ttu-id="1f9ed-148">O arquivo deve estar localizado no mesmo diretório que a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-148">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="1f9ed-149">Uso</span><span class="sxs-lookup"><span data-stu-id="1f9ed-149">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="1f9ed-150">Estes parâmetros definem a seleção de dados:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-150">These parameters define the selection of data:</span></span>

<span data-ttu-id="1f9ed-151">**StartDateTime:** Especifica opcionalmente a data de início do período de seleção.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-151">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="1f9ed-152">Padrão: 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="1f9ed-152">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="1f9ed-153">**EndDateTime:** Especifica opcionalmente a última data do período de seleção.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-153">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="1f9ed-154">Padrão: agora</span><span class="sxs-lookup"><span data-stu-id="1f9ed-154">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="1f9ed-155">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1f9ed-155">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="1f9ed-156">Ferramenta de estresse de chat persistente</span><span class="sxs-lookup"><span data-stu-id="1f9ed-156">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1f9ed-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f9ed-157">Description</span></span>

<span data-ttu-id="1f9ed-158">A ferramenta de estresse de chat persistente oferece uma maneira fácil de simular o uso de chat persistente para testar o desempenho do mundo real, incluindo diferentes modelos de usuário para se adequar melhor aos cenários de uso esperados.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-158">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1f9ed-159">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-159">Requirements</span></span>

<span data-ttu-id="1f9ed-160">Instale as ferramentas do kit de recursos de chat persistente em uma máquina associada a um domínio que tenha acesso ao banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-160">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="1f9ed-161">Além desse computador *controlador* , você precisará de várias máquinas de *carregador* .</span><span class="sxs-lookup"><span data-stu-id="1f9ed-161">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="1f9ed-162">Para todos os usuários de 10K em seu modelo de usuário, você precisará de pelo menos 4 GB de RAM livre em uma máquina de carregador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-162">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="1f9ed-163">Por exemplo, uma execução com usuários do 80K exigirá cerca de 32 GB de RAM distribuídos em todas as máquinas de carregador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-163">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="1f9ed-164">Recomendamos que você tenha pelo menos três máquinas de carregador, independentemente da carga esperada.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-164">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="1f9ed-165">As máquinas de carregador devem ter a estrutura do .NET 4,5, bem como o Visual C++ 2012 Redistributable instalado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-165">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="1f9ed-166">Configuração</span><span class="sxs-lookup"><span data-stu-id="1f9ed-166">Configuration</span></span>

<span data-ttu-id="1f9ed-167">Copie os arquivos do ChatStressTool em uma pasta compartilhada acessível de todas as máquinas de carregador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-167">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="1f9ed-168">Criar usuários e canais para uso na execução de estresse:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-168">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="1f9ed-169">Crie quantos usuários forem suas chamadas de modelo de usuário, habilite-os para o Lync e defina sua política de chat persistente como habilitado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-169">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="1f9ed-170">Crie uma categoria para seus canais de estresse e, em seguida, crie quantas salas forem necessárias nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-170">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="1f9ed-171">A categoria deve ter todos os usuários de estresse em sua lista **permitida** (por meio da adição da ou), e as salas de estresse devem ter uma configuração de privacidade **aberta**.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-171">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="1f9ed-172">Recomendamos a criação de salas de estresse adicionais.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-172">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="1f9ed-173">Você pode criar salas de 50.000 com o seguinte comando de interface de linha de comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-173">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="1f9ed-174">Edite os arquivos de configuração de acordo com sua topologia:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-174">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="1f9ed-175">Em **LoaderProcess.exe.config**, altere "Controller.contoso.com" para o nome de domínio totalmente qualificado (FQDN) do computador do controlador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-175">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="1f9ed-176">No **StressLauncher.exe.config:**</span><span class="sxs-lookup"><span data-stu-id="1f9ed-176">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="1f9ed-177">Altere o valor de configuração "LoaderBinary" para o caminho da pasta compartilhada.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-177">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="1f9ed-178">Altere "AdminUser"/"AdminPassword" para credenciais que têm acesso de administrador a máquinas de carregador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-178">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="1f9ed-179">Altere "ChannelCategory" para o nome da categoria em que os canais de estresse foram criados.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-179">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="1f9ed-180">Altere "UserNamePattern" e "UserPasswordPattern" para um modelo que corresponda às suas credenciais de usuário de estresse.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-180">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="1f9ed-181">{0} é substituído pelo número de índice do usuário.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-181">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="1f9ed-182">Altere "Domain" para o domínio SIP de sua topologia de teste.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-182">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="1f9ed-183">Altere "ConnectionString" para uma sequência de conexão para seu banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-183">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="1f9ed-184">Altere "UserIndexStart" para o índice do primeiro usuário de estresse.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-184">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="1f9ed-185">Altere "LyncFQDN" para o FQDN do seu pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-185">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="1f9ed-186">Modifique a lista "máquinas" para incluir nomes de máquina para todas as máquinas de carregador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-186">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="1f9ed-187">Altere o baseAddress do ponto de extremidade de serviço (o padrão é "controller.contoso.com") para o FQDN do seu computador controlador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-187">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="1f9ed-188">Uso</span><span class="sxs-lookup"><span data-stu-id="1f9ed-188">Usage</span></span>

<span data-ttu-id="1f9ed-189">Após a conclusão da configuração, abra StressLauncher.exe no computador do controlador.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-189">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="1f9ed-190">Você pode iniciar o StressLauncher como qualquer usuário.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-190">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="1f9ed-191">As credenciais sob as quais os processos de carregador começam nas máquinas de carregador devem ser especificadas no arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-191">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="1f9ed-192">Você também deve fornecer uma cadeia de conexão com acesso de leitura ao banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-192">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="1f9ed-193">Se essa cadeia de conexão usar a autenticação integrada do Windows, você deverá iniciar o StressLauncher como um usuário que tenha esse acesso.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-193">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="1f9ed-194">Altere as configurações de modelo de usuário conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-194">Alter the user model settings as needed.</span></span> <span data-ttu-id="1f9ed-195">Clique em **Iniciar carregamento** para iniciar uma execução.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-195">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="1f9ed-196">Após um minuto, os usuários começarão a entrar, e a barra de progresso começará a ser preenchida.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-196">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="1f9ed-197">Neste ponto, é possível que a máquina controladora funcione e tenha medidas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-197">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="1f9ed-198">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="1f9ed-198">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1f9ed-199">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f9ed-199">Description</span></span>

<span data-ttu-id="1f9ed-200">ChatUpgradeVerifier é uma ferramenta de comparação de banco de dados específica de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-200">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="1f9ed-201">A ferramenta compara o banco de dados de chat de grupo 2007 R2 ou de 2010 chat de grupo (2007/2010Db) com o banco de dados de chat persistente 2013 (2013Db).</span><span class="sxs-lookup"><span data-stu-id="1f9ed-201">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="1f9ed-202">A ferramenta verificará, uma por um, cada categoria, sala de chat persistente e suplemento em 2007/2010Db para ver se ela aparece no 2013Db.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-202">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="1f9ed-203">A comparação inclui a verificação de todas as configurações da categoria, da sala de chat ou do suplemento, de qualquer entidade de segurança no escopo da categoria e de qualquer entidade de segurança em uma função na categoria ou na sala de chat.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-203">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="1f9ed-204">Se uma categoria ou uma sala de chat não aparecer corretamente no 2013Db, as diferenças serão de saída para um arquivo de conflitos.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-204">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="1f9ed-205">Se, após a atualização ter ocorrido, o 2007/2010Db for alterado e essa ferramenta for executada, haverá uma saída de diferenças para o arquivo de conflitos.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-205">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="1f9ed-206">Observe que este aplicativo é uma ferramenta de comparação de banco de dados somente e não valida o processo de atualização.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-206">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1f9ed-207">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-207">Requirements</span></span>

<span data-ttu-id="1f9ed-208">Instale as ferramentas do kit de recursos de chat persistente em uma máquina que ingressou em um domínio que tenha acesso aos bancos de dados de back-end de chat persistente (versões anteriores e atuais para chat persistente).</span><span class="sxs-lookup"><span data-stu-id="1f9ed-208">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="1f9ed-209">A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura aos bancos de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-209">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="1f9ed-210">O arquivo ChatUpgradeVerifier.exe.config deve conter o parâmetro GroupChat2007R2Db ou o parâmetro GroupChat2010Db, com uma cadeia de caracteres de conexão para o banco de dados de chat de grupo apropriado (Groupchat 2007R2 ou 2010).</span><span class="sxs-lookup"><span data-stu-id="1f9ed-210">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="1f9ed-211">Também deve conter um parâmetro PersistentChat2013Db, com uma cadeia de caracteres de conexão para o banco de dados chat persistente 2013.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-211">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="1f9ed-212">Uso</span><span class="sxs-lookup"><span data-stu-id="1f9ed-212">Usage</span></span>

<span data-ttu-id="1f9ed-213">Execute o **ChatUpgradeVerifier** sem nenhum parâmetro.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-213">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="1f9ed-214">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1f9ed-214">Example</span></span>

<span data-ttu-id="1f9ed-215">![Executando ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Executando ChatUpgradeVerifier.exe.")</span><span class="sxs-lookup"><span data-stu-id="1f9ed-215">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="1f9ed-216">Relatório de uso de chat persistente</span><span class="sxs-lookup"><span data-stu-id="1f9ed-216">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1f9ed-217">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f9ed-217">Description</span></span>

<span data-ttu-id="1f9ed-218">A ferramenta ChatUsageReport gera um relatório HTML de uso do serviço de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-218">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1f9ed-219">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-219">Requirements</span></span>

<span data-ttu-id="1f9ed-220">Instale as ferramentas do kit de recursos de chat persistente em uma máquina associada a um domínio que tenha acesso ao banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-220">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="1f9ed-221">A conta de usuário sob a qual a ferramenta é executada deve ter acesso de leitura ao banco de dados back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-221">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="1f9ed-222">O arquivo, ChatUsageReport.exe.config, deve conter uma \<connectionStrings\> seção que define a sequência de conexão para o banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-222">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="1f9ed-223">O conteúdo do arquivo de configuração padrão é incluído aqui para sua referência.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-223">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="1f9ed-224">Uso</span><span class="sxs-lookup"><span data-stu-id="1f9ed-224">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="1f9ed-225">Estes parâmetros definem a seleção de dados:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-225">These parameters define the selection of data:</span></span>

<span data-ttu-id="1f9ed-226">**StartDate:** Especifica opcionalmente a data de início UTC do período de seleção.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-226">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="1f9ed-227">Padrão: data mais antiga</span><span class="sxs-lookup"><span data-stu-id="1f9ed-227">Default: Earliest Date</span></span>

<span data-ttu-id="1f9ed-228">**EndDate:** Especifica opcionalmente a data de término UTC do período de seleção.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-228">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="1f9ed-229">Padrão: agora</span><span class="sxs-lookup"><span data-stu-id="1f9ed-229">Default: Now</span></span>

<span data-ttu-id="1f9ed-230">Estes parâmetros definem como e quais dados são exibidos:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-230">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="1f9ed-231">**TopActiveUsers:** Se for especificado, o relatório incluirá a n usuários mais ativos em termos do número de mensagens que o usuário publicou na sala de chat para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-231">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="1f9ed-232">Padrão: 10</span><span class="sxs-lookup"><span data-stu-id="1f9ed-232">Default: 10</span></span>

<span data-ttu-id="1f9ed-233">**TopActiveRooms:** Se for especificado, o relatório incluirá a n salas de chat mais ativas em termos do número de mensagens postadas na sala para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-233">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="1f9ed-234">Padrão: 10</span><span class="sxs-lookup"><span data-stu-id="1f9ed-234">Default: 10</span></span>

<span data-ttu-id="1f9ed-235">**LeastActiveRooms:** Se for especificado, o relatório incluirá as n menos salas de chat ativa em termos do número de mensagens postadas na sala de chat para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-235">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="1f9ed-236">As salas terão pelo menos uma mensagem postada.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-236">Rooms will have at least one message posted.</span></span> <span data-ttu-id="1f9ed-237">Padrão: 10</span><span class="sxs-lookup"><span data-stu-id="1f9ed-237">Default: 10</span></span>

<span data-ttu-id="1f9ed-238">**RoomsInactiveSince:** Se for especificado, o relatório incluirá uma lista de salas de chat que foram inativas desde a data especificada.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-238">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="1f9ed-239">Padrão: hora inteira</span><span class="sxs-lookup"><span data-stu-id="1f9ed-239">Default: Entire Time</span></span>

<span data-ttu-id="1f9ed-240">**OutputFolder:** A pasta na qual as imagens do ChatUsageReport.html e do gráfico serão colocadas.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-240">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="1f9ed-241">Isso deve ser definido no arquivo de configuração ou na linha de comando.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-241">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="1f9ed-242">Todos os valores de parâmetro de linha de comando também podem ser especificados no arquivo de ChatUsageReport.exe.config que está localizado no mesmo diretório que a ferramenta.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-242">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="1f9ed-243">Se qualquer valor for especificado no arquivo de configuração e na linha de comando, o valor da linha de comando substituirá o valor do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-243">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="1f9ed-244">Saída</span><span class="sxs-lookup"><span data-stu-id="1f9ed-244">Output</span></span>

<span data-ttu-id="1f9ed-245">O relatório sempre incluirá o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-245">The report will always include the following output:</span></span>

  - <span data-ttu-id="1f9ed-246">N principais salas de chat ativas por número de postagens de mensagem para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-246">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="1f9ed-247">N primeiros usuários ativos por número de postagens de mensagem para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-247">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="1f9ed-248">N o máximo de salas de chat ativas por número de postagens de mensagem para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-248">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="1f9ed-249">Salas de chat que estão inativas para toda a vida do banco de dados ou desde a data especificada.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-249">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="1f9ed-250">Tendência da postagem diária da mensagem para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-250">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="1f9ed-251">Tendência de postagem de mensagem semanal para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-251">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="1f9ed-252">Tendência de post de mensagem mensal para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-252">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="1f9ed-253">Total de postagens de mensagem para o período selecionado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-253">Total message posts for selected period.</span></span>

  - <span data-ttu-id="1f9ed-254">Número total de salas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-254">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="1f9ed-255">Exemplo</span><span class="sxs-lookup"><span data-stu-id="1f9ed-255">Example</span></span>

<span data-ttu-id="1f9ed-256">O exemplo a seguir gera um relatório de uso para o ano inteiro 2001 e coloca o relatório no OutputFolder especificado no ChatUsageReport.exe.config.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-256">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="1f9ed-257">ChatUsageReport.exe.config:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-257">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="1f9ed-258">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="1f9ed-258">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="1f9ed-259">Descrição</span><span class="sxs-lookup"><span data-stu-id="1f9ed-259">Description</span></span>

<span data-ttu-id="1f9ed-260">ScheduleADSyncForPrincipal é um script do Microsoft SQL Server 2012 que deve ser executado diretamente de dentro do SQL Server Management Studio quando conectado ao banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-260">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="1f9ed-261">Esse script permite forçar o chat persistente a sincronizar seus registros de um usuário com os serviços de domínio do Active Directory, em vez de aguardar o tempo de sincronização agendado.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-261">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="1f9ed-262">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f9ed-262">Requirements</span></span>

<span data-ttu-id="1f9ed-263">A conta de usuário sob a qual o script é executado deve ter acesso de proprietário para o banco de dados de back-end de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="1f9ed-263">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="1f9ed-264">Uso</span><span class="sxs-lookup"><span data-stu-id="1f9ed-264">Usage</span></span>

<span data-ttu-id="1f9ed-265">Veja a seguir o conteúdo do script padrão:</span><span class="sxs-lookup"><span data-stu-id="1f9ed-265">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

