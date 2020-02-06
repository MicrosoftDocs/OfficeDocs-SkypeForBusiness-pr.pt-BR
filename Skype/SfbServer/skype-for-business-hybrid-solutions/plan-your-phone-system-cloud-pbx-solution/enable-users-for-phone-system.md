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
description: Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local. Antes de seguir as etapas deste tópico, você deve ler o seguinte:.
ms.openlocfilehash: c0c9f840c15e40aa3a78b69a5cbbf2f721251bbb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802181"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server
 
Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local. Antes de seguir as etapas deste tópico, você deve ler o seguinte:.
  
- Para saber como configurar a conectividade híbrida, consulte [planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e [implantar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para saber mais sobre como planejar a implantação, consulte [planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para saber mais sobre o sistema telefônico no Office 365, incluindo licenciamento e planos, consulte [planos de chamada PSTN para o Skype for Business](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Mover usuários para o sistema telefônico no Office 365 com conectividade PSTN local

Antes de migrar os usuários para o Skype for Business Online, recomendamos que você habilite os usuários locais no Skype for Business Server ou no Lync Server 2013 e, em seguida, movê-los online. Para obter mais informações, consulte [planejar a conectividade híbrida entre o Skype for Business Server e o Skype for Business online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e a seção considerações especiais de [habilitar os usuários do Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários são hospedados no local). 
  
Todos os usuários devem ser criados no Active Directory local e sincronizados com o Office 365 usando a versão com suporte do Azure AD Connector. Você não pode habilitar usuários para o sistema telefônico no Office 365 que foram criados diretamente no Azure AD. Se você quiser habilitar o sistema telefônico no Office 365 com conectividade PSTN local para um usuário que foi criado no Azure AD, será necessário criar uma nova conta para esse usuário em seu anúncio local, configurar a conta no local e depois sincronizar a conta usando o uma versão com suporte da ferramenta Azure AD Connector. 
  
Habilitar um usuário para o sistema telefônico no Office 365 com conectividade PSTN local e, em seguida, movê-los para o Skype for Business online requer as seguintes etapas:
  
- [Habilite os usuários para Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários estiverem hospedados no local).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (executado enquanto os usuários estão hospedados no local).
    
- [Sincronizar os usuários com a nuvem e atribuir licenças](synchronize-users-to-the-cloud-and-assign-licenses.md) (executadas usando o Office 365).
    
- [Mover usuários locais para o Skype for Business online](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/move-users-from-on-premises-to-skype-for-business-online) (executado usando o Windows PowerShell local, mas usando suas credenciais de administrador do Office 365).
    
- [Habilite os usuários para o Enterprise Voice online e o sistema telefônico no correio de voz do Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (executado usando o PowerShell remoto.
    

