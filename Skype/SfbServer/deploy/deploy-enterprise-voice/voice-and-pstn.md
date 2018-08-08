---
title: Configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Resumo: Saiba como configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para Business Server.'
ms.openlocfilehash: 0292ae0f7f8579c4856059587ed75b172617fe72
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21006503"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="9c86d-103">Configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9c86d-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="9c86d-104">**Resumo:** Saiba como configurar políticas de voz, registros de uso PSTN e roteamentos de voz no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="9c86d-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="9c86d-p101">Políticas de voz, registros de uso PSTN e rotas de voz estão totalmente relacionados. Configure as políticas de voz selecionando um conjunto de recursos de chamada e, em seguida, atribuindo à política um conjunto de registros de uso da PSTN, que especificam quais direitos serão autorizados para os usuários ou grupos aos quais foi atribuída a política de voz. As rotas de voz também recebem registros de uso da PSTN, que servem para corresponder as rotas aos usuários que têm autorização para usá-las. Isto é, os usuários podem somente fazer chamadas que utilizem as rotas para as quais exista um registro de uso da PSTN correspondente.</span><span class="sxs-lookup"><span data-stu-id="9c86d-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="9c86d-109">O fluxo de trabalho recomendado para uma nova implantação Enterprise Voice é de começar configurando uma política de voz que inclua os registros de uso PSTN adequados e, então, associar as rotas apropriadas à cada registro de uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="9c86d-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9c86d-110">Você também pode criar políticas de voz com escopo de *usuário* e atribuí-las aos usuários ou grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="9c86d-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="9c86d-111">Para as etapas detalhas para realizar cada uma destas tarefas, consulte os procedimentos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="9c86d-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9c86d-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="9c86d-112">In this section</span></span>

- [<span data-ttu-id="9c86d-113">Criar ou modificar uma política de voz e configurar registros de uso PSTN no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9c86d-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="9c86d-114">Configurar escape da caixa postal no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9c86d-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="9c86d-115">Exibir registros de uso PSTN em Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9c86d-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="9c86d-116">Criar ou modificar uma rota de voz no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9c86d-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="9c86d-117">Exportar ou importar um arquivo de configuração de rota de voz no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9c86d-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="9c86d-118">Publicar alterações pendentes para a configuração de roteamento de voz no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="9c86d-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

