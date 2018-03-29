---
title: Habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com uma conectividade PSTN local. Antes de seguir as etapas neste tópico, leia o seguinte:.
ms.openlocfilehash: e4b76074f26cbfafc248bfe9787f5886f4a70063
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="47a87-104">Habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="47a87-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="47a87-105">Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com uma conectividade PSTN local.</span><span class="sxs-lookup"><span data-stu-id="47a87-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="47a87-106">Antes de seguir as etapas neste tópico, leia o seguinte:.</span><span class="sxs-lookup"><span data-stu-id="47a87-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="47a87-107">Para saber como configurar a conectividade híbrida, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e a [conectividade de híbrido de Deploy entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="47a87-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="47a87-108">Para saber mais sobre como planejar sua implantação, consulte [Planejar o sistema de telefone no Office 365 com conectividade PSTN local no Skype para Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="47a87-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="47a87-109">Para saber mais sobre o sistema telefônico no Office 365, incluindo o licenciamento e planos, consulte [PSTN chamar planos para Skype para negócios](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="47a87-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="47a87-110">Mover usuários para o sistema telefônico no Office 365 com conectividade PSTN de local</span><span class="sxs-lookup"><span data-stu-id="47a87-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="47a87-111">Antes de mover os usuários para Skype para Business Online, é recomendável que você habilite seus usuários no local no Skype para Business Server ou o Lync Server 2013 e depois movê-los online.</span><span class="sxs-lookup"><span data-stu-id="47a87-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="47a87-112">Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e a seção de considerações especiais de [habilitar os usuários para o Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="47a87-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md).</span></span> 
  
<span data-ttu-id="47a87-113">Todos os usuários devem ser criados no Active Directory no local e sincronizados para o Office 365 usando a versão suportada do Windows Azure AD conector.</span><span class="sxs-lookup"><span data-stu-id="47a87-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="47a87-114">Você não pode habilitar usuários para o sistema telefônico no Office 365, que foram criados diretamente no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="47a87-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="47a87-115">Se você deseja habilitar o sistema telefônico no Office 365 com conectividade PSTN de local para um usuário que foi criado no Azure AD, você precisará criar uma nova conta para o usuário no seu local AD, configurar a conta local e depois sincronizar a conta usando uma versão com suporte da ferramenta do conector do Windows Azure AD.</span><span class="sxs-lookup"><span data-stu-id="47a87-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="47a87-116">Habilitando um usuário para o sistema telefônico no Office 365 com uma conectividade PSTN local e depois movê-los para Skype para Business Online requer as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="47a87-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="47a87-117">[Habilite os usuários para o Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários estão hospedados no local).</span><span class="sxs-lookup"><span data-stu-id="47a87-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="47a87-118">[Atribuir uma política de roteamento de voz](assign-a-voice-routing-policy.md) (executado enquanto os usuários estão hospedados no local).</span><span class="sxs-lookup"><span data-stu-id="47a87-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="47a87-119">[Sincronizar usuários para as nuvem e atribuir licenças](synchronize-users-to-the-cloud-and-assign-licenses.md) (executado usando o Office 365).</span><span class="sxs-lookup"><span data-stu-id="47a87-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="47a87-120">[Mover usuários locais Skype para negócios Online](move-on-premises-users-to-skype-for-business-online.md) (executado usando o Windows PowerShell no local, mas usando suas credenciais de administrador do Office 365).</span><span class="sxs-lookup"><span data-stu-id="47a87-120">[Move on-premises users to Skype for Business Online](move-on-premises-users-to-skype-for-business-online.md) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="47a87-121">[Habilitar usuários para Enterprise Voice online e o sistema telefônico no correio de voz do Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (executado usando o PowerShell remoto).</span><span class="sxs-lookup"><span data-stu-id="47a87-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell).</span></span>
    

