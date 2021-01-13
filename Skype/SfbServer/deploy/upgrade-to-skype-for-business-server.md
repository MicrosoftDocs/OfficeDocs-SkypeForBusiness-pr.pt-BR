---
title: Atualizar para o Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: 'Resumo: Saiba como atualizar do Lync Server 2013 para o Skype for Business Server 2015. Baixe uma avaliação gratuita do Skype for Business Server 2015 do Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: cda83d03db697a0adf404af4f6fe6e350abf6b58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820421"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="3a5f6-104">Atualizar para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a5f6-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3a5f6-105">**Resumo:** Saiba como atualizar do Lync Server 2013 para o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="3a5f6-106">Baixe uma avaliação gratuita do Skype for Business Server 2015 do Centro [de Avaliação da Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="3a5f6-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="3a5f6-107">Use os procedimentos deste documento para atualizar do Lync Server 2013 para o Skype for Business Server 2015 usando o Construtor de Topologias do Skype for Business Server e o novo recurso In-Place Atualização.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="3a5f6-108">Se você quiser atualizar do Lync Server 2010 ou do Office Communications Server 2007 R2, consulte Plano para atualizar para o [Skype for Business Server 2015.](../plan-your-deployment/upgrade.md)</span><span class="sxs-lookup"><span data-stu-id="3a5f6-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3a5f6-109">As atualizações in-place estavam disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3a5f6-110">A coexistência lado a lado é suportada, confira Migração para [o Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="3a5f6-111">Atualização do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a5f6-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="3a5f6-112">A atualização do Lync Server 2013 para o Skype for Business Server 2015 envolve a instalação de softwares de pré-requisitos, o uso do Construtor de Topologias do Skype for Business Server para atualizar bancos de dados no pool e o uso da Atualização do Skype for Business Server In-Place em cada um dos servidores associados ao pool.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="3a5f6-113">Para concluir a atualização, conclua as oito etapas deste tópico.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="3a5f6-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3a5f6-114">Before you begin</span></span>

- <span data-ttu-id="3a5f6-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="3a5f6-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="3a5f6-116">Revise [os requisitos do Servidor para o Skype for Business Server 2015.](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3a5f6-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="3a5f6-117">[Instale os pré-requisitos do Skype for Business Server 2015.](install/install-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="3a5f6-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="3a5f6-118">[Instale o Skype for Business Server 2015.](install/install.md)</span><span class="sxs-lookup"><span data-stu-id="3a5f6-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="3a5f6-119">Etapa 1: Instalar ferramentas de administrador e baixar topologia</span><span class="sxs-lookup"><span data-stu-id="3a5f6-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="3a5f6-120">Conecte-se ao computador na topologia que não tenha o Lync OCSCore ou qualquer outro componente do Lync instalado.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="3a5f6-121">Na mídia de instalação do Skype for Business Server 2015, execute **Setup.exe** de **OCS_Volume\Setup\AMD64**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="3a5f6-122">Clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="3a5f6-123">Aceitar o Contrato de Licença.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="3a5f6-124">No Assistente de Implantação, clique **em Instalar ferramentas do Administrador** e siga as etapas para instalar.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![Screen shot of Deployment Wizard with link to the Install Administrator Tools called out.](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="3a5f6-126">Na tela inicial do Windows, abra o Construtor de Topologias do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="3a5f6-127">Clique **em Baixar topologia da implantação existente** e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="3a5f6-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="3a5f6-128">Insira um nome para a topologia e clique em **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="3a5f6-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="3a5f6-129">Vá para o local onde você salvou a topologia e faça uma cópia da topologia.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="3a5f6-130">Etapa 2: Atualizar e publicar a topologia usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="3a5f6-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="3a5f6-131">Antes de iniciar o processo de atualização, todos os serviços devem estar em execução para os pools que você planeja atualizar.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="3a5f6-132">Isso é para que as alterações de topologia sejam replicadas para o banco de dados local dos servidores no pool.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="3a5f6-133">Salve uma cópia do arquivo de topologia antes de atualizar.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="3a5f6-134">Depois de atualizar, você não poderá fazer downgrade na topologia.> Se seus serviços estão nos mesmos servidores que seus bancos de dados, como o serviço de Chat Persistente está no mesmo servidor que o banco de dados de Chat Persistente, ignore esta etapa e vá para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="3a5f6-135">Depois de interromper os serviços, execute a configuração In-Place Atualização em cada servidor para atualizar os bancos de dados locais.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3a5f6-136">Se a topologia tiver um banco de dados back-end espelhado, você verá os bancos de dados Principal e Espelhado aparecerem quando você publicar a **topologia** usando o Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="3a5f6-137">Certifique-se de que todos os bancos de dados estão sendo executados na entidade de segurança e selecione apenas a entidade de segurança, não o espelho, ao publicar a topologia caso contrário, você verá um aviso depois de publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="3a5f6-138">Escolha uma das opções abaixo para atualizar e publicar uma nova topologia usando o Construtor de Topologias do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="3a5f6-139">Depois de concluir as etapas e publicar a topologia atualizada, vá para a Etapa 3 deste tópico.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="3a5f6-140">Opção 1: Atualizar um pool de Front-End isolado e os armazenamentos de Arquivamento e Monitoramento associados</span><span class="sxs-lookup"><span data-stu-id="3a5f6-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="3a5f6-141">Se o pool que você está atualizando tiver uma dependência de armazenamento de Arquivamento e Monitoramento, quando você usar as etapas a seguir, o armazenamento de Arquivamento e Monitoramento também será atualizado.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="3a5f6-142">No Construtor de Topologias, clique com o botão direito do mouse em um pool do Lync Server 2013, selecione Atualizar para **o Skype for Business Server 2015** e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de tela do menu com o botão direito do mouse com a opção de atualização do Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="3a5f6-144">In Topology Builder, click **Action**  >  **Publish topology** or **Action**  >  **Topology**  >  **Publish**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![Captura de tela do menu Ação com a opção Publicar topologia no Construtor de Topologias.](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="3a5f6-146">Durante a publicação, escolha instalar um banco de dados no armazenamento de Arquivamento e Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="3a5f6-147">Opção 2: Atualizar o pool de Front-End sem atualizar os armazenamentos de Arquivamento e Monitoramento</span><span class="sxs-lookup"><span data-stu-id="3a5f6-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="3a5f6-148">Se você usar as etapas a seguir, o arquivamento e o monitoramento do pool selecionado serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="3a5f6-149">O pool não terá armazenamentos de Arquivamento e Monitoramento após a atualização.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="3a5f6-150">No Construtor de Topologias, selecione o pool do Lync Server 2013 que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="3a5f6-151">Remova a dependência dos armazenamentos de Arquivamento e Monitoramento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="3a5f6-152">Vá para **propriedades de** Edição  >  **de Ação.**</span><span class="sxs-lookup"><span data-stu-id="3a5f6-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="3a5f6-153">Des **clear the Archiving** check box.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-153">Clear the **Archiving** check box.</span></span>
    
     ![Captura de tela da caixa de seleção Arquivamento na caixa de diálogo Editar propriedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="3a5f6-155">Des limpe **a caixa de seleção** Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-155">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra a caixa de seleção Monitoramento.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="3a5f6-157">Clique com o botão direito do mouse no pool do Lync Server 2013, selecione Atualizar para **o Skype for Business Server 2015** e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de tela do menu com o botão direito do mouse com a opção de atualização do Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="3a5f6-159">In Topology Builder, click **Action**  >  **Publish topology** or **Action**  >  **Topology**  >  **Publish**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="3a5f6-160">Opção 3: Atualizar o pool de front-end e associá-lo aos novos armazenamentos de Arquivamento e Monitoramento do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a5f6-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="3a5f6-161">Se você usar as etapas a seguir, o arquivamento e o monitoramento serão parados no armazenamento anterior e começarão no novo armazenamento que você criou.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="3a5f6-162">No Construtor de Topologias, selecione o pool do Lync Server 2013 que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="3a5f6-163">Remova a dependência dos armazenamentos de Arquivamento e Monitoramento do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="3a5f6-164">Vá para **propriedades de** Edição  >  **de Ação.**</span><span class="sxs-lookup"><span data-stu-id="3a5f6-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="3a5f6-165">Des **clear the Archiving** check box.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-165">Clear the **Archiving** check box.</span></span>
    
     ![Captura de tela da caixa de seleção Arquivamento na caixa de diálogo Editar propriedades.](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="3a5f6-167">Des limpe **a caixa de seleção** Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-167">Clear the **Monitoring** check box.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostra a caixa de seleção Monitoramento.](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="3a5f6-169">Clique com o botão direito do mouse no pool do Lync Server 2013, selecione Atualizar para **o Skype for Business Server 2015** e siga as etapas.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Captura de tela do menu com o botão direito do mouse com a opção de atualização do Lync Server 2013.](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="3a5f6-171">Crie um novo armazenamento SQL para Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="3a5f6-172">Selecione o pool e as **propriedades de Edição** de  >  **Ação.**</span><span class="sxs-lookup"><span data-stu-id="3a5f6-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="3a5f6-173">Marque a caixa de seleção **Arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="3a5f6-174">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-174">Click **New**.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostram o botão Novo na seção Arquivamento.](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="3a5f6-176">Crie um novo armazenamento SQL para Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="3a5f6-177">Selecione o pool e as **propriedades de Edição** de  >  **Ação.**</span><span class="sxs-lookup"><span data-stu-id="3a5f6-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="3a5f6-178">Marque a **caixa de seleção** Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="3a5f6-179">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-179">Click **New**.</span></span>
    
     ![Captura de tela da caixa de diálogo Editar propriedades que mostram o botão Novo na seção Monitoramento.](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="3a5f6-181">In Topology Builder, click **Action**  >  **Publish topology** or **Action**  >  **Topology**  >  **Publish**.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="3a5f6-182">Durante a publicação, escolha instalar o banco de dados no novo armazenamento de Arquivamento e Monitoramento.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="3a5f6-183">Etapa 3: Aguardar replicação</span><span class="sxs-lookup"><span data-stu-id="3a5f6-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="3a5f6-184">Dê algum tempo à replicação para publicar a topologia atualizada em todos os servidores no ambiente.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="3a5f6-185">Etapa 4: Interromper a atualização de todos os serviços no pool</span><span class="sxs-lookup"><span data-stu-id="3a5f6-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="3a5f6-186">Em cada servidor que está atendendo o pool que você vai atualizar, execute o seguinte cmdlet no PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3a5f6-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="3a5f6-187">Recomendamos usar o Disable-CsComputer porque talvez seja necessário reiniciar o servidor durante o processo de In-Place Atualização.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="3a5f6-188">Se você usar Stop-CsWindowsService, alguns serviços poderão ser reiniciados automaticamente após uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="3a5f6-189">Isso pode fazer com que a In-Place atualização falhe.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="3a5f6-190">Etapa 5: Atualizar pools de front-end e servidores de pool não front-end</span><span class="sxs-lookup"><span data-stu-id="3a5f6-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="3a5f6-191">Antes de atualizar, instale todos os novos pré-requisitos necessários para o Skype for Business Server 2015, que incluem: > Pelo menos 32 GB de espaço livre antes de tentar uma atualização.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="3a5f6-192">Além disso, certifique-se de que a unidade seja uma unidade local fixa, não esteja conectada por USB ou Firewire, está formatado com o sistema de arquivos NTFS, não está compactado e não contém um arquivo de página.> PowerShell versão 6.2.9 200.0 ou posterior.> A atualização cumulativa mais recente do Lync Server 2013 instalada.> SQL Server 2012 SP1 instalado.> A seguinte KB está instalada (instalada automaticamente se estiver usando o Microsoft Update):> Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)> Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)> Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="3a5f6-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="3a5f6-193">Use a In-Place atualização em cada servidor para atualizar o pool de Front-End, pool de Borda, servidor de Mediação e o pool de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="3a5f6-194">Em cada servidor, execute **Setup.exe** de **OCS_Volume\Setup\amd64** na mídia de instalação do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="3a5f6-195">Aceite o contrato de licença e siga as solicitações para o In-Place Atualização.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="3a5f6-196">Repita essas etapas para cada servidor no pool de Front-End e em cada servidor de pool não Front-End.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3a5f6-197">Você pode ser solicitado a reiniciar o servidor durante a atualização In-Place atualização.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="3a5f6-198">Tudo bem.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-198">That's ok.</span></span> <span data-ttu-id="3a5f6-199">Após a reinicialização, a In-Place Atualização continuará de onde foi deixada.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="3a5f6-200">Quando a In-Place atualização for concluída com êxito, você verá a seguinte mensagem.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![Screen shot that shows in-place upgrade completed successfully.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="3a5f6-202">Etapa 6: Reiniciar serviços em todos os servidores atualizados</span><span class="sxs-lookup"><span data-stu-id="3a5f6-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="3a5f6-203">Antes de reiniciar os serviços, verifique se %ProgramData%\WindowsFabric não existe em todos os servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="3a5f6-204">Se existir, exclua-o antes de iniciar os serviços.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="3a5f6-205">Depois de atualizar todos os servidores no pool de Front-End, reinicie os serviços usando o seguinte comando do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3a5f6-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="3a5f6-206">Se já houver uma reinicialização pendente do sistema necessária antes de iniciar a execução do In-Place Upgrade, a atualização do In-Place não solicitará a reinicialização no final da instalação.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="3a5f6-207">Isso fará com que algumas exceções de assembly sejam lançadas no primeiro servidor front-end quando você tentar iniciar serviços usando o Start-CSPool cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="3a5f6-208">Para resolver esses erros, reinicie todos os servidores no pool e execute o cmdlet novamente.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="3a5f6-209">Nos servidores de pool não Front-End, reinicie os serviços usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="3a5f6-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="3a5f6-210">Depois de clicar **em OK** na página In-Place Atualização, você verá o lembrete a seguir para concluir esta etapa.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![Captura de tela que mostra as próximas etapas após a conclusão bem-sucedida da atualização in-place.](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="3a5f6-212">Etapa 7: Verificar se a funcionalidade do Skype for Business funciona</span><span class="sxs-lookup"><span data-stu-id="3a5f6-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="3a5f6-213">Para garantir que a atualização foi bem-sucedida, para o pool que foi atualizado, teste o Skype for Business para garantir que a funcionalidade está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="3a5f6-214">Etapa 8: Atualizar pools secundários</span><span class="sxs-lookup"><span data-stu-id="3a5f6-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="3a5f6-215">Repita as etapas deste tópico para atualizar quaisquer pools adicionais que você tenha em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="3a5f6-216">Solucionar problemas com a atualização In-Place atualização</span><span class="sxs-lookup"><span data-stu-id="3a5f6-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="3a5f6-217">Se a In-Place atualização falhar, você poderá ver uma mensagem semelhante à que está na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![Screen shot that shows in-place upgrade failing because a required cumulative update isn't installed.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="3a5f6-219">Revise a mensagem completa na parte inferior da página para ajudá-lo a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="3a5f6-220">Clique **em Exibir logs** para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="3a5f6-221">Se a atualização do In-Place  falhar na verificação da preparação da atualização ou na instalação de pré-requisitos **ausentes,** verifique se o servidor tem todas as atualizações mais recentes do Windows Server, do Lync Server e do SQL Server aplicadas e se todos os softwares e funções necessários estão instalados.</span><span class="sxs-lookup"><span data-stu-id="3a5f6-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="3a5f6-222">Para uma lista do que é necessário, consulte Requisitos de servidor para [o Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) e pré-requisitos de instalação para o Skype for Business Server [2015.](install/install-prerequisites.md)</span><span class="sxs-lookup"><span data-stu-id="3a5f6-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3a5f6-223">Confira também</span><span class="sxs-lookup"><span data-stu-id="3a5f6-223">See also</span></span>

[<span data-ttu-id="3a5f6-224">Planejar a atualização para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a5f6-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="3a5f6-225">Requisitos de servidor para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a5f6-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="3a5f6-226">Instalar os pré-requisitos do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a5f6-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="3a5f6-227">Instalar o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="3a5f6-227">Install Skype for Business Server 2015</span></span>](install/install.md)
