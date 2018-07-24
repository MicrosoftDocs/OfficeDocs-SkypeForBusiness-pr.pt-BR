---
title: Implantar o painel de controle de qualidade de chamada para Skype para Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 287f64f5-0f8a-455a-8979-7b34bf0217bb
description: 'Resumo: Saiba mais sobre o processo de implantação para painel de controle de qualidade de chamada. Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.'
ms.openlocfilehash: 860792fc39deed592f0d4369018cf85dd7de4a74
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988983"
---
# <a name="deploy-call-quality-dashboard-for-skype-for-business-server-2015"></a><span data-ttu-id="08501-104">Implantar o painel de controle de qualidade de chamada para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="08501-104">Deploy Call Quality Dashboard for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="08501-105">**Resumo:** Saiba mais sobre o processo de implantação para painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="08501-105">**Summary:** Learn about the deployment process for Call Quality Dashboard.</span></span> <span data-ttu-id="08501-106">Painel de controle de qualidade de chamada é uma ferramenta para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="08501-106">Call Quality Dashboard is a tool for Skype for Business Server 2015.</span></span>
  
## <a name="deployment-overview"></a><span data-ttu-id="08501-107">Visão geral da implantação</span><span class="sxs-lookup"><span data-stu-id="08501-107">Deployment Overview</span></span>

<span data-ttu-id="08501-108">Painel de controle de qualidade de chamada (CQD) consiste em três componentes principais:</span><span class="sxs-lookup"><span data-stu-id="08501-108">Call Quality Dashboard (CQD) consists of three major components:</span></span>
  
- <span data-ttu-id="08501-109">**Banco de dados de arquivamento**, onde os dados de qualidade da experiência (QoE) são replicados e armazenados.</span><span class="sxs-lookup"><span data-stu-id="08501-109">**Archive Database**, where the Quality of Experience (QoE) data is replicated and stored.</span></span>
    
- <span data-ttu-id="08501-110">**Cubo**, onde os dados do banco de dados de arquivo morto de QoE são agregados para otimizados e acesso rápido.</span><span class="sxs-lookup"><span data-stu-id="08501-110">**Cube**, where data from QoE Archive database is aggregated for optimized and fast access.</span></span>
    
- <span data-ttu-id="08501-111">**Portal**, onde os usuários podem facilmente consultar e visualizar os dados do QoE.</span><span class="sxs-lookup"><span data-stu-id="08501-111">**Portal**, where users can easily query and visualize QoE data.</span></span>
    
![Componentes do CQD](../../media/ef3359b1-c98b-4cc5-a549-c84c6e03c011.png)
  
<span data-ttu-id="08501-113">O processo de instalação para arquivo morto de QoE envolve criando o banco de dados de arquivo morto de QoE, implantando um procedimento armazenado do SQL Server que irá mover os dados da fonte de banco de dados de métricas de QoE em banco de dados de arquivamento do QoE e configurando o trabalho do SQL Server Agent para executar o armazenado procedimento em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="08501-113">The setup process for QoE Archive involves creating the QoE Archive database, deploying a SQL Server stored procedure that will move the data from the source QoE Metrics database into QoE Archive database, and setting up the SQL Server Agent job to execute the stored procedure at a regular interval.</span></span> 
  
<span data-ttu-id="08501-114">Implantação de cubo obtém informações do usuário no qual o arquivamento de QoE está localizado, implanta o cubo e configura um trabalho de agente regular do SQL Server que irá atualizar o cubo em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="08501-114">Cube deployment gets information from the user on where the QoE Archive is located, deploys the cube, and sets up a regular SQL Server agent job that will refresh the cube at a regular interval.</span></span>
  
<span data-ttu-id="08501-115">Instalação do portal cria um banco de dados do repositório que armazena o mapeamento de usuários CQD/consultas de relatórios de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="08501-115">Portal install creates a Repository database that stores the mapping of CQD users to each user's reports/queries.</span></span> <span data-ttu-id="08501-116">Em seguida, ele configura um aplicativo web do IIS que é o painel onde os usuários podem ver um conjunto predefinido de relatórios, bem como personalizar e criar suas próprias consultas para visualizar os dados do cubo.</span><span class="sxs-lookup"><span data-stu-id="08501-116">It then sets up an IIS web application which is the dashboard where users can see a pre-defined set of reports as well as customize and create their own queries to visualize data from the cube.</span></span> <span data-ttu-id="08501-117">A instalação do portal cria dois aplicativos web adicionais que expõe APIs para os usuários acessarem programaticamente o repositório e o cubo.</span><span class="sxs-lookup"><span data-stu-id="08501-117">The portal install creates two additional web applications that exposes APIs for users to programmatically access the repository and the cube.</span></span> <span data-ttu-id="08501-118">(Essas APIs são usados internamente pelo painel também.)</span><span class="sxs-lookup"><span data-stu-id="08501-118">(These APIs are used internally by the dashboard as well.)</span></span>
  

|<span data-ttu-id="08501-119">**Fase**</span><span class="sxs-lookup"><span data-stu-id="08501-119">**Phase**</span></span>|<span data-ttu-id="08501-120">**Etapas**</span><span class="sxs-lookup"><span data-stu-id="08501-120">**Steps**</span></span>|<span data-ttu-id="08501-121">**Funções e associação de grupo**</span><span class="sxs-lookup"><span data-stu-id="08501-121">**Roles and group membership**</span></span>|<span data-ttu-id="08501-122">**Documentação**</span><span class="sxs-lookup"><span data-stu-id="08501-122">**Documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08501-123">Instale pré-requisitos de hardware e software.</span><span class="sxs-lookup"><span data-stu-id="08501-123">Install prerequisite hardware and software.</span></span>  <br/> |<span data-ttu-id="08501-124">Decidir sobre a configuração de CQD e escolha um SQL Server a partir do qual efetuar a instalar.</span><span class="sxs-lookup"><span data-stu-id="08501-124">Decide on the CQD configuration, and choose a SQL Server from which to perform the install.</span></span>  <br/> |<span data-ttu-id="08501-125">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="08501-125">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="08501-126">Seção "Pré-requisitos de instalar" na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08501-126">"Pre-install Requirements" section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="08501-127">Instale o CQD.</span><span class="sxs-lookup"><span data-stu-id="08501-127">Install CQD.</span></span>  <br/> |<span data-ttu-id="08501-128">Execute o MSI seguindo o documento de implantação.</span><span class="sxs-lookup"><span data-stu-id="08501-128">Run the MSI following the deployment document.</span></span>  <br/> |<span data-ttu-id="08501-129">Para executar a instalação, a conta de instalação deve ser um usuário de domínio que seja membro do grupo Administradores local e ter acesso de leitura ao banco de dados de métricas de QoE no Monitoring Server.</span><span class="sxs-lookup"><span data-stu-id="08501-129">To perform the setup, the installing account must be a domain user who is a member of the local administrators group and have read access to QoE Metrics database on the Monitoring Server.</span></span>  <br/> |<span data-ttu-id="08501-130">Seções "Contas e as etapas de implantação" na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08501-130">"Accounts and Deployment Steps" sections in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="08501-131">Conceder acesso de usuário.</span><span class="sxs-lookup"><span data-stu-id="08501-131">Grant user access.</span></span>  <br/> |<span data-ttu-id="08501-132">Para gerenciar a autorização de usuários ao Portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="08501-132">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="08501-133">Para obter mais informações, consulte [Understanding IIS 7.0 a autorização de URL](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="08501-133">For more information, see [Understanding IIS 7.0 URL Authorization](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>  <br/> |<span data-ttu-id="08501-134">Usuário do domínio que é membro do grupo local de administradores.</span><span class="sxs-lookup"><span data-stu-id="08501-134">Domain user who is a member of the local administrators group.</span></span>  <br/> |<span data-ttu-id="08501-135">Gerenciando o acesso de usuário para a seção de Portal na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="08501-135">Managing User Access for the Portal section in the deployment documentation.</span></span>  <br/> |
|<span data-ttu-id="08501-136">Opcional: Forneça informações de mapeamento de sub-rede.</span><span class="sxs-lookup"><span data-stu-id="08501-136">Optional: Provide subnet mapping information.</span></span>  <br/> |<span data-ttu-id="08501-137">Preencha a rede e tabelas de mapeamento de construção no banco de dados de arquivo morto de QoE.</span><span class="sxs-lookup"><span data-stu-id="08501-137">Populate network and building mapping tables in QoE Archive database.</span></span>  <br/> |<span data-ttu-id="08501-138">Uma conta com acesso de gravação no banco de dados de arquivo morto de QoE.</span><span class="sxs-lookup"><span data-stu-id="08501-138">An account with write access to the QoE Archive database.</span></span>  <br/> |<span data-ttu-id="08501-139">Seção "Fornecendo informações de sub-rede" na documentação do usuário.</span><span class="sxs-lookup"><span data-stu-id="08501-139">"Supplying Subnet Information" section in the user documentation.</span></span>  <br/> |
   


<span data-ttu-id="08501-140">Configurando a infraestrutura e instalando o software envolve a implantação do painel de controle de qualidade de chamada.</span><span class="sxs-lookup"><span data-stu-id="08501-140">Deployment of Call Quality Dashboard involves setting up the infrastructure and installing the software.</span></span> <span data-ttu-id="08501-141">O procedimento a seguir destaca o processo.</span><span class="sxs-lookup"><span data-stu-id="08501-141">The following procedure outlines the process.</span></span>
  
## <a name="deployment-steps"></a><span data-ttu-id="08501-142">Etapas da implantação</span><span class="sxs-lookup"><span data-stu-id="08501-142">Deployment Steps</span></span>

1. <span data-ttu-id="08501-143">Copie o CallQualityDashboard.msi máquina onde deve ser instalado o componente de banco de dados de arquivamento do CQD (essa é a máquina que tenha o SQL Server instalado).</span><span class="sxs-lookup"><span data-stu-id="08501-143">Copy the CallQualityDashboard.msi to the machine where the archive database component of CQD is to be installed (this is the machine that has SQL Server installed).</span></span> 
    
2. <span data-ttu-id="08501-144">Executar o MSI (Windows perguntará executado com privilégios de administrador, fazê-lo).</span><span class="sxs-lookup"><span data-stu-id="08501-144">Execute the MSI (Windows will prompt to run with administrator privilege, do so).</span></span> 
    
3. <span data-ttu-id="08501-145">Aceite o EULA.</span><span class="sxs-lookup"><span data-stu-id="08501-145">Accept the EULA.</span></span>
    
4. <span data-ttu-id="08501-146">Selecione a pasta de destino onde os arquivos relacionados aos componentes do painel de controle de qualidade de chamada vai ser localizado ou aceite o local padrão.</span><span class="sxs-lookup"><span data-stu-id="08501-146">Select the destination folder where files related to Call Quality Dashboard components will be located or accept the default location.</span></span>
    
5. <span data-ttu-id="08501-147">Selecione todos os recursos.</span><span class="sxs-lookup"><span data-stu-id="08501-147">Select all features.</span></span>
    
6. <span data-ttu-id="08501-148">Na página de configuração de arquivamento de QoE, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="08501-148">At the QoE Archive Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="08501-149">**Métricas de QoE SQL Server:** Nome de instância do SQL Server para onde se encontra o banco de dados de métricas de QoE (Isso será a fonte de dados).</span><span class="sxs-lookup"><span data-stu-id="08501-149">**QoE Metrics SQL Server:** SQL Server instance name for where the QoE Metrics DB is located (this will be the data source).</span></span>
    
   - <span data-ttu-id="08501-150">**Nome de arquivo morto de QoE do SQL Server:** Este é o campo somente leitura e fixa com o nome de domínio totalmente qualificado da máquina local.</span><span class="sxs-lookup"><span data-stu-id="08501-150">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="08501-151">BD de arquivamento pode ser instalado somente na máquina local.</span><span class="sxs-lookup"><span data-stu-id="08501-151">Archive DB can be installed only on the local machine.</span></span>
    
   - <span data-ttu-id="08501-152">**Arquivamento de QoE instância do SQL Server:** Um nome de instância de SQL Server local para onde o banco de dados de arquivo morto deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="08501-152">**QoE Archive SQL Server Instance:** A local SQL Server instance name for where the Archive DB is to be created.</span></span> <span data-ttu-id="08501-153">Para usar uma instância do SQL Server padrão, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="08501-153">To use a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="08501-154">Para usar uma instância nomeada do SQL Server, especifique o nome da instância (por exemplo, o nome após o "\").</span><span class="sxs-lookup"><span data-stu-id="08501-154">To use a named SQL Server instance, specify the instance name (e.g. the name after the "\").</span></span>
    
   - <span data-ttu-id="08501-155">**Banco de dados de arquivamento do QoE:** Por padrão, essa opção é definida como "Criar novo banco de dados".</span><span class="sxs-lookup"><span data-stu-id="08501-155">**QoE Archive Database:** By default, this option is set to "Create new database".</span></span> <span data-ttu-id="08501-156">Desde que não há suporte para a atualização do banco de dados de arquivamento, a única circunstância sob a qual a opção "Usar o banco de dados existente" pode ser usada é se o banco de dados existente do arquivo morto tem o mesmo esquema que a compilação seja instalado.</span><span class="sxs-lookup"><span data-stu-id="08501-156">Since Archive DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Archive database has the same schema as the build to be installed.</span></span>
    
   - <span data-ttu-id="08501-157">**Diretório de arquivos de banco de dados:** Caminho onde os arquivos de banco de dados (arquivos. mdf e. ldf) para o banco de dados de arquivo morto devem ser colocados.</span><span class="sxs-lookup"><span data-stu-id="08501-157">**Database File Directory:** Path to where the database files (.mdf and .ldf) for the Archive DB should be placed.</span></span> <span data-ttu-id="08501-158">Este deve ser em uma unidade separada (HDD2 na configuração de hardware recomendada) do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="08501-158">This should be on a drive (HDD2 in the recommended hardware configuration) separate from the OS.</span></span> <span data-ttu-id="08501-159">Observe que como os nomes de arquivo são corrigidos na instalar, para evitar conflitos potenciais, é recomendável que um diretório em branco com nenhum arquivo ser usado.</span><span class="sxs-lookup"><span data-stu-id="08501-159">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="08501-160">**Use várias partições:** O padrão é definido como "Vários partição", que requer a edição de Business Intelligence ou Enterprise edition do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08501-160">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="08501-161">Para o Standard edition, selecione a opção de "Única partição".</span><span class="sxs-lookup"><span data-stu-id="08501-161">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="08501-162">Observe que o desempenho de processamento de cubo pode ser afetado se única partição for usada.</span><span class="sxs-lookup"><span data-stu-id="08501-162">Note that cube processing performance may be impacted if Single Partition is used.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08501-163">A seleção da opção usar várias partições não pode ser alterada depois que terminar a instalação.</span><span class="sxs-lookup"><span data-stu-id="08501-163">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="08501-164">Para alterá-lo, o cubo de recurso deve ser o primeiro desinstalada e então reinstalado usando a opção "Alterar" no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="08501-164">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span> 
  
   - <span data-ttu-id="08501-165">**Partição de diretório do arquivo:** Caminho para onde as partições do banco de dados de arquivo morto de QoE devem ser colocadas.</span><span class="sxs-lookup"><span data-stu-id="08501-165">**Partition File Directory:** Path to where the partitions for the QoE Archive database should be placed.</span></span> <span data-ttu-id="08501-166">Este deve ser em uma unidade separada (HDD3 na configuração de hardware recomendada) da unidade do sistema operacional e unidade de arquivos de log de banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="08501-166">This should be on a drive (HDD3 in the recommended hardware configuration) separate from the OS drive and SQL database log files drive.</span></span> <span data-ttu-id="08501-167">Observe que como os nomes de arquivo são corrigidos na instalar, para evitar conflitos potenciais, é recomendável que um diretório em branco com nenhum arquivo ser usado.</span><span class="sxs-lookup"><span data-stu-id="08501-167">Note that since the file names are fixed in the install, to avoid any potential conflict, it is recommended that a blank directory with no files be used.</span></span>
    
   - <span data-ttu-id="08501-168">**Usuário de trabalho do SQL Agent - nome de usuário &amp; senha:** Nome de conta de serviço de domínio e a senha (mascaradas) que será usada para executar a etapa de "Dados de arquivamento do QoE" do trabalho de SQL Server Agent (que executará o procedimento armazenado para buscar dados do banco de dados de métricas de QoE em Archive DB, portanto, essa conta deve ter acesso de leitura ao banco de dados de métricas de QoE,  conforme indicado na seção contas.</span><span class="sxs-lookup"><span data-stu-id="08501-168">**SQL Agent Job User - User Name &amp; Password:** Domain service account name and password (masked) that will be used to run the "QoE Archive Data" step of the SQL Server Agent job (which will run the stored procedure to fetch data from QoE Metrics DB into Archive DB, so this account must have read access to QoE Metrics DB, as indicated under Accounts section.</span></span> <span data-ttu-id="08501-169">Essa conta também precisa ter um logon na instância do QoE Archive SQL Server).</span><span class="sxs-lookup"><span data-stu-id="08501-169">This account also needs to have a login in the QoE Archive SQL Server Instance).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="08501-170">A conta que a instância do SQL Server está sendo executado em, como NT SERVICE\MSSQLSERVER, deve ter permissão de acesso/para os diretórios de dado acima para a instalação ter sucesso.</span><span class="sxs-lookup"><span data-stu-id="08501-170">The account that the SQL Server instance is running under, such as NT SERVICE\MSSQLSERVER, must have access/permission to the directories given above for the installation to succeed.</span></span> <span data-ttu-id="08501-171">Para obter detalhes, consulte [Configurar permissões do sistema do arquivo para acesso do mecanismo de banco de dados](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="08501-171">For details, see [Configure File System Permissions for Database Engine Access](https://msdn.microsoft.com/en-us/library/jj219062%28v=sql.110%29.aspx)</span></span>
  
7. <span data-ttu-id="08501-172">Após clicar em Avançar, o instalador executará verificações de pré-requisito e o relatório se ocorrerem problemas.</span><span class="sxs-lookup"><span data-stu-id="08501-172">Upon clicking next, the installer will perform pre-requisite checks and report if any issues are encountered.</span></span> <span data-ttu-id="08501-173">Quando verificações de pré-requisito tudo secreta, o instalador irão para a página Configuração do cubo.</span><span class="sxs-lookup"><span data-stu-id="08501-173">When all pre-requisite checks pass, the installer will go to the Cube Configuration page.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="08501-174">Se o instalador mostrar uma mensagem de aviso que o serviço SQL Server Agent para a instância do SQL Server QoE arquivo morto não está executando no momento, pode continuar a instalação, mas pós-instalação Certifique-se de que o serviço do agente do SQL está em execução e defina o tipo de inicialização como Automático, para que o trabalho agendado seja executado.</span><span class="sxs-lookup"><span data-stu-id="08501-174">If the installer shows a warning message that the SQL Server Agent service for the QoE Archive SQL Server instance is currently not running, installation can proceed, but post installation please make sure that SQL Agent service is running and set the Startup type to Automatic so that the scheduled Job runs.</span></span> 
  
8. <span data-ttu-id="08501-175">Na página Configuração do cubo, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="08501-175">At Cube Configuration page, provide the following information:</span></span>
    
   - <span data-ttu-id="08501-176">**Nome de arquivo morto de QoE do SQL Server:** Este é o campo somente leitura e fixa com o nome de domínio totalmente qualificado da máquina local.</span><span class="sxs-lookup"><span data-stu-id="08501-176">**QoE Archive SQL Server Name:** This is read-only field and fixed to the fully qualified domain name of the local machine.</span></span> <span data-ttu-id="08501-177">Cubo pode ser instalado somente da máquina que tenha um banco de dados de arquivamento de QoE (nota.</span><span class="sxs-lookup"><span data-stu-id="08501-177">Cube can be installed only from the machine that has QoE Archive database (Note.</span></span> <span data-ttu-id="08501-178">Próprio cubo pode ser instalado em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="08501-178">Cube itself may be installed on a remote machine.</span></span> <span data-ttu-id="08501-179">Veja abaixo)</span><span class="sxs-lookup"><span data-stu-id="08501-179">See below)</span></span>
    
   - <span data-ttu-id="08501-180">**Arquivamento de QoE instância do SQL Server:** Nome de instância do SQL Server para onde se encontra o banco de dados de arquivo morto de QoE.</span><span class="sxs-lookup"><span data-stu-id="08501-180">**QoE Archive SQL Server Instance:** SQL Server instance name for where the QoE Archive DB is located.</span></span> <span data-ttu-id="08501-181">Para especificar uma instância do SQL Server padrão, deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="08501-181">To specify a default SQL Server instance, leave this field blank.</span></span> <span data-ttu-id="08501-182">Para especificar uma instância nomeada do SQL Server, insira o nome da instância (por exemplo, o nome após o "\").</span><span class="sxs-lookup"><span data-stu-id="08501-182">To specify a named SQL Server instance, enter the instance name (e.g. the name after the "\").</span></span> <span data-ttu-id="08501-183">Se o componente de arquivo morto de QoE foi selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração de arquivamento de QoE.</span><span class="sxs-lookup"><span data-stu-id="08501-183">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
   - <span data-ttu-id="08501-184">**Cubos do Analysis Server:** Nome de instância do SQL Server Analysis Service para onde o cubo deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="08501-184">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is to be created.</span></span> <span data-ttu-id="08501-185">Isso pode ser uma máquina diferente, mas o usuário de instalação deve ser um membro do grupo Administradores de servidor da instância do SQL Server Analysis Service de destino.</span><span class="sxs-lookup"><span data-stu-id="08501-185">This can be a different machine but the installing user has to be a member of Server administrators of the target SQL Server Analysis Service instance.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="08501-186">Para obter mais informações sobre como configurar permissões de administrador do servidor de serviços de análise, consulte [Conceder permissões de administrador do servidor (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span><span class="sxs-lookup"><span data-stu-id="08501-186">For more information about configuring Analysis Services Server Administrator Permissions, see [Grant Server Administrator Permissions (Analysis Services)](https://msdn.microsoft.com/en-us/library/ms174561.aspx)</span></span>
  
   - <span data-ttu-id="08501-187">**Use várias partições:** O padrão é definido como "Vários partição", que requer a edição de Business Intelligence ou Enterprise edition do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08501-187">**Use Multiple Partitions:** The default is set to "Multiple partition", which requires Business Intelligence edition or Enterprise edition of SQL Server.</span></span> <span data-ttu-id="08501-188">Para o Standard edition, selecione a opção de "Única partição".</span><span class="sxs-lookup"><span data-stu-id="08501-188">For Standard edition, select "Single Partition" option.</span></span> <span data-ttu-id="08501-189">Observe que o desempenho de processamento de cubo pode ser afetado se única partição for usada.</span><span class="sxs-lookup"><span data-stu-id="08501-189">Note that cube processing performance may be impacted if Single Partition is used .</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="08501-190">A seleção da opção usar várias partições não pode ser alterada depois que terminar a instalação.</span><span class="sxs-lookup"><span data-stu-id="08501-190">The selection for Use Multiple Partitions option cannot be changed once Setup completes.</span></span> <span data-ttu-id="08501-191">Para alterá-lo, o cubo de recurso deve ser o primeiro desinstalada e então reinstalado usando a opção "Alterar" no painel de controle.</span><span class="sxs-lookup"><span data-stu-id="08501-191">In order to change it, the Cube feature needs to be first uninstalled and then reinstalled using "Change" option in Control Panel.</span></span>
  
   - <span data-ttu-id="08501-192">**User - nome de usuário de cubos &amp; senha:** Nome de conta de serviço de domínio e a senha (mascaradas) que acionará o processamento do cubo.</span><span class="sxs-lookup"><span data-stu-id="08501-192">**Cube User - User Name &amp; Password:** Domain service account name and password (masked) that will trigger the cube processing.</span></span> <span data-ttu-id="08501-193">Se o componente de arquivo morto de QoE foi selecionado para a instalação, esse campo será preenchido com o valor fornecido na página Configuração de arquivamento para o usuário de trabalho de agente do SQL, mas recomendamos que você especificar uma conta de serviço de domínio diferente para que a instalação pode conceder a privilégios mínimos necessários a ela.</span><span class="sxs-lookup"><span data-stu-id="08501-193">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the Archive Configuration page for the SQL Agent Job User, but we recommend specifying a different domain service account so that Setup can grant the least required privilege to it.</span></span>
    
9. <span data-ttu-id="08501-194">Quando você clica em seguida, outra round de validação será realizada e qualquer problema seja relatado.</span><span class="sxs-lookup"><span data-stu-id="08501-194">When clicking next, another round of validation will be performed and any issue will be reported.</span></span> <span data-ttu-id="08501-195">Após a conclusão bem-sucedida da validação, o instalador irão para a página de configuração de Portal.</span><span class="sxs-lookup"><span data-stu-id="08501-195">Upon successful completion of the validation, the installer will go to the Portal Configuration page.</span></span> 
    
10. <span data-ttu-id="08501-196">Na página Configuração do Portal, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="08501-196">At Portal Configuration page, provide the following information:</span></span>
    
    - <span data-ttu-id="08501-197">**Arquivamento de QoE SQL Server:** Nome de instância do SQL Server para onde se encontra o banco de dados de arquivo morto de QoE.</span><span class="sxs-lookup"><span data-stu-id="08501-197">**QoE Archive SQL Server:** SQL Server instance name for where the QoE Archive database is located.</span></span> <span data-ttu-id="08501-198">Observe que, ao contrário da página de configuração de arquivamento do QoE e a página Configuração do cubo, o nome da máquina não for corrigido e deve ser fornecido.</span><span class="sxs-lookup"><span data-stu-id="08501-198">Note that unlike the QoE Archive Configuration page and the Cube Configuration page, the machine name is not fixed and must be provided.</span></span> <span data-ttu-id="08501-199">Se o componente de arquivo morto de QoE foi selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração de arquivamento de QoE.</span><span class="sxs-lookup"><span data-stu-id="08501-199">If QoE Archive component was selected for the install, this field will be pre-populated with the value provided on the QoE Archive Configuration page.</span></span>
    
    - <span data-ttu-id="08501-200">**Cubos do Analysis Server:** Nome de instância do SQL Server Analysis Service para onde se encontra o cubo.</span><span class="sxs-lookup"><span data-stu-id="08501-200">**Cube Analysis Server:** SQL Server Analysis Service instance name for where the cube is located.</span></span> <span data-ttu-id="08501-201">Se o componente de cubo foi selecionado para a instalação, esse campo será pré-preenchido com o valor fornecido na página Configuração do cubo.</span><span class="sxs-lookup"><span data-stu-id="08501-201">If Cube component was selected for the install, this field will be pre-populated with the value provided on the Cube Configuration page.</span></span>
    
    - <span data-ttu-id="08501-202">**Repositório SQL Server:** Nome da instância do SQL Server onde o banco de dados do repositório deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="08501-202">**Repository SQL Server:** SQL Server instance name where the Repository database is to be created.</span></span> <span data-ttu-id="08501-203">Se o nome da instância do SQL Server para onde se encontra o banco de dados de arquivo morto de QoE foram fornecido anteriormente na configuração (em outros componentes), esse campo será pré-preenchido com o nome da instância de QoE Archive DB SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08501-203">If the SQL Server instance name for where the QoE Archive database is located has been provided earlier in the setup (in other components), this field will be pre-populated with the QoE Archive DB SQL Server instance name.</span></span> <span data-ttu-id="08501-204">Isso pode ser qualquer instância do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08501-204">This can be any SQL Server instance.</span></span>
    
    - <span data-ttu-id="08501-205">**Banco de dados de repositório:** Por padrão, a opção é definida como "Criar novo banco de dados".</span><span class="sxs-lookup"><span data-stu-id="08501-205">**Repository Database:** By default the option is set to "Create new database".</span></span> <span data-ttu-id="08501-206">Desde que não há suporte para a atualização do banco de dados do repositório, a única circunstância sob a qual a opção "Usar o banco de dados existente" pode ser usada é se o banco de dados do repositório existente tem o mesmo esquema que a compilação seja instalado.</span><span class="sxs-lookup"><span data-stu-id="08501-206">Since Repository DB upgrade is not supported, the only circumstance under which the "Use existing database" option can be used is if the existing Repository DB has the same schema as the build to be installed.</span></span>
    
    - <span data-ttu-id="08501-207">**Usuário do Pool de aplicativos do IIS - nome de usuário &amp; senha:** A conta que deve ser executadas sob o pool de aplicativos do IIS.</span><span class="sxs-lookup"><span data-stu-id="08501-207">**IIS App Pool User - User Name &amp; Password:** The account that the IIS application pool should execute under.</span></span> <span data-ttu-id="08501-208">Os campos nome de usuário e senha estará esmaecidos se as contas de sistema interno forem selecionadas.</span><span class="sxs-lookup"><span data-stu-id="08501-208">The User Name and Password fields will be grayed out if built-in system accounts are selected.</span></span> <span data-ttu-id="08501-209">Esses campos só serão ativados se "Other" está selecionada na caixa suspensa para que o usuário pode digitar as informações de conta de serviço de domínio.</span><span class="sxs-lookup"><span data-stu-id="08501-209">These fields will only be enabled if "Other" is selected from the drop down box so the user can enter the domain service account information.</span></span>
    
11. <span data-ttu-id="08501-210">Quando você clica em seguida, será feito o round final de validação para garantir que as instâncias do SQL Server são acessíveis usando as credenciais fornecidas e que o IIS está disponível na máquina.</span><span class="sxs-lookup"><span data-stu-id="08501-210">When clicking next, the final round of validation will be done to ensure that the SQL Server instances are accessible using the credentials provided and that IIS is available on the machine.</span></span> <span data-ttu-id="08501-211">Após a conclusão bem-sucedida da validação, o instalador prosseguirá com a instalação.</span><span class="sxs-lookup"><span data-stu-id="08501-211">Upon successful completion of the validation, the installer will proceed with the setup.</span></span> 
    
<span data-ttu-id="08501-212">O instalador é feito, provavelmente o trabalho do SQL Server Agent ficará em andamento, fazendo o carregamento inicial dos dados QoE e o processamento do cubo.</span><span class="sxs-lookup"><span data-stu-id="08501-212">When the installer is done, most likely the SQL Server Agent job will be in progress, doing the initial load of the QoE data and the cube processing.</span></span> <span data-ttu-id="08501-213">Dependendo da quantidade de dados de QoE, o portal não terá dados disponíveis para exibição ainda.</span><span class="sxs-lookup"><span data-stu-id="08501-213">Depending on the amount of data in QoE, the portal will not have data available for viewing yet.</span></span> <span data-ttu-id="08501-214">Para verificar o status da carga de dados e processamento de cubo, vá para `http://<machinename>/CQD/#/Health`.</span><span class="sxs-lookup"><span data-stu-id="08501-214">To check on the status of the data load and cube processing, go to  `http://<machinename>/CQD/#/Health`.</span></span> 
> [!NOTE]
> <span data-ttu-id="08501-215">Observe que a URL para a verificação do status do processamento de cubo download diferencia maiusculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="08501-215">Note that the URL for checking the status of the download cube processing is case sensitive.</span></span> <span data-ttu-id="08501-216">Se você digitar 'integridade' a URL não funcionará.</span><span class="sxs-lookup"><span data-stu-id="08501-216">If you enter 'health' the URL will not work.</span></span> <span data-ttu-id="08501-217">Você deve inserir integridade no final da URL com uma letra maiuscula H.</span><span class="sxs-lookup"><span data-stu-id="08501-217">You must enter 'Health' at the end of the URL with a capital H.</span></span> 
  
<span data-ttu-id="08501-218">Mensagens de log detalhado serão exibidas se o modo de depuração está habilitado.</span><span class="sxs-lookup"><span data-stu-id="08501-218">Detailed log messages will be shown if debug mode is enabled.</span></span> <span data-ttu-id="08501-219">Para habilitar o modo de depuração, vá para **%SYSTEMDRIVE%\Program Files\Skype para negócios 2015 CQD\QoEDataService\web.config**e atualizar a seguinte linha para que o valor é definido como **True**:</span><span class="sxs-lookup"><span data-stu-id="08501-219">To enable debug mode, go to **%SYSTEMDRIVE%\Program Files\Skype For Business 2015 CQD\QoEDataService\web.config**, and update the following line so the value is set to **True**:</span></span>

```
<add key="QoEDataLib.DebugMode" value="True" /> 
```

<span data-ttu-id="08501-220">A página de portal principal é acessível via `http://<machinename>/CQD`.</span><span class="sxs-lookup"><span data-stu-id="08501-220">The main portal page is accessible via  `http://<machinename>/CQD`.</span></span> 
## <a name="managing-user-access-for-the-portal"></a><span data-ttu-id="08501-221">Gerenciando o acesso de usuário para o Portal</span><span class="sxs-lookup"><span data-stu-id="08501-221">Managing User Access for the Portal</span></span>

<span data-ttu-id="08501-222">Para gerenciar a autorização de usuários ao Portal, recomendamos o uso de autorização de URL, que foi introduzido no IIS 7.0.</span><span class="sxs-lookup"><span data-stu-id="08501-222">For managing user authorization to the Portal, we recommend using URL Authorization, which was introduced in IIS 7.0.</span></span> <span data-ttu-id="08501-223">Para obter mais informações sobre a segurança do IIS, consulte [Noções básicas sobre o IIS 7.0 a autorização de URL ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span><span class="sxs-lookup"><span data-stu-id="08501-223">For more information on IIS security, see [Understanding IIS 7.0 URL Authorization ](https://www.iis.net/learn/manage/configuring-security/understanding-iis-url-authorization).</span></span>
  
<span data-ttu-id="08501-224">Qualquer aplicativo web de site ou web herdam o padrão de autorização de URL configurados para o IIS inteira, que geralmente são "Permitir que todos os usuários".</span><span class="sxs-lookup"><span data-stu-id="08501-224">Any web site or web application inherit the default URL Authorization configured for the entire IIS, which is typically "Allow All Users".</span></span> <span data-ttu-id="08501-225">Se precisar de acesso ao Portal ser mais restritivo, então os administradores podem conceder acesso aos apenas o grupo específico de usuários por meio da edição "Regras de autorização".</span><span class="sxs-lookup"><span data-stu-id="08501-225">If access to the Portal needs to be more restrictive, then administrators can grant access to only the specific group of users by editing the "Authorization Rules".</span></span>
  
![Implantar Qualidade da Chamada - Regras de Autorização no IIS](../../media/0da80c28-58fe-4aca-94b4-db684389468c.png)
  
> [!NOTE]
> <span data-ttu-id="08501-227">O ícone de regras de autorização não é deve ser confundido com a "autorização .NET" sob a seção ASP.NET, que é um mecanismo de autorização diferentes.</span><span class="sxs-lookup"><span data-stu-id="08501-227">The Authorization Rules icon is not to be confused with the ".NET Authorization" under the ASP.NET section, which is a different authorization mechanism.</span></span> 
  
<span data-ttu-id="08501-228">Os administradores devem primeiro remover a regra herdadas "permitir que todos os usuários".</span><span class="sxs-lookup"><span data-stu-id="08501-228">Administrators should first remove the inherited "Allow All Users" rule.</span></span> <span data-ttu-id="08501-229">Isso impede que os usuários não autorizados acessar o Portal.</span><span class="sxs-lookup"><span data-stu-id="08501-229">This prevents any non-authorized users from accessing the Portal.</span></span>
  
![Implantar CQD](../../media/fa17ad19-d303-40f8-8324-d13fd67936ab.png)
  
<span data-ttu-id="08501-231">Em seguida, os administradores devem adicionar novas regras permitir e conceder a permissão para acessar o Portal a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="08501-231">Next, administrators should add new Allow Rules and give specific users the permission to access the Portal.</span></span> <span data-ttu-id="08501-232">É recomendável que um grupo local denominado "CQDPortalUsers" ser criado para gerenciar os usuários.</span><span class="sxs-lookup"><span data-stu-id="08501-232">It is recommended that a local Group called "CQDPortalUsers" be created to manage the users.</span></span>
  
![Implantar Painel de Qualidade da Chamada](../../media/8cfdc141-ec89-4552-921b-53196f497cbf.png)
  
<span data-ttu-id="08501-234">Os detalhes de configuração são armazenados no Web. config localizado no diretório de físico do Portal.</span><span class="sxs-lookup"><span data-stu-id="08501-234">The configuration details are stored in the web.config located at the Portal's physical directory.</span></span>
  
```
<?xml version="1.0" encoding="UTF-8"?> <configuration> <system.webServer> <security> <authorization> <remove users="*" roles="" verbs="" /> <add accessType="Allow" roles="CQDPortalUsers" /> </authorization> </security> </system.webServer> </configuration> 
```

<span data-ttu-id="08501-235">A próxima etapa é configurar o painel do CQD.</span><span class="sxs-lookup"><span data-stu-id="08501-235">The next step is to configure the dashboard of the CQD.</span></span> <span data-ttu-id="08501-236">Depois que os usuários são autenticados pelo IIS, eles terão que tenha permissões de arquivo no diretório CQD para acessar o conteúdo de portal da web.</span><span class="sxs-lookup"><span data-stu-id="08501-236">After users are authenticated by IIS, they will have to have file permissions on the CQD directory in order to access the web portal content.</span></span> <span data-ttu-id="08501-237">É possível alterar as ACLs por meio da guia de segurança das propriedades do diretório CQD para adicionar usuários individuais ou grupos; No entanto, a abordagem recomendada é deixar as permissões de arquivo inalterada.</span><span class="sxs-lookup"><span data-stu-id="08501-237">It is possible to change the ACLs through the security tab of the CQD directory properties to add individual users or groups; however the recommended approach is to leave the file permissions untouched.</span></span> <span data-ttu-id="08501-238">Em vez disso, altere a configuração de IIS para usar o processo de trabalho do IIS para acessar o diretório CQD não importa qual o usuário é autenticado.</span><span class="sxs-lookup"><span data-stu-id="08501-238">Instead, change the IIS setting to use the IIS worker process to access the CQD directory no matter which user is authenticated.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="08501-239">É importante apenas alterar essa configuração para o aplicativo CQD e não para os dois aplicativos de API: QoEDataService e QoERepositoryService.</span><span class="sxs-lookup"><span data-stu-id="08501-239">It is important to only change this setting for the CQD application, and not for the two API applications: QoEDataService and QoERepositoryService.</span></span> 
  
## <a name="configuring-file-access-for-the-cqd-dashboard"></a><span data-ttu-id="08501-240">Configurando o acesso a arquivos para o CQD (painel)</span><span class="sxs-lookup"><span data-stu-id="08501-240">Configuring File Access for the CQD (Dashboard)</span></span>

1. <span data-ttu-id="08501-241">Abra o Editor de configuração para CQD.</span><span class="sxs-lookup"><span data-stu-id="08501-241">Open the Configuration Editor for CQD.</span></span>
    
     ![Implantar Painel de Qualidade da Chamada](../../media/544056eb-3090-434e-bae6-321c984029fa.png)
  
2. <span data-ttu-id="08501-243">Na seção, escolha **system.webServer/serverRuntime**.</span><span class="sxs-lookup"><span data-stu-id="08501-243">Under Section, choose **system.webServer/serverRuntime**.</span></span>
    
     ![Implantar Painel de Qualidade da Chamada](../../media/b0af0e56-21b0-45dd-b610-5381b39319d3.png)
  
3. <span data-ttu-id="08501-245">Alterar authenticatedUserOverride para **UseWorkerProcessUser**.</span><span class="sxs-lookup"><span data-stu-id="08501-245">Change authenticatedUserOverride to **UseWorkerProcessUser**.</span></span>
    
     ![Implantar Painel de Qualidade da Chamada - Editor de Configuração](../../media/a7c127f5-9a90-4710-afba-1d1e588efb37.png)
  
4. <span data-ttu-id="08501-247">Clique em **Aplicar** no lado direito da página.</span><span class="sxs-lookup"><span data-stu-id="08501-247">Click **Apply** on the right-hand side of the page.</span></span>
    
## <a name="known-issues"></a><span data-ttu-id="08501-248">Problemas conhecidos</span><span class="sxs-lookup"><span data-stu-id="08501-248">Known Issues</span></span>

<span data-ttu-id="08501-249">Em casos raros, o instalador falha para criar as configurações corretas no IIS.</span><span class="sxs-lookup"><span data-stu-id="08501-249">In rare cases, the installer fails to create the correct settings in IIS.</span></span> <span data-ttu-id="08501-250">Alteração manual é necessária para permitir que os usuários acesse o CQD.</span><span class="sxs-lookup"><span data-stu-id="08501-250">Manual change is required to allow users to log into the CQD.</span></span> <span data-ttu-id="08501-251">Se os usuários estiverem tendo problemas de logon, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="08501-251">If users are having trouble logging in, please follow these steps:</span></span>
  
1. <span data-ttu-id="08501-252">Abra o Gerenciador do IIS para cima e navegue para o Default Web Site.</span><span class="sxs-lookup"><span data-stu-id="08501-252">Open up IIS Manager, and navigate to Default Web Site.</span></span>
    
     ![Implantar Painel de Qualidade da Chamada](../../media/dc6007aa-870b-4d70-867d-32ffd937063b.png)
  
2. <span data-ttu-id="08501-254">Clique em "Autenticação".</span><span class="sxs-lookup"><span data-stu-id="08501-254">Click on "Authentication".</span></span> <span data-ttu-id="08501-255">Se o "Autenticação anônima", "ASP.NET Impersonation", "Autenticação do formulário" e "Autenticação do Windows" não coincidem com as configurações mostradas abaixo, manualmente alterá-los para coincidir com as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="08501-255">If the "Anonymous Authentication", "ASP.NET Impersonation", "Form Authentication", and "Windows Authentication" do not match the settings shown below, manually change them to match the settings below.</span></span> <span data-ttu-id="08501-256">Todos os outros mecanismos de autenticação devem ser desabilitados.</span><span class="sxs-lookup"><span data-stu-id="08501-256">All other authentication mechanisms should be disabled.</span></span>
    
     ![Implantar Painel de Qualidade da Chamada](../../media/5d9e38fb-8a50-41a2-a423-3ce983a83d0c.png)
  
3. <span data-ttu-id="08501-258">Para "Autenticação do Windows", clique em configurações avançadas no lado direito.</span><span class="sxs-lookup"><span data-stu-id="08501-258">For "Windows Authentication", click on Advanced Settings on the right-hand side.</span></span>
    
     ![Implantar Painel de Qualidade da Chamada](../../media/cad29486-df40-4cc9-82f3-bbdaca52d9ca.png)
  
4. <span data-ttu-id="08501-260">Defina "Extended Protection" para aceitar e marque a caixa "autenticação de modo Kernel Enable".</span><span class="sxs-lookup"><span data-stu-id="08501-260">Set "Extended Protection" to Accept and check the "Enable Kernel-mode authentication" box.</span></span>
    
     ![Implantar Painel de Qualidade da Chamada](../../media/0ab2dda1-0001-4747-8cfc-072e9368b6cb.png)
  
5. <span data-ttu-id="08501-262">Repita as etapas acima para cada uma das entradas "CQD", "QoEDataService" e "QoERepositoryService" abaixo "Site padrão".</span><span class="sxs-lookup"><span data-stu-id="08501-262">Repeat the above steps for each of the "CQD", "QoEDataService", and "QoERepositoryService" entries below "Default Web Site".</span></span>
    
<span data-ttu-id="08501-263">Para ligações de porta HTTP e HTTPS, o instalador criará ligações de porta em que os números de porta padrão (porta 80 para HTTP) e a porta 443 para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="08501-263">For HTTP and HTTPS port bindings the installer will create port bindings on the default port numbers (port 80 for HTTP and port 443 for HTTPS).</span></span> <span data-ttu-id="08501-264">Se não houver outro site na máquina que usa essas ligações, haverá um conflito e o comportamento do IIS não pode ser previsto.</span><span class="sxs-lookup"><span data-stu-id="08501-264">If there is another website on the machine that uses these bindings, there will be a conflict and the IIS behavior cannot be predicted.</span></span> <span data-ttu-id="08501-265">Certifique-se de que não há outros sites são mapeados para portas 80 e 443 antes de instalar o CQD é a melhor maneira de evitar esse problema.</span><span class="sxs-lookup"><span data-stu-id="08501-265">The best way to avoid this problem is to make sure that no other websites are mapped to ports 80 and 443 before installing CQD.</span></span> 
  
<span data-ttu-id="08501-266">Para habilitar o SSL/TLS no IIS e forçar os usuários a se conectar via HTTPS segura, em vez de HTTP:</span><span class="sxs-lookup"><span data-stu-id="08501-266">To enable SSL/TLS in IIS and force users to connect via secure HTTPS instead of HTTP:</span></span>
  
1. <span data-ttu-id="08501-267">Configurar o protocolo SSL no IIS, consulte [Configuring Secure Sockets Layer no IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="08501-267">Configure Secure Sockets Layer in IIS, see [Configuring Secure Sockets Layer in IIS 7](https://technet.microsoft.com/en-us/library/cc771438%28v=ws.10%29.aspx).</span></span> <span data-ttu-id="08501-268">Depois de concluído, substitua `http` com `https`.</span><span class="sxs-lookup"><span data-stu-id="08501-268">Once done, replace  `http` with `https`.</span></span>
    
2. <span data-ttu-id="08501-269">Para obter instruções sobre como ativar TLS as conexões do SQL Server, consulte [como habilitar a criptografia SSL para uma instância do SQL Server usando o Console de gerenciamento Microsoft ](https://support.microsoft.com/en-us/kb/316898/).</span><span class="sxs-lookup"><span data-stu-id="08501-269">For instructions on enabling TLS in the SQL Server connections, see [How to enable SSL encryption for an instance of SQL Server by using Microsoft Management Console ](https://support.microsoft.com/en-us/kb/316898/).</span></span>
    
## <a name="cube-sync-fails"></a><span data-ttu-id="08501-270">Falha na sincronização de cubo</span><span class="sxs-lookup"><span data-stu-id="08501-270">Cube Sync Fails</span></span>

<span data-ttu-id="08501-271">QoEMetrics podem conter alguns registros inválidos com base no relógio do usuário final.</span><span class="sxs-lookup"><span data-stu-id="08501-271">QoEMetrics may contain some invalid records based on end user clocks.</span></span> <span data-ttu-id="08501-272">Se a diferença de horário for maior do que 60 anos, a importação de cubo falhará.</span><span class="sxs-lookup"><span data-stu-id="08501-272">If the time skew is greater than 60 yrs, the cube import will fail.</span></span>
  
 <span data-ttu-id="08501-273">Verifique os Min e Max StartTime/EndTime, usando as seleções abaixo.</span><span class="sxs-lookup"><span data-stu-id="08501-273">Check the Min and Max StartTime/EndTime using the selections below.</span></span> <span data-ttu-id="08501-274">Procurar e excluir registros no futuro extremo passado e muito distante, pode ser desconsiderada, e eles serão interrompidos backup os processos de sincronização.</span><span class="sxs-lookup"><span data-stu-id="08501-274">Look for and delete records in the far past and very distant future, they can be disregarded and they will break up the sync processes.</span></span>
  
- <span data-ttu-id="08501-275">Selecione MIN(StartTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="08501-275">Select MIN(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="08501-276">Selecione MAX(StartTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="08501-276">Select MAX(StartTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="08501-277">Selecione MIN(EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="08501-277">Select MIN(EndTime) FROM CqdPartitionedStreamView</span></span>
    
- <span data-ttu-id="08501-278">Selecione MAX(EndTime) de CqdPartitionedStreamView</span><span class="sxs-lookup"><span data-stu-id="08501-278">Select MAX(EndTime) FROM CqdPartitionedStreamView</span></span>
    
## <a name="post-install-tasks"></a><span data-ttu-id="08501-279">Tarefas pós-instalação</span><span class="sxs-lookup"><span data-stu-id="08501-279">Post-install tasks</span></span>

### <a name="importing-buildings-and-networks"></a><span data-ttu-id="08501-280">Importando prédios e redes</span><span class="sxs-lookup"><span data-stu-id="08501-280">Importing Buildings and Networks</span></span>

<span data-ttu-id="08501-281">Após instalar CQD, execute as seguintes tarefas de configuração:</span><span class="sxs-lookup"><span data-stu-id="08501-281">After Installing CQD, perform the following configuration tasks:</span></span>
  
1. <span data-ttu-id="08501-282">Definem os tipos de construção (recomendados)</span><span class="sxs-lookup"><span data-stu-id="08501-282">Define Building types (recommended)</span></span>
    
2. <span data-ttu-id="08501-283">Definem os tipos de propriedade de construção (recomendados)</span><span class="sxs-lookup"><span data-stu-id="08501-283">Define Building Ownership types (recommended)</span></span>
    
3. <span data-ttu-id="08501-284">Definem os tipos de rede (altamente recomendados)</span><span class="sxs-lookup"><span data-stu-id="08501-284">Define Network types (highly recommended)</span></span>
    
4. <span data-ttu-id="08501-285">Prédios importação (recomendado)</span><span class="sxs-lookup"><span data-stu-id="08501-285">Import Buildings (recommended)</span></span>
    
5. <span data-ttu-id="08501-286">Sub-redes de importação (recomendados)</span><span class="sxs-lookup"><span data-stu-id="08501-286">Import Subnets (recommended)</span></span>
    
### <a name="define-building-types"></a><span data-ttu-id="08501-287">Definem os tipos de construção</span><span class="sxs-lookup"><span data-stu-id="08501-287">Define Building Types</span></span>

<span data-ttu-id="08501-288">Tipos de construção são usados para descrever as definições de prédios diferentes ou os tipos de dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="08501-288">Building types are used to describe the different buildings definitions or types within your organization.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="08501-289">Esta etapa é opcional, mas recomendado.</span><span class="sxs-lookup"><span data-stu-id="08501-289">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="08501-290">Exemplos</span><span class="sxs-lookup"><span data-stu-id="08501-290">Examples</span></span>
  
- <span data-ttu-id="08501-291">Sede</span><span class="sxs-lookup"><span data-stu-id="08501-291">Headquarters</span></span>
    
- <span data-ttu-id="08501-292">Escritórios remotos</span><span class="sxs-lookup"><span data-stu-id="08501-292">Remote Office</span></span>
    
- <span data-ttu-id="08501-293">Local de risco de junção</span><span class="sxs-lookup"><span data-stu-id="08501-293">Joint-venture location</span></span>
    
 <span data-ttu-id="08501-294">**Sintaxe SQL de amostra**</span><span class="sxs-lookup"><span data-stu-id="08501-294">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingType]
([BuildingTypeId],
[BuildingTypeDesc])
VALUES
(1, 
'Headquarters')   
```

<span data-ttu-id="08501-295">Os parâmetros BuildingTypeId e BuildingTypeDesc são necessários.</span><span class="sxs-lookup"><span data-stu-id="08501-295">The BuildingTypeId and BuildingTypeDesc parameters are required.</span></span>
  
### <a name="define-building-ownership-types"></a><span data-ttu-id="08501-296">Definir os tipos de propriedade de construção</span><span class="sxs-lookup"><span data-stu-id="08501-296">Define Building Ownership Types</span></span>

<span data-ttu-id="08501-297">Tipos de propriedade são usados para distinguir os ativos de arrendada versus pertencentes.</span><span class="sxs-lookup"><span data-stu-id="08501-297">Ownership types are used to distinguish owned vs leased assets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08501-298">Esta etapa é opcional, mas recomendado.</span><span class="sxs-lookup"><span data-stu-id="08501-298">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="08501-299">Exemplos</span><span class="sxs-lookup"><span data-stu-id="08501-299">Examples</span></span>
  
- <span data-ttu-id="08501-300">Não-RE Contoso concessão&amp;F</span><span class="sxs-lookup"><span data-stu-id="08501-300">Contoso Leased non-RE&amp;F</span></span>
    
- <span data-ttu-id="08501-301">Contoso concessão RE&amp;F</span><span class="sxs-lookup"><span data-stu-id="08501-301">Contoso Leased RE&amp;F</span></span>
    
- <span data-ttu-id="08501-302">Pertencentes a Contoso</span><span class="sxs-lookup"><span data-stu-id="08501-302">Contoso Owned</span></span>
    
- <span data-ttu-id="08501-303">Subsidiária concedida</span><span class="sxs-lookup"><span data-stu-id="08501-303">Subsidiary Leased</span></span>
    
 <span data-ttu-id="08501-304">**Sintaxe SQL de amostra**</span><span class="sxs-lookup"><span data-stu-id="08501-304">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO
[dbo].[CqdBuildingOwnershipType]
([OwnershipTypeId],
[OwnershipTypeDesc],
)

VALUES
(1,
'Contoso Owned',
)
```

<span data-ttu-id="08501-305">Os parâmetros OwnershipTypeId e OwnershipTypeDesc são necessários.</span><span class="sxs-lookup"><span data-stu-id="08501-305">The OwnershipTypeId and OwnershipTypeDesc parameters are required.</span></span> 
  
### <a name="define-network-names"></a><span data-ttu-id="08501-306">Definir os nomes de rede</span><span class="sxs-lookup"><span data-stu-id="08501-306">Define Network Names</span></span>

<span data-ttu-id="08501-307">Tipos de rede são usados para descrever os tipos diferentes de redes dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="08501-307">Network Types are used to describe different types of networks within the organization.</span></span> <span data-ttu-id="08501-308">Isso oferece a capacidade de filtrar (ou filtrar) tipos específicos de rede.</span><span class="sxs-lookup"><span data-stu-id="08501-308">This gives you the ability to filter on (or filter out) specific Network Types.</span></span>
  
> [!NOTE]
> <span data-ttu-id="08501-309">É altamente recomendável para definir nomes de rede, mas isso é opcional.</span><span class="sxs-lookup"><span data-stu-id="08501-309">It is highly recommended to define Network Names, but it is optional.</span></span> <span data-ttu-id="08501-310">Se você decidir não definir nomes de rede, certifique-se de que a cada entrada de CqdNetwork tem um BuildingId 0.</span><span class="sxs-lookup"><span data-stu-id="08501-310">If you decide to not define network names, ensure the each CqdNetwork entry has a BuildingId of 0.</span></span> 
  
<span data-ttu-id="08501-311">Exemplos</span><span class="sxs-lookup"><span data-stu-id="08501-311">Examples</span></span>
  
- <span data-ttu-id="08501-312">VPN</span><span class="sxs-lookup"><span data-stu-id="08501-312">VPN</span></span>
    
- <span data-ttu-id="08501-313">LABORATÓRIO</span><span class="sxs-lookup"><span data-stu-id="08501-313">LAB</span></span>
    
 <span data-ttu-id="08501-314">**Sintaxe SQL de amostra**</span><span class="sxs-lookup"><span data-stu-id="08501-314">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetworkName] 
( [NetworkName]
,[NetworkType]
 ) 
VALUES
('VPN','VPN') 
```

<span data-ttu-id="08501-315">Os parâmetros NetworkNameID e NetworkName são necessários, o parâmetro NetworkType é opcional, mas recomendado.</span><span class="sxs-lookup"><span data-stu-id="08501-315">The NetworkNameID and NetworkName parameters are required, the NetworkType parameter is optional but recommended.</span></span>
  
### <a name="import-buildings"></a><span data-ttu-id="08501-316">Importação prédios</span><span class="sxs-lookup"><span data-stu-id="08501-316">Import Buildings</span></span>

<span data-ttu-id="08501-317">Importar prédios proporciona a capacidade de obter criando insights específicos (baixa chamadas por criar nas WiFi/com fio, etc.).</span><span class="sxs-lookup"><span data-stu-id="08501-317">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="08501-318">Esta etapa é opcional, mas recomendado.</span><span class="sxs-lookup"><span data-stu-id="08501-318">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="08501-319">Antes de importar a um novo prédio você já deve ter um BuildingKey predefinido identificado.</span><span class="sxs-lookup"><span data-stu-id="08501-319">Before you Import a new building you should already have a predefined BuildingKey identified.</span></span> <span data-ttu-id="08501-320">Para fazer isso, execute o comando SQL "Selecione MAX(BuildingKey) de CqdBuilding" para identificar o valor atual e adicionar 1 para o resultado.</span><span class="sxs-lookup"><span data-stu-id="08501-320">To do that, issue the "SELECT MAX(BuildingKey) FROM CqdBuilding" SQL command to identify the current value and add 1 to the result.</span></span>
  
 <span data-ttu-id="08501-321">**Sintaxe SQL de amostra**</span><span class="sxs-lookup"><span data-stu-id="08501-321">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="08501-322">O BuildingKey BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parâmetros são necessários, os outros parâmetros são opcionais.</span><span class="sxs-lookup"><span data-stu-id="08501-322">The BuildingKey, BuildingName, BuildingShortName, OwnershipTypeId, BuildingTypeId parameters are required, the other parameters are optional.</span></span>
  
### <a name="import-subnets"></a><span data-ttu-id="08501-323">Importar sub-redes</span><span class="sxs-lookup"><span data-stu-id="08501-323">Import Subnets</span></span>

<span data-ttu-id="08501-324">Importar prédios proporciona a capacidade de obter criando insights específicos (baixa chamadas por criar nas WiFi/com fio, etc.).</span><span class="sxs-lookup"><span data-stu-id="08501-324">Importing Buildings gives you the ability to get building specific insights (poor calls per building on WiFi/Wired, etc.).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="08501-325">Esta etapa é opcional, mas recomendado.</span><span class="sxs-lookup"><span data-stu-id="08501-325">This step is optional, but recommended.</span></span> 
  
<span data-ttu-id="08501-326">Importar sub-redes e mapeá-los para os prédios importados na última etapa.</span><span class="sxs-lookup"><span data-stu-id="08501-326">Import Subnets and map them to the Buildings imported in the last step.</span></span> <span data-ttu-id="08501-327">Se você decidiu não preencher NetworkName, certifique-se de que cada entrada nesta tabela usa uma NetworkNameID 0.</span><span class="sxs-lookup"><span data-stu-id="08501-327">If you decided not to populate NetworkName, ensure each entry in this table uses a NetworkNameID of 0.</span></span>
  
 <span data-ttu-id="08501-328">**Sintaxe SQL de amostra**</span><span class="sxs-lookup"><span data-stu-id="08501-328">**Sample SQL Syntax**</span></span>
  
```
INSERT INTO [dbo].[CqdNetwork] 
([Network]
,[NetworkNameID]
,[BuildingKey]
,[UpdatedDate]
)

VALUES
 ('172.16.254.0',0,1,'2015-11-11')
```

<span data-ttu-id="08501-329">A rede e os parâmetros UpdatedDate serão solicitados, os outros parâmetros são opcionais.</span><span class="sxs-lookup"><span data-stu-id="08501-329">The Network, and UpdatedDate parameters are required, the other parameters are optional.</span></span>
  
### <a name="optional-bssid"></a><span data-ttu-id="08501-330">Opcional: BSSID</span><span class="sxs-lookup"><span data-stu-id="08501-330">Optional: BSSID</span></span>

<span data-ttu-id="08501-331">Preencher informações BSSID oferece correlação de stream WiFi adicional pelo controlador ou de rádio.</span><span class="sxs-lookup"><span data-stu-id="08501-331">Populating BSSID information gives you additional WiFi stream correlation by controller or radio.</span></span> <span data-ttu-id="08501-332">Esse aspecto soma filtragem por meio da criação ou sub-rede.</span><span class="sxs-lookup"><span data-stu-id="08501-332">This is in addition to filtering by building or subnet.</span></span> 
  
 <span data-ttu-id="08501-333">**Sintaxe SQL de amostra**</span><span class="sxs-lookup"><span data-stu-id="08501-333">**Sample SQL Syntax**</span></span>
  
```
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

<span data-ttu-id="08501-334">**Detalhes do CqdBssidTable**</span><span class="sxs-lookup"><span data-stu-id="08501-334">**CqdBssidTable Details**</span></span>

|<span data-ttu-id="08501-335">**Conforme mostrado na CQD**</span><span class="sxs-lookup"><span data-stu-id="08501-335">**As shown in CQD**</span></span>|<span data-ttu-id="08501-336">**Tabela CQDBssid**</span><span class="sxs-lookup"><span data-stu-id="08501-336">**CQDBssid Table**</span></span>|<span data-ttu-id="08501-337">**Entradas de exemplo**</span><span class="sxs-lookup"><span data-stu-id="08501-337">**Example inputs**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="08501-338">AP NName</span><span class="sxs-lookup"><span data-stu-id="08501-338">Ap NName</span></span>  <br/> |<span data-ttu-id="08501-339">AP</span><span class="sxs-lookup"><span data-stu-id="08501-339">AP</span></span>  <br/> |<span data-ttu-id="08501-340">AP1</span><span class="sxs-lookup"><span data-stu-id="08501-340">AP1</span></span>  <br/> |
|<span data-ttu-id="08501-341">BBssid</span><span class="sxs-lookup"><span data-stu-id="08501-341">BBssid</span></span>  <br/> |<span data-ttu-id="08501-342">BSS</span><span class="sxs-lookup"><span data-stu-id="08501-342">BSS</span></span>  <br/> |<span data-ttu-id="08501-343">00-00-00-00-00-00 (você deve usar o fformat delimitado)</span><span class="sxs-lookup"><span data-stu-id="08501-343">00-00-00-00-00-00 (you must use the delimited fformat)</span></span>  <br/> |
|<span data-ttu-id="08501-344">Controlador</span><span class="sxs-lookup"><span data-stu-id="08501-344">Controller</span></span>  <br/> |<span data-ttu-id="08501-345">Edifício</span><span class="sxs-lookup"><span data-stu-id="08501-345">Building</span></span>  <br/> |<span data-ttu-id="08501-346">AP de Aruba 7</span><span class="sxs-lookup"><span data-stu-id="08501-346">Aruba AP 7</span></span>  <br/> |
|<span data-ttu-id="08501-347">Dispositivo</span><span class="sxs-lookup"><span data-stu-id="08501-347">Device</span></span>  <br/> |<span data-ttu-id="08501-348">ess</span><span class="sxs-lookup"><span data-stu-id="08501-348">ess</span></span>  <br/> |<span data-ttu-id="08501-349">Controlador1</span><span class="sxs-lookup"><span data-stu-id="08501-349">Controller1</span></span>  <br/> |
|<span data-ttu-id="08501-350">Rádio</span><span class="sxs-lookup"><span data-stu-id="08501-350">Radio</span></span>  <br/> |<span data-ttu-id="08501-351">phy</span><span class="sxs-lookup"><span data-stu-id="08501-351">phy</span></span>  <br/> |<span data-ttu-id="08501-352">BGn</span><span class="sxs-lookup"><span data-stu-id="08501-352">bgn</span></span>  <br/> |
   
### <a name="processing-the-imported-data"></a><span data-ttu-id="08501-353">Os dados importados de processamento</span><span class="sxs-lookup"><span data-stu-id="08501-353">Processing the imported data</span></span>

<span data-ttu-id="08501-354">Por padrão, depois de importar os dados de construção/rede ele aplicará apenas aos registros gerados depois que ponto no tempo.</span><span class="sxs-lookup"><span data-stu-id="08501-354">By default, after you import building/network data it will only apply to records generated after that point in time.</span></span> 
  
<span data-ttu-id="08501-355">Para marcar todos os registros anteriores com esses novos dados, você precisará executar o procedimento armazenado do CqdUpdateBuilding, conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="08501-355">To tag all the previous records with this new data, you will need to run the CqdUpdateBuilding stored procedure as shown below:</span></span> 
  
<span data-ttu-id="08501-356">Dê a ela a data de seu primeiro registro (identificar que usando o comando Selecionar MIN(StartTime) de SQL CqdPartitionedStreamView), EndDate de amanhã, e então nulo para os valores de duas últimas.</span><span class="sxs-lookup"><span data-stu-id="08501-356">Give it the date of your first record (identify that using the Select MIN(StartTime) FROM CqdPartitionedStreamView SQL command ), an EndDate of tomorrow, then NULL for the last two values.</span></span>
  
<span data-ttu-id="08501-357">Depois que os dados estão associados a dados de fluxo, o cubo SSIS precisa reprocessar todos os registros.</span><span class="sxs-lookup"><span data-stu-id="08501-357">Once the data is associated with stream data, the SSIS Cube needs to reprocess all records.</span></span> <span data-ttu-id="08501-358">Isso também se aplica quando em massa adicionando dados BSSID/ISP.</span><span class="sxs-lookup"><span data-stu-id="08501-358">This also applies when bulk adding BSSID/ISP data.</span></span> <span data-ttu-id="08501-359">Certifique-se de que "Processo completo" está selecionado.</span><span class="sxs-lookup"><span data-stu-id="08501-359">Ensure that "Process Full" is selected.</span></span>
  

