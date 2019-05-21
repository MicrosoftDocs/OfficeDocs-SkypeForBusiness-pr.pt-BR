---
title: Habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local. Antes de seguir as etapas deste tópico, você deve ler o seguinte:.
ms.openlocfilehash: c8870cce90963e3a8d4e42de008df3eee779e52a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287458"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="80516-104">Habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="80516-104">Enable users for Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="80516-105">Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local.</span><span class="sxs-lookup"><span data-stu-id="80516-105">This topic describes how to enable users for Phone System in Office 365 with on-premises PSTN connectivity.</span></span> <span data-ttu-id="80516-106">Antes de seguir as etapas deste tópico, você deve ler o seguinte:.</span><span class="sxs-lookup"><span data-stu-id="80516-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="80516-107">Para saber como configurar a conectividade híbrida, consulte [planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="80516-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="80516-108">Para saber mais sobre como planejar a implantação, consulte [planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="80516-108">To learn about planning your deployment, see [Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="80516-109">Para saber mais sobre o sistema telefônico no Office 365, incluindo licenciamento e planos, consulte [planos de chamada PSTN para o Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span><span class="sxs-lookup"><span data-stu-id="80516-109">To learn more about Phone System in Office 365, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a><span data-ttu-id="80516-110">Mover usuários para o sistema telefônico no Office 365 com conectividade PSTN local</span><span class="sxs-lookup"><span data-stu-id="80516-110">Moving users to Phone System in Office 365 with on-premises PSTN connectivity</span></span>

<span data-ttu-id="80516-111">Antes de migrar os usuários para o Skype for Business Online, recomendamos que você habilite os usuários locais no Skype for Business Server ou no Lync Server 2013 e, em seguida, movê-los online.</span><span class="sxs-lookup"><span data-stu-id="80516-111">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="80516-112">Para obter mais informações, consulte [planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e a seção considerações especiais de [habilitar os usuários do Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários são hospedados no local).</span><span class="sxs-lookup"><span data-stu-id="80516-112">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="80516-113">Todos os usuários devem ser criados no Active Directory local e sincronizados com o Office 365 usando a versão com suporte do Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="80516-113">All users must be created in Active Directory on premises and synchronized to Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="80516-114">Você não pode habilitar usuários para o sistema telefônico no Office 365 que foram criados diretamente no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="80516-114">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="80516-115">Se você quiser habilitar o sistema telefônico no Office 365 com conectividade PSTN local para um usuário que foi criado no Azure AD, será necessário criar uma nova conta para esse usuário em seu anúncio local, configurar a conta no local e depois sincronizar a conta usando o uma versão com suporte da ferramenta Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="80516-115">If you want to enable Phone System in Office 365 with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="80516-116">Habilitar um usuário para o sistema telefônico no Office 365 com conectividade PSTN local e, em seguida, movê-los para o Skype for Business online requer as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="80516-116">Enabling a user for Phone System in Office 365 with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="80516-117">[Habilitar os usuários do Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários são hospedados no local).</span><span class="sxs-lookup"><span data-stu-id="80516-117">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="80516-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (executado enquanto os usuários estão hospedados no local).</span><span class="sxs-lookup"><span data-stu-id="80516-118">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="80516-119">[Sincronizar usuários com a nuvem e atribuir licenças](synchronize-users-to-the-cloud-and-assign-licenses.md) (executado usando o Office 365).</span><span class="sxs-lookup"><span data-stu-id="80516-119">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="80516-120">[Mover usuários locais para o Skype for Business online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (executado usando o Windows PowerShell local, mas usando suas credenciais de administrador do Office 365).</span><span class="sxs-lookup"><span data-stu-id="80516-120">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="80516-121">[Habilitar usuários para o Enterprise Voice online e o sistema telefônico no Office 365 correio de voz](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (executado usando o PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="80516-121">[Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

