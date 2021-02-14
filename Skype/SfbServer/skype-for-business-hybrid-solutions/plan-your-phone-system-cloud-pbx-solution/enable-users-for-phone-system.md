---
title: Habilitar usuários para o Sistema de Telefonia com conectividade PSTN local no Skype for Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'Este tópico descreve como habilitar usuários para o Sistema de Telefonia com conectividade PSTN local. Antes de seguir as etapas deste tópico, leia o seguinte: .'
ms.openlocfilehash: 7fb1ae9ee013dafbf0de91611bacb68f685daac8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359137"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="8b873-104">Habilitar usuários para o Sistema de Telefonia com conectividade PSTN local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8b873-104">Enable users for Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="8b873-105">Este tópico descreve como habilitar usuários para o Sistema de Telefonia com conectividade PSTN local.</span><span class="sxs-lookup"><span data-stu-id="8b873-105">This topic describes how to enable users for Phone System with on-premises PSTN connectivity.</span></span> <span data-ttu-id="8b873-106">Antes de seguir as etapas deste tópico, leia o seguinte: .</span><span class="sxs-lookup"><span data-stu-id="8b873-106">Before following the steps in this topic, you should read the following: .</span></span>
  
- <span data-ttu-id="8b873-107">Para saber como configurar a conectividade híbrida, consulte Planejar a conectividade híbrida entre o Skype for Business Server e o [Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business [Online.](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="8b873-107">To learn how to set up hybrid connectivity, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="8b873-108">Para saber mais sobre como planejar sua implantação, consulte [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="8b873-108">To learn about planning your deployment, see [Plan Phone System with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="8b873-109">Para saber mais sobre o Sistema de Telefonia, incluindo licenciamento e planos, consulte Planos de Chamada [PSTN para o Skype for Business.](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)</span><span class="sxs-lookup"><span data-stu-id="8b873-109">To learn more about Phone System, including licensing and plans, see [PSTN Calling plans for Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).</span></span>
    
> [!Important]
> <span data-ttu-id="8b873-110">O Skype for Business Online será retirado em 31 de julho de 2021, após o qual o serviço não estará mais acessível.</span><span class="sxs-lookup"><span data-stu-id="8b873-110">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="8b873-111">Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá mais suporte.</span><span class="sxs-lookup"><span data-stu-id="8b873-111">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="8b873-112">Saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="8b873-112">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a><span data-ttu-id="8b873-113">Mover usuários para o Sistema de Telefonia com conectividade PSTN local</span><span class="sxs-lookup"><span data-stu-id="8b873-113">Moving users to Phone System with on-premises PSTN connectivity</span></span>

<span data-ttu-id="8b873-114">Antes de mover seus usuários para o Skype for Business Online, é recomendável que você habilita seus usuários no local no Skype for Business Server ou no Lync Server 2013 e, em seguida, movê-los online.</span><span class="sxs-lookup"><span data-stu-id="8b873-114">Before moving your users to Skype for Business Online, it is recommended that you enable your users on premises in Skype for Business Server or Lync Server 2013, and then move them online.</span></span> <span data-ttu-id="8b873-115">Para obter mais informações, consulte Planejar a conectividade híbrida entre o [Skype for Business Server](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e o Skype for Business Online e a seção de considerações especiais de Habilitar os usuários para o Enterprise [Voice](enable-the-users-for-enterprise-voice-on-premises.md) local (executado enquanto os usuários estão no local).</span><span class="sxs-lookup"><span data-stu-id="8b873-115">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and the special considerations section of [Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span> 
  
<span data-ttu-id="8b873-116">Todos os usuários devem ser criados no Active Directory local e sincronizados com o Microsoft 365 ou o Office 365 usando a versão compatível do Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="8b873-116">All users must be created in Active Directory on premises and synchronized to Microsoft 365 or Office 365 using the supported version of Azure AD Connector.</span></span> <span data-ttu-id="8b873-117">Você não pode habilitar usuários para o Sistema de Telefonia no Office 365 que foram criados diretamente no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8b873-117">You cannot enable users for Phone System in Office 365 who were created directly in Azure AD.</span></span> <span data-ttu-id="8b873-118">Se você quiser habilitar o Sistema de Telefonia com conectividade PSTN local para um usuário que foi criado no Azure AD, será necessário criar uma nova conta para esse usuário no AD local, configurar a conta local e sincronizar a conta usando uma versão compatível da ferramenta Azure AD Connector.</span><span class="sxs-lookup"><span data-stu-id="8b873-118">If you want to enable Phone System with on-premises PSTN connectivity for a user who was created in Azure AD, you'll need to create a new account for that user in your on-premises AD, configure the account on-premises, and then synchronize the account using a supported version of the Azure AD Connector tool.</span></span> 
  
<span data-ttu-id="8b873-119">A habilitação de um usuário para o Sistema de Telefonia com conectividade PSTN local e, em seguida, a mudança para o Skype for Business Online requer as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8b873-119">Enabling a user for Phone System with on-premises PSTN connectivity and then moving them to Skype for Business Online requires the following steps:</span></span>
  
- <span data-ttu-id="8b873-120">[Habilitar os usuários para o Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários estão no local).</span><span class="sxs-lookup"><span data-stu-id="8b873-120">[Enable the users for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8b873-121">[Atribuir uma Política de Roteamento](assign-a-voice-routing-policy.md) de Voz (executada enquanto os usuários estão no local).</span><span class="sxs-lookup"><span data-stu-id="8b873-121">[Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (performed while the users are homed on-premises).</span></span>
    
- <span data-ttu-id="8b873-122">[Sincronizar usuários com a nuvem e atribuir licenças (executadas](synchronize-users-to-the-cloud-and-assign-licenses.md) usando o Office 365).</span><span class="sxs-lookup"><span data-stu-id="8b873-122">[Synchronize users to the cloud and assign licenses](synchronize-users-to-the-cloud-and-assign-licenses.md) (performed using Office 365).</span></span>
    
- <span data-ttu-id="8b873-123">[Mova os usuários](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) locais para o Skype for Business Online (realizado usando o Windows PowerShell local, mas usando suas credenciais de administrador do Office 365).</span><span class="sxs-lookup"><span data-stu-id="8b873-123">[Move on-premises users to Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (performed using Windows PowerShell on-premises, but using your Office 365 administrator credentials).</span></span>
    
- <span data-ttu-id="8b873-124">[Habilitar usuários para o Enterprise Voice Online e a Caixa Postal do Sistema de Telefonia](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (realizado usando o PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="8b873-124">[Enable users for Enterprise Voice online and Phone System Voicemail](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (performed using Remote PowerShell.</span></span>
    

