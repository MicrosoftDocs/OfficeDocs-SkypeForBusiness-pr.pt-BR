---
title: Configurar servidores de aplicativo confiáveis
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Em um ambiente misto, se você criar um novo servidor de aplicativos confiáveis, você deve definir o pool do próximo salto para ser um Skype para Business Server 2019 pool. Em um ambiente misto, tanto o pool herdado e o Skype para Business Server 2019 pool aparecem na lista suspensa. Não há suporte para selecionar o pool herdado.
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238679"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="1c7ab-105">Configurar servidores de aplicativo confiáveis</span><span class="sxs-lookup"><span data-stu-id="1c7ab-105">Configure trusted application servers</span></span>

<span data-ttu-id="1c7ab-106">Em um ambiente misto, se você criar um novo servidor de aplicativos confiáveis, você deve definir o pool do próximo salto para ser um Skype para Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="1c7ab-107">Em um ambiente misto, tanto o pool herdado e o Skype para Business Server 2019 pool aparecem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="1c7ab-108">Não há suporte para selecionar o pool herdado.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1c7ab-109">Se você estiver migrando o servidor de aplicativo confiável, você também deverá atualizar a versão do UCMA que você está usando.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="1c7ab-110">Se você criar um novo Pool de aplicativos confiáveis para Skype for Business Server 2019, você deverá atualizar UCMA para a versão incluída Skype para Business Server 2019 ou a versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="1c7ab-111">Selecione Skype para Business Server 2019 como próximo salto ao criar um servidor de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="1c7ab-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="1c7ab-112">Abra o construtor de topologia.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="1c7ab-113">No painel esquerdo, clique com o botão **servidores de aplicativos confiáveis** e clique em **Novo Pool de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="1c7ab-114">Insira o **FQDN do Pool** do pool de aplicativos confiáveis e selecione se será servidor único ou vários servidores.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="1c7ab-115">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="1c7ab-116">Na página **Selecionar o próximo salto** , na lista, selecione o Skype para pool de negócios 2019 Front-End Server.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="1c7ab-117">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="1c7ab-118">Selecione o nó superior **Skype para Business Server**e, no menu **ação** , selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="1c7ab-119">Verifique se o **Pool de aplicativos confiáveis** foi criado com êxito e associado ao pool de Front-End correto.</span><span class="sxs-lookup"><span data-stu-id="1c7ab-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

