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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com uma conectividade PSTN local. Antes de seguir as etapas neste tópico, leia o seguinte:.
ms.openlocfilehash: 7427bf33c275d55b99c240aaf192d180c2d63945
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30642200"
---
# <a name="enable-users-for-phone-system-in-office-365-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype para Business Server
 
Este tópico descreve como habilitar usuários para o sistema telefônico no Office 365 com uma conectividade PSTN local. Antes de seguir as etapas neste tópico, leia o seguinte:.
  
- Para saber como configurar a conectividade híbrida, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e a [conectividade de híbrido de Deploy entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
    
- Para saber mais sobre como planejar sua implantação, consulte [Planejar o sistema de telefone no Office 365 com conectividade PSTN local no Skype para Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para saber mais sobre o sistema telefônico no Office 365, incluindo o licenciamento e planos, consulte [PSTN chamar planos para Skype para negócios](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918).
    
## <a name="moving-users-to-phone-system-in-office-365-with-on-premises-pstn-connectivity"></a>Mover usuários para o sistema telefônico no Office 365 com conectividade PSTN de local

Antes de mover os usuários para Skype para Business Online, é recomendável que você habilite seus usuários no local no Skype para Business Server ou o Lync Server 2013 e depois movê-los online. Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) e a seção de considerações especiais de [habilitar os usuários para o Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md). 
  
Todos os usuários devem ser criados no Active Directory no local e sincronizados para o Office 365 usando a versão suportada do Windows Azure AD conector. Você não pode habilitar usuários para o sistema telefônico no Office 365, que foram criados diretamente no Azure AD. Se você deseja habilitar o sistema telefônico no Office 365 com conectividade PSTN de local para um usuário que foi criado no Azure AD, você precisará criar uma nova conta para o usuário no seu local AD, configurar a conta local e depois sincronizar a conta usando uma versão com suporte da ferramenta do conector do Windows Azure AD. 
  
Habilitando um usuário para o sistema telefônico no Office 365 com uma conectividade PSTN local e depois movê-los para Skype para Business Online requer as seguintes etapas:
  
- [Habilite os usuários para o Enterprise Voice no local](enable-the-users-for-enterprise-voice-on-premises.md) (executado enquanto os usuários estão hospedados no local).
    
- [Assign a Voice Routing Policy](assign-a-voice-routing-policy.md) (executado enquanto os usuários estão hospedados no local).
    
- [Sincronizar usuários para as nuvem e atribuir licenças](synchronize-users-to-the-cloud-and-assign-licenses.md) (executado usando o Office 365).
    
- [Mover usuários locais Skype para negócios Online](move-on-premises-users-to-skype-for-business-online.md) (executado usando o Windows PowerShell no local, mas usando suas credenciais de administrador do Office 365).
    
- [Habilitar usuários para Enterprise Voice online e o sistema telefônico no correio de voz do Office 365](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (executado usando o PowerShell remoto).
    

