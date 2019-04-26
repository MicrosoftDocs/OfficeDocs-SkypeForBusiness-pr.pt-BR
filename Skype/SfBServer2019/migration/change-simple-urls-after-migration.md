---
title: Alterar URLs simples após a migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server oferece suporte a URLs simples.
ms.openlocfilehash: 02f4cc729a50459a8125e216265b935d557007c6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238748"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="1e298-103">Alterar URLs simples após a migração</span><span class="sxs-lookup"><span data-stu-id="1e298-103">Change simple URLs after migration</span></span>

<span data-ttu-id="1e298-104">Skype para Business Server suporta três URLs simples:</span><span class="sxs-lookup"><span data-stu-id="1e298-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="1e298-105">**Reunir** é usado como a URL base para todas as conferências no local ou organização.</span><span class="sxs-lookup"><span data-stu-id="1e298-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="1e298-106">Com o URL reunir simples, links para ingressar em reuniões são fáceis de compreender e fáceis de se comunicar e distribuir.</span><span class="sxs-lookup"><span data-stu-id="1e298-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="1e298-107">**Discada** permite o acesso a página da Web configurações de conferência discada.</span><span class="sxs-lookup"><span data-stu-id="1e298-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="1e298-108">A URL simples Dial-in é incluída em todos os convites de reunião para que os usuários que desejam discar para a reunião possam acessar o número de telefone e as informações de PIN necessárias.</span><span class="sxs-lookup"><span data-stu-id="1e298-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="1e298-109">**Admin** permite acesso rápido ao Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="1e298-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="1e298-110">A URL simples de Admin é parte interna da sua organização.</span><span class="sxs-lookup"><span data-stu-id="1e298-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="1e298-111">Após migrar para o Skype para Business Server, você deve estar ciente como a alteração afeta seus registros DNS e certificados para URLs simples.</span><span class="sxs-lookup"><span data-stu-id="1e298-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="1e298-112">Se o Skype herdado para o Diretor de servidor de negócios permanecer em uso na topologia, nenhuma alteração aos seus URLs simples é necessárias.</span><span class="sxs-lookup"><span data-stu-id="1e298-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="1e298-113">Se o Skype para negócios servidor Diretor for removido da topologia após a migração, os registros de DNS de URL simples devem ser atualizados para apontar para um do Skype para pools de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="1e298-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="1e298-114">Sempre que você alterar um nome de URL simple, no entanto, você deve executar Enable-CsComputer em cada diretor e o servidor Front-End para registrar a alteração.</span><span class="sxs-lookup"><span data-stu-id="1e298-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="1e298-115">Para atualizar o URL reunir simples</span><span class="sxs-lookup"><span data-stu-id="1e298-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="1e298-116">No construtor de topologia, clique com botão direito no nó superior **Skype para Business Server**e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1e298-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="1e298-117">Selecione **URLs simples** no painel esquerdo, em seguida, abaixo **URLs de reunião:** selecione a URL de reunião e clique em **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="1e298-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="1e298-118">Atualize a URL para o valor desejado e, em seguida, clique em **Okey** para salvar a URL editada.</span><span class="sxs-lookup"><span data-stu-id="1e298-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="1e298-119">Para atualizar a URL simple de Admin</span><span class="sxs-lookup"><span data-stu-id="1e298-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="1e298-120">No construtor de topologia, clique com botão direito no nó superior **Skype para Business Server**e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1e298-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="1e298-121">Selecione **URLs simples** no painel esquerdo, em seguida, abaixo caixa **URL de acesso administrativo** , digite a URL simples que você deseja para acesso administrativo ao Skype para painel de controle do Business Server e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="1e298-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="1e298-122">Nós recomendamos que você use a URL do administrador mais simples possível.</span><span class="sxs-lookup"><span data-stu-id="1e298-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="1e298-123">É a opção mais simples https://admin. <em> \<domínio\></em>.</span><span class="sxs-lookup"><span data-stu-id="1e298-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1e298-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="1e298-124">See also</span></span>

[<span data-ttu-id="1e298-125">Requisitos de DNS para URLs simples no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="1e298-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
