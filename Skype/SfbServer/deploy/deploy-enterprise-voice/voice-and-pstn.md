---
title: Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Resumo: saiba como configurar políticas de voz, registros de uso de PSTN e rotas de voz no Skype for Business Server.'
ms.openlocfilehash: f8c9f75f24a06b210a1c17ed11a1485ab5158f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830441"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a><span data-ttu-id="73c7a-103">Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73c7a-103">Configure voice policies, PSTN usage records, and voice routes in Skype for Business</span></span>
 
<span data-ttu-id="73c7a-104">**Resumo:** Saiba como configurar políticas de voz, registros de uso de PSTN e rotas de voz no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="73c7a-104">**Summary:** Learn how to configure voice policies, PSTN usage records, and voice routes in Skype for Business Server.</span></span>
  
<span data-ttu-id="73c7a-p101">Políticas de voz, registros de uso PSTN e rotas de voz estão totalmente relacionados. Configure as políticas de voz selecionando um conjunto de recursos de chamada e, em seguida, atribuindo à política um conjunto de registros de uso da PSTN, que especificam quais direitos serão autorizados para os usuários ou grupos aos quais foi atribuída a política de voz. As rotas de voz também recebem registros de uso da PSTN, que servem para corresponder as rotas aos usuários que têm autorização para usá-las. Isto é, os usuários podem somente fazer chamadas que utilizem as rotas para as quais exista um registro de uso da PSTN correspondente.</span><span class="sxs-lookup"><span data-stu-id="73c7a-p101">Voice policies, PSTN usage records, and voice routes are integrally related. You configure voice policies by selecting a set of calling features and then assigning the policy a set of PSTN usage records, which specify what rights are authorized for the users or groups who are assigned the voice policy. Voice routes are also assigned PSTN usage records, which serve to match routes with the users who are authorized to use them. That is, users can only place calls that use the routes for which they have a matching PSTN usage record.</span></span>
  
<span data-ttu-id="73c7a-109">O fluxo de trabalho recomendado para uma nova implantação Enterprise Voice é de começar configurando uma política de voz que inclua os registros de uso PSTN adequados e, então, associar as rotas apropriadas à cada registro de uso PSTN.</span><span class="sxs-lookup"><span data-stu-id="73c7a-109">The recommended workflow for a new Enterprise Voice deployment is to start by configuring a voice policy that includes the appropriate PSTN usage records, and then associate the appropriate routes to each PSTN usage record.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="73c7a-110">Você também pode criar políticas de voz com  *escopo de*  usuário e atribuí-las a usuários ou grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="73c7a-110">You can also create voice policies with  *user*  scope and assign them to individual users or groups.</span></span>
  
<span data-ttu-id="73c7a-111">Para as etapas detalhas para realizar cada uma destas tarefas, consulte os procedimentos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="73c7a-111">For the detailed steps to perform each of these tasks, see the procedures in this section.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="73c7a-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="73c7a-112">In this section</span></span>

- [<span data-ttu-id="73c7a-113">Criar ou modificar uma política de voz e configurar registros de uso de PSTN no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73c7a-113">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)
    
- [<span data-ttu-id="73c7a-114">Configurar escape de caixa postal no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73c7a-114">Configure voice mail escape in Skype for Business</span></span>](configure-voice-mail-escape.md)
    
- [<span data-ttu-id="73c7a-115">Exibir registros de uso de PSTN no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73c7a-115">View PSTN usage records in Skype for Business</span></span>](view-pstn-usage-records.md)
    
- [<span data-ttu-id="73c7a-116">Criar ou modificar uma rota de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73c7a-116">Create or modify a voice route in Skype for Business</span></span>](create-or-modify-a-voice-route.md)
    
- [<span data-ttu-id="73c7a-117">Exportar ou importar um arquivo de configuração de rota de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73c7a-117">Export or import a voice route configuration file in Skype for Business</span></span>](voice-route-configuration-import-export.md)
    
- [<span data-ttu-id="73c7a-118">Publicar alterações pendentes na configuração de roteamento de voz no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="73c7a-118">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)
    

