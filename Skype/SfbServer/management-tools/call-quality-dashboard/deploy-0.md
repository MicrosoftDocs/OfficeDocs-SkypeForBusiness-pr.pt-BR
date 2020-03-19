---
title: Implantar o painel de qualidade de chamada para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumo: Saiba mais sobre o processo de implantação do painel de qualidade de chamada. O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.'
ms.openlocfilehash: 5879c4a99eec8471763e0fccc3a4886be660dbb6
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42840155"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="6413a-104">Implantar o painel de qualidade de chamada para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6413a-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="6413a-105">**Resumo:** Saiba mais sobre o processo de implantação do painel de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="6413a-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="6413a-106">O painel de qualidade de chamada é uma ferramenta para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6413a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="6413a-107">Visão geral da implantação</span><span class="sxs-lookup"><span data-stu-id="6413a-107">Deployment Overview</span></span>

<span data-ttu-id="6413a-108">O painel de qualidade de chamada (CQD) consiste em três componentes principais:</span><span class="sxs-lookup"><span data-stu-id="6413a-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="6413a-109">**Arquivar banco**de dados, onde os dados de QoE (qualidade da experiência) são replicados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="6413a-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="6413a-110">**Cubo**, onde os dados do banco de dados de arquivo de QoE são agregados para acesso otimizado e rápido.</span><span class="sxs-lookup"><span data-stu-id="6413a-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="6413a-111">**Portal**, onde os usuários podem facilmente consultar e Visualizar dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="6413a-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Componentes do CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="6413a-113">O processo de instalação para o arquivo de QoE envolve a criação do banco de dados de arquivamento QoE, a implantação de um procedimento armazenado do SQL Server que moverá os dados do banco de dados de métricas de QoE de origem para o banco de dados de arquivo de distribuição e Configurando o trabalho do SQL Server Agent para executar o armazenamento procedimento em um intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="6413a-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="6413a-114">A implantação de cubo Obtém informações do usuário em que o arquivo de QoE está localizado, implanta o cubo e configura um trabalho regular do SQL Server Agent que atualizará o cubo em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="6413a-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="6413a-115">A instalação do portal cria um banco de dados de repositório que armazena o mapeamento de usuários do CQD para relatórios/consultas de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="6413a-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="6413a-116">Em seguida, ele configura um aplicativo Web IIS, que é o painel em que os usuários podem ver um conjunto predefinido de relatórios, bem como personalizar e criar suas próprias consultas para visualizar dados do cubo.</span><span class="sxs-lookup"><span data-stu-id="6413a-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="6413a-117">A instalação do portal cria dois aplicativos Web adicionais que expõem APIs para que os usuários acessem programaticamente o repositório e o cubo.</span><span class="sxs-lookup"><span data-stu-id="6413a-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="6413a-118">(Essas APIs também são usadas internamente pelo painel).</span><span class="sxs-lookup"><span data-stu-id="6413a-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="6413a-119">**Fase**</span><span class="sxs-lookup"><span data-stu-id="6413a-119">**Phase**</span></span>|<span data-ttu-id="6413a-120">**Etapas**</span><span class="sxs-lookup"><span data-stu-id="6413a-120">**Steps**</span></span>|<span data-ttu-id="6413a-121">**Funções e Associação de grupo**</span><span class="sxs-lookup"><span data-stu-id="6413a-121">**Roles and group membership**</span></span>|<span data-ttu-id="6413a-122">**Documentação**</span><span class="sxs-lookup"><span data-stu-id="6413a-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6413a-123">Instale os pré-requisitos de hardware e software.</span><span class="sxs-lookup"><span data-stu-id="6413a-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="6413a-124">Decida sobre a configuração do CQD e escolha um SQL Server a partir do qual a instalação será executada.</span><span class="sxs-lookup"><span data-stu-id="6413a-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="6413a-125">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="6413a-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="6413a-126">Seção "requisitos de pré-instalação" na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6413a-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="6413a-127">Instale o CQD.</span><span class="sxs-lookup"><span data-stu-id="6413a-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="6413a-128">Execute o MSI após o documento de implantação.</span><span class="sxs-lookup"><span data-stu-id="6413a-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="6413a-129">Para executar a configuração, a conta de instalação deve ser um usuário de domínio que seja membro do grupo Administradores local e ter acesso de leitura ao banco de dados de métricas de QoE no servidor de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="6413a-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="6413a-130">Seções "etapas de contas e implantação" na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6413a-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="6413a-131">Conceder acesso de usuário.</span><span class="sxs-lookup"><span data-stu-id="6413a-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="6413a-132">Para gerenciar a autorização do usuário no portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="6413a-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="6413a-133">Para obter mais informações, consulte [Understanding IIS 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="6413a-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="6413a-134">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="6413a-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="6413a-135">Gerenciar o acesso do usuário para a seção portal na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6413a-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="6413a-136">Opcional: fornecer informações de mapeamento da sub-rede.</span><span class="sxs-lookup"><span data-stu-id="6413a-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="6413a-137">Preencha as tabelas de mapeamento de rede e criação no banco de dados de arquivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="6413a-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="6413a-138">Uma conta com acesso de gravação ao banco de dados de arquivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="6413a-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="6413a-139">Seção "fornecendo informações de sub-rede" na documentação do usuário.</span><span class="sxs-lookup"><span data-stu-id="6413a-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="6413a-140">A implantação do painel de qualidade de chamada envolve a configuração da infraestrutura e a instalação do software.</span><span class="sxs-lookup"><span data-stu-id="6413a-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="6413a-141">O procedimento a seguir descreve o processo.</span><span class="sxs-lookup"><span data-stu-id="6413a-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="6413a-142">Etapas de implantação</span><span class="sxs-lookup"><span data-stu-id="6413a-142">Deployment Steps</span></span>

1. <span data-ttu-id="6413a-143">Copie o CallQualityDashboard. msi para a máquina onde o componente de banco de dados de arquivamento do CQD deve ser instalado (esta é a máquina que tem o SQL Server instalado).</span><span class="sxs-lookup"><span data-stu-id="6413a-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="6413a-144">Execute o MSI (o Windows solicitará a execução com o privilégio de administrador, faça isso).</span><span class="sxs-lookup"><span data-stu-id="6413a-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="6413a-145">Aceite o EULA.</span><span class="sxs-lookup"><span data-stu-id="6413a-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="6413a-146">Selecione a pasta de destino onde os arquivos relacionados a componentes de painel de qualidade de chamada serão localizados ou aceite o local padrão.</span><span class="sxs-lookup"><span data-stu-id="6413a-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="6413a-147">Selecione todos os recursos.</span><span class="sxs-lookup"><span data-stu-id="6413a-147">Select all features.</span></span>
    
6. <span data-ttu-id="6413a-148">Na página configuração de arquivo de QoE, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6413a-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="6413a-149">**Métricas de QoE SQL Server:** Nome da instância do SQL Server para onde o banco de dados de métricas de QoE está localizado (será a fonte de dados).</span><span class="sxs-lookup"><span data-stu-id="6413a-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="6413a-150">**Arquivo de QoE nome do servidor SQL:** Este é um campo somente leitura e é corrigido para o nome de domínio totalmente qualificado do computador local.</span><span class="sxs-lookup"><span data-stu-id="6413a-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="6413a-151">O banco de arquivo DB só pode ser instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="6413a-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="6413a-152">**Arquivo de QoE instância do SQL Server:** Um nome de instância local do SQL Server para onde o DB de arquivo morto deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="6413a-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="6413a-153">Para usar uma instância padrão do SQL Server, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="6413a-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="6413a-154">Para usar uma instância nomeada do SQL Server, especifique o nome da instância (por exemplo, o nome\"após ").</span><span class="sxs-lookup"><span data-stu-id="6413a-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="6413a-155">**Banco de dados de arquivo de QoE:** Por padrão, essa opção é definida como "criar novo banco de dados".</span><span class="sxs-lookup"><span data-stu-id="6413a-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="6413a-156">Como a atualização do banco de dados de arquivo morto não é suportada, a única circunstância sob a qual a opção "usar banco de dados existente" pode ser usada é se o banco de dados de arquivo morto existente tiver o mesmo esquema que a compilação a ser instalada.</span><span class="sxs-lookup"><span data-stu-id="6413a-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="6413a-157">**Diretório de arquivos do banco de dados:** Caminho onde os arquivos de banco de dados (. MDF e. ldf) para o banco de dados de arquivo morto devem ser colocados.</span><span class="sxs-lookup"><span data-stu-id="6413a-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="6413a-158">Ele deve estar em uma unidade (HDD2 na configuração de hardware recomendada) separada do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="6413a-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="6413a-159">Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.</span><span class="sxs-lookup"><span data-stu-id="6413a-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="6413a-160">**Use várias partições:** O padrão é definido como "várias partições", que requer o Business Intelligence Edition ou Enterprise Edition do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6413a-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="6413a-161">Para Standard Edition, selecione a opção "partição única".</span><span class="sxs-lookup"><span data-stu-id="6413a-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="6413a-162">Observe que o desempenho do processamento do cubo pode ser afetado se uma única partição for usada.</span><span class="sxs-lookup"><span data-stu-id="6413a-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6413a-163">A opção seleção para usar várias partições não pode ser alterada após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="6413a-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="6413a-164">Para alterá-la, o recurso de cubo precisa ser primeiro desinstalado e, em seguida, reinstalado usando a opção "alterar" no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="6413a-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="6413a-165">**Diretório de arquivos de partição:** Caminho onde as partições para o banco de dados de arquivo de QoE devem ser colocadas.</span><span class="sxs-lookup"><span data-stu-id="6413a-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="6413a-166">Ele deve estar em uma unidade (HDD3 na configuração de hardware recomendada) separada da unidade do sistema operacional e da unidade de arquivos de log do banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="6413a-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="6413a-167">Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.</span><span class="sxs-lookup"><span data-stu-id="6413a-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="6413a-168">**Nome &amp; de usuário do trabalho do SQL Agent-senha:** Nome e senha da conta de serviço de domínio (mascarado) que serão usados para executar a etapa "dados de arquivo de QoE" do trabalho do SQL Server Agent (que executará o procedimento armazenado para buscar dados do banco de dados de métricas de QoE no banco de dados de arquivo morto, portanto, essa conta deverá ter acesso de leitura ao banco de dados de métricas de QoE, conforme</span><span class="sxs-lookup"><span data-stu-id="6413a-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="6413a-169">Essa conta também precisa ter um logon na instância do SQL Server de arquivo de QoE).</span><span class="sxs-lookup"><span data-stu-id="6413a-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="6413a-170">A conta sob a qual a instância do SQL Server está sendo executada, como NT SERVICE\MSSQLSERVER, deve ter acesso/permissão aos diretórios acima para que a instalação seja bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6413a-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="6413a-171">Para obter detalhes, consulte [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="6413a-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="6413a-172">Ao clicar em avançar, o instalador executará verificações de pré-requisitos e relatará se algum problema for encontrado.</span><span class="sxs-lookup"><span data-stu-id="6413a-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="6413a-173">Quando as verificações de pré-requisitos passam, o instalador vai para a página de configuração do cubo.</span><span class="sxs-lookup"><span data-stu-id="6413a-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6413a-174">Se o instalador mostrar uma mensagem de aviso informando que o serviço do SQL Server Agent para o arquivo de QoE instância do SQL Server não está em execução, a instalação pode continuar, mas após a instalação, verifique se o serviço do SQL Agent está em execução e defina o tipo de inicialização como Automático para que o trabalho agendado seja executado.</span><span class="sxs-lookup"><span data-stu-id="6413a-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="6413a-175">Na página configuração de cubo, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6413a-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="6413a-176">**Arquivo de QoE nome do servidor SQL:** Este é um campo somente leitura e é corrigido para o nome de domínio totalmente qualificado do computador local.</span><span class="sxs-lookup"><span data-stu-id="6413a-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="6413a-177">O cubo pode ser instalado apenas da máquina que tem um banco de dados de arquivo de QoE (observação.</span><span class="sxs-lookup"><span data-stu-id="6413a-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="6413a-178">O próprio cubo pode ser instalado em uma máquina remota.</span><span class="sxs-lookup"><span data-stu-id="6413a-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="6413a-179">Veja abaixo)</span><span class="sxs-lookup"><span data-stu-id="6413a-179">See below)</span></span>
    
   - <span data-ttu-id="6413a-180">**Arquivo de QoE instância do SQL Server:** Nome da instância do SQL Server para onde o DB de arquivo de QoE está localizado.</span><span class="sxs-lookup"><span data-stu-id="6413a-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="6413a-181">Para especificar uma instância padrão do SQL Server, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="6413a-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="6413a-182">Para especificar uma instância nomeada do SQL Server, digite o nome da instância (por exemplo, o nome\"após ").</span><span class="sxs-lookup"><span data-stu-id="6413a-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="6413a-183">Se o componente de arquivo de QoE foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de arquivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="6413a-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="6413a-184">**Servidor de análise de cubo:** Nome da instância do serviço de análise do SQL Server para onde o cubo deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="6413a-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="6413a-185">Pode ser uma máquina diferente, mas o usuário de instalação precisa ser membro dos administradores de servidor da instância do serviço de análise de destino do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6413a-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="6413a-186">Para obter mais informações sobre como configurar permissões de administrador de servidor do Analysis Services, consulte [Grant Server Administrative Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="6413a-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="6413a-187">**Use várias partições:** O padrão é definido como "várias partições", que requer o Business Intelligence Edition ou Enterprise Edition do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6413a-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="6413a-188">Para Standard Edition, selecione a opção "partição única".</span><span class="sxs-lookup"><span data-stu-id="6413a-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="6413a-189">Observe que o desempenho do processamento do cubo pode ser afetado se uma única partição for usada.</span><span class="sxs-lookup"><span data-stu-id="6413a-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="6413a-190">A opção seleção para usar várias partições não pode ser alterada após a conclusão da instalação.</span><span class="sxs-lookup"><span data-stu-id="6413a-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="6413a-191">Para alterá-la, o recurso de cubo precisa ser primeiro desinstalado e, em seguida, reinstalado usando a opção "alterar" no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="6413a-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="6413a-192">**Usuário de cubo-senha &amp; de nome de usuário:** Nome e senha da conta de serviço de domínio (mascarado) que dispararão o processamento de cubo.</span><span class="sxs-lookup"><span data-stu-id="6413a-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="6413a-193">Se o componente de arquivo de QoE foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de arquivo morto para o usuário de trabalho do SQL Agent, mas recomendamos especificar uma conta de serviço de domínio diferente para que a instalação possa conceder a privilégio menos necessário para ele.</span><span class="sxs-lookup"><span data-stu-id="6413a-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="6413a-194">Ao clicar em avançar, uma nova rodada de validação será executada e qualquer problema será relatado.</span><span class="sxs-lookup"><span data-stu-id="6413a-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="6413a-195">Após a conclusão bem-sucedida da validação, o instalador vai para a página de configuração do Portal.</span><span class="sxs-lookup"><span data-stu-id="6413a-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="6413a-196">Na página configuração do portal, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6413a-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="6413a-197">**Arquivo de QoE do SQL Server:** Nome da instância do SQL Server para onde o banco de dados de arquivo de QoE está localizado.</span><span class="sxs-lookup"><span data-stu-id="6413a-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="6413a-198">Observe que, diferentemente da página de configuração de arquivo de QoE e da página de configuração de cubo, o nome do computador não é corrigido e deve ser fornecido.</span><span class="sxs-lookup"><span data-stu-id="6413a-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="6413a-199">Se o componente de arquivo de QoE foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de arquivo de QoE.</span><span class="sxs-lookup"><span data-stu-id="6413a-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="6413a-200">**Servidor de análise de cubo:** Nome da instância do serviço de análise do SQL Server para onde o cubo está localizado.</span><span class="sxs-lookup"><span data-stu-id="6413a-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="6413a-201">Se o componente de cubo foi selecionado para a instalação, este campo será preenchido previamente com o valor fornecido na página configuração de cubo.</span><span class="sxs-lookup"><span data-stu-id="6413a-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="6413a-202">**SQL Server do repositório:** Nome da instância do SQL Server onde o banco de dados do repositório deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="6413a-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="6413a-203">Se o nome da instância do SQL Server para onde o banco de dados de arquivo de QoE está localizado tiver sido fornecido anteriormente na configuração (em outros componentes), esse campo será preenchido previamente com o nome da instância do SQL Server do banco de dados do servidor da QoE.</span><span class="sxs-lookup"><span data-stu-id="6413a-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="6413a-204">Pode ser qualquer instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6413a-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="6413a-205">**Banco de dados de repositório:** Por padrão, a opção é definida como "criar novo banco de dados".</span><span class="sxs-lookup"><span data-stu-id="6413a-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="6413a-206">Como a atualização do banco de dados de repositório não é suportada, a única circunstância sob a qual a opção "usar banco de dados existente" pode ser usada se o banco de dados do repositório existente tiver o mesmo esquema que a compilação a ser instalada.</span><span class="sxs-lookup"><span data-stu-id="6413a-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="6413a-207">**Usuário do pool de aplicativos do IIS &amp; senha do nome de usuário:** A conta na qual o pool de aplicativos do IIS deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="6413a-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="6413a-208">Os campos nome de usuário e senha serão esmaecidos se as contas de sistema internas estiverem selecionadas.</span><span class="sxs-lookup"><span data-stu-id="6413a-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="6413a-209">Esses campos só serão habilitados se "outros" estiver selecionado na caixa suspensa para que o usuário possa inserir as informações da conta de serviço de domínio.</span><span class="sxs-lookup"><span data-stu-id="6413a-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="6413a-210">Ao clicar em avançar, a última rodada de validação será feita para garantir que as instâncias do SQL Server sejam acessíveis usando as credenciais fornecidas e que o IIS esteja disponível no computador.</span><span class="sxs-lookup"><span data-stu-id="6413a-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="6413a-211">Após a conclusão bem-sucedida da validação, o instalador prosseguirá com a configuração.</span><span class="sxs-lookup"><span data-stu-id="6413a-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="6413a-212">Quando o instalador estiver concluído, provavelmente o trabalho do SQL Server Agent estará em andamento, realizando a carga inicial dos dados de QoE e o processamento de cubos.</span><span class="sxs-lookup"><span data-stu-id="6413a-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="6413a-213">Dependendo da quantidade de dados no QoE, o portal ainda não terá dados disponíveis para exibição.</span><span class="sxs-lookup"><span data-stu-id="6413a-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="6413a-214">Para verificar o status da carga de dados e processamento de cubo, acesse `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="6413a-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="6413a-215">Observe que a URL para verificar o status do processamento do cubo de download diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6413a-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="6413a-216">Se você digitar "saúde", a URL não funcionará.</span><span class="sxs-lookup"><span data-stu-id="6413a-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="6413a-217">Você deve inserir "Health" no final da URL com um H maiúsculo.</span><span class="sxs-lookup"><span data-stu-id="6413a-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="6413a-218">As mensagens de log detalhadas serão mostradas se o modo de depuração estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="6413a-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="6413a-219">Para habilitar o modo de depuração, vá para **%systemdrive%\Arquivos de Files\Skype para negócios 2015 CQD\QoEDataService\web.config**e atualize a linha a seguir para que o valor seja definido como **true**:</span><span class="sxs-lookup"><span data-stu-id="6413a-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="6413a-220">A página do portal principal é acessível `http://<machinename>/CQD`via.</span><span class="sxs-lookup"><span data-stu-id="6413a-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="6413a-221">Gerenciando o acesso do usuário ao portal</span><span class="sxs-lookup"><span data-stu-id="6413a-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="6413a-222">Para gerenciar a autorização do usuário no portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="6413a-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="6413a-223">Para obter mais informações sobre a segurança do IIS, consulte [Understanding iis 7,0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="6413a-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="6413a-224">Qualquer site ou aplicativo da Web herdará a autorização de URL padrão configurada para todo o IIS, que normalmente é "permitir todos os usuários".</span><span class="sxs-lookup"><span data-stu-id="6413a-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="6413a-225">Se o acesso ao portal precisar ser mais restritivo, os administradores podem conceder acesso apenas ao grupo específico de usuários editando as "regras de autorização".</span><span class="sxs-lookup"><span data-stu-id="6413a-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Implantar regras de autorização de qualidade de chamada no IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="6413a-227">O ícone de regras de autorização não deve ser confundido com a "autorização .NET" na seção ASP.NET, que é um mecanismo de autorização diferente.</span><span class="sxs-lookup"><span data-stu-id="6413a-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="6413a-228">Os administradores devem primeiro remover a regra herdada "permitir todos os usuários".</span><span class="sxs-lookup"><span data-stu-id="6413a-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="6413a-229">Isso impede que usuários não autorizados acessem o Portal.</span><span class="sxs-lookup"><span data-stu-id="6413a-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Implantar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="6413a-231">Em seguida, os administradores devem adicionar novas regras de permissão e conceder aos usuários específicos a permissão para acessar o Portal.</span><span class="sxs-lookup"><span data-stu-id="6413a-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="6413a-232">É recomendável que um grupo local chamado "CQDPortalUsers" seja criado para gerenciar os usuários.</span><span class="sxs-lookup"><span data-stu-id="6413a-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Implantar painel de qualidade de chamada](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="6413a-234">Os detalhes de configuração são armazenados no Web. config localizado no diretório físico do Portal.</span><span class="sxs-lookup"><span data-stu-id="6413a-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="6413a-235">A próxima etapa é configurar o painel do CQD.</span><span class="sxs-lookup"><span data-stu-id="6413a-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="6413a-236">Depois que os usuários são autenticados pelo IIS, eles precisarão ter permissões de arquivo no diretório CQD para acessar o conteúdo do portal da Web.</span><span class="sxs-lookup"><span data-stu-id="6413a-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="6413a-237">É possível alterar as ACLs por meio da guia Segurança das propriedades do diretório CQD para adicionar usuários individuais ou grupos; no entanto, a abordagem recomendada é deixar as permissões de arquivo inalteradas.</span><span class="sxs-lookup"><span data-stu-id="6413a-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="6413a-238">Em vez disso, altere a configuração do IIS para usar o processo de trabalho do IIS para acessar o diretório CQD, independentemente de qual usuário é autenticado.</span><span class="sxs-lookup"><span data-stu-id="6413a-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6413a-239">É importante apenas alterar essa configuração para o aplicativo CQD e não para os dois aplicativos de API: QoEDataService e QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="6413a-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="6413a-240">Configurando o acesso a arquivos para o CQD (painel)</span><span class="sxs-lookup"><span data-stu-id="6413a-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="6413a-241">Abra o editor de configuração do CQD.</span><span class="sxs-lookup"><span data-stu-id="6413a-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Implantar painel de qualidade de chamada](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="6413a-243">Em seção, escolha **System. WebServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="6413a-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Implantar painel de qualidade de chamada](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="6413a-245">Altere authenticatedUserOverride para **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="6413a-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Implantar painel de qualidade da chamada-editor de configuração](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="6413a-247">Clique em **aplicar** no lado direito da página.</span><span class="sxs-lookup"><span data-stu-id="6413a-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="6413a-248">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="6413a-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="6413a-249">O CQD não mostra dados após a implantação</span><span class="sxs-lookup"><span data-stu-id="6413a-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="6413a-250">Você pode receber o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="6413a-250">You may receive the following error:</span></span>

<span data-ttu-id="6413a-251">*Não foi possível executar a consulta ao executá-la no cubo. Use o editor de consultas para modificar a consulta e corrigir problemas. Além disso, certifique-se de que o cubo está acessível.*</span><span class="sxs-lookup"><span data-stu-id="6413a-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="6413a-252">Isso significa que o cubo deve ser processado no SQL Server Analysis Services antes de ser usado no CQD.</span><span class="sxs-lookup"><span data-stu-id="6413a-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="6413a-253">É possível resolver isso, seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6413a-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="6413a-254">Abra o SQL Management Studio e selecione o **Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="6413a-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="6413a-255">Expanda o objeto **QoECube** , selecione **métrica de QoE**, clique com o botão direito do mouse e escolha **procurar**.</span><span class="sxs-lookup"><span data-stu-id="6413a-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="6413a-256">Se isso retornar um navegador vazio, o cubo ainda não foi continuado.</span><span class="sxs-lookup"><span data-stu-id="6413a-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="6413a-257">Clique com o botão direito do mouse em **QoE métrico** e escolha **processo**.</span><span class="sxs-lookup"><span data-stu-id="6413a-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="6413a-258">Quando o processamento estiver concluído, clique com o botão direito do mouse novamente no objeto e escolha **procurar** para confirmar que a página do navegador agora mostra os dados.</span><span class="sxs-lookup"><span data-stu-id="6413a-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="6413a-259">Os usuários têm problemas para fazer logon porque o instalador não cria as configurações corretas no IIS</span><span class="sxs-lookup"><span data-stu-id="6413a-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="6413a-260">Em casos raros, o instalador não cria as configurações corretas no IIS.</span><span class="sxs-lookup"><span data-stu-id="6413a-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="6413a-261">A alteração manual é necessária para permitir que os usuários façam logon no CQD.</span><span class="sxs-lookup"><span data-stu-id="6413a-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="6413a-262">Se os usuários estiverem tendo problemas para fazer logon, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="6413a-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="6413a-263">Abra o Gerenciador do IIS e navegue até o site da Web padrão.</span><span class="sxs-lookup"><span data-stu-id="6413a-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Implantar painel de qualidade de chamada](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="6413a-265">Clique em "autenticação".</span><span class="sxs-lookup"><span data-stu-id="6413a-265">Click on "Authentication".</span></span> <span data-ttu-id="6413a-266">Se a "autenticação anônima", "representação de ASP.NET", "autenticação de formulário" e "autenticação do Windows" não corresponder às configurações mostradas abaixo, altere-as manualmente para que correspondam às configurações abaixo.</span><span class="sxs-lookup"><span data-stu-id="6413a-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="6413a-267">Todos os outros mecanismos de autenticação devem ser desabilitados.</span><span class="sxs-lookup"><span data-stu-id="6413a-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Implantar painel de qualidade de chamada](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="6413a-269">Em "autenticação do Windows", clique em configurações avançadas no lado direito.</span><span class="sxs-lookup"><span data-stu-id="6413a-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Implantar painel de qualidade de chamada](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="6413a-271">Defina "proteção estendida" para aceitar e marcar a caixa "habilitar autenticação de modo kernel".</span><span class="sxs-lookup"><span data-stu-id="6413a-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Implantar painel de qualidade de chamada](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="6413a-273">Repita as etapas acima para cada uma das entradas "CQD", "QoEDataService" e "QoERepositoryService", abaixo de "Default Web site".</span><span class="sxs-lookup"><span data-stu-id="6413a-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="6413a-274">Para associações de porta HTTP e HTTPS, o instalador criará associações de porta nos números de porta padrão (porta 80 para HTTP e porta 443 para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="6413a-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="6413a-275">Se houver outro site na máquina que usa essas associações, haverá um conflito e o comportamento do IIS não poderá ser previsto.</span><span class="sxs-lookup"><span data-stu-id="6413a-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="6413a-276">A melhor maneira de evitar esse problema é certificar-se de que nenhum outro site esteja mapeado para as portas 80 e 443 antes da instalação do CQD.</span><span class="sxs-lookup"><span data-stu-id="6413a-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="6413a-277">Para habilitar o SSL/TLS no IIS e forçar os usuários a se conectar via HTTPS seguro em vez de HTTP:</span><span class="sxs-lookup"><span data-stu-id="6413a-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="6413a-278">Configure Secure Sockets Layer no IIS, consulte [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="6413a-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="6413a-279">Após concluir, substitua `http` por `https`.</span><span class="sxs-lookup"><span data-stu-id="6413a-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="6413a-280">Para instruções sobre como habilitar o TLS nas conexões do SQL Server, confira [como habilitar a criptografia SSL para uma instância do SQL Server usando o console de gerenciamento Microsoft](https://support.microsoft.com/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="6413a-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="6413a-281">Falha na sincronização do cubo</span><span class="sxs-lookup"><span data-stu-id="6413a-281">Cube Sync Fails</span></span>

<span data-ttu-id="6413a-282">O QoEMetrics pode conter alguns registros inválidos com base nos relógios dos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="6413a-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="6413a-283">Se a diferença de tempo for maior que 60 yrs, a importação de cubo falhará.</span><span class="sxs-lookup"><span data-stu-id="6413a-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="6413a-284">Verifique o min e o Max StartTime/EndTime usando as seleções abaixo.</span><span class="sxs-lookup"><span data-stu-id="6413a-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="6413a-285">Procure e exclua os registros distantes e distantes no futuro, eles podem ser desconsiderados e quebrar os processos de sincronização.</span><span class="sxs-lookup"><span data-stu-id="6413a-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="6413a-286">Selecione mín (início) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6413a-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="6413a-287">Selecione MAX (StartTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6413a-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="6413a-288">Selecione mín (EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6413a-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="6413a-289">Selecione máximo (EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="6413a-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="6413a-290">Tarefas pós-instalação</span><span class="sxs-lookup"><span data-stu-id="6413a-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="6413a-291">Importando edifícios e redes</span><span class="sxs-lookup"><span data-stu-id="6413a-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="6413a-292">Após instalar o CQD, execute as seguintes tarefas de configuração:</span><span class="sxs-lookup"><span data-stu-id="6413a-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="6413a-293">Definir tipos de construção (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6413a-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="6413a-294">Definir tipos de propriedade de criação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6413a-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="6413a-295">Definir tipos de rede (altamente recomendado)</span><span class="sxs-lookup"><span data-stu-id="6413a-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="6413a-296">Edifícios de importação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6413a-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="6413a-297">Importar sub-redes (recomendado)</span><span class="sxs-lookup"><span data-stu-id="6413a-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="6413a-298">Definir tipos de construção</span><span class="sxs-lookup"><span data-stu-id="6413a-298">Define Building Types</span></span>

<span data-ttu-id="6413a-299">Os tipos de construção são usados para descrever as diferentes definições de prédios ou tipos dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6413a-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6413a-300">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="6413a-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="6413a-301">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6413a-301">Examples</span></span>
  
- <span data-ttu-id="6413a-302">Sede</span><span class="sxs-lookup"><span data-stu-id="6413a-302">Headquarters</span></span>
    
- <span data-ttu-id="6413a-303">Escritórios remotos</span><span class="sxs-lookup"><span data-stu-id="6413a-303">Remote Office</span></span>
    
- <span data-ttu-id="6413a-304">Localização de joint venture</span><span class="sxs-lookup"><span data-stu-id="6413a-304">Joint-venture location</span></span>
    
  <span data-ttu-id="6413a-305">**Exemplo de sintaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="6413a-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="6413a-306">Os parâmetros BuildingTypeId e BuildingTypeDesc são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="6413a-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="6413a-307">Definir tipos de propriedade de criação</span><span class="sxs-lookup"><span data-stu-id="6413a-307">Define Building Ownership Types</span></span>

<span data-ttu-id="6413a-308">Os tipos de propriedade são usados para distinguir ativos de propriedade vs alugados.</span><span class="sxs-lookup"><span data-stu-id="6413a-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6413a-309">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="6413a-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="6413a-310">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6413a-310">Examples</span></span>
  
- <span data-ttu-id="6413a-311">Não-Redirecionado&amp;F concedido da contoso</span><span class="sxs-lookup"><span data-stu-id="6413a-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="6413a-312">Da Contoso concedido RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="6413a-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="6413a-313">Propriedade da contoso</span><span class="sxs-lookup"><span data-stu-id="6413a-313">Contoso Owned</span></span>
    
- <span data-ttu-id="6413a-314">Subsidiária alugada</span><span class="sxs-lookup"><span data-stu-id="6413a-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="6413a-315">**Exemplo de sintaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="6413a-315">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc]
)

VALUES
(1,
'Contoso Owned'
)
```

<span data-ttu-id="6413a-316">Os parâmetros OwnershipTypeId e OwnershipTypeDesc são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="6413a-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="6413a-317">Definir nomes de rede</span><span class="sxs-lookup"><span data-stu-id="6413a-317">Define Network Names</span></span>

<span data-ttu-id="6413a-318">Os tipos de rede são usados para descrever diferentes tipos de redes dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="6413a-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="6413a-319">Isso dá a você a capacidade de filtrar (ou filtrar) tipos de rede específicos.</span><span class="sxs-lookup"><span data-stu-id="6413a-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6413a-320">É altamente recomendável definir nomes de rede, mas é opcional.</span><span class="sxs-lookup"><span data-stu-id="6413a-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="6413a-321">Se você decidir não definir nomes de rede, certifique-se de que cada entrada CqdNetwork tenha um Buildingid de 0.</span><span class="sxs-lookup"><span data-stu-id="6413a-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="6413a-322">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6413a-322">Examples</span></span>
  
- <span data-ttu-id="6413a-323">VPN</span><span class="sxs-lookup"><span data-stu-id="6413a-323">VPN</span></span>
    
- <span data-ttu-id="6413a-324">Labs</span><span class="sxs-lookup"><span data-stu-id="6413a-324">LAB</span></span>
    
  <span data-ttu-id="6413a-325">**Exemplo de sintaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="6413a-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="6413a-326">Os parâmetros NetworkNameID e NetworkName são necessários, o parâmetro NetworkType é opcional, mas recomendado.</span><span class="sxs-lookup"><span data-stu-id="6413a-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="6413a-327">Edifícios de importação</span><span class="sxs-lookup"><span data-stu-id="6413a-327">Import Buildings</span></span>

<span data-ttu-id="6413a-328">A importação de edifícios oferece a capacidade de criar insights específicos (chamadas ruins por prédio em WiFi/Wired, etc.).</span><span class="sxs-lookup"><span data-stu-id="6413a-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6413a-329">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="6413a-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="6413a-330">Antes de importar um novo edifício, você já deve ter um BuildingKey predefinido identificado.</span><span class="sxs-lookup"><span data-stu-id="6413a-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="6413a-331">Para fazer isso, emita o comando "SELECT MAX (BuildingKey) FROM CqdBuilding" para identificar o valor atual e adicionar 1 ao resultado.</span><span class="sxs-lookup"><span data-stu-id="6413a-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="6413a-332">**Exemplo de sintaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="6413a-332">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBuilding] 
( [BuildingKey]
,[BuildingName]
,[BuildingShortName]
,[OwnershipTypeId],
[BuildingTypeId]
)
VALUES
(2, 'Ann Arbor', 'AA', 0, 0)
```

<span data-ttu-id="6413a-333">Os parâmetros BuildingKey, Buildingname, BuildingShortName, OwnershipTypeId, BuildingTypeId são obrigatórios, os outros parâmetros são opcionais.</span><span class="sxs-lookup"><span data-stu-id="6413a-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="6413a-334">Importar sub-redes</span><span class="sxs-lookup"><span data-stu-id="6413a-334">Import Subnets</span></span>

<span data-ttu-id="6413a-335">A importação de edifícios oferece a capacidade de criar insights específicos (chamadas ruins por prédio em WiFi/Wired, etc.).</span><span class="sxs-lookup"><span data-stu-id="6413a-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6413a-336">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="6413a-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="6413a-337">Importe sub-redes e mapeie-as para os edifícios importados na última etapa.</span><span class="sxs-lookup"><span data-stu-id="6413a-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="6413a-338">Se você optou por não preencher o NetworkName, certifique-se de que cada entrada desta tabela use um NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="6413a-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="6413a-339">Para obter mais informações sobre sintaxe e parâmetros SQL para o painel de qualidade da chamada, consulte [use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span><span class="sxs-lookup"><span data-stu-id="6413a-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="6413a-340">**Exemplo de sintaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="6413a-340">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkRange]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',32,0,1,'2015-11-11')
```

<span data-ttu-id="6413a-341">A rede e os parâmetros UpdatedDate são necessários, os outros parâmetros são opcionais.</span><span class="sxs-lookup"><span data-stu-id="6413a-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="6413a-342">Opcional: BSSID</span><span class="sxs-lookup"><span data-stu-id="6413a-342">Optional: BSSID</span></span>

<span data-ttu-id="6413a-343">O preenchimento de informações de BSSID fornece correlação de fluxo de WiFi adicional por controlador ou rádio.</span><span class="sxs-lookup"><span data-stu-id="6413a-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="6413a-344">Isso é uma adição à filtragem por compilação ou sub-rede.</span><span class="sxs-lookup"><span data-stu-id="6413a-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="6413a-345">**Exemplo de sintaxe SQL**</span><span class="sxs-lookup"><span data-stu-id="6413a-345">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdBssid]
([Ap],
[Bss],
[Building],
[ess],
[phy]
)
VALUES
('AP1','00-00-00-00-00-00','Aruba AP 1','Controller1','bgn')
```

<span data-ttu-id="6413a-346">**Detalhes do CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="6413a-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="6413a-347">**Conforme mostrado no CQD**</span><span class="sxs-lookup"><span data-stu-id="6413a-347">**As shown in CQD**</span></span>|<span data-ttu-id="6413a-348">**Tabela CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="6413a-348">**CQDBssid Table**</span></span>|<span data-ttu-id="6413a-349">**Exemplos de entradas**</span><span class="sxs-lookup"><span data-stu-id="6413a-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6413a-350">AP NName</span><span class="sxs-lookup"><span data-stu-id="6413a-350">Ap NName</span></span>  <br/> |<span data-ttu-id="6413a-351">APS</span><span class="sxs-lookup"><span data-stu-id="6413a-351">AP</span></span>  <br/> |<span data-ttu-id="6413a-352">AP1</span><span class="sxs-lookup"><span data-stu-id="6413a-352">AP1</span></span>  <br/> |
|<span data-ttu-id="6413a-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="6413a-353">BBssid</span></span>  <br/> |<span data-ttu-id="6413a-354">BBS</span><span class="sxs-lookup"><span data-stu-id="6413a-354">BSS</span></span>  <br/> |<span data-ttu-id="6413a-355">00-00-00-00-00-00 (você deve usar o fformat delimitado)</span><span class="sxs-lookup"><span data-stu-id="6413a-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="6413a-356">Controlador</span><span class="sxs-lookup"><span data-stu-id="6413a-356">Controller</span></span>  <br/> |<span data-ttu-id="6413a-357">Build</span><span class="sxs-lookup"><span data-stu-id="6413a-357">Building</span></span>  <br/> |<span data-ttu-id="6413a-358">Ponto de acesso 7 de Aruba</span><span class="sxs-lookup"><span data-stu-id="6413a-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="6413a-359">Device</span><span class="sxs-lookup"><span data-stu-id="6413a-359">Device</span></span>  <br/> |<span data-ttu-id="6413a-360">ESS</span><span class="sxs-lookup"><span data-stu-id="6413a-360">ess</span></span>  <br/> |<span data-ttu-id="6413a-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="6413a-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="6413a-362">Radio</span><span class="sxs-lookup"><span data-stu-id="6413a-362">Radio</span></span>  <br/> |<span data-ttu-id="6413a-363">PHY</span><span class="sxs-lookup"><span data-stu-id="6413a-363">phy</span></span>  <br/> |<span data-ttu-id="6413a-364">bgn</span><span class="sxs-lookup"><span data-stu-id="6413a-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="6413a-365">Processamento dos dados importados</span><span class="sxs-lookup"><span data-stu-id="6413a-365">Processing the imported data</span></span>

<span data-ttu-id="6413a-366">Por padrão, depois que você importa dados de construção/rede, ele só se aplica aos registros gerados após esse momento determinado.</span><span class="sxs-lookup"><span data-stu-id="6413a-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="6413a-367">Para marcar todos os registros anteriores com esses novos dados, você precisará executar o procedimento armazenado CqdUpdateBuilding, conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="6413a-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="6413a-368">Dê a ela a data do primeiro registro (identifique que usando o comando SELECT MIN (StartTime) do CqdPartitionedStreamView SQL), um EndDate de amanhã, então nulo para os dois últimos valores.</span><span class="sxs-lookup"><span data-stu-id="6413a-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="6413a-369">Depois que os dados são associados aos dados de fluxo, o cubo do SSIS precisa reprocessar todos os registros.</span><span class="sxs-lookup"><span data-stu-id="6413a-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="6413a-370">Isso também se aplica ao acréscimo de dados de BSSID/ISP em massa.</span><span class="sxs-lookup"><span data-stu-id="6413a-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="6413a-371">Assegure-se de que "processo completo" esteja selecionado.</span><span class="sxs-lookup"><span data-stu-id="6413a-371">Ensure that "Process Full" is selected.</span></span>
  

