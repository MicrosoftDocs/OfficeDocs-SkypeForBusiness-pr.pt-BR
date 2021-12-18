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
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 3cc3db88-0210-4804-b54e-ba4af1234884
description: 'Este tópico descreve como habilitar usuários para Sistema de Telefonia com conectividade PSTN local. Antes de seguir as etapas deste tópico, leia o seguinte: .'
ms.openlocfilehash: ffd7e9f02466dddeef31ba7ffd3a194a04b9b2ff
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563658"
---
# <a name="enable-users-for-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>Habilitar usuários para o Sistema de Telefonia com conectividade PSTN local no Skype for Business Server

Este tópico descreve como habilitar usuários para Sistema de Telefonia com conectividade PSTN local. Antes de seguir as etapas deste tópico, leia o seguinte: .
  
- Para saber como configurar a conectividade híbrida, consulte [Plan hybrid connectivity between Skype for Business Server](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and Skype for Business Online and Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
    
- Para saber mais sobre como planejar sua implantação, consulte [Plan Sistema de Telefonia with on-premises PSTN connectivity in Skype for Business Server](plan-phone-system-with-on-premises-pstn-connectivity.md).
    
- Para saber mais sobre Sistema de Telefonia, incluindo licenciamento e planos, consulte Planos de Chamada [PSTN para](https://support.office.com/article/PSTN-Calling-plans-for-Skype-for-Business-f47c6a97-bc8b-42e6-b5d4-ce6b41ed1918)Skype for Business .
    
> [!Important]
> O Skype for Business Online foi retirado em 31 de julho de 2021 e a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não tem mais suporte. Saiba como conectar sua rede de telefonia local a Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

## <a name="moving-users-to-phone-system-with-on-premises-pstn-connectivity"></a>Mover usuários para Sistema de Telefonia com conectividade PSTN local

Antes de mover seus usuários para o Skype for Business Online, é recomendável que você habilita seus usuários no local no Skype for Business Server ou no Lync Server 2013 e, em seguida, movê-los online. Para obter mais informações, consulte Plan [hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) between Skype for Business Server and Skype for Business Online and the special considerations section of Enable the users [for Enterprise Voice on premises](enable-the-users-for-enterprise-voice-on-premises.md) (performed while the users are homed on-premises). 
  
Todos os usuários devem ser criados no Active Directory local e sincronizados com Microsoft 365 ou Office 365 usando a versão suportada do Conector do Azure AD. Você não pode habilitar usuários para Sistema de Telefonia em Office 365 que foram criados diretamente no Azure AD. Se você quiser habilitar o Sistema de Telefonia com conectividade PSTN local para um usuário que foi criado no Azure AD, será necessário criar uma nova conta para esse usuário no AD local, configurar a conta local e sincronizar a conta usando uma versão suportada da ferramenta conector do Azure AD Connector. 
  
Habilenciar um usuário para Sistema de Telefonia com conectividade PSTN local e, em seguida, habilita-lo para o Skype for Business Online exige as seguintes etapas:
  
- [Habilitar os usuários para Enterprise Voice local (executados](enable-the-users-for-enterprise-voice-on-premises.md) enquanto os usuários estão em casa no local).
    
- [Atribua uma Política de Roteamento](assign-a-voice-routing-policy.md) de Voz (executada enquanto os usuários estão no local).
    
- [Sincronizar usuários com a nuvem e atribuir licenças (executadas](../../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) usando Office 365).
    
- [Mova os usuários locais para](../../../SfbHybrid/hybrid/move-users-from-on-premises-to-skype-for-business-online.md) o Skype for Business Online (executado usando o Windows PowerShell local, mas usando suas credenciais de Office 365 administrador).
    
- [Habilitar usuários para Enterprise Voice online e Sistema de Telefonia Caixa Postal](enable-users-for-enterprise-voice-online-and-phone-system-voicemail.md) (executadas usando o PowerShell Remoto.
