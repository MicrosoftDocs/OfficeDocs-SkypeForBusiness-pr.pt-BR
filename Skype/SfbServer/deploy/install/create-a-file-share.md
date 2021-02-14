---
title: Criar um compartilhamento de arquivos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
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
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumo: saiba como criar um compartilhamento de arquivos do Windows Server como parte da instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812231"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="3012e-104">Criar um compartilhamento de arquivos no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3012e-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="3012e-105">**Resumo:** Saiba como criar um compartilhamento de arquivos do Windows Server como parte da instalação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3012e-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="3012e-106">Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .</span><span class="sxs-lookup"><span data-stu-id="3012e-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="3012e-107">O Skype for Business Server requer um compartilhamento de arquivos para que os computadores em toda a topologia possam trocar arquivos.</span><span class="sxs-lookup"><span data-stu-id="3012e-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="3012e-108">Criar um compartilhamento de arquivos é a etapa 2 de 8 no processo de instalação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3012e-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="3012e-109">Você pode realizar as etapas 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="3012e-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="3012e-110">No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="3012e-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="3012e-111">Para detalhes de planejamento sobre compartilhamento de arquivos, consulte [Requisitos](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) de ambiente para Skype for Business Server ou requisitos de servidor [para o Skype for Business Server 2019.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3012e-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Diagrama de visão geral](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="3012e-113">Criar um compartilhamento de arquivos básico</span><span class="sxs-lookup"><span data-stu-id="3012e-113">Create a basic file share</span></span>

<span data-ttu-id="3012e-114">Esta seção orienta você na criação de um compartilhamento de arquivos básico do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="3012e-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="3012e-115">Um compartilhamento de arquivos básico do Windows Server é suportado com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3012e-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="3012e-116">No entanto, ele não fornece explicitamente alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="3012e-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="3012e-117">Para um ambiente de alta disponibilidade, recomenda-se um compartilhamento de arquivos DFS (Sistema de Arquivos Distribuído).</span><span class="sxs-lookup"><span data-stu-id="3012e-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="3012e-118">Para obter mais informações sobre um compartilhamento de arquivos de alta disponibilidade e DFS, consulte Plano para alta disponibilidade e recuperação de desastres [no Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="3012e-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3012e-119">O Windows Server 2012 R2 fez grandes saltos no fornecimento de soluções de compartilhamento de arquivos como SAN (Rede de Área de Armazenamento) usando a plataforma do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="3012e-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="3012e-120">Quando comparada a um dispositivo baseado em SAN tradicional, uma solução de armazenamento do Windows Server 2012 R2 pode cortar custos pela metade com muito impacto mínimo sobre o desempenho.</span><span class="sxs-lookup"><span data-stu-id="3012e-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="3012e-121">Para obter mais informações sobre opções de compartilhamento de arquivos no Windows Server 2012 R2, consulte o white paper baixável [Windows Server 2012 R2 Storage.](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)</span><span class="sxs-lookup"><span data-stu-id="3012e-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="3012e-122">Assista às etapas de vídeo **para criar um compartilhamento de arquivos:**</span><span class="sxs-lookup"><span data-stu-id="3012e-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="3012e-123">Criar um compartilhamento de arquivos básico</span><span class="sxs-lookup"><span data-stu-id="3012e-123">Create a basic file share</span></span>

1. <span data-ttu-id="3012e-124">Faça logoff no computador que hospedará o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3012e-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="3012e-125">Clique com o botão direito do mouse na pasta que você planeja compartilhar e selecione **Propriedades.**</span><span class="sxs-lookup"><span data-stu-id="3012e-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="3012e-126">Selecione a **guia Compartilhamento** e clique em **Compartilhamento Avançado.**</span><span class="sxs-lookup"><span data-stu-id="3012e-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="3012e-127">Clique **em Compartilhar esta pasta.**</span><span class="sxs-lookup"><span data-stu-id="3012e-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="3012e-128">Clique em **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="3012e-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="3012e-129">Adicione o grupo de **Administradores** local do servidor que hospeda o compartilhamento de arquivos, conceda a Eles os direitos Permitir: Controle **Total,** Alterar e Leitura e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="3012e-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="3012e-130">Clique **em OK** novamente e anote o caminho da rede.</span><span class="sxs-lookup"><span data-stu-id="3012e-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="3012e-131">Clique **em Feito** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="3012e-131">Click **Done** to close the wizard.</span></span>
    
     ![Guia de compartilhamento para compartilhar uma pasta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="3012e-133">Se o armazenamento de arquivos estiver hospedado em um compartilhamento DFS, o seguinte aviso será recebido:</span><span class="sxs-lookup"><span data-stu-id="3012e-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="3012e-134">Aviso: Não é possível acessar permissões de compartilhamento para " \\ <domain> \<share> ".</span><span class="sxs-lookup"><span data-stu-id="3012e-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="3012e-135">Isso é esperado se você não for um administrador no servidor de arquivos ou se for um compartilhamento dfs (sistema de arquivos distribuídos).</span><span class="sxs-lookup"><span data-stu-id="3012e-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="3012e-136">Se as permissões de compartilhamento já foram configuradas, esse aviso pode ser ignorado.</span><span class="sxs-lookup"><span data-stu-id="3012e-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="3012e-137">Se for um novo compartilhamento, consulte a documentação para obter detalhes sobre como configurar manualmente as permissões de compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="3012e-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="3012e-138">Devido à incapacidade de acessar as permissões de compartilhamento em um compartilhamento DFS, o Skype for Business Server não poderá definir explicitamente grupos no compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="3012e-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="3012e-139">Para garantir que os componentes do Skype for Business Server possam acessar o compartilhamento de arquivos com as permissões apropriadas, verifique se os seguintes grupos RTC foram adicionados com permissões de compartilhamento de nível de Leitura e Alteração, além dos Administradores locais com permissões de compartilhamento controle total.</span><span class="sxs-lookup"><span data-stu-id="3012e-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="3012e-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3012e-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="3012e-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="3012e-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="3012e-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="3012e-142">RTCUniversalServerAdmins</span></span>
