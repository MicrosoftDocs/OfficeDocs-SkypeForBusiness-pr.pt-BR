---
title: Configurar os servidores de aplicativos confiáveis
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o pool de próximo salto como um pool do Skype for Business Server 2019. Em um ambiente misto, o pool herdado e o pool do Skype for Business Server 2019 aparecem na lista suspensa. Selecionar o pool herdado não é suportado.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753941"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="a2ac8-105">Configurar os servidores de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="a2ac8-105">Configure trusted application servers</span></span>

<span data-ttu-id="a2ac8-106">Em um ambiente misto, se você criar um novo servidor de aplicativos confiável, deverá definir o pool de próximo salto como um pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="a2ac8-107">Em um ambiente misto, o pool herdado e o pool do Skype for Business Server 2019 aparecem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="a2ac8-108">Selecionar o pool herdado não é suportado.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a2ac8-109">Se você estiver migrando um servidor de aplicativos confiável, também deverá atualizar a versão do UCMA que você está usando.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="a2ac8-110">Se você criar um novo pool de aplicativos confiáveis para o Skype for Business Server 2019, deverá atualizar o UCMA para a versão incluída no Skype for Business Server 2019 ou na versão mais recente disponível.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="a2ac8-111">Selecionar o Skype for Business Server 2019 como próximo salto ao criar um servidor de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="a2ac8-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="a2ac8-112">Abra o Construtor de Topologia.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="a2ac8-113">No painel esquerdo, clique com o botão direito do mouse em **servidores de aplicativos confiáveis** e clique em **novo pool de aplicativos confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="a2ac8-114">Insira o **FQDN do pool** do pool de aplicativos confiáveis e selecione se ele será de servidor único ou de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="a2ac8-115">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="a2ac8-116">Na página **selecionar o próximo salto** , na lista, selecione o pool de front-ends do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="a2ac8-117">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="a2ac8-118">Selecione o nó superior **Skype for Business Server**e, no menu **ação** , selecione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="a2ac8-119">Verifique se o **pool de aplicativos confiáveis** foi criado com êxito e associado ao pool de front-ends correto.</span><span class="sxs-lookup"><span data-stu-id="a2ac8-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

