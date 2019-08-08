---
title: Alterar URLs simples após a migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O Skype for Business Server oferece suporte a URLs simples.
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239490"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="4e6f4-103">Alterar URLs simples após a migração</span><span class="sxs-lookup"><span data-stu-id="4e6f4-103">Change simple URLs after migration</span></span>

<span data-ttu-id="4e6f4-104">O Skype for Business Server oferece suporte a três URLs simples:</span><span class="sxs-lookup"><span data-stu-id="4e6f4-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="4e6f4-105">A **reunião** é usada como a URL base para todas as conferências no site ou na organização.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="4e6f4-106">Com a URL simples de reunião, os links para ingressar em reuniões são fáceis de compreender e fáceis de se comunicar e distribuir.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="4e6f4-107">\*\*\*\* A discagem permite o acesso à página da Web configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="4e6f4-108">A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="4e6f4-109">O **administrador** permite acesso rápido ao painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="4e6f4-110">A URL simples de Admin é parte interna da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="4e6f4-111">Depois de migrar para o Skype for Business Server, você deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="4e6f4-112">Se o diretor herdado do Skype for Business permanecer em uso na topologia, não será necessária nenhuma alteração nas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="4e6f4-113">Se o diretor do servidor do Skype for Business for removido da topologia após a migração, os registros DNS de URL simples deverão ser atualizados para apontar para um dos pools do servidor do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="4e6f4-114">No entanto, sempre que você alterar um nome de URL simples, você deve executar Enable-CsComputer em cada director e servidor front-end para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="4e6f4-115">Para atualizar a URL de reunião simples</span><span class="sxs-lookup"><span data-stu-id="4e6f4-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="4e6f4-116">No construtor de topologias, clique com o botão direito do mouse no nó superior do **Skype for Business Server**e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="4e6f4-117">Selecione **URLs simples** no painel esquerdo e, abaixo de **URLs de reunião:** selecione a URL do encontro e clique em **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="4e6f4-118">Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="4e6f4-119">Para atualizar a URL simples de administrador</span><span class="sxs-lookup"><span data-stu-id="4e6f4-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="4e6f4-120">No construtor de topologias, clique com o botão direito do mouse no nó superior do **Skype for Business Server**e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="4e6f4-121">Selecione **URLs simples** no painel esquerdo e, em seguida, abaixo da caixa **URL de acesso administrativo** , insira a URL simples que você deseja para acesso administrativo ao painel de controle do Skype for Business Server e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="4e6f4-122">Nós recomendamos que você use a URL do administrador mais simples possível.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="4e6f4-123">A opção mais simples é https://admin. <em> \<domínio\></em>.</span><span class="sxs-lookup"><span data-stu-id="4e6f4-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4e6f4-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e6f4-124">See also</span></span>

[<span data-ttu-id="4e6f4-125">Requisitos de DNS para URLs simples no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4e6f4-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
