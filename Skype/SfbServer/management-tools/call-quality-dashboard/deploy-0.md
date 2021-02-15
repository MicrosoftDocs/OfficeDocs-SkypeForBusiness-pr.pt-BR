---
title: Implantar o Painel de Qualidade da Chamada para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumo: saiba mais sobre o processo de implantação do Painel de Qualidade da Chamada. O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.'
ms.openlocfilehash: 797288428530a055987d8b0a8e1ebf6a9e8b9dcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832711"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="1596f-104">Implantar o Painel de Qualidade da Chamada para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1596f-104">Deploy Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="1596f-105">**Resumo:** Saiba mais sobre o processo de implantação do Painel de Qualidade da Chamada.</span><span class="sxs-lookup"><span data-stu-id="1596f-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="1596f-106">O Painel de Qualidade da Chamada é uma ferramenta do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1596f-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="1596f-107">Visão geral da implantação</span><span class="sxs-lookup"><span data-stu-id="1596f-107">Deployment Overview</span></span>

<span data-ttu-id="1596f-108">O Painel de Qualidade da Chamada (CQD) consiste em três componentes principais:</span><span class="sxs-lookup"><span data-stu-id="1596f-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="1596f-109">**Banco de Dados** de Arquivo Morto, onde os dados de QoE (Qualidade da Experiência) são replicados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="1596f-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="1596f-110">**Cubo**, onde os dados do banco de dados de Arquivo QoE são agregados para acesso otimizado e rápido.</span><span class="sxs-lookup"><span data-stu-id="1596f-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="1596f-111">**Portal**, onde os usuários podem facilmente consultar e visualizar dados de QoE.</span><span class="sxs-lookup"><span data-stu-id="1596f-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Componentes CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="1596f-113">O processo de instalação do Arquivamento de QoE envolve a criação do banco de dados de Arquivo QoE, a implantação de um procedimento armazenado do SQL Server que move os dados do banco de dados de Métricas de QoE de origem para o banco de dados de Arquivo Morto QoE e a configuração do trabalho do SQL Server Agent para executar o procedimento armazenado em um intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="1596f-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="1596f-114">A implantação de cubo obtém informações do usuário sobre onde o Arquivo de QoE está localizado, implanta o cubo e configura um trabalho de agente regular do SQL Server que atualizará o cubo em um intervalo regular.</span><span class="sxs-lookup"><span data-stu-id="1596f-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="1596f-115">A instalação do portal cria um banco de dados de Repositório que armazena o mapeamento de usuários do CQD para relatórios/consultas de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="1596f-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="1596f-116">Em seguida, ele configura um aplicativo Web do IIS, que é o painel onde os usuários podem ver um conjunto pré-definido de relatórios, bem como personalizar e criar suas próprias consultas para visualizar dados do cubo.</span><span class="sxs-lookup"><span data-stu-id="1596f-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="1596f-117">A instalação do portal cria dois aplicativos Web adicionais que expõem APIs para que os usuários acessem programaticamente o repositório e o cubo.</span><span class="sxs-lookup"><span data-stu-id="1596f-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="1596f-118">(Essas APIs também são usadas internamente pelo painel.)</span><span class="sxs-lookup"><span data-stu-id="1596f-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="1596f-119">**Fase**</span><span class="sxs-lookup"><span data-stu-id="1596f-119">**Phase**</span></span>|<span data-ttu-id="1596f-120">**Etapas**</span><span class="sxs-lookup"><span data-stu-id="1596f-120">**Steps**</span></span>|<span data-ttu-id="1596f-121">**Funções e associação de grupo**</span><span class="sxs-lookup"><span data-stu-id="1596f-121">**Roles and group membership**</span></span>|<span data-ttu-id="1596f-122">**Documentação**</span><span class="sxs-lookup"><span data-stu-id="1596f-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1596f-123">Instale o hardware e o software de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="1596f-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="1596f-124">Decida sobre a configuração do CQD e escolha um SQL Server do qual executar a instalação.</span><span class="sxs-lookup"><span data-stu-id="1596f-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="1596f-125">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="1596f-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="1596f-126">Seção "Requisitos de pré-instalação" na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1596f-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="1596f-127">Instale o CQD.</span><span class="sxs-lookup"><span data-stu-id="1596f-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="1596f-128">Execute o MSI após o documento de implantação.</span><span class="sxs-lookup"><span data-stu-id="1596f-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="1596f-129">Para executar a configuração, a conta de instalação deve ser um usuário de domínio que seja membro do grupo de administradores locais e tenha acesso de leitura ao banco de dados de Métricas de QoE no Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="1596f-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="1596f-130">Seções "Contas e Etapas de Implantação" na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1596f-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="1596f-131">Conceder acesso ao usuário.</span><span class="sxs-lookup"><span data-stu-id="1596f-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="1596f-132">Para gerenciar a autorização do usuário no Portal, recomendamos usar a Autorização de URL, que foi introduzida no IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="1596f-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="1596f-133">Para obter mais informações, consulte Noções básicas sobre a autorização de URL do [IIS 7.0.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="1596f-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="1596f-134">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="1596f-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="1596f-135">Gerenciando o acesso do usuário para a seção Portal na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="1596f-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="1596f-136">Opcional: forneça informações de mapeamento de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="1596f-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="1596f-137">Preencha as tabelas de mapeamento de rede e criação no banco de dados de Arquivo QoE.</span><span class="sxs-lookup"><span data-stu-id="1596f-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="1596f-138">Uma conta com acesso de gravação ao banco de dados de Arquivo QoE.</span><span class="sxs-lookup"><span data-stu-id="1596f-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="1596f-139">Seção "Fornecendo informações da sub-rede" na documentação do usuário.</span><span class="sxs-lookup"><span data-stu-id="1596f-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="1596f-140">A implantação do Painel de Qualidade de Chamada envolve a configuração da infraestrutura e a instalação do software.</span><span class="sxs-lookup"><span data-stu-id="1596f-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="1596f-141">O procedimento a seguir descreve o processo.</span><span class="sxs-lookup"><span data-stu-id="1596f-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="1596f-142">Etapas de implantação</span><span class="sxs-lookup"><span data-stu-id="1596f-142">Deployment Steps</span></span>

1. <span data-ttu-id="1596f-143">Copie o CallQualityDashboard.msi para o computador onde o componente de banco de dados de arquivo morto do CQD deve ser instalado (esse é o computador que tem o SQL Server instalado).</span><span class="sxs-lookup"><span data-stu-id="1596f-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="1596f-144">Execute o MSI (o Windows solicitará a execução com privilégios de administrador, faça isso).</span><span class="sxs-lookup"><span data-stu-id="1596f-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="1596f-145">Aceite o EULA.</span><span class="sxs-lookup"><span data-stu-id="1596f-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="1596f-146">Selecione a pasta de destino onde os arquivos relacionados aos componentes do Painel de Qualidade de Chamada estarão localizados ou aceitem o local padrão.</span><span class="sxs-lookup"><span data-stu-id="1596f-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="1596f-147">Selecione todos os recursos.</span><span class="sxs-lookup"><span data-stu-id="1596f-147">Select all features.</span></span>
    
6. <span data-ttu-id="1596f-148">Na página Configuração de Arquivo QoE, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1596f-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="1596f-149">**Métricas de QoE SQL Server:** Nome da instância do SQL Server para onde o banco de dados de métricas de QoE está localizado (essa será a fonte de dados).</span><span class="sxs-lookup"><span data-stu-id="1596f-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="1596f-150">**Nome do SQL Server para arquivamento de QoE:** Este é um campo somente leitura e corrigido para o nome de domínio totalmente qualificado da máquina local.</span><span class="sxs-lookup"><span data-stu-id="1596f-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="1596f-151">O banco de dados de arquivo morto só pode ser instalado no computador local.</span><span class="sxs-lookup"><span data-stu-id="1596f-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="1596f-152">**Instância do SQL Server de arquivo QoE:** Um nome de instância do SQL Server local para onde o banco de dados de arquivo morto deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="1596f-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="1596f-153">Para usar uma instância padrão do SQL Server, deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="1596f-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="1596f-154">Para usar uma instância nomeada do SQL Server, especifique o nome da instância (por exemplo, o nome após o " \" ).</span><span class="sxs-lookup"><span data-stu-id="1596f-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="1596f-155">**Banco de dados de arquivo QoE:** Por padrão, essa opção é definida como "Criar novo banco de dados".</span><span class="sxs-lookup"><span data-stu-id="1596f-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="1596f-156">Como a atualização de Arquivo Morto não é suportada, a única circunstância na qual a opção "Usar banco de dados existente" pode ser usada é se o banco de dados arquivo morto existente tiver o mesmo esquema que o build a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="1596f-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="1596f-157">**Diretório de Arquivos de Banco de Dados:** Caminho para onde os arquivos de banco de dados (.mdf e .ldf) para o banco de dados de arquivo morto devem ser colocados.</span><span class="sxs-lookup"><span data-stu-id="1596f-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="1596f-158">Isso deve estar em uma unidade (HDD2 na configuração de hardware recomendada) separada do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="1596f-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="1596f-159">Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.</span><span class="sxs-lookup"><span data-stu-id="1596f-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="1596f-160">**Use várias partições:** O padrão é definido como "Várias partições", que exige a edição Business Intelligence ou a edição Enterprise do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1596f-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="1596f-161">Para a edição Standard, selecione a opção "Partição Única".</span><span class="sxs-lookup"><span data-stu-id="1596f-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="1596f-162">Observe que o desempenho do processamento de cubos poderá ser afetado se a Partição Única for usada.</span><span class="sxs-lookup"><span data-stu-id="1596f-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="1596f-163">A seleção para a opção Usar Várias Partições não pode ser alterada após a conclusão da Instalação.</span><span class="sxs-lookup"><span data-stu-id="1596f-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="1596f-164">Para alterá-lo, o recurso Cubo precisa ser desinstalado primeiro e reinstalado usando a opção "Alterar" no Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="1596f-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="1596f-165">**Diretório de arquivos de partição:** Caminho para onde as partições do banco de dados de Arquivo QoE devem ser colocadas.</span><span class="sxs-lookup"><span data-stu-id="1596f-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="1596f-166">Isso deve estar em uma unidade (HDD3 na configuração de hardware recomendada) separada da unidade do sistema operacional e da unidade de log do banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="1596f-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="1596f-167">Observe que, como os nomes de arquivo são corrigidos na instalação, para evitar possíveis conflitos, é recomendável que um diretório em branco sem arquivos seja usado.</span><span class="sxs-lookup"><span data-stu-id="1596f-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="1596f-168">**Usuário do Trabalho do SQL Agent - Nome de Usuário &amp; Senha:** Nome e senha da conta de serviço de domínio (mascarada) que será usada para executar a etapa "Dados de Arquivo Morto de QoE" do trabalho do SQL Server Agent (que executará o procedimento armazenado para buscar dados do banco de dados de métricas de QoE no banco de dados de arquivo morto, portanto, essa conta deve ter acesso de leitura ao banco de dados de métricas de QoE, conforme indicado na seção Contas.</span><span class="sxs-lookup"><span data-stu-id="1596f-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="1596f-169">Essa conta também precisa ter um logon na Instância do SQL Server de Arquivo QoE.</span><span class="sxs-lookup"><span data-stu-id="1596f-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="1596f-170">A conta em que a instância do SQL Server está sendo executado, como NT SERVICE\MSSQLSERVER, deve ter acesso/permissão aos diretórios dados acima para que a instalação seja bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="1596f-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="1596f-171">Para obter detalhes, consulte [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1596f-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="1596f-172">Ao clicar em seguida, o instalador executará verificações de pré-requisitos e relatará se algum problema for encontrado.</span><span class="sxs-lookup"><span data-stu-id="1596f-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="1596f-173">Quando todas as verificações de pré-requisito passarem, o instalador irá para a página Configuração do Cubo.</span><span class="sxs-lookup"><span data-stu-id="1596f-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1596f-174">Se o instalador mostrar uma mensagem de aviso informando que o serviço do SQL Server Agent para a instância do SQL Server de Arquivo QoE não está em execução no momento, a instalação poderá prosseguir, mas após a instalação, verifique se o serviço do SQL Agent está em execução e de definir o tipo de Inicialização como Automático para que o Trabalho agendado seja executado.</span><span class="sxs-lookup"><span data-stu-id="1596f-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="1596f-175">Na página Configuração do Cubo, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1596f-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="1596f-176">**Nome do SQL Server para arquivamento de QoE:** Este é um campo somente leitura e corrigido para o nome de domínio totalmente qualificado da máquina local.</span><span class="sxs-lookup"><span data-stu-id="1596f-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="1596f-177">O cubo só pode ser instalado a partir do computador que tem o banco de dados de Arquivo QoE (Observação.</span><span class="sxs-lookup"><span data-stu-id="1596f-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="1596f-178">O próprio cubo pode ser instalado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="1596f-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="1596f-179">Veja abaixo)</span><span class="sxs-lookup"><span data-stu-id="1596f-179">See below)</span></span>
    
   - <span data-ttu-id="1596f-180">**Instância do SQL Server de arquivo QoE:** Nome da instância do SQL Server para onde o banco de dados de arquivo morto QoE está localizado.</span><span class="sxs-lookup"><span data-stu-id="1596f-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="1596f-181">Para especificar uma instância padrão do SQL Server, deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="1596f-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="1596f-182">Para especificar uma instância nomeada do SQL Server, insira o nome da instância (por exemplo, o nome após o " \" ).</span><span class="sxs-lookup"><span data-stu-id="1596f-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="1596f-183">Se o componente arquivo QoE tiver sido selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração de Arquivo QoE.</span><span class="sxs-lookup"><span data-stu-id="1596f-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="1596f-184">**Cube Analysis Server:** Nome da instância do SQL Server Analysis Service para onde o cubo deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="1596f-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="1596f-185">Pode ser um computador diferente, mas o usuário de instalação deve ser um membro dos administradores de Servidor da instância do SQL Server Analysis Service de destino.</span><span class="sxs-lookup"><span data-stu-id="1596f-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="1596f-186">Para obter mais informações sobre como configurar as Permissões de Administrador do Servidor do Analysis Services, consulte Conceder Permissões de Administrador do Servidor [(Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="1596f-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="1596f-187">**Use várias partições:** O padrão é definido como "Várias partições", que exige a edição Business Intelligence ou a edição Enterprise do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1596f-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="1596f-188">Para a edição Standard, selecione a opção "Partição Única".</span><span class="sxs-lookup"><span data-stu-id="1596f-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="1596f-189">Observe que o desempenho do processamento de cubos poderá ser afetado se a Partição Única for usada.</span><span class="sxs-lookup"><span data-stu-id="1596f-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
     > [!NOTE]
     >  <span data-ttu-id="1596f-190">A seleção para a opção Usar Várias Partições não pode ser alterada após a conclusão da Instalação.</span><span class="sxs-lookup"><span data-stu-id="1596f-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="1596f-191">Para alterá-lo, o recurso Cubo precisa ser desinstalado primeiro e reinstalado usando a opção "Alterar" no Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="1596f-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="1596f-192">**Usuário do Cubo - Nome de Usuário &amp; Senha:** nome e senha da conta de serviço de domínio (mascarada) que dispararão o processamento do cubo.</span><span class="sxs-lookup"><span data-stu-id="1596f-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="1596f-193">Se o componente de Arquivo Morto de QoE tiver sido selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração do Arquivo Morto para o Usuário do Trabalho do SQL Agent, mas recomendamos especificar uma conta de serviço de domínio diferente para que a Instalação possa conceder o menor privilégio necessário a ela.</span><span class="sxs-lookup"><span data-stu-id="1596f-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="1596f-194">Ao clicar em seguida, outra rodada de validação será executada e qualquer problema será relatado.</span><span class="sxs-lookup"><span data-stu-id="1596f-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="1596f-195">Após a conclusão bem-sucedida da validação, o instalador irá para a página Configuração do Portal.</span><span class="sxs-lookup"><span data-stu-id="1596f-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="1596f-196">Na página Configuração do Portal, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1596f-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="1596f-197">**Arquivo QoE do SQL Server:** Nome da instância do SQL Server para onde o banco de dados de Arquivo QoE está localizado.</span><span class="sxs-lookup"><span data-stu-id="1596f-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="1596f-198">Observe que, ao contrário da página Configuração de Arquivo QoE e da página Configuração do Cubo, o nome do computador não é fixo e deve ser fornecido.</span><span class="sxs-lookup"><span data-stu-id="1596f-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="1596f-199">Se o componente arquivo QoE tiver sido selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração de Arquivo QoE.</span><span class="sxs-lookup"><span data-stu-id="1596f-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="1596f-200">**Cube Analysis Server:** Nome da instância do SQL Server Analysis Service para onde o cubo está localizado.</span><span class="sxs-lookup"><span data-stu-id="1596f-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="1596f-201">Se o componente Cubo tiver sido selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração do Cubo.</span><span class="sxs-lookup"><span data-stu-id="1596f-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="1596f-202">**Repositório SQL Server:** Nome da instância do SQL Server onde o banco de dados de Repositório deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="1596f-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="1596f-203">Se o nome da instância do SQL Server para onde o banco de dados de Arquivo QoE está localizado tiver sido fornecido anteriormente na instalação (em outros componentes), esse campo será pré-preenchido com o nome da instância do SQL Server do banco de dados de arquivo QoE.</span><span class="sxs-lookup"><span data-stu-id="1596f-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="1596f-204">Pode ser qualquer instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1596f-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="1596f-205">**Banco de dados de repositório:** Por padrão, a opção é definida como "Criar novo banco de dados".</span><span class="sxs-lookup"><span data-stu-id="1596f-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="1596f-206">Como a atualização do banco de dados do repositório não é suportada, a única circunstância na qual a opção "Usar banco de dados existente" pode ser usada é se o banco de dados de repositório existente tiver o mesmo esquema que o build a ser instalado.</span><span class="sxs-lookup"><span data-stu-id="1596f-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="1596f-207">**Usuário do Pool de Aplicativos do IIS - Nome de Usuário &amp; Senha:** a conta em que o pool de aplicativos do IIS deve ser executado.</span><span class="sxs-lookup"><span data-stu-id="1596f-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="1596f-208">Os campos Nome de Usuário e Senha estarão es cinzas se as contas internas do sistema forem selecionadas.</span><span class="sxs-lookup"><span data-stu-id="1596f-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="1596f-209">Esses campos só serão habilitados se "Outros" estiver selecionado na caixa de lista baixa para que o usuário possa inserir as informações da conta de serviço de domínio.</span><span class="sxs-lookup"><span data-stu-id="1596f-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="1596f-210">Ao clicar em seguida, a rodada final de validação será feita para garantir que as instâncias do SQL Server sejam acessíveis usando as credenciais fornecidas e que o IIS está disponível no computador.</span><span class="sxs-lookup"><span data-stu-id="1596f-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="1596f-211">Após a conclusão bem-sucedida da validação, o instalador prosseguirá com a instalação.</span><span class="sxs-lookup"><span data-stu-id="1596f-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="1596f-212">Quando o instalador estiver pronto, provavelmente o trabalho do SQL Server Agent estará em andamento, fazendo a carga inicial dos dados de QoE e o processamento do cubo.</span><span class="sxs-lookup"><span data-stu-id="1596f-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="1596f-213">Dependendo da quantidade de dados na QoE, o portal ainda não terá dados disponíveis para exibição.</span><span class="sxs-lookup"><span data-stu-id="1596f-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="1596f-214">Para verificar o status da carga de dados e do processamento do cubo, vá para  `http://<machinename>/CQD/#/Health` .</span><span class="sxs-lookup"><span data-stu-id="1596f-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="1596f-215">Observe que a URL para verificar o status do processamento do cubo de download faz a análise de caso.</span><span class="sxs-lookup"><span data-stu-id="1596f-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="1596f-216">Se você inserir 'health', a URL não funcionará.</span><span class="sxs-lookup"><span data-stu-id="1596f-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="1596f-217">Você deve inserir 'Health' no final da URL com um H maiús..</span><span class="sxs-lookup"><span data-stu-id="1596f-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="1596f-218">Mensagens de log detalhadas serão mostradas se o modo de depuração estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="1596f-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="1596f-219">Para habilitar o modo de depuração, vá para **%SYSTEMDRIVE%\Program Files\Skype for Business 2015 CQD\QoEDataService\web.config** e atualize a seguinte linha para que o valor seja definido como **True:**</span><span class="sxs-lookup"><span data-stu-id="1596f-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```xml
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="1596f-220">A página principal do portal pode ser acessada por  `http://<machinename>/CQD` meio de .</span><span class="sxs-lookup"><span data-stu-id="1596f-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="1596f-221">Gerenciando o acesso do usuário para o Portal</span><span class="sxs-lookup"><span data-stu-id="1596f-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="1596f-222">Para gerenciar a autorização do usuário no Portal, recomendamos usar a Autorização de URL, que foi introduzida no IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="1596f-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="1596f-223">Para obter mais informações sobre segurança do IIS, consulte Noções básicas sobre a autorização de URL do [IIS 7.0.](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization)</span><span class="sxs-lookup"><span data-stu-id="1596f-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="1596f-224">Qualquer site ou aplicativo Web herda a Autorização de URL padrão configurada para todo o IIS, que normalmente é "Permitir Todos os Usuários".</span><span class="sxs-lookup"><span data-stu-id="1596f-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="1596f-225">Se o acesso ao Portal precisar ser mais restritivo, os administradores poderão conceder acesso apenas ao grupo específico de usuários editando as "Regras de Autorização".</span><span class="sxs-lookup"><span data-stu-id="1596f-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Implantar Qualidade de Chamada - Regras de Autorização no IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="1596f-227">O ícone de Regras de Autorização não deve ser confundido com a "Autorização .NET" na seção ASP.NET, que é um mecanismo de autorização diferente.</span><span class="sxs-lookup"><span data-stu-id="1596f-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="1596f-228">Os administradores devem primeiro remover a regra herdada "Permitir Todos os Usuários".</span><span class="sxs-lookup"><span data-stu-id="1596f-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="1596f-229">Isso impede que usuários não autorizados acessem o Portal.</span><span class="sxs-lookup"><span data-stu-id="1596f-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Implantar o CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="1596f-231">Em seguida, os administradores devem adicionar novas Regras de Permissão e dar aos usuários específicos a permissão para acessar o Portal.</span><span class="sxs-lookup"><span data-stu-id="1596f-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="1596f-232">É recomendável que um Grupo local chamado "CQDPortalUsers" seja criado para gerenciar os usuários.</span><span class="sxs-lookup"><span data-stu-id="1596f-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Implantar o Painel de Qualidade de Chamadas](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="1596f-234">Os detalhes da configuração são armazenados no web.config localizado no diretório físico do Portal.</span><span class="sxs-lookup"><span data-stu-id="1596f-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```xml
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="1596f-235">A próxima etapa é configurar o painel do CQD.</span><span class="sxs-lookup"><span data-stu-id="1596f-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="1596f-236">Depois que os usuários são autenticados pelo IIS, eles terão que ter permissões de arquivo no diretório CQD para acessar o conteúdo do portal da Web.</span><span class="sxs-lookup"><span data-stu-id="1596f-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="1596f-237">É possível alterar as ACLs por meio da guia de segurança das propriedades de diretório do CQD para adicionar usuários ou grupos individuais; no entanto, a abordagem recomendada é deixar as permissões de arquivo intocadas.</span><span class="sxs-lookup"><span data-stu-id="1596f-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="1596f-238">Em vez disso, altere a configuração do IIS para usar o processo de trabalho do IIS para acessar o diretório do CQD, independentemente de qual usuário seja autenticado.</span><span class="sxs-lookup"><span data-stu-id="1596f-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="1596f-239">É importante alterar somente essa configuração para o aplicativo CQD, e não para os dois aplicativos de API: QoEDataService e QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="1596f-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="1596f-240">Configurando o acesso a arquivos para o CQD (Painel)</span><span class="sxs-lookup"><span data-stu-id="1596f-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="1596f-241">Abra o Editor de Configuração para CQD.</span><span class="sxs-lookup"><span data-stu-id="1596f-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Implantar o Painel de Qualidade de Chamadas](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="1596f-243">Em Seção, escolha **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="1596f-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Implantar o Painel de Qualidade de Chamadas](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="1596f-245">Altere authenticatedUserOverride para **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="1596f-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Implantar Painel de Qualidade de Chamada - Editor de Configuração](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="1596f-247">Clique **em** Aplicar no lado direito da página.</span><span class="sxs-lookup"><span data-stu-id="1596f-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="1596f-248">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="1596f-248">Known Issues</span></span>

### <a name="the-cqd-shows-no-data-after-deployment"></a><span data-ttu-id="1596f-249">O CQD não mostra dados após a implantação</span><span class="sxs-lookup"><span data-stu-id="1596f-249">The CQD shows no data after deployment</span></span>

<span data-ttu-id="1596f-250">Você pode receber o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="1596f-250">You may receive the following error:</span></span>

<span data-ttu-id="1596f-251">*Não conseguimos executar a consulta durante a execução no Cubo. Use o Editor de Consultas para modificar a consulta e corrigir quaisquer problemas. Além disso, certifique-se de que o Cubo está acessível.*</span><span class="sxs-lookup"><span data-stu-id="1596f-251">*We couldn’t perform the query while running it on the Cube. Use the Query Editor to modify the query and fix any issues. Also make sure that the Cube is accessible.*</span></span>

<span data-ttu-id="1596f-252">Isso significa que o cubo deve ser processado no SQL Server Analysis Services antes de ser usado no CQD.</span><span class="sxs-lookup"><span data-stu-id="1596f-252">This means that the cube must be processed in SQL Server Analysis Services prior to being used in CQD.</span></span> <span data-ttu-id="1596f-253">Você pode resolver isso seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1596f-253">You can resolve this by following these steps:</span></span>

1. <span data-ttu-id="1596f-254">Abra o SQL Management Studio e selecione **Analysis Services.**</span><span class="sxs-lookup"><span data-stu-id="1596f-254">Open SQL Management Studio and select **Analysis Services**.</span></span>

2. <span data-ttu-id="1596f-255">Expanda **o objeto QoECube,** selecione **Métrica de QoE**, clique com o botão direito do mouse e escolha **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="1596f-255">Expand the **QoECube** object, select **QoE Metric**, right-click, and then choose **Browse**.</span></span> 

    <span data-ttu-id="1596f-256">Se isso retornar um navegador vazio, o cubo ainda não foi prosseguir.</span><span class="sxs-lookup"><span data-stu-id="1596f-256">If this returns empty browser, the cube hasn’t been proceed yet.</span></span>

3. <span data-ttu-id="1596f-257">Clique com o botão **direito do mouse na métrica QoE** e escolha **Processo.**</span><span class="sxs-lookup"><span data-stu-id="1596f-257">Right-click **QoE Metric** angain and choose **Process**.</span></span>

4. <span data-ttu-id="1596f-258">Quando o processamento estiver concluído, clique com  o botão direito do mouse no objeto novamente e escolha Procurar para confirmar se a página do navegador agora mostra dados.</span><span class="sxs-lookup"><span data-stu-id="1596f-258">When processing is complete, right-click the object again, and choose **Browse** to confirm that the browser page now shows data.</span></span> 


### <a name="users-have-trouble-logging-in-because-installer-fails-to-create-the-correct-settings-in-iis"></a><span data-ttu-id="1596f-259">Os usuários têm problemas para entrar porque o instalador falha ao criar as configurações corretas no IIS</span><span class="sxs-lookup"><span data-stu-id="1596f-259">Users have trouble logging in because installer fails to create the correct settings in IIS</span></span>

<span data-ttu-id="1596f-260">Em casos raros, o instalador falha ao criar as configurações corretas no IIS.</span><span class="sxs-lookup"><span data-stu-id="1596f-260">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="1596f-261">A alteração manual é necessária para permitir que os usuários se conectem ao CQD.</span><span class="sxs-lookup"><span data-stu-id="1596f-261">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="1596f-262">Se os usuários estão com problemas para entrar, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1596f-262">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="1596f-263">Abra o Gerenciador do IIS e navegue até o Site Padrão.</span><span class="sxs-lookup"><span data-stu-id="1596f-263">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Implantar o Painel de Qualidade de Chamadas](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="1596f-265">Clique em "Autenticação".</span><span class="sxs-lookup"><span data-stu-id="1596f-265">Click on "Authentication".</span></span> <span data-ttu-id="1596f-266">Se "Autenticação Anônima", "Representação de ASP.NET", "Autenticação de Formulário" e "Autenticação do Windows" não corresponderem às configurações mostradas abaixo, altere-as manualmente para corresponder às configurações abaixo.</span><span class="sxs-lookup"><span data-stu-id="1596f-266">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="1596f-267">Todos os outros mecanismos de autenticação devem ser desabilitados.</span><span class="sxs-lookup"><span data-stu-id="1596f-267">All other authentication mechanisms should be disabled.</span></span>
    
     ![Implantar o Painel de Qualidade de Chamadas](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="1596f-269">Para "Autenticação do Windows", clique em Configurações Avançadas no lado direito.</span><span class="sxs-lookup"><span data-stu-id="1596f-269">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Implantar o Painel de Qualidade de Chamadas](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="1596f-271">De definir "Proteção Estendida" para Aceitar e marque a caixa "Habilitar autenticação no modo Kernel".</span><span class="sxs-lookup"><span data-stu-id="1596f-271">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Implantar o Painel de Qualidade de Chamadas](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="1596f-273">Repita as etapas acima para cada uma das entradas "CQD", "QoEDataService" e "QoERepositoryService" abaixo de "Default Web Site".</span><span class="sxs-lookup"><span data-stu-id="1596f-273">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="1596f-274">Para vinculações de porta HTTP e HTTPS, o instalador criará ligações de porta nos números de porta padrão (porta 80 para HTTP e porta 443 para HTTPS).</span><span class="sxs-lookup"><span data-stu-id="1596f-274">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="1596f-275">Se houver outro site no computador que use essas vinculações, haverá um conflito e o comportamento do IIS não poderá ser previsto.</span><span class="sxs-lookup"><span data-stu-id="1596f-275">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="1596f-276">A melhor maneira de evitar esse problema é garantir que nenhum outro site seja mapeado para as portas 80 e 443 antes de instalar o CQD.</span><span class="sxs-lookup"><span data-stu-id="1596f-276">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="1596f-277">Para habilitar SSL/TLS no IIS e forçar os usuários a se conectarem via HTTPS seguro em vez de HTTP:</span><span class="sxs-lookup"><span data-stu-id="1596f-277">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="1596f-278">Configure Secure Sockets Layer no IIS, consulte [Configurando Secure Sockets Layer no IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="1596f-278">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="1596f-279">Depois de terminar, substitua  `http` por `https` .</span><span class="sxs-lookup"><span data-stu-id="1596f-279">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="1596f-280">Para obter instruções sobre como habilitar o TLS nas conexões do SQL Server, consulte Como habilitar a criptografia [SSL](https://support.microsoft.com/kb/316898/)para uma instância do SQL Server usando o Console de Gerenciamento Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1596f-280">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console](https://support.microsoft.com/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="1596f-281">Falha na sincronização do cubo</span><span class="sxs-lookup"><span data-stu-id="1596f-281">Cube Sync Fails</span></span>

<span data-ttu-id="1596f-282">A QoEMetrics pode conter alguns registros inválidos com base nos relógios do usuário final.</span><span class="sxs-lookup"><span data-stu-id="1596f-282">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="1596f-283">Se a distorção de tempo for maior que 60 yrs, a importação do cubo falhará.</span><span class="sxs-lookup"><span data-stu-id="1596f-283">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="1596f-284">Verifique Min e Max StartTime/EndTime usando as seleções abaixo.</span><span class="sxs-lookup"><span data-stu-id="1596f-284">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="1596f-285">Procure e exclua registros no futuro distante e muito distante, eles podem ser desconsiderados e eles quebrarão os processos de sincronização.</span><span class="sxs-lookup"><span data-stu-id="1596f-285">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="1596f-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="1596f-286">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="1596f-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="1596f-287">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="1596f-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="1596f-288">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="1596f-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="1596f-289">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="1596f-290">Tarefas pós-instalação</span><span class="sxs-lookup"><span data-stu-id="1596f-290">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="1596f-291">Importando edifícios e redes</span><span class="sxs-lookup"><span data-stu-id="1596f-291">Importing Buildings and Networks</span></span>

<span data-ttu-id="1596f-292">Depois de instalar o CQD, execute as seguintes tarefas de configuração:</span><span class="sxs-lookup"><span data-stu-id="1596f-292">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="1596f-293">Definir tipos de construção (recomendado)</span><span class="sxs-lookup"><span data-stu-id="1596f-293">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="1596f-294">Definir tipos de propriedade de construção (recomendado)</span><span class="sxs-lookup"><span data-stu-id="1596f-294">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="1596f-295">Definir tipos de rede (altamente recomendado)</span><span class="sxs-lookup"><span data-stu-id="1596f-295">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="1596f-296">Importar edifícios (recomendado)</span><span class="sxs-lookup"><span data-stu-id="1596f-296">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="1596f-297">Importar Sub-redes (recomendado)</span><span class="sxs-lookup"><span data-stu-id="1596f-297">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="1596f-298">Definir tipos de construção</span><span class="sxs-lookup"><span data-stu-id="1596f-298">Define Building Types</span></span>

<span data-ttu-id="1596f-299">Os tipos de construção são usados para descrever as diferentes definições de edifícios ou tipos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1596f-299">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1596f-300">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="1596f-300">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="1596f-301">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1596f-301">Examples</span></span>
  
- <span data-ttu-id="1596f-302">Headquarters</span><span class="sxs-lookup"><span data-stu-id="1596f-302">Headquarters</span></span>
    
- <span data-ttu-id="1596f-303">Office Remoto</span><span class="sxs-lookup"><span data-stu-id="1596f-303">Remote Office</span></span>
    
- <span data-ttu-id="1596f-304">Localização de joint-joint-location</span><span class="sxs-lookup"><span data-stu-id="1596f-304">Joint-venture location</span></span>
    
  <span data-ttu-id="1596f-305">**Sintaxe SQL de exemplo**</span><span class="sxs-lookup"><span data-stu-id="1596f-305">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="1596f-306">Os parâmetros BuildingTypeId e BuildingTypeDesc são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="1596f-306">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="1596f-307">Definir tipos de propriedade de construção</span><span class="sxs-lookup"><span data-stu-id="1596f-307">Define Building Ownership Types</span></span>

<span data-ttu-id="1596f-308">Os tipos de propriedade são usados para distinguir ativos de propriedade versus arrendados.</span><span class="sxs-lookup"><span data-stu-id="1596f-308">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1596f-309">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="1596f-309">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="1596f-310">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1596f-310">Examples</span></span>
  
- <span data-ttu-id="1596f-311">Contoso Leased non-RE &amp; F</span><span class="sxs-lookup"><span data-stu-id="1596f-311">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="1596f-312">RE F com concessão da Contoso &amp;</span><span class="sxs-lookup"><span data-stu-id="1596f-312">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="1596f-313">Contoso Owned</span><span class="sxs-lookup"><span data-stu-id="1596f-313">Contoso Owned</span></span>
    
- <span data-ttu-id="1596f-314">Subsidiária arrendada</span><span class="sxs-lookup"><span data-stu-id="1596f-314">Subsidiary Leased</span></span>
    
  <span data-ttu-id="1596f-315">**Sintaxe SQL de exemplo**</span><span class="sxs-lookup"><span data-stu-id="1596f-315">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="1596f-316">Os parâmetros OwnershipTypeId e OwnershipTypeDesc são necessários.</span><span class="sxs-lookup"><span data-stu-id="1596f-316">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="1596f-317">Definir nomes de rede</span><span class="sxs-lookup"><span data-stu-id="1596f-317">Define Network Names</span></span>

<span data-ttu-id="1596f-318">Tipos de rede são usados para descrever diferentes tipos de redes dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="1596f-318">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="1596f-319">Isso permite filtrar (ou filtrar) tipos de rede específicos.</span><span class="sxs-lookup"><span data-stu-id="1596f-319">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1596f-320">É altamente recomendável definir nomes de rede, mas é opcional.</span><span class="sxs-lookup"><span data-stu-id="1596f-320">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="1596f-321">Se você decidir não definir nomes de rede, verifique se cada entrada CqdNetwork tem BuildingId 0.</span><span class="sxs-lookup"><span data-stu-id="1596f-321">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="1596f-322">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1596f-322">Examples</span></span>
  
- <span data-ttu-id="1596f-323">VPN</span><span class="sxs-lookup"><span data-stu-id="1596f-323">VPN</span></span>
    
- <span data-ttu-id="1596f-324">LAB</span><span class="sxs-lookup"><span data-stu-id="1596f-324">LAB</span></span>
    
  <span data-ttu-id="1596f-325">**Sintaxe SQL de exemplo**</span><span class="sxs-lookup"><span data-stu-id="1596f-325">**Sample SQL Syntax**</span></span>
  
```SQL
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="1596f-326">Os parâmetros NetworkNameID e NetworkName são necessários, o parâmetro NetworkType é opcional, mas recomendado.</span><span class="sxs-lookup"><span data-stu-id="1596f-326">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="1596f-327">Importar edifícios</span><span class="sxs-lookup"><span data-stu-id="1596f-327">Import Buildings</span></span>

<span data-ttu-id="1596f-328">A importação de edifícios oferece a capacidade de obter informações específicas (chamadas ruins por edifício em WiFi/Com fio, etc.).</span><span class="sxs-lookup"><span data-stu-id="1596f-328">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1596f-329">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="1596f-329">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="1596f-330">Antes de importar um novo edifício, você já deve ter um BuildingKey predefinido identificado.</span><span class="sxs-lookup"><span data-stu-id="1596f-330">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="1596f-331">Para fazer isso, em seguida, o comando SQL "SELECT MAX(BuildingKey) FROM CqdBuilding" para identificar o valor atual e adicionar 1 ao resultado.</span><span class="sxs-lookup"><span data-stu-id="1596f-331">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="1596f-332">**Sintaxe SQL de exemplo**</span><span class="sxs-lookup"><span data-stu-id="1596f-332">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="1596f-333">Os parâmetros BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId são necessários, os outros parâmetros são opcionais.</span><span class="sxs-lookup"><span data-stu-id="1596f-333">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="1596f-334">Importar Sub-redes</span><span class="sxs-lookup"><span data-stu-id="1596f-334">Import Subnets</span></span>

<span data-ttu-id="1596f-335">A importação de edifícios oferece a capacidade de obter informações específicas (chamadas ruins por edifício em WiFi/Com fio, etc.).</span><span class="sxs-lookup"><span data-stu-id="1596f-335">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1596f-336">Esta etapa é opcional, mas recomendada.</span><span class="sxs-lookup"><span data-stu-id="1596f-336">This step is optional, but recommended.</span></span>
  
<span data-ttu-id="1596f-337">Importe sub-redes e mapeie-as para os edifícios importados na última etapa.</span><span class="sxs-lookup"><span data-stu-id="1596f-337">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="1596f-338">Se você decidiu não preencher NetworkName, certifique-se de que cada entrada nesta tabela use um NetworkNameID de 0.</span><span class="sxs-lookup"><span data-stu-id="1596f-338">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span> <span data-ttu-id="1596f-339">Para obter mais informações sobre sintaxe SQL e parâmetros para o Painel de Qualidade da Chamada, consulte Usar o Painel de Qualidade da Chamada [para o Skype for Business Server.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use)</span><span class="sxs-lookup"><span data-stu-id="1596f-339">For more information on SQL syntax and parameters for the Call Quality Dashboard, see [Use Call Quality Dashboard for Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/use).</span></span>
  
 <span data-ttu-id="1596f-340">**Sintaxe SQL de exemplo**</span><span class="sxs-lookup"><span data-stu-id="1596f-340">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="1596f-341">Os parâmetros Network e UpdatedDate são necessários, os outros parâmetros são opcionais.</span><span class="sxs-lookup"><span data-stu-id="1596f-341">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="1596f-342">Opcional: BSSID</span><span class="sxs-lookup"><span data-stu-id="1596f-342">Optional: BSSID</span></span>

<span data-ttu-id="1596f-343">O populamento de informações de BSSID oferece correlação de fluxo WiFi adicional por controlador ou rádio.</span><span class="sxs-lookup"><span data-stu-id="1596f-343">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="1596f-344">Isso é além da filtragem por meio de construção ou sub-rede.</span><span class="sxs-lookup"><span data-stu-id="1596f-344">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="1596f-345">**Sintaxe SQL de exemplo**</span><span class="sxs-lookup"><span data-stu-id="1596f-345">**Sample SQL Syntax**</span></span>
  
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

<span data-ttu-id="1596f-346">**Detalhes do CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="1596f-346">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="1596f-347">**Conforme mostrado no CQD**</span><span class="sxs-lookup"><span data-stu-id="1596f-347">**As shown in CQD**</span></span>|<span data-ttu-id="1596f-348">**Tabela CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="1596f-348">**CQDBssid Table**</span></span>|<span data-ttu-id="1596f-349">**Exemplo de entradas**</span><span class="sxs-lookup"><span data-stu-id="1596f-349">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1596f-350">Ap NName</span><span class="sxs-lookup"><span data-stu-id="1596f-350">Ap NName</span></span>  <br/> |<span data-ttu-id="1596f-351">AP</span><span class="sxs-lookup"><span data-stu-id="1596f-351">AP</span></span>  <br/> |<span data-ttu-id="1596f-352">AP1</span><span class="sxs-lookup"><span data-stu-id="1596f-352">AP1</span></span>  <br/> |
|<span data-ttu-id="1596f-353">BBssid</span><span class="sxs-lookup"><span data-stu-id="1596f-353">BBssid</span></span>  <br/> |<span data-ttu-id="1596f-354">BSS</span><span class="sxs-lookup"><span data-stu-id="1596f-354">BSS</span></span>  <br/> |<span data-ttu-id="1596f-355">00-00-00-00-00-00 (você deve usar a fformatação delimitada)</span><span class="sxs-lookup"><span data-stu-id="1596f-355">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="1596f-356">Controlador</span><span class="sxs-lookup"><span data-stu-id="1596f-356">Controller</span></span>  <br/> |<span data-ttu-id="1596f-357">Construção</span><span class="sxs-lookup"><span data-stu-id="1596f-357">Building</span></span>  <br/> |<span data-ttu-id="1596f-358">Aruba AP 7</span><span class="sxs-lookup"><span data-stu-id="1596f-358">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="1596f-359">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="1596f-359">Device</span></span>  <br/> |<span data-ttu-id="1596f-360">ess</span><span class="sxs-lookup"><span data-stu-id="1596f-360">ess</span></span>  <br/> |<span data-ttu-id="1596f-361">Controller1</span><span class="sxs-lookup"><span data-stu-id="1596f-361">Controller1</span></span>  <br/> |
|<span data-ttu-id="1596f-362">Rádio</span><span class="sxs-lookup"><span data-stu-id="1596f-362">Radio</span></span>  <br/> |<span data-ttu-id="1596f-363">phy</span><span class="sxs-lookup"><span data-stu-id="1596f-363">phy</span></span>  <br/> |<span data-ttu-id="1596f-364">bgn</span><span class="sxs-lookup"><span data-stu-id="1596f-364">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="1596f-365">Processando os dados importados</span><span class="sxs-lookup"><span data-stu-id="1596f-365">Processing the imported data</span></span>

<span data-ttu-id="1596f-366">Por padrão, depois de importar dados de rede/com construção, eles serão aplicados somente aos registros gerados após esse ponto no tempo.</span><span class="sxs-lookup"><span data-stu-id="1596f-366">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="1596f-367">Para marcar todos os registros anteriores com esses novos dados, você precisará executar o procedimento armazenado CqdUpdateBuilding, conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="1596f-367">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="1596f-368">Dê a ele a data do seu primeiro registro (identifique que usando o comando SELECT MIN(StartTime) FROM CqdPartitionedStreamView SQL ), uma EndDate de amanhã e NULL para os dois últimos valores.</span><span class="sxs-lookup"><span data-stu-id="1596f-368">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="1596f-369">Depois que os dados são associados a dados de fluxo, o cubo do SSIS precisa reprocessar todos os registros.</span><span class="sxs-lookup"><span data-stu-id="1596f-369">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="1596f-370">Isso também se aplica ao adicionar dados BSSID/ISP em massa.</span><span class="sxs-lookup"><span data-stu-id="1596f-370">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="1596f-371">Certifique-se de que "Processo Completo" está selecionado.</span><span class="sxs-lookup"><span data-stu-id="1596f-371">Ensure that "Process Full" is selected.</span></span>
  

