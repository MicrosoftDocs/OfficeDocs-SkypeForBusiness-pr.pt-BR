---
title: Atualização para o Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumo: Saiba como atualizar do Lync Server 2013 para Skype para Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: f3c451e0c1590daab2c6576964c1e1ce5ec3c4ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="d4818-104">Atualização para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d4818-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d4818-105">**Resumo:** Saiba como atualizar do Lync Server 2013 para Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d4818-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="d4818-106">Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="d4818-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="d4818-107">Use os procedimentos neste documento para atualizar do Lync Server 2013 para Skype para Business Server 2015 usando o Skype para o construtor de topologia de servidor de negócios e o novo recurso de atualização in-loco.</span><span class="sxs-lookup"><span data-stu-id="d4818-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="d4818-108">Se você deseja atualizar do Lync Server 2010 ou do Office Communications Server 2007 R2, consulte [Planejar a atualização para Skype para Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="d4818-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="d4818-109">Atualização do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4818-109">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="d4818-110">Atualizando o Lync Server 2013 para Skype para Business Server 2015 envolve instalando o software de pré-requisito, usando o Skype para o construtor de topologia de servidor de negócios para atualizar bancos de dados no pool e o uso do Skype para Business Server In-Place Upgrade em cada um do servidores associados ao pool.</span><span class="sxs-lookup"><span data-stu-id="d4818-110">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="d4818-111">Para completar a atualização, siga as oito etapas descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d4818-111">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="d4818-112">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="d4818-112">Before you begin</span></span>

- <span data-ttu-id="d4818-113">Revise a [Planejar a atualização para Skype para Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="d4818-113">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="d4818-114">Examine os [requisitos de servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4818-114">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="d4818-115">[Instalar os pré-requisitos do Skype para Business Server 2015](install/install-prerequisites.md) .</span><span class="sxs-lookup"><span data-stu-id="d4818-115">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="d4818-116">[Instale o Skype para Business Server 2015](install/install.md) .</span><span class="sxs-lookup"><span data-stu-id="d4818-116">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="d4818-117">Etapa 1: instalar ferramentas do Administrador e baixar a topologia</span><span class="sxs-lookup"><span data-stu-id="d4818-117">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="d4818-118">Conecte-se ao computador na topologia que não tenha o Lync OCSCore ou quaisquer outros componentes do Lync instalados.</span><span class="sxs-lookup"><span data-stu-id="d4818-118">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="d4818-119">A partir do Skype para a mídia de instalação do Business Server 2015, execute **Setup.exe** de **OCS_Volume\Setup\AMD64**.</span><span class="sxs-lookup"><span data-stu-id="d4818-119">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="d4818-120">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d4818-120">Click **Install**.</span></span> 
    
4. <span data-ttu-id="d4818-121">Aceite o contrato de licença.</span><span class="sxs-lookup"><span data-stu-id="d4818-121">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="d4818-122">No Assistente de Implantação, clique em **Instalar ferramenta do Administrador**, e siga as etapas para a instalação.</span><span class="sxs-lookup"><span data-stu-id="d4818-122">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Captura de tela do Assistente de Implantação com link ativado para Instalar Ferramentas de Administrador.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="d4818-124">Na tela Iniciar do Windows, abra Skype do construtor de topologia de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="d4818-124">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="d4818-125">Clique em **Baixar Topologia da implantação existente** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d4818-125">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="d4818-126">Digite um nome para a topologia e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d4818-126">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="d4818-127">Vá para o local onde você salvou a topologia e faça uma cópia dela.</span><span class="sxs-lookup"><span data-stu-id="d4818-127">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="d4818-128">Etapa 2: atualizar e publicar a topologia usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="d4818-128">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="d4818-129">Antes de começar o processo de atualização, todos os serviços devem estar executando para os pools de que planejar a atualização.</span><span class="sxs-lookup"><span data-stu-id="d4818-129">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="d4818-130">Isso porque mudanças na topologia serão replicadas para o banco de dados local dos servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="d4818-130">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="d4818-131">Salve uma cópia do seu arquivo de topologia antes de fazer a atualização.</span><span class="sxs-lookup"><span data-stu-id="d4818-131">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="d4818-132">Após a atualização, você não poderá fazer downgrade a topologia. > se seus serviços estão nos mesmos servidores conforme seus bancos de dados, como o Chat persistente serviço estiver no mesmo servidor de banco de dados de Chat persistente, ignore esta etapa e vá para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="d4818-132">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="d4818-133">Depois de interromper os serviços, execute a atualização in-loco em cada servidor para atualizar os bancos de dados locais.</span><span class="sxs-lookup"><span data-stu-id="d4818-133">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4818-p107">Se a topologia tiver um banco de dados de back-end espelhado, os bancos de dados Principal e Espelhado aparecerão **quando você publicar a topologia** usando o Construtor de Topologias. Certifique-se de que todos os bancos de dados estão em execução no Principal e selecione apenas o Principal, não o Espelhado, ao publicar a topologia. Caso contrário, você verá um aviso após a publicação da topologia.</span><span class="sxs-lookup"><span data-stu-id="d4818-p107">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder. Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="d4818-136">Escolha uma das opções a seguir para atualizar e publicar uma nova topologia usando o Skype para o construtor de topologias do Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d4818-136">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="d4818-137">Depois de concluir as etapas e publicar a topologia atualizada, siga para a Etapa 3 deste tópico.</span><span class="sxs-lookup"><span data-stu-id="d4818-137">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="d4818-138">Opção 1: atualizar um pool isolado de Front-End e associar os repositórios de Monitoramento e Arquivamento</span><span class="sxs-lookup"><span data-stu-id="d4818-138">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="d4818-139">Se o pool que você está atualizando tiver uma dependência de repositório de Monitoramento e Arquivamento, quando você executar as seguintes etapas, o repositório também será atualizado.</span><span class="sxs-lookup"><span data-stu-id="d4818-139">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="d4818-140">No construtor de topologia, do mouse em um pool do Lync Server 2013, selecione **atualizar para o Skype para Business Server 2015**e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="d4818-140">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de tela do menu de atalho com opção de atualização para o Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="d4818-142">No construtor de topologia, clique em **ação** > **Publicar topologia** ou **ação** > **topologia** > **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d4818-142">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Captura de tela do menu Ação com a opção Publicar topologia no Construtor de Topologias.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="d4818-144">Durante a publicação, instale um banco de dados no repositório de Monitoramento e Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="d4818-144">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="d4818-145">Opção 2: Pool de Front-End atualização sem atualizar repositórios de monitoramento e arquivamento</span><span class="sxs-lookup"><span data-stu-id="d4818-145">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="d4818-p109">Se você executar as seguintes etapas, o arquivamento e monitoramento do pool selecionado serão desabilitados. O pool não terá repositórios de Monitoramento e Arquivamento após a atualização.</span><span class="sxs-lookup"><span data-stu-id="d4818-p109">If you use the following steps, archiving and monitoring for the selected pool are disabled. The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="d4818-148">No construtor de topologias, selecione o pool do Lync Server 2013 que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="d4818-148">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="d4818-149">Remova a dependência para os repositórios de arquivamento do Lync Server 2013 e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="d4818-149">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="d4818-150">Vá para a **ação** > **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d4818-150">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="d4818-151">Desmarque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="d4818-151">Clear the **Archiving** check box.</span></span>
    
     ![Captura de tela na caixa de seleção Arquivamento na caixa de diálogo Editar propriedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="d4818-153">Desmarque a caixa de seleção **Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="d4818-153">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra a caixa de seleção Monitoramento.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="d4818-155">Com o botão direito do pool do Lync Server 2013, selecione **atualizar para o Skype para Business Server 2015**e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="d4818-155">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de tela do menu de atalho com opção de atualização para o Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="d4818-157">No construtor de topologia, clique em **ação** > **Publicar topologia** ou **ação** > **topologia** > **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d4818-157">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="d4818-158">Opção 3: Pool de Front-End atualização e associá-lo ao novo Skype para repositórios de negócios, incluindo Server 2015 arquivamento e monitoramento</span><span class="sxs-lookup"><span data-stu-id="d4818-158">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="d4818-159">Se você usar as seguintes etapas, o arquivamento e monitoramento serão interrompidos no repositório anterior e reiniciados no novo repositório que você criou.</span><span class="sxs-lookup"><span data-stu-id="d4818-159">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="d4818-160">No construtor de topologias, selecione o pool do Lync Server 2013 que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="d4818-160">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="d4818-161">Remova a dependência para os repositórios de arquivamento do Lync Server 2013 e monitoramento.</span><span class="sxs-lookup"><span data-stu-id="d4818-161">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="d4818-162">Vá para a **ação** > **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d4818-162">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="d4818-163">Desmarque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="d4818-163">Clear the **Archiving** check box.</span></span>
    
     ![Captura de tela na caixa de seleção Arquivamento na caixa de diálogo Editar propriedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="d4818-165">Desmarque a caixa de seleção **Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="d4818-165">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra a caixa de seleção Monitoramento.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="d4818-167">Com o botão direito do pool do Lync Server 2013, selecione **atualizar para o Skype para Business Server 2015**e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="d4818-167">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de tela do menu de atalho com opção de atualização para o Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="d4818-169">Crie um novo repositório do SQL para Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="d4818-169">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="d4818-170">Selecione o pool e a **ação** > **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d4818-170">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="d4818-171">Marque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="d4818-171">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="d4818-172">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d4818-172">Click **New**.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra o botão Novo na seção Arquivamento.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="d4818-174">Crie um novo repositório do SQL para Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="d4818-174">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="d4818-175">Selecione o pool e a **ação** > **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="d4818-175">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="d4818-176">Marque a caixa de seleção **Monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="d4818-176">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="d4818-177">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d4818-177">Click **New**.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra o botão Novo na seção Monitoramento.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="d4818-179">No construtor de topologia, clique em **ação** > **Publicar topologia** ou **ação** > **topologia** > **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d4818-179">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="d4818-180">Durante a publicação, instale o banco de dados no novo repositório de Monitoramento e Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="d4818-180">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="d4818-181">Etapa 3: aguardar a replicação</span><span class="sxs-lookup"><span data-stu-id="d4818-181">Step 3: Wait for replication</span></span>

<span data-ttu-id="d4818-182">Aguarde alguns instantes até a replicação publicar a topologia atualizada em todos os servidores do ambiente.</span><span class="sxs-lookup"><span data-stu-id="d4818-182">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="d4818-183">Etapa 4: interromper todos os serviços no pool a ser atualizado</span><span class="sxs-lookup"><span data-stu-id="d4818-183">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="d4818-184">Em cada servidor que está servindo o pool que você vai atualizar, execute o seguinte cmdlet do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d4818-184">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```
Disable-CsComputer -Scorch
```

<span data-ttu-id="d4818-185">É recomendável usar Disable-CsComputer, pois será necessário reinicializar o servidor durante o processo de atualização In-loco.</span><span class="sxs-lookup"><span data-stu-id="d4818-185">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="d4818-186">Se você usar o Stop-CsWindowsService, alguns serviços podem reiniciar automaticamente depois de uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="d4818-186">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="d4818-187">Isso pode fazer com que a atualização in-loco não seja bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="d4818-187">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="d4818-188">Etapa 5: atualizar servidores de pools de Front-Ends e de pools não-Front-End</span><span class="sxs-lookup"><span data-stu-id="d4818-188">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="d4818-189">Antes de atualizar instale todos os pré-requisitos novos necessários para Skype para Business Server 2015 que incluem: > pelo menos 32GB de espaço livre antes de tentar uma atualização.</span><span class="sxs-lookup"><span data-stu-id="d4818-189">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="d4818-190">Além disso, certifique-se de que a unidade é uma unidade local fixa, não está conectada por USB ou Firewire, está formatada com o sistema de arquivos NTFS, não será compactada e não contém um arquivo de página. > PowerShell versão 6.2.9200.0 ou posterior. > mais recente Microsoft Lync Server 2013 Atualização cumulativa instalada. > SQL Server 2012 SP1 instalado. > os seguinte KB do instalado (instalado automaticamente se usando o Microsoft Update): > Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="d4818-190">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="d4818-191">Use In-loco para atualização em cada servidor para atualizar o pool de borda, o pool de Front-End, servidor de mediação e o pool de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d4818-191">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="d4818-192">Em cada servidor, execute **Setup.exe** de **OCS_Volume\Setup\amd64** no Skype para a mídia de instalação do Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d4818-192">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="d4818-193">Aceite o contrato de licença e siga os prompts para a atualização In-loco.</span><span class="sxs-lookup"><span data-stu-id="d4818-193">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="d4818-194">Repita essas etapas para cada servidor no pool Front-End e em cada servidor do pool não - Front-End.</span><span class="sxs-lookup"><span data-stu-id="d4818-194">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d4818-195">Você pode ser solicitado a reiniciar o servidor durante a atualização in-loco.</span><span class="sxs-lookup"><span data-stu-id="d4818-195">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="d4818-196">Não tem problema.</span><span class="sxs-lookup"><span data-stu-id="d4818-196">That's ok.</span></span> <span data-ttu-id="d4818-197">Após a reinicialização, a atualização In-loco continuará de onde parou.</span><span class="sxs-lookup"><span data-stu-id="d4818-197">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="d4818-198">Quando a atualização in-loco for concluída com sucesso, você verá a seguinte mensagem.</span><span class="sxs-lookup"><span data-stu-id="d4818-198">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Captura de tela que mostra atualização no local concluída com sucesso.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="d4818-200">Etapa 6: reiniciar serviços em todos os servidores atualizados</span><span class="sxs-lookup"><span data-stu-id="d4818-200">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="d4818-201">Antes de reiniciar os serviços, verifique se %ProgramData%\WindowsFabric não existir em todos os servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="d4818-201">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="d4818-202">Se existir, exclua antes de iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="d4818-202">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="d4818-203">Depois que você tiver atualizado todos os servidores no pool Front-End, reinicie os serviços usando o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d4818-203">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="d4818-p114">Se já houver uma reinicialização de sistema pendente necessária antes de iniciar a execução da atualização in-loco, ela não solicitará a reinicialização quando a instalação for concluída. Isso fará com que algumas exceções de assembly sejam jogadas no primeiro servidor Front-End quando você tentar iniciar os serviços usando o cmdlet Start-CSPool. Para resolver esses erros, reinicie todos os servidores no pool e execute o cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="d4818-p114">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation. This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet. To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="d4818-207">Nos servidores do pool não-Front-End, reinicie os serviços usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d4818-207">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```
  Start-CsWindowsService
  ```

<span data-ttu-id="d4818-208">Depois de clicar em **OK** na página de atualização in-loco, você verá o seguinte lembrete para concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="d4818-208">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Captura de tela que mostra as próximas etapas depois de a atualização no local ser concluída com sucesso.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="d4818-210">Etapa 7: Verificar Skype para funciona da funcionalidade de negócios</span><span class="sxs-lookup"><span data-stu-id="d4818-210">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="d4818-211">Para certificar-se de que a atualização foi bem-sucedida, para o pool que foi atualizado, Skype for Business para se certificar de que a funcionalidade de teste está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="d4818-211">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="d4818-212">Etapa 8: atualizar pools secundários</span><span class="sxs-lookup"><span data-stu-id="d4818-212">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="d4818-213">Repita as etapas deste tópico para atualizar quaisquer pools adicionais que você tenha no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="d4818-213">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="d4818-214">Solução de problemas com a atualização in-loco</span><span class="sxs-lookup"><span data-stu-id="d4818-214">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="d4818-215">Se a atualização in-loco falhar, você pode ver uma mensagem similar à seguinte imagem.</span><span class="sxs-lookup"><span data-stu-id="d4818-215">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Captura de tela que mostra falha na atualização no local por conta de uma atualização cumulativa não ter sido instalada.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="d4818-p115">Reveja a mensagem completa parte inferior da página para ajudar a solucionar o problema. Clique em **Exibir logs** para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d4818-p115">Review the full message at the bottom of the page to help you troubleshoot the issue. Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="d4818-219">Se a atualização In-loco falha em **preparação para atualização de Verifying** ou * * instalando pré-requisitos ausentes * *, verifique se o servidor tem todos os mais recentes do Windows Server, Lync Server e atualizações do SQL Server aplicadas, e todos os softwares necessários e funções estão instalado.</span><span class="sxs-lookup"><span data-stu-id="d4818-219">If the In-Place Upgrade fails on **Verifying upgrade readiness** or ** Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="d4818-220">Para obter uma lista do que é necessário, consulte [requisitos de servidor para Skype para Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e [instalar os pré-requisitos do Skype para Business Server 2015](install/install-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="d4818-220">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d4818-221">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d4818-221">See also</span></span>

#### 

[<span data-ttu-id="d4818-222">Planejar a atualização para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d4818-222">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="d4818-223">Requisitos de servidor do Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d4818-223">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="d4818-224">Instalar os pré-requisitos para Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="d4818-224">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="d4818-225">Instale o Skype para o servidor de negócios 2015</span><span class="sxs-lookup"><span data-stu-id="d4818-225">Install Skype for Business Server 2015</span></span>](install/install.md)

