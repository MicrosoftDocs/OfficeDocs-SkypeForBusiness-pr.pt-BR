---
title: Alterar URLs simples após a migração
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
description: O Skype for Business Server oferece suporte a URLs simples.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753901"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="3a922-103">Alterar URLs simples após a migração</span><span class="sxs-lookup"><span data-stu-id="3a922-103">Change simple URLs after migration</span></span>

<span data-ttu-id="3a922-104">O Skype for Business Server oferece suporte a três URLs simples:</span><span class="sxs-lookup"><span data-stu-id="3a922-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="3a922-105">**Reunir** é usado como URL base para todas as conferências no site ou na organização.</span><span class="sxs-lookup"><span data-stu-id="3a922-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="3a922-106">Com o URL Reunir simples, os links para ingressar em reuniões são fáceis de compreender, de comunicar e distribuir.</span><span class="sxs-lookup"><span data-stu-id="3a922-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="3a922-107">**Discar** possibilita o acesso à página da web Configurações de Conferência Discada.</span><span class="sxs-lookup"><span data-stu-id="3a922-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="3a922-108">O URL Discar é incluído em todos os convites de reuniões para que o usuário que desejar discar para ingressar na reunião possa obter acesso ao número de telefone necessário, bem como as informações do PIN.</span><span class="sxs-lookup"><span data-stu-id="3a922-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="3a922-109">O **administrador** permite acesso rápido ao painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a922-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="3a922-110">A URL simples de Admin é interna à organização.</span><span class="sxs-lookup"><span data-stu-id="3a922-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="3a922-111">Após migrar para o Skype for Business Server, você deve estar ciente de como a alteração impacta seus registros DNS e certificados para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="3a922-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="3a922-112">Se o diretor de servidor do Skype for Business herdado permanecer em uso na topologia, não será necessário fazer alterações nas suas URLs simples.</span><span class="sxs-lookup"><span data-stu-id="3a922-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="3a922-113">Se o diretor do Skype for Business Server for removido da topologia após a migração, os registros DNS de URL simples devem ser atualizados para apontar para um dos pools do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3a922-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="3a922-114">Contudo, sempre que você alterar o nome de um URL simples, você deve executar o Enable-CsComputer em cada servidor Diretor e Front End para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="3a922-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="3a922-115">Para atualizar a URL simples de reunião</span><span class="sxs-lookup"><span data-stu-id="3a922-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="3a922-116">No construtor de topologias, clique com o botão direito do mouse no nó superior **Skype for Business Server**e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3a922-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="3a922-117">Selecione **URLs simples** no painel esquerdo e, abaixo das **URLs da reunião:** selecione a URL de reunião e clique em **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="3a922-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="3a922-118">Atualize a URL para o valor desejado e clique em **OK** para salvar a URL editada.</span><span class="sxs-lookup"><span data-stu-id="3a922-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="3a922-119">Para atualizar a URL simples de administrador</span><span class="sxs-lookup"><span data-stu-id="3a922-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="3a922-120">No construtor de topologias, clique com o botão direito do mouse no nó superior **Skype for Business Server**e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3a922-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="3a922-121">Selecione **URLs simples** no painel esquerdo e, em seguida, abaixo da caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao painel de controle do Skype for Business Server e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a922-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="3a922-122">Recomendamos usar a URL mais simples possível para a URL Admin.</span><span class="sxs-lookup"><span data-stu-id="3a922-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="3a922-123">A opção mais simples é https://admin . <em>\<domain\></em> .</span><span class="sxs-lookup"><span data-stu-id="3a922-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3a922-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="3a922-124">See also</span></span>

[<span data-ttu-id="3a922-125">Requisitos de DNS para URLs simples no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3a922-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
