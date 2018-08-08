---
title: Crie um compartilhamento de arquivo no Skype para Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 'Resumo: Saiba como criar um compartilhamento de arquivo do Windows Server como parte da instalação do Skype para Business Server. Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a84e37c3d069c3f51570b600d5ec4804d2a5ee3c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967111"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="ef688-104">Crie um compartilhamento de arquivo no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="ef688-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="ef688-105">**Resumo:** Saiba como criar um compartilhamento de arquivo do Windows Server como parte da instalação do Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef688-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="ef688-106">Baixe uma versão de avaliação gratuita do Skype para Business Server do centro da Evaluation da Microsoft em:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="ef688-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="ef688-107">Skype para Business Server requer um compartilhamento de arquivos, para que os computadores em toda a topologia podem trocar arquivos.</span><span class="sxs-lookup"><span data-stu-id="ef688-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="ef688-108">Criação de um compartilhamento de arquivo é a etapa 2 de 8 no processo de instalação de Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef688-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="ef688-109">As etapas 1 a 5 podem ser executadas em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="ef688-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="ef688-110">No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="ef688-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="ef688-111">Para detalhes sobre compartilhamento de arquivos de planejamento, consulte [requisitos de ambiente para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) ou [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef688-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![Diagrama de visão geral](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="ef688-113">Criar um compartilhamento de arquivo básico</span><span class="sxs-lookup"><span data-stu-id="ef688-113">Create a basic file share</span></span>

<span data-ttu-id="ef688-114">Esta seção ajuda você a criar um compartilhamento de arquivos básico no Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ef688-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="ef688-115">Um compartilhamento de arquivos básico do Windows Server é compatível com Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="ef688-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="ef688-116">No entanto, ele não explicitamente oferece alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="ef688-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="ef688-117">Para um ambiente de alta disponibilidade, recomenda-se um compartilhamento de arquivo de sistema de arquivos distribuído (DFS).</span><span class="sxs-lookup"><span data-stu-id="ef688-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="ef688-118">Para obter mais informações sobre um compartilhamento de arquivos de alta disponibilidade e o DFS, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ef688-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef688-119">O Windows Server 2012 R2 deu grandes saltos no fornecimento de soluções de compartilhamento similares à rede SAN usando a plataforma do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ef688-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="ef688-120">Quando comparada a um aplicativo baseado em uma rede SAN tradicional, uma solução de armazenamento do Windows Server 2012 R2 pode cortar custos pela metade, com mínimo impacto sobre o desempenho.</span><span class="sxs-lookup"><span data-stu-id="ef688-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="ef688-121">Para obter mais informações sobre as opções de compartilhamento de arquivo no Windows Server 2012 R2, consulte o white paper baixável [O armazenamento do Windows Server 2012 R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span><span class="sxs-lookup"><span data-stu-id="ef688-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="ef688-122">Assista as etapas do vídeo para **criar um compartilhamento de arquivos**:</span><span class="sxs-lookup"><span data-stu-id="ef688-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="ef688-123">Criar um compartilhamento de arquivo básico</span><span class="sxs-lookup"><span data-stu-id="ef688-123">Create a basic file share</span></span>

1. <span data-ttu-id="ef688-124">Faça logon no computador que hospedará o compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ef688-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="ef688-125">Clique com botão direito na pasta que você planeja compartilhar e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ef688-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="ef688-126">Selecione a guia **Compartilhamento** e clique em **Compartilhamento Avançado**.</span><span class="sxs-lookup"><span data-stu-id="ef688-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="ef688-127">Clique em **Compartilhar esta pasta**.</span><span class="sxs-lookup"><span data-stu-id="ef688-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="ef688-128">Clique em **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="ef688-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="ef688-129">Adicione o **grupo local de administradores** do servidor que está hospedando o compartilhamento de arquivos, concedendo **Permitir: Todos os direitos de Controle, Alteração e Leitura** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ef688-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="ef688-130">Clique em **OK** novamente e tome nota do caminho da rede.</span><span class="sxs-lookup"><span data-stu-id="ef688-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="ef688-131">Clique em **Concluído** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="ef688-131">Click **Done** to close the wizard.</span></span>
    
     ![Guia de compartilhamento para compartilhar uma pasta.](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

